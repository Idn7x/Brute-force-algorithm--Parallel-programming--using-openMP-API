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

How the crack algorithms work:
We have a function for each possible length of the password. We have an array 
CharGeneratorKey that holds all the possible characters the password can contain.
Functions
CheckPassword Crack2 Crack3 Crack4 Crack5 crack6
2 Loops
CheckPassword
3 Loops
CheckPassword
4 Loops
CheckPassword
5 Loops
CheckPassword
6 Loops
CheckPassword
We start at the beginning of the array (signified by Char1Start) and go until the last 
character of the array. After each for loop execution, our current letter gets assigned 
to the next in the array.
Note: we use ++Char1Start so we get the next character before we assign it.
To get our Generated or guessed password, we assign the first letter, then append 
the rest. We only print out the generated password every 100 million iterations 
because cout statement greatly reduce the speed of the program if printed too often.
Finally, the idea behind what the for loops do is create all possible combinations in 
our alphabet (array). For simplicity's sake, let's take length 3 consisting of the 
alphabet {a,b} and look at the combinations: aaa, aab, aba, abb, baa, bab, bba, bbb
Note: The number of potential combinations is equal to the number of characters in 
our alphabet raised to the power of the length. 
So if we take our length 3 example, we have 2 characters in our alphabet, so the 
number of combinations is 2^3 = 8. 
This program handles 69 characters with a max length of 6, so approximately
1*10^11 combinations are possible
