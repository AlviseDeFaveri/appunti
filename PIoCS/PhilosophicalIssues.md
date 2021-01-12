# Turing, *Computing Machinery and Intelligence*, 1950

----

## 1. Imitation game

- **Can machines think?**  $\Rightarrow$ Define *machine* and *think* $\Rightarrow$ answer would depend on how these terms are commonly used $\Rightarrow$ statistical approach (absurd)
- **Imitation game**:
    - played by a man (A), a woman (B), the interrogator (C)
    - interrogator in a room apart
    - goal of *interrogator*: find who is the man and who the woman
    - goal of *A*: make the interrogator fail
    - goal of *B*: help the interrogator
- New form for the problem: **what happens when a machine takes the part of A** in the imitation game?
    - Will the interrogator decide wrongly as often as in the human-played version?

## 2. Critiques

- **Is this question worthy to investigate?**
    - advantage: no influence from the physical appearance
    - SHARP LINE between *physical* and *intellectual* capacities
    - We don't want to penalize the machine or the human
- **Odds weighted too heavily against the machine?**
    - A human couldn't simulate a machine
- May not machines *think* in a different from what a man does?
    - $\rightarrow$ *we don't need to worry if the machine succeeded*
- *Game theory* $\rightarrow$ **is there a better strategy for the machine** than imitating the human in this game?
  - not likely
  - not interested in this $\Rightarrow$ we assume that it's the best strategy

## 3. Machines concerned in the game

* **Definition of machine**
  * should include any kind of engineering techniques
  * might include also things that cannot be completely described by the authors
  * should not include men "born in the usual way"
    * not even e.g. "reconstructed" from some human cell with a biological technique
    * $\Rightarrow$ not *every* technique should be permitted
* The present interest on thinking machines has been aroused by a particular kind, **electronic computers**
  * $\Rightarrow$ permit only computers
    * Not too drastic
    * Will be unsatisfactory only if they can't play the imitation game [*Turing thinks they can*]
* **Why not try the experiment straight away?**
  * We are asking whether digital computers *could* play it, not if the can today

## 4. Digital Computers

* **1st definition** digital computer built to do everything a human computer can
  * Human computers: 
    * follow fixed rules, provided in a book
    * no authority to deviate
    * $\infty$ paper
  * **BUT** risk of circularity argument
* **2nd definition** give an outline of *how* the desired effect is achieved
  * *store* $\rightarrow$ like paper for calculations + "book of rules" (i.e. *table of instructions*) + human memory
  * *executive unit* $\rightarrow$ carries out operations
  *  *control* $\rightarrow$ make the rules of the book happen correctly and in the right order
  * information broken down in *packets*
  * *instructions*
    * operands and opcode in defined positions of a packet
    * add, jump, conditional jump ($\Rightarrow$ for loop)
  * *programming* $\rightarrow$ construct book of rules

