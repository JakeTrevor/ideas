Take a photo of a receipt and work out the macros on it.

## Basic Requirements:
- A database
- A dashboard
- A receipt processing system

## Receipt Processing
Receipt processing requies:
- convert image to text
- itemize list
- filter list (e.g. remove bleach)
- get macro values for items on list
- store for reporting on dashboard

## Further Development:
This alone would be pretty useful, but there is more work to do if we want.
I buy a bag of rice, but unlike a pack of chicken or box of mushrooms, I dont get through the whole thing in a week. So the macro values of items like rice, pasta, etc. (i.e. non-perishables) should be spread out over time.
There are many ways we could approach this problem;

a) simple and dumb: produce an average over multiple weeks. A convolution would allow us to track change over time while still using this solution.
b) simple, a bit less dumb: ask the user about what they eat/in what timeframe.
c) more complex: attempt to figure out 

# MVP:
- receipt photo to list & macros
- allow user to patch macros
	- some system for weird oneoffs
- keep an inventory of what you have
- use items up for meals
- save meals
	- record meals feature
- progressive adoption


