# 						FLC Lab Cheatsheet

​									*albione, Mr. ghiellazzo*

## EXPRESSIONS

##### Operazioni tra espressioni

```c
t_axe_expression handle_bin_numeric_op (t_program_infos *program, 
										t_axe_expression exp1, 
										t_axe_expression exp2, 
										int binop)
										
binop: ADD, ANDB, ORB, SUB, SHL, SHR, MUL, DIV
```

Date due espressioni ed un tipo di operazione si occupa di allocare i registri, produrre l'operazione binaria a livello di assembly e restituisce una nuova espressione contenente il risultato dell'operazione.

*ESEMPIO : \$1 - 1*

```c
// Crea la costante 1 come expression
t_axe_expression one_const = create_expression(1, IMMEDIATE);
// Produce l'operazione $1 - 1
t_axe_expression sub_one = handle_bin_numeric_op(program, $1, one_const, SUB);
```

---

##### Comparare Espressioni

```C
t_axe_expression handle_binary_comparison (t_program_infos *program, 
                                           t_axe_expression exp1, 
                                           t_axe_expression exp2, 
                                           int condition)
    
condition: _LT_, _GT_, _EQ_, _NOTEQ_, _LTEQ_, _GTEQ_
```

Date due espressioni e una condizione da verificare, restituisce una nuova espressione con il risultato del confronto, 1 se vero, 0 altrimenti.

*ESEMPIO*: *\$1 == \$3?*

```
t_axe_expression gt = handle_binary_comparison(program, $1, $3, _GT_);
```
*ESEMPIO: expr == true?*

Genera le istruzioni per capire <u>a runtime</u> se un'expression è vera

```C
// Crea la costante 0 come expression
t_axe_expression zero_const = create_expression(0, IMMEDIATE);
// Genera l'istruzione che compara il risultato di $1 con 0
t_axe_expression is_exp_zero = handle_binary_comparison (program, $1, zero_const, _EQ_);
```

---

##### Valore di un'espressione

Prende il valore intero contenuto in un'espressione

```C
int val;
// Copiala dentro se è una costante
if($2.expression_type == IMMEDIATE){
    val = gen_load_immediate(program, $2.value);
}
// Altrimenti prendi il valore dell'espressione
else {
    val = $2.value;
}
```

---

## LABELS

##### Creare Label

```C
t_axe_label* newLabel(t_program_infos *program);
```


Crea una nuova etichetta, senza assegnarla, utilizzata per i forward jump (nel momento in cui genero l'istruzione di salto non ho ancora assegnato l'etichetta nel punto di arrivo)

*ESEMPIO*: `$1 = newLabel(program);`

--------------

##### Assegnare Label

```C
t_axe_label* assignLabel(t_program_infos *program, t_axe_label *label);
```

Assegna un'etichetta, creata precedentemente, alla **prossima istruzione**.

*ESEMPIO*:  `assignLabel(program, $1);`

------------

##### Creare e Assegnare (subito) Label

```C
t_axe_label* assignNewLabel(t_program_infos* program);
```

Crea e assegna una nuova etichetta alla prossima istruzione (usata nei backward jump).
*ESEMPIO*:  `condition_label = assignNewLabel(program);`

-----

## JUMPS

```C
t_axe_instruction gen_<JUMP>_instruction(t_program_infos* program,
										 t_axe_label* dest,
										 int addr);

<JUMP>: bt, bne, beq, bge, bgt, ble, blt
```

Se la condizione <JUMP> è verificata, salta alla label *dest* con offset *addr* (normalmente = 0).

La condizione <JUMP> si basa sul risultato dell'istruzione precedente:

| JUMP |         SIGNIFICATO          |
| :--: | :--------------------------: |
|  bt  | true (salto sempre eseguito) |
| bne  |             != 0             |
| beq  |             == 0             |
| bge  |             >= 0             |
| bgt  |             > 0              |
| ble  |             <= 0             |
| blt  |             < 0              |

*ESEMPIO*:  `gen_bt_instruction(program, start, 0);  // salta alla label "start"`

-----
## REGISTERS

##### Riservare un registro

```C
int getNewRegister(t_program_infos *program);
```

Restituisce un intero che identifica il registro libero che viene riservato.

----------------

##### Assegnare il valore di un registro

```C
int gen_load_immediate(t_program_infos *program, int immediate);
```

Carica una costante in un registro. Viene restituito l'identificativo del registro.

*ESEMPIO: settare $$ = 0*

```C
$$.value = gen_load_immediate(program, 0)    // inizializza $$ a 0
```

----------
##### Creare espressione da un registro

```C
t_axe_expression create_expression(int value, int type);
```

*type* può essere IMMEDIATE o REGISTER.
*value* è la costante (se IMMEDIATE) o la location del registro (se REGISTER).

*ESEMPIO* (Caricare un'espressione in un registro)

```C
int from_reg;
t_axe_expression from_expr, start;

// Se è una costante, copiala dentro
if(start.expression_type == IMMEDIATE) {
	from_reg = gen_load_immediate(program, start.value);
}
// Altrimenti salva il valore di start dentro a un nuovo reg
else {
	from_reg = getNewRegister(program);
	gen_andb_instruction(program, from_reg, start.value, start.value, CG_DIRECT_ALL);
}
// Crea l'espressione
from_expr = create_expression(from_reg, REGISTER);
```

---

## ARRAYS

#### Leggere da un array

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

#### Scrivere in un array

```C
void storeArrayElement (t_program_infos *program, 
                        char *ID, 
                        t_axe_expression index, 
                        t_axe_expression data);
```

Carica in posizion index l'espressione data.

*ESEMPIO*: `storeArrayElement(program, array->ID, to_expr, el1_expr);`

-----

#### Capire se una variabile è un array

```C
t_axe_variable* array = getVariable(program, $1);

if(!array->isArray){
    notifyError(AXE_INVALID_VARIABLE);
}
```

---

#### Capire se una variabile è uno scalare

```C
t_axe_variable* scalar = getVariable(program, $1);

if(scalar->isArray){
    notifyError(AXE_INVALID_VARIABLE);
}
```

----

#### Lunghezza di un Array

```C
t_axe_variable* array;
int len = array->arraySize;    // controllare prima che sia un array
```

---

## LOOPS

*ESEMPIO*

```C
t_axe_label* condition_label, end_label;
int index_reg; // TODO: inizializzare l'indice!

// creo e assegno la label di inizio ciclo
condition_label = assignNewLabel(program);
// decremento l'indice di 1
gen_subi_instruction(program, index_reg, index_reg, 1);
// creo la label di fine ciclo (senza assegnarla)
end_label = newLabel(program);
// genero il salto alla fine
gen_beq_instruction(program, end_label, 0);

/**** loop body    ****/

// alla fine di un'iterazione, torno alla label di inizio
gen_bt_instruction(program, condition_label, 0);

// Assegno la label finale -> dopo il ciclo salto qui!
assignLabel(program, end_label);
```

![](/home/elvis/Pictures/flc.png)

---

## VARIABILI

#### Trovare il registro associato a una variabile

Prende il registro contenente la variabile a partire dal suo nome (ovvero il suo ID)

```C
exp: IDENTIFIER {
    // prende il registro collegato alla variabile IDENTIFIER
	int location = get_symbol_location(program, $1, 0);
}
```



## TODO

- free
- quando usare variabili globali
- aggiungere nuovo type (se vuoi ritornare più cose al livello superiore)