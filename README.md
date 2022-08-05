# Brute-force-algorithm--Parallel-programming--using-openMP-API
<h2 align="center">The introducion:</h2>
Our algorithm is a program where you input a password (from length 2 to 6) and this will 
continue to run until it finds the password you inputted or fails due to the password 
containing a character not accounted for in the CharGeneratorKey array or the 
password is longer than 6 characters. we use the openMP for parallelizing the code in order to reduce the execution time.
we parallelized the code using two methods:
 * First method using nested loops
 * Second method using recursive algorithm
 <h2 align="center"> First method using nested loops::</h2>
    1- Sequential code:
    This is NOT a real password cracker. You cannot put in an encrypted password and 
find out what it is.
This program simply cycles through an array in an attempt to "brute force" or "guess" 
the password you entered.
Here is a simple flowchart that explains our sequential code, that contains six 
functions the first one is “ CheckPassword “that will compare the generated string by
the other five functions ( crack2, crack3 … ) with the password entered.
