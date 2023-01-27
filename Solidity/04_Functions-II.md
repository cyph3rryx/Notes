## Public/Private Functions:

In Solidity, functions are `public` by default. This means anyone (or any other contract) can call your contract's function and execute its code.

- Obviously this isn't always desirable, and can make your contract  vulnerable to attacks. Thus it's good practice to mark your functions as `private` by default, and then only make `public` the functions you want to expose to the world.

Let's look at how to declare a private function:

```solidity
uint[] numbers;

function _addToArray(uint _number) private {
  numbers.push(_number);
}
```

- This means only other functions within our contract will be able to call this function and add to the `numbers` array.
- As you can see, we use the keyword `private` after the function name.
- And as with function parameters, it's convention to start private function names with an underscore (`_`).

## Example 2:

```solidity
//Modify createZombie so it's a private function in previous problem

function _createZombie(string memory _name, uint _dna) private {
```

`Return` : To return a value from a function

```solidity
// Example of return function
string welcome = "Wassup dog";

function comeHome() public returns (string memory) {
  return welcome;
}
```

Now to know that our function is in only read only mode then we have to use `view` keyword after declaring the function in private.

```solidity
function comeHome() public view returns (string memory) {
```

Another keyword `pure` is also used which means you're not even accessing any data in the app.

Confusion can be created in using both the function but the compiler of Solidity will give us an error if we used another one in place of other. 

```solidity
// Example of pure function
function _multiply(uint a, uint b) private pure returns (uint) {
  return a * b;
}
```

## Example 2:

``` solidity 
//Create a private function called _generateRandomDna.
//It will take one parameter named _str (a string), and return a uint. 
//This function will view some of our contract's variables but not modify them, 
//so mark it as view.

pragma solidity >=0.5.0 <0.6.0;

contract ZombieFactory {

    uint dnaDigits = 16;
    uint dnaModulus = 10 ** dnaDigits;

    struct Zombie {
        string name;
        uint dna;
    }

    Zombie[] public zombies;

    function _createZombie(string memory _name, uint _dna) private {
        zombies.push(Zombie(_name, _dna));
    }

    function _generateRandomDna(string memory _str) private view returns (uint){
        
    }

}
```
