# Julia-Programming
Installing Package
Pkg.add("DataFrames")

Using a package
using JuMP

Defining a model
m = Model()

Creating two variables x and y
@defVar(m, x >= 0)
@defVar(m, y >= 0)

Creating objectives
@setObjective(m, Max, 300x + 200y)

Adding Constraints to the model
@addConstraint(m, x + y <= 60) #land
@addConstraint(m, 3x + 2y <= 100) #labor
@addConstraint(m, 2x + 4y <= 120) #Fertilizer

To print the model
println(m)

To check the status of the model
status=solve(m)

To print the value of a decision variable 'x'
print("x = ", getValue(x))
	
To print the value of a decision variable 'y'
print("y = ", getValue(y))

To print the value of the objective
print("Objective = ", getObjectiveValue(m))
