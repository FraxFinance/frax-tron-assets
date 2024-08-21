# Frax Tron

## Resources
- https://tronscan.org
- https://www.btcschools.net/tron/tron_tool_base58check_hex.php
  - Ignore the "41" at the start when decoding Base58

## Addresses
### Official
#### Tron
- FRAX: `TArMTLyihUsuscLtL3hzrFF65r8NbWkW9f`
- sFRAX: `TDsivFeAJ9pPWJEWvrWotXYiqY85s1EYW4`
- FXS: `TAJgjCjWSQUzkLfxRWU4q2smEBMGZCeWfL`


### Test
#### Tron
- Deployer / Authorized Minter
  - `TLNe6KF1dUSYBcZ4fzTstoKB8bkzQewz42`
- FRAX Mintable ERC20 (test)
  - `TQZTkTMbkC9923LtVHZcSrdqcW5rVhkZHP`
- FRAX Ferry
  - `TGxtcNUY9q19FATX3tFxzkmBhQigVDTFJs`

### Fraxtal
- Deployer / Ferry owner
  - `0xb0E1650A9760e0f383174af042091fc544b8356f`
- FRAX Ferry
  - `0xa5677a5bF6e8759D3C904d2da85D1318E398cf3A`

## Optional Setup
Add:
```
function profile() {
  FOUNDRY_PROFILE=$1 "${@:2}"}
```
To easily execute specific foundry profiles like `profile test forge test -w`

## Installation
`pnpm i`

## Compile
`forge build`

## Test
`profile test forge test`

`profile test forge test -w` watch for file changes

`profile test forge test -vvv` show stack traces for failed tests

## Deploy
- Update environment variables where needed
- `source .env`
```
`forge script src/script/{ScriptName}.s.sol \
  --rpc-url ${mainnet || fraxtal || fraxtal_testnet || polygon} \
  --etherscan-api-key {$ETHERSCAN_API_KEY || FRAXSCAN_API_KEY || POLYGONSCAN_API_KEY} \
  --broadcast --verify --watch
```

## Tooling
This repo uses the following tools:
- frax-standard-solidity for testing and scripting helpers
- forge fmt & prettier for code formatting
- lint-staged & husky for pre-commit formatting checks
- solhint for code quality and style hints
- foundry for compiling, testing, and deploying
