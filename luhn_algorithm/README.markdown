## Luhn Algorithm

The Luhn algorithm is a check-summing algorithm best known for checking the validity of credit card numbers.

You can checkout the full description on Wikipedia: http://en.wikipedia.org/wiki/Luhn_algorithm

### Description

(adapted from Wikipedia)

The formula verifies a number against its included check digit, which is usually appended to a partial account number to generate the full account number. This full account number must pass the following test:

* from the rightmost digit, which is the check digit, moving left, double the value of every second digit
* if product of this doubling operation is greater than 9 (e.g., 7 * 2 = 14), then sum the digits of the products (e.g., 10: 1 + 0 = 1, 14: 1 + 4 = 5).
* take the sum of all the digits
* if and only if the total modulo 10 is equal to 0 then the number is valid

### Example

#### Calculating the Check Digit

Take an account identifier `7992739871`. To make it an account number, we need to calculate and append a check digit. Calling the digit `x`, the full account number will look like `7992739871x`.

We use the algorithm to calculate the correct checksum digit:

* `Account identifier:    7   9   9   2   7   3   9   8   7   1   x`
* `2x every other digit:  7   18  9   4   7   6   9   16  7   2   x`
* `Summed digits over 10: 7   9   9   4   7   6   9   7   7   2   x`
* `Results summed:        7   9   9   4   7   6   9   7   7   2` = 67

With the result of `67`, we take the ones digit (`7`) and subtract it from `10`: `10 - 7 = 3`. Thus `3` is the check digit.

The full account number with check digit is `79927398713`.

#### Validating an Account Number

We can use the same process to validate an account number. Using `79927398713` as our sample input:

* `Account identifier:    7   9   9   2   7   3   9   8   7   1   3`
* `2x every other digit:  7   18  9   4   7   6   9   16  7   2   3`
* `Summed digits over 10: 7   9   9   4   7   6   9   7   7   2   3`
* `Results summed:        7   9   9   4   7   6   9   7   7   2   3` = 70

Since the summed results modulo 10 is zero, the account number is valid according to the algorithm.


