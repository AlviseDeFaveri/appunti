# FLC Lab Cheatsheet

*albione, mr. ghiellazzo, brikkarè*

### EXPRESSIONS

```c
t_axe_expression handle_bin_numeric_op (t_program_infos *program, 
										t_axe_expression exp1, 
										t_axe_expression exp2, 
										int binop)
										
binop: ADD, ANDB, ORB, SUB, SHL, SHR, MUL, DIV
```

Date due espressioni ed un tipo di operazione si occupa di allocare i registri, produrre l'operazione binaria a livello di assembly e restituisce una nuova espressione contenente il risultato dell'operazione.

*ESEMPIO*: 

```c
t_axe_expression e_split = handle_bin_numeric_op(program, e_arraysize, $3, SUB);
```

----------

```C
t_axe_expression handle_binary_comparison (t_program_infos *program, 
                                           t_axe_expression exp1, 
                                           t_axe_expression exp2, 
                                           int condition)
    
condition: _LT_, _GT_, _EQ_, _NOTEQ_, _LTEQ_, _GTEQ_
```

Date due espressioni e una condizione da verificare, restituisce una nuova espressione con il risultato del confronto, 1 se vero, 0 altrimenti.

*ESEMPIO*: 

```
t_axe_expression gt = handle_binary_comparison(program, $1, $3, _GT_);
```
-----

Generare istruzioni per capire se un'expression è vera

```C
// crea la costante 0 come espression
t_axe_expression zero_const = create_expression(0, IMMEDIATE);

// genero l'istruzione che compara il risultato di $5 con 0
t_axe_expression is_exp_zero = handle_binary_comparison (program, $5, zero_const, _EQ_);
```

---

Prendere il valore intero di una espressione

```C
int val;
if($2.expression_type == IMMEDIATE){
    val = gen_load_immediate(program, $2.value);
}
else {
    val = $2.value;
}
```

---

### LABELS

```C
t_axe_label* newLabel(t_program_infos *program);
```


Crea una nuova etichetta, senza assegnarla, utilizzata per i forward jump (nel momento in cui genero l'istruzione di salto non ho ancora assegnato l'etichetta nel punto di arrivo)

*ESEMPIO*: `$1 = newLabel(program);`

--------------

```C
t_axe_label* assignLabel(t_program_infos *program, t_axe_label *label);
```

Assegna un'etichetta creata precedentemente.

*ESEMPIO*:  `assignLabel(program, $1);`

------------

```C
t_axe_label* assignNewLabel(t_program_infos* program);
```

Crea e assegna una nuova etichetta (usata nei backward jump).
*ESEMPIO*:  `condition_label = assignNewLabel(program);`

-----

### JUMPS

```C
t_axe_instruction gen_<JUMP>_instruction(t_program_infos *program, t_axe_label * dest, int addr);

<JUMP>: bt, bne, beq, bge, bgt, ble, blt
```


Genera un'istruzione di salto, la cui condizione è espressa da <JUMP> alla posizione indicata dalla label dest.

*ESEMPIO*:  `gen_bt_instruction(program, start, 0);`

-----

### REGISTERS

```C
int getNewRegister(t_program_infos *program);
```


Restituisce un intero che identifica il registro libero che viene riservato.

----------------

```C
int gen_load_immediate(t_program_infos *program, int immediate);
```

Carica una costante in un registro. Viene restituito l'identificativo del registro.

*ESEMPIO*

```C
$$.value = gen_load_immediate(program, 0)    // init $$ a 0
```

----------

```C
t_axe_expression create_expression(int value, int type);
```

Crea un'espressione da registro, può essere IMMEDIATE o REGISTER.

*ESEMPIO* (Caricare un'espressione in un registro)

```C
int from_reg;
t_axe_expression from_expr, start;

if(start.expression_type == IMMEDIATE) {
	from_reg = gen_load_immediate(program, start.value);
}
else {
	from_reg = getNewRegister(program);
	gen_andb_instruction(program, from_reg, start.value, start.value, CG_DIRECT_ALL);
}
from_expr = create_expression(from_reg, REGISTER);
```

---

### ARRAYS

```C
int loadArrayElement(t_program_infos *program, char *ID, t_axe_expression index);
```

Restituisce un riferimento al registro in cui è stato caricato l'elemento dell'array ID situato all'indice index.

*ESEMPIO*: 

```C
t_axe_variable* array;
int el1_reg = loadArrayElement(program, array->ID, from_expr);
```

-------------

```C
void storeArrayElement (t_program_infos *program, 
                        char *ID, 
                        t_axe_expression index, 
                        t_axe_expression data);
```

Carica in posizion index l'espressione data.

*ESEMPIO*: `storeArrayElement(program, array->ID, to_expr, el1_expr);`

-----

Capire se una var è array

```C
t_axe_variable* array = getVariable(program, $1);

if(!array->isArray){
    notifyError(AXE_INVALID_VARIABLE);
}
```

Capire se una var è scalare

```C
t_axe_variable* scalar = getVariable(program, $1);

if(scalar->isArray){
    notifyError(AXE_INVALID_VARIABLE);
}
```

Lunghezza array

```C
t_axe_variable* array;
int len = array->arraySize;    // controllare prima che sia un array
```

---

### LOOPS

*ESEMPIO*

```C
// init index

t_axe_label* condition_label, end_label;

condition_label = assignNewLabel(program);               // creo e assegno label
gen_subi_instruction(program, index_reg, index_reg, 1);  // i--

end_label = newLabel(program);               // creo label (senza assegnarla)
gen_beq_instruction(program, end_label, 0);  // salto alla label appena creata

// loop body

gen_bt_instruction(program, condition_label, 0);

/* Assegno la label finale */
assignLabel(program, end_label);    // assegno label finale
```

![](/home/elvis/Pictures/flc.png)

### VARIABILI

Prendere il registro contenente la variabile a partire dal suo nome (ovver il suo ID)

```C
/* get the location of the symbol with the given ID */
location = get_symbol_location(program, $1, 0);
```

