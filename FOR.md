# Modeling an optimization problem
* Decisions -> *Variables*
* Rules -> *Mathematical constraints* ($\le, \ge, \ne$)
* Objective -> *Function* (to maximize)

## Variables

* *Non Negative Absolute* quantities (e.g.  $x_p \ge 0$ = how many phones to be producted)
* *Unrestricted Absolute* quantities (e.g. temperatures)
* *Unrestricted variables* (can be negative, e.g. perturbation) 
  * Passare da non negativi a negativi: $\pi_{ts} = \pi_{ts+} - \pi_{ts-} $
* *Logical Variables (0-1)* -> Relative value that can be 0 or 1 ($x_1 \in {0,1})$
  * Complement $x' = 1 - x$
* *Integer Variables* (Discrete value variables)

## Constraints

* Requirement constraints (e.g. minimum required calories, maximum budget)
  * Transformations = ??
* Blending constraints (e.g. at least 30% vegetables in diet)
* Logical constraints
  * binary variables = logical variables
  * $\or = +$, $\and = *$
  * SAT-> (conjunctive normal form) $P = x, non P = 1-x$, clause = inequality
* Flow constraints

## Objective function





