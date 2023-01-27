### Arrays:

There are two types of array: Fixed and Dynamic 

## **Fixed Array**:

We are limiting our Array size by some value

## Dynamic Array:

We are not limiting our Array size and rather giving it an infinite amount of input.

## Example:

```solidity
// Array with a fixed length of 2 elements:
uint[2] fixedArray;
// another fixed Array, can contain 5 strings:
string[5] stringArray;
// a dynamic Array - has no fixed size, can keep growing:
uint[] dynamicArray;
```


## Note: Remember that state variables are stored permanently in the blockchain? So creating a dynamic array of structs like this can be useful for storing structured data in your contract, kind of like a database.


### Example:

`Person[] people; // dynamic Array, we can keep adding to it`

## Public Arrays

You can declare an array as `public`, and Solidity will automatically create a ***getter*** method for it. The syntax looks like:

```solidity
Person[] public people;
```

Other contracts would then be able to read from, but not write to, this array. So this is a useful pattern for storing public data in your contract.

### Example 2:

``` soliity 
// Create a public array called Zombie within the Struct Zombies
pragma solidity >=0.5.0 <0.6.0;

contract ZombieFactory {

    uint dnaDigits = 16;
    uint dnaModulus = 10 ** dnaDigits;

    struct Zombie {
        string name;
        uint dna;
    }

    Zombie[] public zombies;


}
```

## Author: Cyph3rRyx
