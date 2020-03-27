Write a function that takes an (unsigned) integer as input, and returns the number of bits that are equal to one in the binary representation of that number.

Example: The binary representation of 1234 is 10011010010, so the function should return 5 in this case

Solution:
I found out two solutions to this challenge. 

1. Solution 1

    var countBits = function(n) 
    {
        // make an array with the bit result
        const base = (n).toString(2).split('');
        
        // make a sum with the array and make the index a Number
        const result = base.reduce((sum, num) => sum + Number(num), 0);
        
        return result;
    };


2. Solution 2

    var countBits = function(n) 
    {
        // Initialise count with a value 0.
        var count = 0;
        // when n is not equal to 0.
        while (n != 0)
        {
            // ensure that n is never a 0.
            n = n & (n-1);
            count++;
        }
        return count;
    };