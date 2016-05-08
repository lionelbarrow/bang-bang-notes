### What Developers and Economists Can Learn From Each Other

_Rob Jefferson_

Economists do a ton of programming. After being in both programming and economics, Rob things the two disciplines can learn a lot from each other.

Background: Rob went to CMU for 2 years for CS, dropped out and did stuff, came back and finished a degree in economics, then went to Northwestern to do an econ PhD but dropped out. Eventually wound up as a researcher turned software engineer. Now works for Comcast as a devops engineer.

Modern economics is programming!
* Statistical modeling is a primary task for empirical work
* Computational econ is increasingly popular, simulates things with AI
* Using GPUs for econ linear algebra is increasingly popular
* Algorithmic game theory is of considerable interest to both CS and econ. Applications in auctions, load balancing and routing.

Yet, coding gets short shrift. Very little econ students get formal training in programming.

There's some hope!
* There's now a quant-econ project: open source Python and Julia libraries with lots of tests.
* Some software carpentry
* FRED (Fed Reserve Economic Data) and Quandl open common data sets
* Open Knowledge Foundation

Some need to understand algorithms. Not at an expert level, but at least a basic understanding of asymptotic behavior. Need to understand that nesting more loops is not always the answer. Use memoization, dynamic programming, etc. Finally, need more testing.

How bad could it be? (aka disasters in econ research)
* Donohue and Levitt (2011), aka the "abortions and crime" paper largely due to bugs in the software modeling the effect
* Feldstein (1974), "Social security depresses savings"
* Reinhart and Rogoff (2010)

Economists should learn to write tests. Unit, integration and regression. They should use standard libraries. Use version control.

What programmers can learn from economists?
* Causation and modeling. In any sort of model, we have factors X and interested in their impact on Y. If X is correlated with Y, have an endogeneity bias, so need to replace X with Z, which is correlated with X but not Z.
* Unfortunately endogeneity bias is everywhere and very hard to avoid.
* Don't avoid institutional effects! Sometimes seemingly technical problems are actually policy related.
* Understand cultural and historical contexts -- classic example being "falsehoods programmers believe about names".
* Specialization and trade. Generalists are great but life is too short to do everything. Need specialists. But specialists are only useful when trade is involved.
* Comparative and absolute advantage. Comparative advantage demonstrates what's possible, not necessarily what's best.

What should both programmers and economists learn?
* Stop putting such a huge premium on the hardcore. In tech, OS hackers are hardcore and real, web devs are not. In econ, theorists are at the top.
* We're only as good as what we tolerate. Econ: privileging theory over empirical results. Tech: privileging tools over people.
* Minorities in both fields are highly under-represented.

What can we do?
* More inclusive events.
* Make it easier to get into technical and economic discourse.
* Be patient and listen. Don't impose problem with tools first -- wait and see.

Talk is dedicated to Tiago Pires, 1984-2016. 
