# Project Overview

This project aims to find a design for a 3-string instrument/arc in terms of the tensions (τ), lengths (l), mass densities (μ), and center of mass that produces a set of strictly odd "harmonics." <br>
The primary focus is on achieving the first 5 harmonics.

## design.py

`design.py` is a design class that provides you with the spectral equation of a design given a set of parameters<br>
It can find the roots, plot them, and return a percentage error to the expected harmonics ([1,3,5,7,9]). <br>
To run this file, you need a few Python libraries: matplotlib, pychebfun, and numpy. <br>
These can be installed with the following commands:

```sh
pip install matplotlib
pip install pychebfun
pip install numpy
```
To run this program, simply type:
```sh
python3 design.py
```
## SPSAtwo.py


`SPSAtwo.py` uses SPSA, a hill climbing algo to find the best design. <br>
It randomly generates a design to start with (you can provide one via file input as well by modifying the code and uncommenting/commenting out some lines), and then runs a normal SPSA! 
<br> This file requires `design.py` and all of its imports. 
<br>No additional imports are required. Running it is as simple as typing:
```sh
python3 SPSAtwo.py
```
<br> Once you run this program, you will get prompted for an input asking for the number of iterations you would like to run. Once it runs all of these iterations, it will then display a graph of the progress from design 1 -> final design. 

<br>Alternatively, you could run
```sh
python3 SPSAtwo.py 100
```
or any number as a command prompt argument which represents the number of iterations!
<br>
## SPSAbitmask.py

`SPSAbitmask.py` is similar to `SPSAtwo.py`, but instead of only looking in two directions ( all add or all subtract ), it tries all combinations of adding and subtracting using a bitmask ( where 0 is subtract, and 1 is add ). <br>
The same imports are required, and to run it, you do:

```sh
python3 SPSAbitmask.py
```
<br> This program has a similar input/output as `SPSAtwo.py`, but takes a bit longer to run each iteration as internally, its doing 256x more spectra checks than `SPSAtwo.py`!

<br> A good number of iterations such that too much time is not taken is 10. This can be done with:
```sh
python3 SPSAbitmask.py 10
```
<br><br>
## Building the Paper and Slides
The LaTeX source code to build a paper and slide presentation explaining this research are located in the paper/ and slides/ folders, respectively.

To build the PDF paper, inside Paper/, run
```
pdflatex main.tex
```

To build the PDF presentation, inside Presentation/, run
```
pdflatex main.tex
```
<br><br>
Please make sure to have all the necessary files and libraries installed before running the programs. Happy harmonics designing!
