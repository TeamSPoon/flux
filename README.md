# FLUX

FLUX is a high-level programming system for cognitive agents of all
kinds, including autonomous robots. Cognitive agents control themselves
using an internal model of their environment. The FLUX kernel system
endows agents with the general cognitive ability to reason about their
actions and sensor data they acquire. FLUX agents are also able to plan
ahead their actions in order to achieve specific goals. FLUX allows to
implement complex strategies with concise and modular agent programs. An
efficient constraint logic program, the FLUX system scales up well to
domains which require large states and long action sequences.

FLUX is an implementation of the Fluent Calculus. A versatile action
representation formalism, this calculus provides a basic solution to
the classical frame problem using the concept of state update axioms.

The official FLUX project page is https://web.archive.org/web/20070302104140/http://www.fluxagent.org:80/
 See also [https://web.archive.org/web/*/http://www.fluxagent.org:80/*]

This library is free software according to the GNU Library General Public
License (GPL) 2. Please see the COPYING file for details.

# ALPprolog 

ALPprolog is a Prolog implementation of an action programming language.

With ALPprolog you can program strategies for autonomous agents in dynamic domains like e.g. the Wumpus world.Hook and/or override assert, retract, call, clause, erase, etc for specific predicates
It requires SWI-Prolog (available at http://www.swi-prolog.org) or ECLiPSe Prolog (available at http://www.eclipse-clp.org).

It implements a fragment of the theoretical framework of Action Logic Programs
as described in http://www.computational-logic.org/content/projects/wisslogpubs/DreSchiThi-FroCoS09.pdf

An ALPprolog program describes the strategy of an agent that executes the program
online. Hence only simple substitutions are used for evaluating queries like
e.g. ?- holds(safe(Cell)). In the offline setting reasoning by cases via
disjunctive substitutions ensures that the Action Logic Program framework
becomes logically complete.

# Installation

Using SWI-Prolog 7.1 or later:

```prolog

    ?- pack_install('https://github.com/TeamSPoon/flux.git').

```

Source code available and pull requests accepted at


```prolog
?- ensure_loaded(library(flux)).
true.

?- ensure_loaded(library(alpprolog)).
true.

?- 

```


# Some TODOs

Document this pack!

Write tests

Untangle the 'pack' install deps 
(Moving predicates over here from logicmoo_base)


# Not _obligated_ to maintain a git fork just to contribute

Dislike having tons of forks that are several commits behind the main git repo?

Be old school - Please ask to be added to TeamSPoon and Contribute directly !

Still, we wont stop you from doing it the Fork+PullRequest method

# [BSD 2-Clause License](LICENSE.md)

Copyright (c) 2017, 
TeamSPoon and Douglas Miles <logicmoo@gmail.com> 
All rights reserved.

General Information
===================


Requirements
============

For running and using the FLUX files, ECLiPSe Prolog (ECLiPSe
Constraint Logic Programming System) is required, Copyright
Imperial College London and ICL. It can be obtained from IC-Parc at
http://www.icparc.ic.ac.uk/eclipse/
Versions 5.4 and 4.2.3 have been used successfully.


Installation
============

See the file 'INSTALL'


Usage
=====

Please consult the journal paper [1] for an introduction to the
Fluent Calculus and the FLUX programming method, which is available
at www.fluxagent.org -> Publications.  You may also find the examples
useful that are available at our website, too.

In the following, a run of the Wumpus World is shown.

$ eclipse
ECLiPSe Constraint Logic Programming System [kernel]
Copyright Imperial College London and ICL
Certain libraries copyright Parc Technologies Ltd
GMP library copyright Free Software Foundation
Version 5.4 #27, Wed May 15 00:13 2002
[eclipse 1]: [wumpus].
fd_domain.eco loaded traceable 0 bytes in 0.01 seconds
fd_arith.eco loaded traceable 0 bytes in 0.03 seconds
fd_util.eco loaded traceable 0 bytes in 0.00 seconds
fd_chip.eco loaded traceable 0 bytes in 0.01 seconds
fd_elipsys.eco loaded traceable 0 bytes in 0.01 seconds
fd.eco     loaded traceable 0 bytes in 0.06 seconds
strings.eco loaded traceable 0 bytes in 0.00 seconds
chr2pl.eco loaded traceable 0 bytes in 0.01 seconds
chr.eco    loaded traceable 0 bytes in 0.02 seconds
lists.eco  loaded traceable 0 bytes in 0.01 seconds
fluent.chr compiled traceable 25658 bytes in 0.03 seconds
fluent.pl  compiled traceable 45772 bytes in 0.00 seconds
flux.pl    compiled traceable 13120 bytes in 0.12 seconds
wumpus_simulator.pl compiled traceable 7764 bytes in 0.00 seconds
wumpus.pl  compiled traceable 21192 bytes in 0.13 seconds

Yes (0.13s cpu)
[eclipse 2]: main.
wumpus(1, 6)
gold(2, 6)
pit(3, 5)
pit(6, 10)
pit(6, 2)
pit(2, 3)
pit(8, 7)
pit(4, 1)
pit(9, 1)
pit(7, 5)
pit(5, 1)
pit(8, 10)
pit(3, 3)
pit(4, 10)
enter
go
go
turn
turn
go
turn
turn
turn
go
turn
go
turn
turn
turn
go
turn
turn
go
turn
go
turn
turn
turn
go
turn
turn
turn
go
exit

Constraints:
(4) not_holds_all(wumpus(_1774, _1788), Z_1612)
(5) not_holds(dead, Z_1612)
(6) not_holds(pit(1, 1), Z_1612)
(7) not_holds_all(pit(_2067, 0), Z_1612)
(8) not_holds_all(pit(_2222, 13), Z_1612)
(9) not_holds_all(pit(0, _2389), Z_1612)
(10) not_holds_all(pit(11, _2568), Z_1612)
(11) not_holds_all(at(_2759, _2773), Z_1612)
(12) not_holds_all(facing(_2975), Z_1612)
(15) not_holds(has(arrow), Z_1612)
(18) duplicate_free(Z_1612)
(38) not_holds(pit(2, 1), Z_1612)
(48) not_holds(pit(1, 2), Z_1612)
(78) not_holds(gold(1, 1), Z_1612)
(107) not_holds(pit(2, 2), Z_1612)
(117) not_holds(pit(1, 3), Z_1612)
(147) not_holds(gold(1, 2), Z_1612)
(211) or_holds([pit(2, 3), pit(1, 4)], Z_1612)
(236) not_holds(gold(1, 3), Z_1612)
(467) or_holds([pit(3, 2), pit(2, 3)], Z_1612)
(492) not_holds(gold(2, 2), Z_1612)
(593) not_holds(pit(3, 1), Z_1612)
(633) not_holds(gold(2, 1), Z_1612)
(752) or_holds([pit(4, 1), pit(3, 2)], Z_1612)
(777) not_holds(gold(3, 1), Z_1612)

There are 232 delayed goals. Do you want to see them? (y/n)
More (0.14s cpu) ?
[eclipse 3]:
bye


Contact
=======

You are welcome to send comments, suggestions and feedback to the
addresses given at our website www.fluxagent.org


Literature
==========

[1]  M. Thielscher.  FLUX: A Logic Programming Method for Reasoning
Agents.  Theory And Practice of Logic Programming.  2004.

