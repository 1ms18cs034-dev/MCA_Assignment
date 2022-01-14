# MCA_Assignment
There are 3 versions of kNN implemented:
1) Serial version with C++
2) Version 1 with C++ and MPI
3) Version 2 with C++ and MPI
The training set: https://archive.ics.uci.edu/ml/datasets/Skin+Segmentation#
It has 245057 instances. The test set has 100 instances, random generated with instances that haven't occurred in the training set.

Version 1 with C++ and MPI

This version should be started with number of processors equal to the number of testing instances. Each processor takes one of the testing instance, runs the algorithm and make a decision by itself. Experiments show that this version is more efficient that the 2nd one.

Version 2 with C++ and MPI

In this version, each processor takes part in the solving the algorithm for each testing instance. The whole training set is split on (almost) equal parts (manually setting the boundaries) for each processor. Then, each processor runs the algorithm for its part of the set, and returns the result to the master processor (default 0). Master processor (default 0) does some more calculations to find the class for each test instance, and finally, prints out the class value for each instance.

Compile and run:

To compile: mpicxx -o (*name of exec*) main.cpp -std=c++11
To run the exec: mpirun -np (*num of processors*) (*name of exec*)
