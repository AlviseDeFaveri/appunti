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

#### Learning Machines

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


# Searle, *Minds, Brains and Programs*, 1980
---------------------------------------------------------------------------


# Brooks, *CS as Toolsmith*, 1994
---------------------------------------------------------------------------


# Scheultz, *Philosophical Issues about Computation*, 2000
---------------------------------------------------------------------------


# Denning & Rosenbloom, *Fourth domain of Science*, 2009
---------------------------------------------------------------------------




