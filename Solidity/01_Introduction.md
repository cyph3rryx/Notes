## INTRODUCTION TO SOLIDITY

`pragma solidity >=0.5.0 <0.6.0;`

here >=0.5.0 <0.6.0 indicates the version of solidity.

### Creating an empty “Hello World” smart contract will be like this:

`pragma solidity >=0.5.0 <0.6.0;`

`contract HelloWorld {`

`//start here`

`}`

***State variables***
 are permanently stored in  contract storage. This means they're written to the Ethereum blockchain. Think of them like writing to a DB.

### Example:

```solidity
contract Example {
  // This will be stored permanently in the blockchain
  uint myUnsignedInteger = 100;
}

// In this example contract, we created a uint called myUnsignedInteger and set it equal to 100.
```

***uint*** data type is an unsigned integer, meaning **its value must be non-negative**

***int*** data type is an for signed integer

Example:

`pragma solidity >=0.5.0 <0.6.0;`

`contract ZombieFactory {`

`uint dnaDigits = 16;`

`}`

// here we declared an unsigned Integer named “dnaDigits” with the value 16.

Math in Solidity:

- Addition: `x + y`
- Subtraction: `x - y`
- Multiplication: `x * y`
- Division: `x / y`
- Modulus / remainder: `x % y`
- Power : `x ** y`

`uint x = 5 ** 2; // equal to 5^2 = 25`

### Example 2:

```solidity
// Create a unsigned variable which shows the value 10^dnaDigits

pragma solidity >=0.5.0 <0.6.0;
contract ZombieFactory {
uint dnaDigits = 16;
uint dnaModulus = 10 ** dnaDigits;
```

To handle more of the complex data in Solidity:

### Struct:

***Structs*** allow you to create more complicated data types that have multiple properties.

**Example:**

```solidity
struct Person {
  uint age;
  string name;
}
```

` Struct is like a class. It helps you to combine multiple variable’s type in one block.`


### Example 2:

```solidity
// Create a Struct named Zombie and make the 'name' and 'dna' variable in it

pragma solidity >=0.5.0 <0.6.0;
contract ZombieFactory {

uint dnaDigits = 16;

uint dnaModulus = 10 ** dnaDigits;

struct Zombie {

			string name;

			uint dna;

}

}
```
