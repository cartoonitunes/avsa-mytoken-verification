# AVSA MyToken — Bytecode Verification

Source code recovery for 8 unverified Ethereum contracts deployed by Alex Van de Sande (AVSA, `0xd1220a0cf47c7b9be7a2e6ba89f429762e7b9adb`) in February 2016 as part of the [Ethereum Token Tutorial](https://github.com/ethereum/ethereum.org).

## Contracts

All 8 contracts share the same bytecode source family (MyToken ERC-20 token), compiled with Solidity `v0.2.0-nightly.2016.1.13+commit.d2f18c7` (`--optimize`).

### 1802B Variant — `src/MyToken_1802c.sol`

Functions declared **before** state variables in MyToken body; `transferOwnership` in `MyToken`; fallback throws.

| Contract | Block | Timestamp |
|----------|-------|-----------|
| [`0xe36905580fa8cc3006c14bafab9d0ecf39c9c124`](https://etherscan.io/address/0xe36905580fa8cc3006c14bafab9d0ecf39c9c124) | 988921 | 2016-02-11 |
| [`0xab15f08da9b99cbd2f71922953af9a38942d05ec`](https://etherscan.io/address/0xab15f08da9b99cbd2f71922953af9a38942d05ec) | 988935 | 2016-02-11 |

### 1830B Variant A — `src/MyToken_1830a.sol`

transfer/mintToken/freezeAccount/transferOwnership declared before state vars; remaining functions after; fallback forwards ETH to owner (no throw).

| Contract | Block | Timestamp |
|----------|-------|-----------|
| [`0x1a3970be1fcfc610a588b268e3f4e8fa8add1076`](https://etherscan.io/address/0x1a3970be1fcfc610a588b268e3f4e8fa8add1076) | 987976 | 2016-02-11 |
| [`0x59a273f78e4d22fcde1a254251941a49295c6786`](https://etherscan.io/address/0x59a273f78e4d22fcde1a254251941a49295c6786) | 987979 | 2016-02-11 |
| [`0x1f75047233517dcf67970d9e3c3bb385cb647f30`](https://etherscan.io/address/0x1f75047233517dcf67970d9e3c3bb385cb647f30) | 987982 | 2016-02-11 |

### 1830B Variant B — `src/MyToken_1830b.sol`

State variables declared before all functions; `transferOwnership` in `owned`; fallback forwards ETH to owner (no throw).

| Contract | Block | Timestamp |
|----------|-------|-----------|
| [`0x8cb1f47bf87ba23221053933e10933f92f74105b`](https://etherscan.io/address/0x8cb1f47bf87ba23221053933e10933f92f74105b) | 988798 | 2016-02-11 |
| [`0x41a7820c86f4bea29e6c9239aeb0fbdba12dd790`](https://etherscan.io/address/0x41a7820c86f4bea29e6c9239aeb0fbdba12dd790) | 988807 | 2016-02-11 |
| [`0x6bbfe039121bc99e907303c533b81f7048e840e6`](https://etherscan.io/address/0x6bbfe039121bc99e907303c533b81f7048e840e6) | 988814 | 2016-02-11 |

## Verified Reference

[`0xa8c94f66f0c9add0f50ae91bfe985c03b5493511`](https://etherscan.io/address/0xa8c94f66f0c9add0f50ae91bfe985c03b5493511) — already verified on Etherscan, used as compilation reference.

## Compilation

```bash
solc v0.2.0-nightly.2016.1.13+commit.d2f18c7 --optimize --bin-runtime src/MyToken_1802c.sol
```

## Submitted by

[EthereumHistory](https://ethereumhistory.com) — documenting Ethereum's early history.
