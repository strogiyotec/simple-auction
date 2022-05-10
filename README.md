# simple-auction
Auction smart contract for Solana blockchain


## Dependencies
1. Install [solana](https://docs.solana.com/cli/install-solana-cli-tools)
2. Install [anchor](https://project-serum.github.io/anchor/getting-started/installation.html)
3. Install [ts-mocha](https://github.com/piotrwitek/ts-mocha)

## How to run
`anchor test`

## Smart contract overview
The source code for contract is located under `/programs/auction/src/lib.rs`
The contract has the following methods
### Initialize
Initialize the contract 
<br>
Arguments: 
1. initial prise (in lamports)
2. end date in seconds

### Bid
Bid new price
<br>
Arguments:
1. amount (in lamports)

<br>
Checks:
1. No amount less than initial bid
2. If person has already bed the highest bid then transaction is aborted
3. If person has bed before then we add-up remaining tokens to a new bed

### end_auction
End the auction
<br>
Checks:
1. Only end auction after the initial time has passed
2. Can't end twice

### refund
Request a refund after the auction has finished
<br>
Checks:
1. Can't request a refund twice per account

## How to verify ? 
There is a test case written in `tests/auction.ts` file it will be running on `anchor test` command
