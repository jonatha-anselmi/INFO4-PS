# INFO4-PS: Probabilit&eacute; et Simulation

This is the website for the course "Probabilit&eacute; et Simulation" held at PolyTech INFO4, 2021-2022.

[Jonatha Anselmi](mailto:jonatha.anselmi@inria.fr) is in charge of the
lectures and [Louis-Sebastien Rebuffi](mailto:louis-sebastien.rebuffi@univ-grenoble-alpes.fr) will help with practical sessions.

The official schedule with room information is
[here](http://redirect.univ-grenoble-alpes.fr/ADE_ETUDIANTS_POLYTECH).

We will follow and cover most of the material
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
   


## Program

| Semaine    | Cours                                                | TD                                                                |
|:-----------|:--------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------|
| 6-10 sep.  | [Introduction au cours](#09-09-2021-lecture-1)                            |  [Basic Exercises and Rstudio](#10-09-2021-practical-session-1) |
| 20-24 sep. | [Probability basics](#23-09-2021-lecture-2)                               |  [Basic Exercises and Rstudio](#23-09-2021-practical-session-2)     |
| 27-01 sep. | [Common discrete probability laws](#30-09-2021-lecture-3)                                        |                                                         |
| 04-08 oct. | ["Théorème de transfert"](#07-10-2021-lecture-4)                                        | |
| 11-15 oct. | [Continuous random variables and common pdfs](#14-10-2021-lecture-5)   |                                 |
| 18-22 oct. | [Théorème de transfert (continuous case)](#21-10-2021-lecture-6) |               |
| 25-29 oct. | [Random generation of continuous and discrete random variables](#28-10-2021-lecture-7) |               |
| 01-05 nov. | Vacances                                                                  | Vacances                 |
| 15-19 nov. | [Rejection Sampling](#18-11-2021-lecture-8)                               |  [Rejection Sampling in R](#18-11-2021-practical-session-8)     |
| 22-26 nov. | [Modes of convergence of sequences of random variables](#25-11-2021-lecture-9)                               |  [Discrete generation in R](#25-11-2021-practical-session-9)     |
| 29-03 nov. | [Law of Large Numbers / Central Limit Theorem](#02-12-2021-lecture-10)                               |  [LLN and CLT in R](#02-12-2021-practical-session-10)     |
| 06-10 dec. | [Confidence Intervals](#09-12-2021-lecture-11)                               |  [Exercises on CIs](#09-12-2021-practical-session-11)     |
| 13-17 dec. | Pas de cours                               |   [Correction of past exams](#16-12-2021-practical-session-12)     |
| 03-07 jan. | Pas de cours                               |   Q/A     |






## [10-09-2021] Lecture 1
### Documents

Course content, objectives and organization.

- Started Chapter 1:
   + Definition of probability over a finite state space <img src="https://render.githubusercontent.com/render/math?math=\Omega">
   + Identification/Construction of <img src="https://render.githubusercontent.com/render/math?math=\Omega"> for some examples (eg, the [Birthday problem](https://en.wikipedia.org/wiki/Birthday_problem))


### Assignments: Install R and Rstudio

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

## [11-09-2021] Practical Session 1

[Mr. and Mrs. Smith, A winner among K](http://rpubs.com/janselmi/TD2)



## [23-09-2021] Lecture 2

- Chapter 1 (finite state space):
   + Solution of the [Birthday problem](https://en.wikipedia.org/wiki/Birthday_problem) and of its variant "Same birthday as you"
   + Conditional probability and examples (e.g., Exercise 1.3.10)
   + Independence

## [23-09-2021] Practical Session 2

Implementing with R and playing around a few exercises from Chapter 1 of [Probabilités et statistique pour
l’ingénieur](https://cermics.enpc.fr/~jourdain/probastat/poly.pdf).





## [30-09-2021] Lecture 3

- Chapter 2 (countable state space): Probability space, discrete random variables, independence, expected value


## [07-10-2021] Lecture 4

- Chapter 2:
   + A reasoned introduction to common probability law (Bernoulli, Binomial, Poisson and Geometric) with their properties and exercices
   + Variance, Theorem 2.3.6 ("Théorème de transfert")

## [14-10-2021] Lecture 5

- Chapter 3 (uncountable state space): Continuous random variables, pdf, cdf, common pdfs (uniform, exponential, gaussian)

## [21-10-2021] Lecture 6

- Chapter 3 (uncountable state space): Expected value and "Théorème de transfert" again! See Theorem 3.3.4

## [28-10-2021] Lecture 7

- Chapter 4: Random generation of continuous random variables
    + By inversion of the cumulative distribution function  
    + Polar method for generating normal random variables
    + Rejection sampling (intro)

## [18-11-2021] Lecture 8

- Chapter 4: More on the rejection sampling method (Section 4.2.4).


## [25-11-2021] Lecture 9

- Chapter 5: Modes of convergence of sequences of random variables. In particular:
	+ Definition 5.1.1 (almost sure convergence and convergence in Lp)
	+ Section 5.3.2 (Convergence in law) 

## [25-11-2021] Practical Session 9

Simulation of discrete random variables in R; 
[[Exercises](https://github.com/jonatha-anselmi/INFO4-PS/blob/master/pdf/TD_PS_RICM4_discrete.pdf)] 
[[Code written in class](https://github.com/jonatha-anselmi/INFO4-PS/blob/master/Rmd/TD4-5_discrete.Rmd)]


## [02-12-2021] Lecture 10

- Chapter 5:
	+ Strong and Weak Laws of Large Numbers
	+ Central Limit Theorem


## [09-12-2021] Lecture 11

- Chapter 5:
	+ Applications of the Strong Law of Large Numbers and of the Central Limit Theorem
	+ Confidence Intervals (Section 5.4.2)

## [09-12-2021] Practical Session 11

Exercises based on the Strong and Weak Laws of Large Numbers: Exercises 5.5.3 and 5.5.4


## [16-12-2021] Practical Session 12

Corrigé [[examen 04/01/2021](https://github.com/jonatha-anselmi/INFO4-PS/blob/master/pdf/PS-examen-21-01-05.pdf)]
