# INFO4-PS

[Jonatha Anselmi](mailto:jonatha.anselmi@inria.fr) is in charge of the
lectures while [Arnaud Legrand](mailto:arnaud.legrand@imag.fr) is in
charge of practical sessions.

The pad is [here](http://pads.univ-grenoble-alpes.fr/p/INFO4_PS_20)
and the official schedule with room information is
[here](http://redirect.univ-grenoble-alpes.fr/ADE_ETUDIANTS_POLYTECH).

In this lecture, we will follow and cover most of the material
presented in [Probabilités et statistique pour
l’ingénieur](https://cermics.enpc.fr/~jourdain/probastat/poly.pdf), by
Benjamin Jourdain.

- Some additional references for the interested student (deeper and longer explanations on most topics):
   + [Cours de Jean Bérard](http://math.univ-lyon1.fr/~jberard/cours-www.pdf)
   + Méthodes de simulation de variables continues: [Non-uniform
     Random Variate Generation](http://www.eirene.de/Devroye.pdf) by
     Luc Devroye
   + [Initiation aux
     probabilités](https://books.google.fr/books?id=6TjJW8tpQLwC&redir_esc=y&hl=fr)
     by Sheldon M. Ross.
   + Initiation aux Probabilités, by P. Brémaud (un ouvrage de référence, très très complet)
   + [Theoretical Computer Science Cheat Sheet](https://www.tug.org/texshowcase/cheat.pdf) :)
   

| Semaine    | Cours (Jeudi, 10h00-11h30)                      | TD (Vendredi, 9h45-13h00)                                                 |
|:-----------|:------------------------------------------------|:--------------------------------------------------------------------------|
| 7-11 sep.  | 14h00-15h00 [Introduction au cours](#10-09-2020-lecture-1) | (-> Lundi 14) [Introduction à Rstudio et Rmarkdown](#14-09-2020-practical-session-1) |
| 14-18 sep. | [Probability basics](#17-09-2020-lecture-2)                |                                                                           |
| 21-25 sep. | [Chapter 2](#24-09-2020-lecture-3)                               |                                                                           |
| 28-02 sep. | [Chapter 2](#01-10-2020-lecture-4)                               |                                                                           |
| 05-09 oct. | [Chapter 3](#08-10-2020-lecture-5)                               | [Modeling and simulating simple conditional situations](#09-10-2020-practical-session-2)                                               |
| 12-16 oct. | [Random generation of discrete random variables](#15-10-2020-lecture-6)                               | [Generating randomness](#16-10-2020-practical-session-3)                                               |
| 19-23 oct. | [Random generation of continuous random variables](#22-10-2020-lecture-7)                               | [Generating uniformly over a finite set](#23-10-2020-practical-session-4)                                               |
| 26-3O oct. | Vacances                                        | Vacances                                                                  |
| 02-06 nov. | [Q/A - Recap - Exos](#05-11-2020-lecture-8)                               | [Generating discrete distributions](#06-11-2020-practical-session-5)                                               |
| 09-13 nov. | [Convergence of sequences of random variables](#12-11-2020-lecture-9)                               | [Discussion about the evolution the University](#13-11-2020-practical-session-6)                                               |
| 16-20 nov. | [Gaussian Random Vectors](#19-11-2020-lecture-10)                              | [Methods for generating continuous distributions](#20-11-2020-practical-session-7)                                               |
| 23-27 nov. | [TBA](#lecture-11)                              | [Normal Distribution](#27-11-2020-practical-session-8)                                               |
| 30-03 nov. | [TBA](#lecture-12)                              | [TBA](#practical-session-9)                                               |
| 07-11 dec. | [TBA](#lecture-13)                              | [TBA](#practical-session-10)                                              |
| 14-18 dec. |                                                 | [TBA](#practical-session-11)                                              |
| 21-25 dec. | Vacances                                        | Vacances                                                                  |
| 28-01 dec. | Vacances                                        | Vacances                                                                  |
| 04-09 jan. | Exam?                                           |                                                                           |


## [10-09-2020] Lecture 1
### Documents

Course content, objectives and organization.

- Started Chapter 1:
   + Definition of probability over a finite state space <img src="https://render.githubusercontent.com/render/math?math=\Omega">
   + Identification/Construction of <img src="https://render.githubusercontent.com/render/math?math=\Omega"> for some examples (eg, the [Birthday problem](https://en.wikipedia.org/wiki/Birthday_problem))


### Assignments
For the practical session of next Monday (14/09), you should

##### Answer our calculus survey
Take 10-20 minutes to answer this [Quick survey](pdf/Quick_0.pdf)
and send your answers (as an annotated pdf) to
`arnaud.legrand@imag.fr` with the following subject `[INFO4-PS] Quick
0 Nom, Prénom`. This should be done before Friday evening at 19h00 so
that we can analyze them before the next lecture. This survey will not
be graded. The main objective is (1) for us to identify those who need specific help in calculus and (2)
for you to know whether you need to catch up some basics or not.

##### Install R and Rstudio
If you're running a debian or an ubuntu,
simply follow the following steps (otherwise, e.g., MacOS X or
Windows, you may want to have a look at [these
guidelines](https://gitlab.inria.fr/learninglab/mooc-rr/mooc-rr-ressources/-/blob/master/module2/ressources/rstudio_fr.org)):

``` shell
sudo apt-get install r-base r-cran-knitr r-cran-tidyverse
```
	
Installing software through your OS package manager is generally
the preferred way to do, although packages can also be installed
from R itself. Make sure you have a recent (>= 3.2.0) version or R. For example,
here is what I have on my machine:
	
``` shell	
R --version
```

    R version 3.5.2 (2018-12-20) -- "Eggshell Igloo"
    Copyright (C) 2018 The R Foundation for Statistical Computing
    Platform: x86_64-pc-linux-gnu (64-bit)

    R is free software and comes with ABSOLUTELY NO WARRANTY.
    You are welcome to redistribute it under the terms of the
    GNU General Public License versions 2 or 3.
    For more information about these matters see
    http://www.gnu.org/licenses/.

If it's not the case, it may be because you're running an old debian
stable or an old LTD ubuntu. In such case, you may want to [include
testing
packages](http://serverfault.com/questions/22414/how-can-i-run-debian-stable-but-install-some-packages-from-testing)... Ask
your local linux guru or run a VM if you're affraid to break your
OS. For the braves, let's keep going!

Rstudio and knitr are unfortunately not packaged within debian so
the easiest is to download the corresponding debian package on the
[Rstudio webpage](http://www.rstudio.com/ide/download/desktop)
and then to install it manually (depending on when you do this,
you should obviously change the version number and you may have to
update the url so that it matches your OS).

``` shell
cd /tmp/
wget https://download1.rstudio.org/desktop/bionic/amd64/rstudio-1.3.1073-amd64.deb
sudo dpkg -i rstudio-1.3.1073-amd64.deb
sudo apt-get update ; sudo apt-get -f install # to fix possibly missing dependencies
```

You may have trouble when installing some R packages. If so, try to
install these ones:

``` shell
sudo apt-get install libcurl4-openssl-dev libssl-dev
```

Finally you should be able to open rstudio. Try then to open a new
RMarkdown document (in the menu File New File R Markdown. When
doing so and depending on what has been installed on your machine,
Rstudio may complain that it requires upgraded versions of knitr,
rmarkdown and tinytex... :( Just proceed and you'll be ready for the
practical session.

## [14-09-2020] Practical Session 1
### Documents
Today, we'll get familiar with R and Rstudio. I'll roughly cover this
[tutorial on
Rstudio](http://swcarpentry.github.io/r-novice-gapminder/01-rstudio-intro/index.html)
and this tutorial on [R
Markdown](https://swcarpentry.github.io/r-novice-gapminder/15-knitr-markdown/))
and show you how to use R to simulate and study simple stochastic
scenarios. I've tried to explain you some of the principles and a few
possble pitfals but as you may have understood R is a very particular
language so I encourage you to read this [newcomer’s (angry) guide to
R](http://arrgh.tim-smith.us) as it mentions several common pitfals.

Here are the Rmd files we wrote during this session:

- [Group 1](Rmd/TD1_G1.Rmd) (I took the time to comment a bit this one)
- [Group 2](Rmd/TD1_G2.Rmd)

### Assignments
- Model the second situation (when one of the son is named Omar) and
  compute the conditional probability assuming you have a probability
  $\epsilon$ to be named Omar if you are a boy. Check that this
  probability tends to $1/2$ when $\epsilon$ tends to 0. Check that
  the value you computed with your simulation corresponds to
  $\epsilon=0.2$.
  
- Learn the basics of data manipulation (vector and data frames) with
  R. A quite effective way is to use [SWIRL](http://swirlstats.com/),
  an interactive learning environment that will guide through
  self-paced lesson.
  ``` R
  install.packages("swirl")
  library(swirl)
  install_from_swirl("R Programming")
  swirl()
  ```
  You should look at lessons `4: Vectors`, `6: Subsetting Vectors`,
  `12: Looking at Data`, and `13: Simulation` since this is roughly
  what we covered today.

  Those of you that would prefer a textbook introducing R (not
  Rstudio) may want to read [R for
  Beginners](http://cran.r-project.org/doc/contrib/Paradis-rdebuts_en.pdf)
  or the following tutorials:
  1. http://uc-r.github.io/basics
  2. http://uc-r.github.io/r_markdown
  3. http://uc-r.github.io/vectors
  4. http://uc-r.github.io/dataframes

  But it will not provide you with as much practice as when using
  swirl. If you really hate typing commands as swirl is suggesting,
  you may find the scenarios in the github webpage (e.g.,
  https://github.com/swirldev/swirl_courses/blob/master/R_Programming/Simulation/lesson.yaml)


## [17-09-2020] Lecture 2

- Chapter 1 (almost finished):
   + Solution of the [Birthday problem](https://en.wikipedia.org/wiki/Birthday_problem) and of its variant "Same birthday as you"
   + Conditional probability and examples (e.g., Exercise 1.3.10)

## [24-09-2020] Lecture 3

- Chapter 2: Probability space, discrete random variables, independence, expected value, variance, Theorem 2.3.6 ("Théorème de transfert")  

## [01-10-2020] Lecture 4

- Chapter 2: A reasoned introduction to common probability law (Bernoulli, Binomial, Poisson and Geometric), exercices

## [08-10-2020] Lecture 5

- Chapter 2: Conditional expectation
   + We do not cover the part on generating functions (Section 2.4).

- Chapter 3: Continuous random variables, pdf, cdf, expected value, variance, conditional expectation

## [09-10-2020] Practical Session 2
### Documents
Implementing with R and playing around a few exercises from Chapter 1 of [Probabilités et statistique pour
l’ingénieur](https://cermics.enpc.fr/~jourdain/probastat/poly.pdf).
- [Group 1,2](Rmd/TD2_G2.Rmd)
### Assignments
Proceed similarly with other exercises from the same chapter. Then try
to compute the probabilities analytically and check that it is
coherent with your computer simulations.

## [15-10-2020] Lecture 6

- Chapter 3: Exercise 3.5.8 and 3.5.14 -- "Théorème de transfert" again! See Theorem 3.3.4, an extension of Theorem 2.3.6 for continuous random variables/vectors.
- Chapter 4: Random generation of discrete random variables

## [16-10-2020] Practical Session 3
### Documents
- Implementing with R Exercise 3.5.14 of [Probabilités et statistique pour
l’ingénieur](https://cermics.enpc.fr/~jourdain/probastat/poly.pdf).
- [Pseudo randomness generation](http://polaris.imag.fr/arnaud.legrand/teaching/2015/RICM4_PS_TD3.pdf)
   - [Group 1,2](Rmd/TD3_G1.Rmd) The R code we wrote during this session.
### Assignments
- Exercise 5 (*Comment faire une bonne pièce avec une fausse?*) of the [Pseudo randomness generation](http://polaris.imag.fr/arnaud.legrand/teaching/2015/RICM4_PS_TD3.pdf).


## [22-10-2020] Lecture 7

- Chapter 4: Random generation of continuous random variables
    + By inversion of the cumulative distribution function  
    + Polar method for generating normal random variables
    + Rejection sampling
    
For a reminder about the "change of variable" theorem, see Section 3.1.2 of the book (and in particular the solved exercise 3.1.5).
## [23-10-2020] Practical Session 4
### Documents
- Exercise 5 (*Comment faire une bonne pièce avec une fausse?*) of the [Pseudo randomness generation](http://polaris.imag.fr/arnaud.legrand/teaching/2015/RICM4_PS_TD3.pdf).
- [Uniform finite generation](http://polaris.imag.fr/arnaud.legrand/teaching/2016/RICM4_PS_TD3_uniform.pdf)
  We wrote almost no code because I foremost wanted to show how to
  think and writ proofs on this. Yet, writing a simple R code to
  simulate is the easiest way to get the answer to these exercises
  before engaging into the proof. Here is for example what I wrote for
  exercise 5:
  
  ``` R
  N = 100000; R = runif(N) ; Y=floor(R*6)+1 ; summary(as.factor(Y))/N
  ```
  
             1      2      3      4      5      6 
        .16496 .16752 .16701 .16769 .16578 .16704 

  ``` R
  N = 100000; R = runif(N) ; Y=round(R*5)+1 ; summary(as.factor(Y))/N ; hist(Y)
  ```
  
              1       2       3       4       5       6 
        0.10107 0.20009 0.19850 0.20088 0.20071 0.09875

- [Discrete
  generation](http://polaris.imag.fr/arnaud.legrand/teaching/2018/TD_PS_RICM4_discrete.pdf)
### Assignments
- Complete all exercises of the first sheet. You may start working on
  the second one on which we'll work next time.

## [05-11-2020] Lecture 8

### Q/A - Recap - Exos

- "Théorème de transfert" -- Theorem 2.3.6 (discrete case) and Theorem 3.3.4 (continuous case)
- Exercises 4.3.1 and 4.3.5

[Notes taken during the lecture](https://hackmd.io/LAXVN2wYSh2OiYtwwLa2tg)

## [06-11-2020] Practical Session 5
### Documents
- [Discrete
  generation](http://polaris.imag.fr/arnaud.legrand/teaching/2018/TD_PS_RICM4_discrete.pdf)
- [Some nice slides with nice drawings and explanations on the
  aliasing
  method](http://polaris.imag.fr/arnaud.legrand/teaching/2018/Cours_PS_RICM4_5.pdf)
- [A video recording of the sesssion](https://scalelite.univ-grenoble-alpes.fr/presentation/5547779c938b85752d344f40d03b39c5c9ed937c-1604651989772/video/webcams.webm)
### Assignments
- Make sure you understood everything we said about questions 1.1 and
  1.2. Do not hesitate to try to code them in R to make sure you
  understand how they work and the different trade-offs
- Prepare questions 1.3 and 1.4.
## [12-11-2020] Lecture 9

### Convergence of sequences of random variables (Chapter 5)

- Sequences of random variables: modes of convergence 
	+ almost sure, in probability, in L1, in L2 and in law
- Law of large numbers (strong and weak version)
- Central limit theorem
- Introduction to confidence intervals

## [13-11-2020] Practical Session 6
Black screen: no lecture. We talked about politics instead. Here some
resources to look at for next week.
### Resources
- [A video detailing how to solve the first question](https://youtu.be/sFur7wYql90)
- [Some R code for questions 1-4](Rmd/TD4-5_discrete.Rmd).

## [19-11-2020] Lecture 10

Exercise 5.5.4

### Gaussian random vectors (Chapter 6)
- Key points of the lecture: Definition, Stability, Exercise 6.3.2, Proposition 6.2.1, Corollary 6.2.4.


## [20-11-2020] Practical Session 7
- [Continuous generation](http://polaris.imag.fr/arnaud.legrand/teaching/2013/RICM4_TD5.pdf)

### Ressources
- [The notes I wrote on the board for group 1](pdf/PS7_G1.pdf)
- [The notes I wrote on the board for group 2](pdf/PS7_G2.pdf)
- Some dummy code snippets, just in case:
  ```{R}
  # Generating data following the triangular distribution
  hist(sqrt(runif(1000000)),breaks=100)
  plot(sqrt(runif(1000)))
  # Generating data following the exponential distribution
  lambda = 10
  hist(rexp(100000, rate = lambda))
  hist(-log(runif(10000))/lambda)
  ```
- [A few notes (, which I did not use yet) that detail the rejection algorithm ](http://polaris.imag.fr/arnaud.legrand/teaching/2018/TD_PS_RICM4_rejet.png)

### To do for the next time
- Make sure you have completed the exercise sheet on discrete law generation. The code is [here](Rmd/TD4-5_discrete.Rmd) so you can easily play with it to check whether you understood things right. Again, the code is useless if you do not understand the method.
- Prepare questions if needed and ask them on your discord server. If points are unclear and the questions are general enough, I'll try to prepare a video beforehand to save you some time and make sure you stay focus.
- Write the R code for the generation of laws of Q1.5(b) and (c) of [Continuous generation](http://polaris.imag.fr/arnaud.legrand/teaching/2013/RICM4_TD5.pdf) using both the inverse of the cdf method and the rejection method.

I'll take some time next time to answer questions you may still add and I'll move on the generation of a normal distribution. Prepare this by:
- Trying to generate normally distributed numbers using the rejection method when bounding with an exponential distribution (the very last part of Q3). 


## [27-11-2020] Practical Session 8
Today's topic was about the main properties of the Normal distribution
and how we could build on them to propose random generation
algorithms.

### Ressources
- [The notes I wrote on the board for group 1](pdf/PS8_G1.pdf) and [the
  R code](Rmd/TD8_G1.Rmd).
- [The notes I wrote on the board for group 2](pdf/PS8_G2.pdf) and [the
  R code](Rmd/TD8_G2.Rmd)
- [A few notes (, which I did not use yet) that detail the rejection algorithm ](http://polaris.imag.fr/arnaud.legrand/teaching/2018/TD_PS_RICM4_rejet.png)

### To do for the next time
- Implement in R the three methods we have detailed during the
  session (rejection when generating under the exponential
  distribution, sum of uniforms from the Central Limit Theorem, Box
  Müller thanks to the particular shape of the joint law).

## [04-12-2020] Practical Session 9
Today's topic was about computing confidence intervals with the Normal distribution.

### Ressources
- Here are the [Exercises](http://polaris.imag.fr/arnaud.legrand/teaching/2013/RICM4_TD6.pdf)
- Here are some [solutions in R](https://rpubs.com/alegrand/10993)
- [The notes I wrote on the board for group 1](pdf/PS9_G1.pdf) and [group 2](pdf/PS9_G2.pdf)
- [Video recording of the session](https://scalelite.univ-grenoble-alpes.fr/presentation/5547779c938b85752d344f40d03b39c5c9ed937c-1607077272917/video/webcams.webm)

