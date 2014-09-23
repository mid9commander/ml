MLPR Homework: Linear Models

The purpose of this assignment is to implement and understand
the basic learning algorithms for linear classifiers.

Your assignment should be sent by email to the TA
- Send your email in plain text (no msword, no html, no postscript, no pdf).
- late submissions will be penalized.
- you must implement the code by yourself, but you are 
  encouraged to discuss your results with other students.
- Include your source code as attachment(s).


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
The following learning algorithms must be implemented
with ridge (L2) regularization:
- the perceptron algorithm
- direct solution of linear regression
- on-line (stochastic) linear regression
- on-line (stochastic) logistic regression

the dataset with which to test the algorithm is called
uci-spambase. It is a two-class classification problems from
the UC Irvine machine learning dataset repository
(http://www.ics.uci.edu/~mlearn/MLRepository.html):

The dataset contains 4601 samples with 57 variables.
The task is to predict whether an email message is spam
or not (see ../datasets/uci-spambase/spambase.names for details).

The data is available in comma-separated-value format
in the file ../datasets/uci-spambase/spambase.data

The Lush code to read the data and format it is provided.
A skeleton of the learning code is also provided in Lush. 

You simply need to edit the file "linear-classifier.lsh" and implement
the "energy" and "learn-sample" methods of the classes perceptron,
logistic-reg, and linear-reg, and the "mse-solve" method of
linear-reg.  Then edit and modify the script main.lsh to run
the learning experiments.


1 - implement:
    a - the perceptron learning algorithm (perceptron class)
        methods to implement: energy, loss, learn-sample 
    b - the linear regression with quadratic loss (linear-reg class)
        methods to implement: energy, loss, learn-sample, mse-solve
        learn-sample is the online/stochastic gradient descent version
        while mse-solve is the direct solution through a linear system solver.
    c -the logistic regression algorithm (logistic-reg class)
        methods to implement: energy, loss, learn-sample 

   REMEMBER TO TAKE CARE OF THE BIAS PARAMETER!!!
   The bias is implemented a separate parameter,
   don't forget to update it in your code.

    ==> include your code as attachment.

2 - Experiments with the Spambase dataset

    - train each algorithm with
       10, 30, 100, and 500, and 3000 training samples,
       and 1000 test samples. The provided Lush code uses
       the first samples as training and the last ones as test
       (after shuffling the samples).
     - The linear regression and logistic regression
       algorithms require you to find good values
       for the learning rate (the step size, eta).
     - find which value of the learning rate will cause
       divergence for each size of the training set.
     - find the learning rate values for fastest convergence.
     - implement a stopping criterion that detects convergence.

     ==> for each size of training set, provide:
       - the final value of the average loss, and classification 
         error on the training set and the test set
       - the value of the learning rate used
       - the number of iterations performed

    - what is the asymptotic value of the training/test error 
      for very large training sets?

3 - Modify your code for linear regression (online and direct-solution
    versions) and logistic regression to add the "ridge regression" 
    regularizer to the cost function: decay*||W||^2  

    ==> can you improve the performance on the test set for
        small sizes of the training set by varying the 
        value of "decay"? If yes, provide the size of the
        training set and the value of "decay" for which
        you get an improvement.

