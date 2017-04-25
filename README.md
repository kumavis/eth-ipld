# eth-ipld cli util

## Installation

`npm install -g eth-ipld`

## Usage

### cid

```
eth-ipld cid 0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421
```
```
          eth-block  z43AaGExa3pXMbZ2ea4Q4RfQrpUwrFmyWj8M325QXzqt5bhrBpk
     eth-block-list  z43c7o78Yf2uqVd1g8pGMdk5YuGQ4s42RvNdpqguWdvQypXtuAG
        eth-tx-trie  z443fKyJXGFJKPgzhha8eqpkEz3rHUL5M7cvcfJQVGzwt3MwcVn
             eth-tx  z44VCrqUVsTgoHkyjGKzx3uQw4qJW5c8GJsDQUuuTv5UnGBzKqJ
eth-tx-receipt-trie  z44vkPheUUg5HBpxkq5sFFz5d9ckigtBBW7WCJXQSZA1gV233Ap
     eth-tx-receipt  z45NHvZpT5tTm5twnPqjYU4kKEQCwJAE6hMnz88uRCEYahr5kWL
     eth-state-trie  z45oqTRzRh6rEyxvoxbbqg9R1KBf9uSH1tc5mwkQPqK5Uvg8Tqr
   eth-storage-trie  z46gvXALNuXdCn6ts67LS6JkPUkZb7zNrH6fMayQM7U9HNLDtWt
```

### block

parse a binary block. use -b to unwrap a blockbody.
```
curl 'http://localhost:5001/api/v0/block/get?arg=z43AaGEywSDX5PUJcrn5GfZmb6FjisJyR7uahhWPk456f7k7LDA' | ./bin.js block -b
```
```
{
  "parentHash": "0xdb0f5f78f3b0cc22789aca081ef54f1031c2ce6aa7e3db178192f1f5e60f14e8",
  "uncleHash": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
  "coinbase": "0x6c7f03ddfdd8a37ca267c88630a4fee958591de0",
  "stateRoot": "0x5954472acafb6b623591d2b64d97ca3d447d06dde34f1d76a96271a5c8ecbf58",
  "transactionsTrie": "0xcbb23cec06c609a7be76b95372686ddc7b2e65a923f795388772c12f4d6cc6a2",
  "receiptTrie": "0x10c70b964436dfb641e0a7b780e4485b205466e209622c419596579a3552521a",
  "bloom": "0x00000000000000000000000000000000000000080000000000000000000020000000800000000000000000040000000000000000000000400000000000000000000000000000000000000000000000000000000000000000000000000000000001000000000000000000000000040000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000800000000000000000000000000000000000000000000000000000000000000000000000000000000000120000000000200000000040000000000000000000000000000000000000000000000000000000",
  "difficulty": "0x722222f44a4c",
  "number": "0x302516",
  "gasLimit": "0x3d184e",
  "gasUsed": "0x083322",
  "timestamp": "0x589d29dc",
  "extraData": "0x416c70657265756d204555524f5045",
  "mixHash": "0x973a29b1b01cb41a5735b35deb6e8ce75f0d53b05e1568c1e0b76816a3a50570",
  "nonce": "0x5ce86c5f9c94d361"
}
```

### node

parse a binary trie node

```
curl 'http://localhost:5001/api/v0/block/get?arg=z45oqTRzb9a5xyvx5RbfSXH1K5jibyZ4AxnXyYReuLw7KU5veYw' | eth-ipld node
```
```
{
  "type": "branch",
  "children": {
    "0": "27959e5e8139706534ffc415a2855cbe66c6d6cab337e53536a2998291e9a906",
    "1": "a27c81e50fadccbef1c214a9b730db83f538b7ad6f54c8967dca8a66db43ffcf",
    "2": "63ec3f9242e0c9a32d42215e4eaf316ec7ba9a6e0d8f6e5293c1ab5bd9db7edb",
    "3": "59519efc66cfdecc9e5061f9e4f92366a2d59d67f713bcf0b5d152d8e17f7cbe",
    "4": "7f11a6c4ec8d58b8e2c93732026198b1925132dab1ebf085df241cb3fbc5a5b2",
    "5": "61e92caf02a0889260854631c53f516dffeb33237b66124d20f011289877678d",
    "6": "cc0199de9c77b84717a132b93f91f383c13f784e40d6f5230eef28a72a2835ba",
    "7": "d6ef683193988ee4aa12fcebd44e5cc623cd1d08945580e0b29ad61d72aeb068",
    "8": "55027154397cfcb73ee222a6e54977ea9aef06ef9f12c4349abefe6e338d2e0f",
    "9": "e5529249911cadc505498d7e26569409fce424f6859c59a3b913334f14caa672",
    "a": "b45e94681dde95ff915c692f6b71df04753180e79d550186755aa92a15483992",
    "b": "cf37a05e013417f71a0194d9aa86ec7acfbfd8b4be9586f89e59ebdb11f48104",
    "c": "7286f10482603b4f27998ac2b5989d4ee0bd5931cd9777a0e127980632f4d4df",
    "d": "324a3f5aea56a689f0a9c8dddf04317946318f72363623cf167582f6372f2e84",
    "e": "f8c16b7449322e4e88ae38558c65ea0d138e1de2ed186b0979bbdcdc7c47a0e2",
    "f": "fada56018977d23b546b86db67acd0ed493beceafa2b1cbc6bedf127486971b6"
  },
  "value": "0x"
}
```
