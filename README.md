# PHSX815_Project3: Orbit Stability Simulation of Planetary systems

## Project Description
Similar to project 1 and 2, we will simulate an idealized planetary system with the Sun at the center, corresponding to orbital parameters samples from Beta distribution. We implement the Hill stability Criterion \cite{Chambers:1996} \cite{Gladman:1993} to calculate fractional orbital separation for examination of stability of two bodies system. The difference in this project is that the model parameter we are interested in will be estimated using simulated data from the experiment. 


Note: alpha and beta are two shape parameters of beta distribution.

## This repository contains several types of programs:
* python/ `Simulation.ipynb`, `Analysis.ipynb` , `Random.py`
* `demo-py/` contains programs from HW 8 and HW9


## Code Usage : NO NEED TO RUN IN TERMINAL, GENERATED IN JUPYTER NOTEBOOK.
 
In this project, we can implicitly specify non-default values for the probability of stable outcome (like a coin toss experiment) by specifying two model parameters alpha_{0}.  This simulation is with beta_{0} = 0.5 fixed. Nexp, Nmeasurement, Nsamples can be changed by users.

two output files will be analyzed: `stb.txt` and `out.txt`

## For Peer reviewer [EXPIRED]
Begin with `OrbitSim.py`, it will call from random class, samples from beta distribution by alpha and beta to calculate Delta_critical. Then numeriacally calculate the probability of being stable and pass to bernoulli probabaility distribution. A result of stable or unstable outcome is simulated by specifying number of systems and number of experiments you wish to evaluate. This program will generate simulated stable/untable systems indicating as '0' ot '1' and pipe it to a text file. 

	*  Options can be called from the command line with the -h 
	*  eg: `python3.8 python/OrbitSim.py -a 0.5 -b 0.5 -Nsystem 100 -Nexp 10000 -output H0.txt `
	*  -a alpha value
	*  -b beta value
	*  -output [filename]  name of file for hypothesis

It will also generate a distribution of Delta_{cr} samples from Beta distribution for two different set of shape parameters, alpha = 0.5 and beta = 0.5, click to see plot below: 

* ![plot](delta_cr_0.5_0.5.pdf)

Next step, we will use the text file data (fixed), analyze the simulated data to find the value of \\alpha and \\beta that maximizes L(alpha, beta|X) (the data is ”fixed” in an experiment), I am also planning to run the Neyman construction to compare the true value of alpha with calculated value. 

* project 2 `SimAnalysis.py` usage: `python3.8 python/SimAnalysis.py -a0 0.5 -b0 0.5 -a1 3.0 -b1 3.0 -input0 H0.txt -input1 H1.txt`
* A background paper extracted from paper 2 is provided for reviewer to know this simulation details.


