# 2- Notes

**Methods:**
* Used for common problems
  * Common mathematical problems
* Reading from/writing to files

*Terminology*
* Parameters
  * Inputs passed to method
* Call
  * Invoking method
* Return type
  * Data type method evaluates to

**Predefined Methods:**

* Math.pow()- exponents
* Math.sqrt()- square roots

### Methods are just functions

**Groups of Related Methods can be Classes (in java)**

**Common Math Methods**
*Use name of class- Math.random() - returns random number*
* sqrt()- return square root [double, double]
* round()- round up from 0.5, down otherwise [double, int]
* ceil()- always round up [double, double]
* floor()- always round down [double, double]
* abs()- take absolute value (remove sign) [int, int]
* abs()- overloaded-- take absolute value (remove sign) [double, double]

**Random Numbers**
*True Random Numbers*
* Numbers generated due to physical processes
  * Rolling dice or shuffling playing cars

*Pseudorandom Number Generators (PRNGs)*
  * Algorithms for generating numbers that *seem* random
  * Dependent on a seed (time in python)

* Must meet two critical definitions
  * Unpredictable
  * Must appear to be a random distribution

**Generating Random Numbers in Java**

* import java.util.Random;
* Random rand = new Random();
* int r = random.nextInt();
* *Generates number between -2,147,483,647 & 2,147,483,647*
* Use % to reduce range of numbers Math.abs(rand.nextInt()) % 10 + 1 = [0, 10] -- (I think)

# Algorithms

* "An algorithm is a finite sequence of unambiguous instructions that, given any necessary input, produces a correct result and stops"
  * finite- has an end, countable
  * sequence- order is critical
  * unambiguous- completely clear, not subject to interpretations
  * instructions- specific command to perform a well-defined action

**Real World Algorithms**
  * Recipes
    * Pb&J
    * Browning meat
  * Registering for courses
  * Not algorithms
    * Falling in love

*Generating a Random Die Roll*
1. Seed the random number generator
2. Request a random number
3. Divide that number by 6 *using integer notation*
4. Capture the remainder, not the quotient (%)
5. Add 1 (+1) to that result
6. Store in a variable

### If/Else (you know this)
