## Typecasting

Sometimes you need to convert between data types. Take the following example:

```solidity
uint8 a = 5;
uint b = 6;
// throws an error because a * b returns a uint, not uint8:
uint8 c = a * b;
// we have to typecast b as a uint8 to make it work:
uint8 c = a * uint8(b);
```

In the above, `a * b` returns a `uint`, but we were trying to store it as a `uint8`, which could cause potential problems. By casting it as a `uint8`, it works and the compiler won't throw an error.

## Example 2:

1. The first line of code should take the `keccak256` hash of `abi.encodePacked(_str)` to generate a pseudo-random hexadecimal, typecast it as a `uint`, and finally store the result in a `uint` called `rand`.

2. We want our DNA to only be 16 digits long (remember our `dnaModulus`?). So the second line of code should `return` the above value modulus (`%`) `dnaModulus`.

``` solidity
pragma solidity  >=0.5.0 <0.6.0;

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

    function _generateRandomDna(string memory _str) private view returns (uint) {
        uint rand = uint(keccak256(abi.encodePacked(_str)));
        return rand % dnaModulus;
    }

}
```
