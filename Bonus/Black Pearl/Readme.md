# Part 1

![File 1](./part1.jpg)
This is the **HUBBLE**

# Part 2

![File 2](./part2.jpg)
This is block1, but according to the ctf prompt it's **BLOCKNO1**

# Part 3

Running exiftool in both files
![Exiftool 1](./data1.png)
![Exiftool 2](./data2.png)

```bash
77.9700642674036 # data 1
30.416381511669755 # data 2
```

These are the Coordinates, but we don't know which one is latitude and longitude.

As we know that the place is inside the college, so we can to do hit and trial method.
![Answer 3](./ans3.png)

As it is inside college so the part 3 of the flag is `RIG_ZONE`

`CSCTF{HUBBLE,BLOCKNO1,RIG_ZONE}`
