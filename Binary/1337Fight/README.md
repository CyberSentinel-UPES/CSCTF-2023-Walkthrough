# How To Hack

![Type of file](./file.png "Type Of File")

As it's a **Binary ELF** file we have to give it executable permissions.

```bash
chmod +x ./chall
```

![Main Screen](./display.png "Main Screen")

1. Open the binary in some decompiler, I'm using **Ghidra**
   ![Ghidra View](./ghidra1.png "Ghidra View")

1. Look for interesting functions
   ![Ghidra Functions](./ghidraFunctions.png "Ghidra Functions")

1. Formatting that function for better understanding
   ![formatting](./formatit.png "Fomatting Function")

1. Running that function in python3

```python3
from Crypto.Util.number import long_to_bytes

encList = [
    long_to_bytes(0x426b516c7e697969),  # convertting numbers to bytes
    long_to_bytes(0x4b427e7512675345),  # convertting numbers to bytes
    long_to_bytes(0x594b4f587e4f6858),  # convertting numbers to bytes
    long_to_bytes(0xb4f585f),  # convertting numbers to bytes
    b'W'
]

xorNum = 0x2a

for enc in encList:
    for e in enc[::-1]:  # converting little-endian to big-endian
        print(chr(e ^ xorNum), end="")
print()
```

![Flag](./solve.png "FLAG")
