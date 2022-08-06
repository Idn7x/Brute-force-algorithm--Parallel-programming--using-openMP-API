# Brute-force-algorithm--Parallel-programming--using-OpenMP-API
<h2 align="center">The introducion:</h2>
Our algorithm is a program where you input a password (from length 2 to 6) and this will 
continue to run until it finds the password you inputted or fails due to the password 
containing a character not accounted for in the CharGeneratorKey array or the 
password is longer than 6 characters. we use the openMP for parallelizing the code in order to reduce the execution time.
we parallelized the code using two methods:
 * First method using nested loops
 * Second method using recursive algorithm

    This is NOT a real password cracker. You cannot put in an encrypted password and find out what it is.

 <h2 align="center"> - First method using nested loops::</h2>
 
   1- Sequential code:
    
    This is NOT a real password cracker. You cannot put in an encrypted password and find out what it is.
This program simply cycles through an array in an attempt to "brute force" or "guess" 
the password you entered.
Here is a simple flowchart that explains our sequential code, that contains six 
functions the first one is “ CheckPassword “that will compare the generated string by
the other five functions ( crack2, crack3 … ) with the password entered.

How the crack algorithms work:

We have a function for each possible length of the password. We have an array 
CharGeneratorKey that holds all the possible characters the password can contain.

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

 2- Parallel code :
 
To parallelize the code we had three possible methods:

 * Parallelize only inside of the functions.
 * Parallelize only inside of the main.
 * Parallelize inside of the main and functions.
We parallelized the code using the three methods but After a multiple tries and tests
of execution we confirm that the best method to parallelize our code is the second 
one ( Parallelize only inside of the main ).

How we parallelize the code:

As we had mentioned above we Parallelize the code only inside of the main.
We parallelize the code with 6 sections, each one of theme assume the cracking of
the password with specified length ( try all the possible combinations for a specified 
length of the password) depends on the function called in the section, if we call for 
example the ‘crack5’ function, the section will assume to crack the password with the 
length of 5 that means try all the possible combinations existed in the length of five
characters. 69^5 = 1564031349 combinations

 <h2 align="center"> - Second method using recursive algorithm:</h2>

  1-Sequential code:

So, our second code includes a recursive function and it has as parameters:

 * an array of characters.
 * a string which is a combination of characters from the array.
 * n : length of the array.
 * k : length of the string. 
 
the function will add or remove characters until k is reached. the base case is when k 
has been reached, if not then iterate through the array, after that create new string 
with next character and call crack again until string has reached its length.

  2-Parallel code :
  
To parallelize the code, we had three possible methods:

 * Parallelize only inside of the functions.
 * Parallelize only inside of the main.
 * Parallelize inside of the main and functions.

We parallelized the code using the three methods but After a multiple tries and tests 
of execution we confirm that the best method to parallelize our code is the second 
one ( Parallelize only inside of the main ).

How we parallelize the code:

We parallelize the code using the parallel for. We started from the same principle.
We try to give each thread to cover the cracking of the password with specified 
length as before in the first parallel program but this time not with functions but with 
iterations, in each iteration of the for loop will try all the possible combinations for a 
specified length of the password depends on the value of the integer I that will starts 
from 2 to 6 ( password with 2 characters to 6 characters.

<h2 align="center">Code Source</h2>

    if you need the code source of both sequential or parallel program of the two methods. Be free to contact me:
    naciri.works@gmail.com



