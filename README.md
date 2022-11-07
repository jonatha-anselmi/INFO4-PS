# INFO4-PS: Probabilit&eacute; et Simulation

This is the website for the course "Probabilit&eacute;s et simulation" held at PolyTech INFO4, 2022-2023.

[Jonatha Anselmi](mailto:jonatha.anselmi@inria.fr) is in charge of the lectures and [Victor Boone](mailto:victor.boone@univ-grenoble-alpes.fr) will help with practical sessions (TD).

The official schedule with room information is
[here](https://ade-uga-ro-vs.grenet.fr/direct/index.jsp).

**We will follow and cover most of the material
presented in [Probabilités et statistique pour
l’ingénieur](https://cermics.enpc.fr/~jourdain/probastat/poly.pdf), by
Benjamin Jourdain.**

- Some additional references for the interested student (deeper and longer explanations on most topics):
   + [Cours de Jean Bérard](http://math.univ-lyon1.fr/~jberard/cours-www.pdf)
   + Méthodes de simulation de variables continues: [Non-uniform Random Variate Generation](http://www.eirene.de/Devroye.pdf) by
     Luc Devroye
   + [Initiation aux probabilités](https://books.google.fr/books?id=6TjJW8tpQLwC&redir_esc=y&hl=fr)
     by Sheldon M. Ross.
   + Initiation aux Probabilités, by P. Brémaud (un ouvrage de référence, très très complet)
   + [Theoretical Computer Science Cheat Sheet](https://www.tug.org/texshowcase/cheat.pdf) :)


## Program

| Semaine    | Cours                                                | TD                                                                |
|:-----------|:--------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------|
| 5-09 sep.  | Introduction  (Ch.1)                          |   |
| 19-23 sep. | Probability basics  (Ch.1)                             |     |
| 26-02 sep. | Common discrete probability laws (Ch.2)                 |                      |
| 03-07 oct. | Expectation and "Théorème de transfert" (Ch.2)                                       | |
| 10-14 oct. | Continuous random variables and common pdfs I (Ch.3)  |                                 |
| 17-21 oct. | Continuous random variables and common pdfs II (Ch.3)|               |
| 24-28 oct. | Expectation and "Théorème de transfert" (continuous case) (Ch.3)|               |
| 01-04 nov. | Vacances                                                                  | Vacances                 |
| 14-18 nov. | Control continu                               |       |
| 21-25 nov. | Random generation of continuous and discrete random variables (Ch.4) |  Discrete generation in R     |
| 28-02 nov. | Rejection Sampling  (Ch.4)     |    Rejection Sampling in R   |
| 05-09 dec. | Modes of convergence of sequences of random variables  (Ch.5)                             |      |
| 12-16 dec. | Law of Large Numbers / Central Limit Theorem  (Ch.5)                               |  LLN and CLT in R      |
| 02-06 dec. | Pas de cours                               |   Correction of past exams     |




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
