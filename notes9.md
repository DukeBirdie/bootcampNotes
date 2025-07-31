# Data Representation:
## Integer Representation:
### Binary and Bits:
* Binary
  * Number system -> only digits are 0 & 1
  * Also called base 2
* Everything represented as binary
  * Numbers, letters, videos, prgms.
* Each unit of data is represented by 1 or more bits
  * Bit - binary digit

### Convert Decimal to Binary:
1. Start with any base 10 integer
2. Divide number by 2, storing remainder & quotient
   3. If remainder is 1, write a 1 in the next column, going from right to left
   4. If the remainder is 0, write a 0 in the next column, going from right to left
5. If the quotient from Step 2 is > 0, return to step 2
6. Otherwise, end

## Integer Datatypes:
* Why don't these lines of code work?
`long mspy = 1000 * 60 * 60 * 24 * 365;`
`System.out.println("Milliseconds per year: " + mspy;`
* Java can only perform arithmetic operations with numbers of the same type
    * Multiply: int * int = int
    * long * int = ?
* Need to designate 1 or more #'s as long
  * Force Java to convert all to long
* 2 options
  * Make one a long variable before multiplying
  * *End one or more integer literals with an "L" (e.g. 1000L)* 

## Things Counted With Prefixes
* Bits
  * Mb
* Bytes
  * MB
* Hertz (Hz)
  * Cycles / second
  * CPUs - typically gigahertz (billions of cycles/second)
  * RAM - typically megahertz (millions of cycles/second)
  * Common RAM - 2133 Mhz (equal to 2.133 GHz)

## When is 1000 not 1000?
* Remember that 2^10 is 1,024
* Often used as a replacement for 1,000
* Does 1MB mean 1024 * 1024 bytes (1,048,576 bytes or 1,000,000 bytes)?
  * Technically the latter
    * Both are used
    * Also mebibyte, gibibyte (for 1024) - rarely used
