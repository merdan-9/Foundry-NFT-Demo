This project corresponds to the tutorial [Creating an NFT with solmate and foundry](https://onbjerg.github.io/foundry-book/tutorials/solmate-nft.html) from the Foundry Book and includes the implementation of a basic Opensea compatible NFT using the foundry framework to test and deploy your contract. Furthermore it offers an implementation using both [Solmate](https://github.com/Rari-Capital/solmate/blob/main/src/tokens/ERC721.sol)'s gas optimised ERC721 library as well as [Open Zeppelin](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/ERC721.sol)'s ERC721 library. 

### Run tests:
```bash
forge test
```

### Compare gas costs between OpenZeppelin and Solmate library
```bash
forge test --gas-report
```

### Gas report
#### Solmate
| Deployment Cost   | Deployment Size |       |        |       |         |
| ----------------- | --------------- | ----- | ------ | ----- | ------- |
| 1163822           | 6564            |       |        |       |         |
| Function Name     | min             | avg   | median | max   | # calls |
| MINT_PRICE        | 250             | 250   | 250    | 250   | 4       |
| balanceOf         | 705             | 705   | 705    | 705   | 2       |
| currentTokenId    | 2308            | 2308  | 2308   | 2308  | 1       |
| mintTo            | 383             | 49291 | 69393  | 72739 | 11      |
| ownerOf           | 600             | 600   | 600    | 600   | 1       |
| withdrawPayments  | 2606            | 18529 | 18529  | 34453 | 2       |

#### Openzeppelin
| Deployment Cost   | Deployment Size |       |        |       |         |
| ----------------- | --------------- | ----- | ------ | ----- | ------- |
| Function Name     | min             | avg   | median | max   | # calls |
| MINT_PRICE        | 250             | 250   | 250    | 250   | 4       |
| balanceOf         | 705             | 705   | 705    | 705   | 2       |
| currentTokenId    | 2308            | 2308  | 2308   | 2308  | 1       |
| mintTo            | 383             | 49640 | 69726  | 73293 | 11      |
| ownerOf           | 602             | 602   | 602    | 602   | 1       |
| withdrawPayments  | 2606            | 18529 | 18529  | 34453 | 2       |
