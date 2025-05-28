# How to programmatically claim SOPH rewards?

## Getting needed data

Open the Merkle Tree file [here](./merkletree.json) and locate your address.

You will find something like this:

```json
...
{
    "address": "0xe4c06bfd663C94005B8b159Cd320Fd7976549f9b",
    "tokenAmount": "300000000000000000",
    "merkleIndex": "1",
    "merkleProof": [
      "0xeb19859777adbfa7e5d5ce2c60353f1d0c7a8454c313fc3398f004483f6de228",
      "0x9335c3f944e5ddf6e9da97cf0ee568c5d08ecc6c96d5edf408bc66ad2756c780"
    ]
  },
...
```

### Go to claimer contract

1. Open [Sophscan explorer](https://sophscan.xyz/address/0xf4551b26cbB924BFa6117aD7b5D5Da2f70Fe8b9B#writeProxyContract#F7) and jump into the Claimer contract. Go to "Contract" → "Write as Proxy".
2. Connect your wallet using Metamask or your preferred wallet.

3. Find the `claim()` function (you will see 2 functions with the same name, it's the one that shows first, which does NOT receive a signature parameter).

### Fill in the inputs

Fill in the following parameters:

1. **`_user`** → the `address` from the file, this is your eligible address
2. **`_amount`** → the `tokenAmount` from the file
3. **`_merkleIndex`** → the `merkleIndex` from the file
4. **`_merkleProof`** → the `merkleProof` from the file

**Important:** When writing the input values, including the proof, make sure you are not including any quotation marks (") at the beginning or end of any value. The merkle proof is a continuous string of characters without any punctuation except for the commas (,) as separators. The brackets ([ and ]) should be **excluded**.

4. Sign and execute
