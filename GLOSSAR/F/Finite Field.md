# Finite Field

Mathematically, a finite field is defined as a **finite set of numbers and two operations + (addition) and ⋅ (multiplication)** that satisfy the following:

1. If a and b are in the set, a + b and a ⋅ b are in the set. We call this property **closed**.

2. 0 exists and has the property a + 0 = a. We call this the additive identity.

3. 1 exists and has the property a ⋅ 1 = a. We call this the multiplicative identity.

4. If a is in the set, –a is in the set, which is defined as the value that makes a + (–a) = 0. This is what we call the additive inverse.

5. If a is in the set and is not 0, a–1 is in the set, which is defined as the value that makes a x a^-1 (a mal a hoch -1 ist 1 geteilt durch a). This is what we call the multiplicative inverse.

In math notation the finite field set looks like this:

> Fp = {0, 1, 2, ... p–1}

A finite field of order 11 looks like this:

> F11 = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}

Notice the order of the field is always 1 more than the largest element. 

You might have noticed **that the field has a prime order every time**. For a variety of reasons that will become clear later, it turns out that fields must have an order that is a power of a prime, and that the finite fields whose order is prime are the ones we’re interested in.

To make the definition of a CLOSED set work with real numbers, we have to replace the "normal" addition and the "normal" multiplication by new function we are calling +f und *f. 

*a +f b* is defined as the "normal" sum of a and b and then taken modulo at the base of the set's order

or in a concrete example

in F11 (which is the set with the numbers {0, 1, ... , 10}) 

1. **Addition** > 5 +f 9 = 3  whitch is calculated 5+9%11

and 

2. **Substraction** > 5 -f 9 = 7  whitch is calculated 5-9%11 (weil -1*11 + 7 = -4 ist) 


3. **Multiplication** > 5 *f 9 = 1  whitch is calculated 5*9%11 = 45%11 = 1


3. **Exponential** > 7 ^f 3 = 1  whitch is calculated 7^3%11 = 343%11 = 1

5. **Division** > 7 /f 3 = 
