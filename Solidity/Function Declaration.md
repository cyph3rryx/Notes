## Function Declarations:

A function declaration in solidity looks like the following:

```solidity
function Norway(string memory _name, uint _amount) public {

}
```

- This is a function named `Norway` that takes 2 parameters: a `string` and a `uint`.
- For now the body of the function is empty. Note that we're specifying the function visibility as `public`.
- We're also providing instructions about where the `_name` variable should be stored- in `memory`.
- This is required for all reference types such as arrays, structs, mappings, and strings.

### What is a reference type you ask?

Well, there are two ways in which you can pass an argument to a Solidity function:

- By value, which means that the Solidity compiler creates a new copy of the parameter's value and passes it to your function. This allows your function to modify the value without worrying that the value of the initial parameter gets changed.
- By reference, which means that your function is called with a...reference to the original variable. Thus, if your function changes the value of the variable it receives, the value of the original variable gets changed.

## Example 2:

```solidity
//Create a public function named createZombie. It should take two parameters:
// _name (a string), and _dna (a uint). 
// Don't forget to pass the first argument by value by using the memory keyword
contract ZombieFactory {

    uint dnaDigits = 16;
    uint dnaModulus = 10 ** dnaDigits;

    struct Zombie {
        string name;
        uint dna;
    }

    Zombie[] public zombies;

    function createZombie(string memory _name, uint _dna) public{
        
    }

}
```

## Understanding the concept of Array and Structs:

### Creating New Structs

Remember our `Person` struct in the previous example?

```solidity
struct Person {
  uint age;
  string name;
}

Person[] public people;
```

Now we're going to learn how to create new `Person`s and add them to our `people` array.

```solidity
// create a New Person:
Person jenish = Person(172, "Jenish");

// Add that person to the Array:
people.push(jenish);
```

We can also combine these together and do them in one line of code to keep things clean:

```solidity
people.push(Person(20, "Jenish"));
```

Note that `array.push()` adds something to the **end** of the array, so the elements are in the order we added them. See the following example:

```solidity
uint[] numbers;
numbers.push(5);
numbers.push(10);
numbers.push(15);
// numbers is now equal to [5, 10, 15]
```

## Example 2:
``` solidity 
// Fill in the function body so it creates a 'new Zombie', 
//and adds it to the 'zombies' array. 
//The 'name' and 'dna' for the new Zombie should come from the function arguments

pragma solidity >=0.5.0 <0.6.0;

contract ZombieFactory {

    uint dnaDigits = 16;
    uint dnaModulus = 10 ** dnaDigits;

    struct Zombie {
        string name;
        uint dna;
    }

    Zombie[] public zombies;

    function createZombie(string memory _name, uint _dna) public {
        zombies.push(Zombie(_name, _dna));
    }

}```
