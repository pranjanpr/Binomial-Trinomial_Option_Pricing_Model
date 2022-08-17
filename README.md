# Binomial_Option_Pricing_Model
This repository contains the code for call options implemented via the binomial option pricing model

The details of model can be found [here](https://drive.google.com/file/d/1GH97BbTVJwf1f9mmwr31S3c_geXKZDo9/view?usp=sharing).

Here XYZ is represents “American Options” and ABC is the underlying commodity.
We are using trinomial option pricing for calculating the actual price of XYZ at trading date (td).
Implementation of price_xyz():
1.	Firstly, evaluate the duration for the trinomial tree. It is given by te – td.
2.	Once we have duration, we will calculate the time steps (delta T).
3.	Then we evaluate p_u, p_d, j_u and j_d with the help of formulas given in the problem.
4.	We will then for the pricing tree of commodity abc in the root to leaf fashion. For this I have created a rectangular numpy array with appropriate sizes.
5.	Once we have the prices of abc at each time step with all the possibilities, we will create the trinomial tree for xyz pricing.
6.	Firstly, we will set the correct prices on the leave nodes.
7.	Then we will go in the leaf to root fashion and evaluate the xyz price at each node.
8.	Once we reach the root node, we know the extrinsic price of xyz and we will output it.
Implementation of volrisk_xyz():
1.	I have implemented this function utilising the price_xyz() function.
2.	The value dX_td/dsigma can be evaluated using first principle of differentiation.
3.	The above value is calculated by:-
(Price_xyz(….., sigma+delta, …) - Price_xyz(….., sigma, …)) /delta
	We have estimated it in partial differentiation fashion which might give incorrect results.
