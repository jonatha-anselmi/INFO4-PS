# INFO4-PS: Probabilit&eacute; et Simulation

This is the website for the course "Probabilit&eacute; et Simulation" held at PolyTech INFO4, 2022-2023.

[Jonatha Anselmi](mailto:jonatha.anselmi@inria.fr) is in charge of the lectures and [Victor Boone](mailto:victor.boone@univ-grenoble-alpes.fr) will help with practical sessions (TD).

The official schedule with room information is
[here](https://ade-uga-ro-vs.grenet.fr/direct/index.jsp).

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
| 5-09 sep.  | [Introduction au cours](#08-09-2022-lecture-1)                            |  [Basic Exercises](#09-09-2022-practical-session-1) |
| 19-23 sep. | [Probability basics](#22-09-2022-lecture-2)                               |  [Basic Exercises](#22-09-2022-practical-session-2)     |
| 26-02 sep. | [Common discrete probability laws](#29-09-2022-lecture-3)                                        |                                                         |
| 03-07 oct. | ["Théorème de transfert"](#06-10-2022-lecture-4)                                        | |
| 10-14 oct. | [Continuous random variables and common pdfs](#13-10-2022-lecture-5)   |                                 |
| 17-21 oct. | [Théorème de transfert (continuous case)](#20-10-2022-lecture-6) |               |
| 24-28 oct. | [Random generation of continuous and discrete random variables](#27-10-2022-lecture-7) |               |
| 01-04 nov. | Vacances                                                                  | Vacances                 |
| 14-18 nov. | [Rejection Sampling](#17-11-2021-lecture-8)                               |  [Rejection Sampling in R](#17-11-2022-practical-session-8)     |
| 21-25 nov. | [Modes of convergence of sequences of random variables](#24-11-2021-lecture-9)                               |  [Discrete generation in R](#25-11-2021-practical-session-9)     |
| 28-02 nov. | [Law of Large Numbers / Central Limit Theorem](#01-12-2021-lecture-10)                               |  [LLN and CLT in R](#01-12-2022-practical-session-10)     |
| 05-09 dec. | [Confidence Intervals](#08-12-2022-lecture-11)                               |  [Exercises on CIs](#08-12-2022-practical-session-11)     |
| 12-16 dec. | Pas de cours                               |   [Correction of past exams](#15-12-2022-practical-session-12)     |
| 02-06 jan. | Pas de cours                               |   Q/A     |







## Install R and Rstudio

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

## Links to exercises done in class

[Mr. and Mrs. Smith, A winner among K](http://rpubs.com/janselmi/TD2)

[[Ex1](https://github.com/jonatha-anselmi/INFO4-PS/blob/master/pdf/TD_PS_RICM4_discrete.pdf)] 
[[Code](https://github.com/jonatha-anselmi/INFO4-PS/blob/master/Rmd/TD4-5_discrete.Rmd)]

Exam 2020-2021 : [[examen 04/01/2021](https://github.com/jonatha-anselmi/INFO4-PS/blob/master/pdf/PS-examen-21-01-05.pdf)]
Corrigé Exo 3 et commentaires exo 4 [Elements de correction Exam 2020-21.pdf](https://github.com/jonatha-anselmi/INFO4-PS/files/7774115/Elements.de.correction.Exam.2020-21.pdf)
