you definitely will eventually need calculus (truly, multivariable calculus) if you want to follow and derive much of ML

tel [2:24 PM]2:24
but its a bit less necessary than linalg since it tends to be a tool used instead of the very basis of language

tel [2:25 PM]
a crash course in the concepts is simple though!

tel [2:25 PM]
since you basically will use the same trick from calculus over and over

tel [2:25 PM]
essentially:

tel [2:26 PM]
we formalize an ML problem by looking at a space of possible solutions

tel [2:26 PM]
(sometimes called “models” but that word gets a lot of overloading)

tel [2:26 PM]
for each solution, `s`, we build a function

tel [2:26 PM]
```howBad :: Solution -> Double```

tel [2:27 PM]
from solutions to, say, positive reals

tel [2:27 PM]
and then we seek to find the least bad solution

tel [2:27 PM]
the `howBad` minimizer

levinotik [2:27 PM] 
solutions, like hypotheses?

tel [2:28 PM] 
yeah, that word gets used often, too

levinotik [2:28 PM] 
cool

tel [2:28 PM] 
the ML system looks a bit like `learn :: Data -> Model` (edited)

tel [2:28 PM]
errrr

tel [2:28 PM]
lemme fix that (fixed now) (edited)

tel [2:29 PM]
we use `Data` to construct our notion of `howBad`

tel [2:29 PM]
and then the output is the least bad model

tel [2:30 PM]
(from some space of “all possible models” which is defined in our choice of ML method)

tel [2:30 PM]
anyway, the goal is to somehow find that least bad thing

tel [2:30 PM]
we could just guess randomly over and over

tel [2:31 PM]
indeed some ML algorithms do exactly this

tel [2:31 PM]
guess 1000000 random choices and return the minimizer of that set

tel [2:32 PM]
but most efficient ML is based on somehow taking advantage of knowledge about the `howBad` function to get to the true minimizer faster

tel [2:32 PM]
calculus is a major tool here

tel [2:32 PM]
the idea is that the derivative of `howBad` can sometimes be computed

levinotik [2:33 PM] 
this is a great high-level view.

levinotik [2:33 PM]
thanks tel

tel [2:33 PM] 
if we have a derivative, we’ll call it `d :: Model -> Delta Model -> Delta Double` (edited)

tel [2:34 PM]
(np! :simple_smile: )

tel [2:34 PM]
there we go

tel [2:34 PM]
`Delta a` basically means “a small change in `a`"

tel [2:34 PM]
so we can do

tel [2:35 PM]
`applyDelta :: a -> Delta a -> a` to make a small step from one point `a` to another

tel [2:35 PM]
so here’s how we use calculus

tel [2:36 PM]
we start _somewhere_, _anywhere_ in model space: `initialModel :: Model`

tel [2:36 PM]
we apply the `howBad` derivative `d initialModel :: Delta Model -> Delta Double`

tel [2:37 PM]
and now we know for all small changes to our model how the output of `howBad` will change

tel [2:37 PM]
so we take a step in the direction which gives us the biggest gain!

tel [2:38 PM]
often times it is _very_ easy to find this “best, local direction of improvement”

tel [2:39 PM]
and then we assume that iterating that process will take us quickly to the best answer

tel [2:39 PM]
much more quickly than random guessing anyway

tel [2:39 PM]
and that’s the core of how ML uses calculus