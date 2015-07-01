# Machine Learning

[Lecture 1](https://www.youtube.com/watch?v=VeKeFIepJBU)

example use case: predict how viewer will rate movie. Netflix paid out $1M prize for people who improved this prediction by 10%. 

Why is this an ML problem? 

Essence of ML works when:

+ Some pattern does exist, but..
+ It can't be pinned down mathematically
+ We actually have some data 


## Movie rating solution

Describe a viewer as a **vector of factors**, or a "profile"

[Is this the vector we're talking about?](https://www.khanacademy.org/math/linear-algebra/vectors_and_spaces/vectors/v/vector-introduction-linear-algebra)


so you have

```
viewer - likes comedy * likes action ...

movie  - has comedy   * has action
```

you match the movie and viewer factors, add the contributions of each factor and get the predicted rating.

But that's **not** machine learning. To do this, you'd have to watch the movie and analyze it and also interview the viewer  :(

ML is about not doing this and instead letting the machine come up with this on its own :)

Ml reverses the process described above. It **starts with the rating** and tries to find out which factors would be consistent with that rating. 

We take random factors from viewer and movie. For every user and every movie. There's no chance that the inner product between these random factors that you'd arrive at a an actual rating. Instead, you take a **real, actual** rating and start nudging the factors every so slightly towards the actual rating. Make the direction of the inner product and get closer to the rating. [inner product or dot product](https://www.khanacademy.org/math/linear-algebra/vectors_and_spaces/dot_cross_products/v/vector-dot-product-and-vector-length)