**N.B.**: *digital computers having random elements are sometimes described to have free will (not Turing's position: randomness is not observable from outside)*.

**N.B.B.**: *no theoretical difficulty in imagining infinite storage*

* Idea of digital computer: **Babbage 1828-1839, Analytical Engine**
  * Was entirely mechanical $\Rightarrow$ the fact that the nervous system and digital computers is just a superficial similarity

## 5. Universality of Digital Computers

* **Discrete state-machines**
  * although the reality is continuous, their state can be represented as discrete, e.g. light switch
  * given initial state and inputs it is always possible to predict all future states
  * differently from continuous systems, where small difference can have large consequences, this doesn't occur in discrete states
  * number of possible states of digital computers are incredibly large
* **A digital computer can mimic the behavior of any state machine** $\Rightarrow$ the digital computer is a *Universal Machine*
  * $\Rightarrow$ all digital computers are in a sense equivalent
* New formulation: *can a discrete state machine play the imitation game?*
  * equivalent to *can a digital computer with enough storage and an appropriate program play the imitation game?*

## 6. Contrary Views

* Turing's position
  1. A machine of capacity 109 can play the imitation game with 70% precision after 5 minutes
  2. "Can machines think?" is a meaningless question
  3. The concept of *thinking* will change in the general opinion and people will talk about thinking machines
  4. Science does not proceed from facts to facts, it need conjectures

#### Theological

*God hasn't given thinking to anything other than immortal souls aka humans.*

* god has the freedom to confer souls to anything e.g. animals
* attempting to construct machines is not usurping God's creation power more than creating children

#### Heads in the Sand

*The consequences of machines thinking would be too dreadful. Let us hope and believe*
*that they cannot do so.*

* We believe that man is superior to the rest of the creation. It is best if we show he is necessarily superior.

#### Mathematical

Limitations of discrete-state machines (Godel 1931). In particular Turing 1937 demonstrates that there are some things that digital computers cannot do.

* If we imagine just question with yes and no as answers, machines fail at answering the question *given a certain machine xyz, will it always answer yes?*
* But also humans give wrong answers
* Moreover, we can triumph on one machine but this demonstrates that a human is better than all machines

#### Consciousness

*Machines cannot compose poems because of thoughts and emotions instead of symbols*.

* Solipsist view $\rightarrow$ the only way to be sure is to be the machine and feel if it feels
* There are ways to understand if someone has really understood something and is not only repeating is like a parrot.
* There are mysteries of consciousness but they don't need to be solved in order to build thinking machines. 

#### Disabilities

*I grant you that you cannot make a machine which does X (be kind, fall in love, do something really new)*

* Mostly scientific induction, no proof
* *machines can't make mistakes*
  * two kind of mistakes, *errors of functioning* (ignored in philosophical discussion) and *errors of conclusion* (arise when meaning is attached to the output, <u>e.g.</u> English or maths)
* *can't reason about themselves*
  * a program can be an input for another program or the program itself
* Most claims are disguised version of the consciousness argument

#### Lady Lovelace

*Machines can only do things that we know how to order them to*

* At the time of Lovelace it was like this, but this does not exclude the possibility to build machines that can think for themselves or learn
* *machines can never do nothing really new* , do humans always do new things, or are they *implanted* by their teachers?
* *machines never take us by surprise*, Turing is very surprised when he is debugging stuff
  * It's false that there is no virtue in working out consequences from a general principle to a specific conclusion. The conclusion can be surprising.

#### Continuity in the Nervous System

*The nervous system in continuous not discrete*

* the interrogator can't notice

#### Informality of Behavior

*It is not possible to synthesize human behavior as a set of fixed rules*

* There are certainly some rules, we can never say *we have seen everything and there are no rules*
  * We can't even be sure to find such rules if they existed
  * <u>e.g.</u> Manchester machine can also give unpredictable responses if you don't know the program

#### Extrasensory Perception

Isolate the interrogator from possible extrasensory premonitions/mind-reading

## 7. Learning Machines

- No good arguments until now, only critiques of counterarguments
- Can a machine be made to be supercritical (given an idea produces many consequent ideas and doesn't drop into quiescence)
- Mind is fully mechanic?
  - We can see the mind as a series of onion-like skins: the outer is the chemical functioning, but if we go deep enough and the last skin doesn't contain anything, we can say the whole onion is made by skin, so we could say that the mind is made only by mechanical functions
- **Why not produce a machine that simulates a *child's* mind and make it learn**?
  - selection by an experimenter is like a fast version of evolution
  - education must be done separately from human children
  - punishments and rewards can be done without the need of emotions
  - cannot just use punishments and rewards, you need also to have a way of communicating things in a symbolic way
    - if you ave to teach a machine to learn a poem by just rewards and punishments it would take too much
  - simple learning machine vs a complete system of logical inference "built in"
    - storage mainly occupied by well-established facts, conjectures and *imperatives*
    - and imperative should cause a correlated action if is built-in / provided by an authoritative source (e.g. the teacher)
    - order of the rules important
  - how can a fixed machine learn new things if the program is fixed?
    - learned stuff is more ephemeral than the program
  - random element needed in a learning machine
- We may hope that machines will eventually compete with men in all purely intellectual
  fields
  - where to start? Purely intellectual (chess) vs try to reproduce sensorially a human

# Newell & Simon, *CS as Empirical Inquiry: Symbols and Search*, 1975
----------------------------------------------------------------------------

Computer Science $\rightarrow$ *study of the phenomena surrounding computer*

* computer as the programmed, living machine
* **computer science is a empirical discipline**
  * *experimental science*, even if some of its forms of observation doesn't fit in traditional science
  * machines are experiments
  * constructing a machine poses a question to nature (*answer: analyze the machine in operation*)
  * we can relate structure to behavior and learn lessons with even 1 experiment
* **Reasons to build computers and programs**
  * serve society (serve economic tasks)
  * discover new phenomena (the phenomena around computers are deep and obscure)
    * learning more about these phenomena pays off in permanent acquisition of new techniques, that can create instruments to help society
* <u>purpose of the paper</u>: examine how cs *develops understanding by empirical inquiry*.
  1. Symbolic systems
  2. Heuristic search $\Rightarrow$ Both contribute to understanding how intelligence works

## Physical Symbols System

* Main contribution of CS $\rightarrow$ understand what symbols are (empirically)
  * AI makes us understand the system requirements for *intelligent action*, i.e. ability to achieve goals in unknown environment
  * There's no *intelligence principle* (something which is entirely responsible of intelligence)
  * A requirement for intelligence is that it must store and manipulate symbols
* Laws of **qualitative structure** are important in scientific discovery
  * **Cell doctrine** was developed before explicitly defining all things that compose a cell
  * **Plate Tectonics** the surface of the world is made by huge plates. Started as highly qualitative theory
  * **Germ Theory**  most disease are caused by transmitting single cell organisms that reproduce inside bodies $\rightarrow$ the law has many exceptions
  * **Atomism** things are made by small, uniform particles
* Definition of **Physical symbols systems**
  * *physical* $\rightarrow$ 1. obeys the laws of physics, 2. not restricted to humans
  * has a set of physical patterns called *symbols* that are grouped in *symbol structures* (expressions)
  * has a collection of *processes* that operate on these expressions to produce other expressions
    * *Designation* $\rightarrow$ A symbol designates an object if given the symbol, the system can modify or "read" the object (access to object via an expression)
    * *Interpretation* $\rightarrow$ A system can interpret an expression if it designates a process and the process is carried out by the system
  * no a-priori prescription of which symbols can designate which expressions
  * there is an expression that designates every possible process of the machine
  * there are processes for creating and modifying expressions
  * expressions don't change on their own
  * the number of expression is unbounded
* The **Physical Symbol System Hypothesis**: a physical symbol system has the necessary and sufficient means for general intelligent action (i.e. appropriate to the goal and adaptive w.r.t. the environment)
  * The physical symbol system is an instance of a universal machine

## Development of the Symbol System Hypothesis

* **Logic**: Frege and Russell put the notions of *proof* and *deduction* on a secure footing
  * culminated in mathematical logic
  * logic is played on purely syntactic rules (symbols have no meaning)
  * **formal symbol manipulation**
* **Turing machine** 
  * contains the notions both of **what cannot be computed** and of **universal machines**
  * Concurrently discovered by Emil Post and Alonzo Church : this convinces us that we have captured the essence of information processing
  * **automatic formal symbol manipulation** 
  * half of the *interpretation* (machines can run from a description)
* **Store Program** program is data
  * other half of the *interpretation*: the system's own data can be interpreted
* **List Processing**
  * pointers to other elements $\rightarrow$ Symbols that *designate*  other symbol structures
  * first time dynamic memory
  * showed that computers are data + operations on the data
* Things we have discovered about symbolic processing are caused by the evolution of computers

### Evidence

<u>Hypothesis</u>: *Physical symbol systems are capable of intelligent action, and intelligent action calls for a symbol system* (empirical generalization)

* Look at tasks that call for intelligence, then construct a program that can do it
  * like the germ hypothesis $\rightarrow$ find for a disease, look for a germ
  * many programs have been constructed that are steadily getting better
  * found some general things about intelligent programs
    * e.g. general problem solvers
* Human symbolic behavior (model human behavior with symbol systems)
  * Psychology observes human intelligent activity and try to model it with symbol systems
* Absence of competing hypothesis

$\implies$ Computer science develops scientific hypothesis (e.g. about intelligence) and tries to verify them by empirical inquiry.

## Heuristic Search

**Symbols systems solve problems using heuristic search **(not logically derived but empirically)

* Solutions are symbolic structures. Physical symbol system exercise intelligence by generating and progressively modifying symbols until they reach a solution structure
* **Problem solving** is a typical task for intelligent agents
  * how do you know what you are searching for? and how you know you found a solution?
    * you have a *generator* of symbol structures (potential solutions) 
      * requires a *solution space*
      * to display *intelligence* means exploring the solution space in a way in which more likely solutions are likely to appear before others
      * you have to *extract information* from the problem space
        * if solutions are distributed randomly you cannot have intelligence
        * there must be some pattern to recognize and the symbol system needs to be capable of extracting this information
    * and a *test* to verify correctness
      * it is not automatic to derive a solution from the test
  * e.g. tree exploration
    * in chess, choosing where to branch is more important that exploring deeply the tree
    * intelligence is not exploring a lot, but going directly to the objective in a space where you could potentially explore a lot if you are not intelligent
      * control exponential explosion
    * <u>basic question</u>: what shall be done next?

* **New directions**
  * Nonlocal use of info
  * Semantics (e.g. recognizing good positions in chess)
  * selecting appropriate representations



# Searle, *Minds, Brains and Programs*, 1980

---------------------------------------------------------------------------

## Abstract

Propositions:

1. Intentionality is a product of causal features of the brain (i.e. there is a causal relationship between mental processes and brains)
2. Instantiating a computer program is never a sufficient condition of intentionality (i.e. a human agent could instantiate the program without having intentionality)
3. $\Rightarrow$ The brain doesn't produce intentionality by instantiating a computer program
4. Any mechanism capable of producing intentionality must have at least the causal powers of th brain (consequence of 1)
5. Strong AI (i.e. intentionality created artificially) could not succeed just by designing programs

$\implies$ **No program by itself is sufficient for thinking**

## Strong vs Weak AI

* Weak AI: computer is a powerful tool to study mind and test hypothesis on them
* Strong AI: a computer with the right program is literally a mind, i.e. can literally understand
  * e.g. Schank program to understand stories, i.e. answer to questions that are not explicitly stated in the story
  * claims made by strong AI: Shank's machine is literally  thinking, and the machine porgram is the explanation of how humans understand stories

## Chinese Room Experiment

Setting: locked in a room, I don't know chinese

1. Start with a large batch of chinese writing (**script**)
2. Second batch + rules to correlate first batch $\rightarrow$ second batch (**story**)
   - Rule entirely about the formal symbols
3. Third batch (**questions**) + rules to correlate to the first two + rules to answer

Rule = the program

4. Script+ story + questions are also made in english

One could say I know both english and chinese (*false* $\implies$ I am just manipulation symbols).

## Consequences

1. I don't understand chinese $\implies$ Schank's machine doesn't understand stories
2. Is computation a necessary condition for understanding? I.e. when I read in english, am I doing just more of the same thing I am doing for chinese?
   - Might be the case but there is no evidence
   - E.g. in the chinese room I understand english but not chinese, yet for the chinese I was given a **program** (computational operations of purely formally specified elements) while for english I didn't
     - $\implies$ not only they are not sufficient, but they are not necessary and don't even seem to be relevant

$\implies$ Whatever purely formal principles you give a machine, they are not sufficient to understanding, since if they are given to a human that doesn't guarantee understanding.

## Understanding

**Critics**: there are different degrees of understanding $\rightarrow$ Whether x understands y is a matter of discussion not a fact

* not a problem in the chinese room: I literally understand english and don't understand chinese, we are at the two opposites

We attribute understanding to objects because our tools are extensions of our purposes.

Claim of Newell&Simon: the way machine understand is the way in which humans understand. Searle's claim: machine can't understand anything.

## Replies

### Systems reply

*The understanding is not ascribed to the single individual, but to the system individual + rules*

<u>Response</u>: what if the individual internalizes all the information, e.g. memorizes all the rules?

* The two "subsystems", individual + english and individual + chinese are not even remotely similar.
* Adequacy of the Turing test is under discussion: there are two systems that pass the turing test but of which only one of them understands
* Absurd consequence of the system view: my stomach should be conscious (has input and ouput)
  * AI must make a distinction between mental and non-mental, and it must be intrinsic to the mind and not just an opinion
  * We are asked to accept it as a discovery of AI that the hunk of metal on the wall has beliefs in the exact same sense we have

### Robot reply

*Adding sensors and actuators to be more similar to humans*

* This view concedes the fact that pure symbols manipulation is not enough

<u>Response</u>: even if symbols were given in other forms in the chinese room, e.g. television, it would still be just symbols manipulation, where symbols can be received from the perceptual apparatus

### Brain Simulator reply

*What if the program was to simulate exactly the neuron activity of a brain when talking chinese*

* This is not very in line with the strong AI idea, which should be that we don't know how the brain (hardware) works to know how the mind (software) works

<u>Response</u>: simulating the brain still doesn't mean that the simulator understands what's happening (e.g. if in the chinese room I have instructions on how to drive some water pipes that simulate neurons)

$\implies$ Formal properties are not sufficient for the causal properties

### Combination reply

*If we could build a robot whose behavior was indistinguishable over a large range from human behavior, we would attribute intentionality to it, pending some reason not to*

<u>Response</u>: true because we would ascribe it intentionality *only if we don't know that's not the case*. E.g. if we discover that there's a man inside manipulating symbols without understanding them we wouldn't ascribe it intentionality.

The reason we think that animals have intentions are :

1. we can't make sense of the animal's behavior
2. animals are made of a similar stuff as humans ($\Rightarrow$ same causal stuff underlying it)
   * As soon as we knew the behavior is a result of a formal program and that the causal properties of the physical substance don't matter, we don't ascribe intentionality

### Other Minds reply

*How do I ascribe intentionality to others? Only by behavior: if the machine passes the test is good*

<u>Response</u> we are analyzing whether computational processes alone can describe what I mean when I attribute cognitive state to something. They can't, because they exist without cognition.

### Many Mansions reply

*You are focusing only on analogue and digital computers*

<u>Response</u> The point is to contradict the claim that mental processes are just computational processes over formally defined elements.

## Can machines have intentions?

In principle why not, just not only in terms of computational processes over formally defined elements ($\implies$ not with computer programs).

No purely formal model will ever be sufficient for intentionality.

<u>Conclusion</u> machines can think, but it is not true that something can think only because it is a computer program

* syntax without semantics $\implies$no reasoning
* simulation is not duplication in the case of intentionality (i.e. can't really separate formal program from the realization)

## Why do people believe that computers can be conscious?

1. mistaking simulation with duplication
2. both minds and computers do information processing (but it's a different kind of processing, one is on symbols that have meaning the others don't)
3. behaviouristic and operationalistic view (if it does something similar to humans it has to be like humans)
4. dualistic view of the brain

# Brooks, *Computer Scientist as Toolsmith*, 1994

---------------------------------------------------------------------------

## Mistaken name

*Science is observation and classification of facts, especially with the establishment of quantitative general rules.*

**Science vs Engineering**

* Scientists build in order to study
* Engineers study in order to build

Computer Science is the engineering of making things which others use to satisfy human needs $\Rightarrow$ **Toolsmith**

**What is the problem of misnaming?**

1. trying to say science > engineering
2. we care on discovering *new* things, but they should be measured on how *useful* they are
3. we forget users
4. we are misdirecting labor for from concrete problem to abstract problems

*Computer* is right $\rightarrow$ these machine have enabled arbiratry complexity previously could not be handled

Important aspect of computer science: *subcreation* 

## Evolution of CS

AI goals are much more difficult than expected, and went into the wrong direction.

**IA** (intelligence amplifying) always > AI

Working on problems given by others can enrich computer science:

* real-scale problems
* honest success and failures
* can't abstract away only the mathematical part
* drive for new pieces of cs
* fun



# Scheutz, *Philosophical Issues about Computation*, 2000

---------------------------------------------------------------------------

## What is computation?

* execution of algorithms
  * What is an algorithm? $\rightarrow$ finite set of instructions that operate on *symbols* and that can be *implemented* by a mechanism
  * The mechanism performs a sequence of discrete atomic steps
* history
  * Leibniz: mechanical reasoner
  * Thinking involves *representations*
  * Computation $\rightarrow$ mechanically manipulate representations

# Moor, *What is Computer Ethics?*, 2006

----



# Denning & Rosenbloom, *Fourth domain of Science*, 2009

---------------------------------------------------------------------------



