# Привіт. 

# Виконання скрипта зі слайду 20:

generate-keypair.ts
```
import { Keypair } from "@solana/web3.js";
const keypair = Keypair.generate();
console.log('✅ Keypair generated:', keypair)

// badasya
```

Output: 
```
✅ Keypair generated: Keypair {
  _keypair: {
    publicKey: Uint8Array(32) [
       86, 192,  32,  53,  91,  37,  11, 211,
      129, 178, 176,   7, 156, 172, 249, 193,
        4, 111,  40, 195, 174, 165,  15, 151,
       32, 115, 124, 143, 165, 132,  80,  75
    ],
    secretKey: Uint8Array(64) [
       52, 147, 104,  11,  93, 209, 210,  13, 141,  56, 51,
       76, 249, 199,  96, 154,  40, 133,  84, 213, 111, 68,
      114, 174, 244,  96, 218,  83,  13, 193,  57,   5, 86,
      192,  32,  53,  91,  37,  11, 211, 129, 178, 176,  7,
      156, 172, 249, 193,   4, 111,  40, 195, 174, 165, 15,
      151,  32, 115, 124, 143, 165, 132,  80,  75
    ]
  }
}
```
![image](https://github.com/user-attachments/assets/7337aa17-16a9-41ca-adf4-fb0f69e1dcca)

# Виконання скрипта зі слайду 21:

generate-keypair.ts
```
import { Keypair } from "@solana/web3.js"

const keypair = Keypair.generate();

console.log('✅ Keypair generated:', keypair)

console.log('Public key', keypair.publicKey.toBase58())
console.log('Secret key', keypair.secretKey)

console.log(`✅ Finished!`);

// badasya
```

Output:
```
✅ Keypair generated: Keypair {
  _keypair: {
    publicKey: Uint8Array(32) [
      97,  73,  14,  26, 222, 228,  63, 205,
      91,   2, 205,  26, 166, 160, 147, 130,
      21, 165,  74, 120, 226, 246, 125, 249,
      48, 206, 203,  18,  37,   3, 218, 122
    ],
    secretKey: Uint8Array(64) [
       65,  45, 165, 197,  92,  70, 179,  14, 129, 108, 104,
       15, 224, 194,  21, 132, 185, 205,  12,  47, 125,  65,
      201, 167,  41,  71,  29, 165, 115, 239, 113, 204,  97,
       73,  14,  26, 222, 228,  63, 205,  91,   2, 205,  26,
      166, 160, 147, 130,  21, 165,  74, 120, 226, 246, 125,
      249,  48, 206, 203,  18,  37,   3, 218, 122
    ]
  }
}
Public key 7YmA75xgfuRqWVifJTCUvjiXaYuB19ky73cBm2jKaD9s
Secret key Uint8Array(64) [
   65,  45, 165, 197,  92,  70, 179,  14, 129, 108, 104,
   15, 224, 194,  21, 132, 185, 205,  12,  47, 125,  65,
  201, 167,  41,  71,  29, 165, 115, 239, 113, 204,  97,
   73,  14,  26, 222, 228,  63, 205,  91,   2, 205,  26,
  166, 160, 147, 130,  21, 165,  74, 120, 226, 246, 125,
  249,  48, 206, 203,  18,  37,   3, 218, 122
]
✅ Finished!

```
![image](https://github.com/user-attachments/assets/867411de-bc15-4b3f-a003-e545e484ee2d)

# Виконання скрипта зі слайду 23:

load-keypair.ts
```
import * as dotenv from "dotenv";
dotenv.config();
import { Keypair } from "@solana/web3.js";

let privateKey = process.env["SECRET_KEY"];
if (privateKey === undefined) {
  console.log("Add SECRET_KEY to .env!");
  process.exit(1);
}
const asArray = Uint8Array.from(JSON.parse(privateKey));
const keypair = Keypair.fromSecretKey(asArray);

console.log(`Public key: ${keypair.publicKey.toBase58()}`);

// badasya
```

Output:
```
Public key: 7YmA75xgfuRqWVifJTCUvjiXaYuB19ky73cBm2jKaD9s
```
![image](https://github.com/user-attachments/assets/c851199f-8a25-4359-bdbe-7bfefa95c29b)

