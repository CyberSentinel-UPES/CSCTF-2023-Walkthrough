1) open the file with wireshark using `wireshark babyshark.pcapng`
2) Right click on any HTTP packet and click follow > HTTP stream.
3) Scroll down till you find a POST request which contains the following body:
```
ip=google.com+%7C+true%281%29+%26%26+echo+Q1NDVEZ7c0hhcms1X0RPX04wdF9IQXYzX2JPbjM1fQ%3D%3D+%3E+%2Fdev%2Fnull+2%3E%261+%26%26+ls+-al&submit=submit
```
4) URL decode the body using any tool like [URL Decoder/Encoder (meyerweb.com)](https://meyerweb.com/eric/tools/dencoder/) 
5) After decoding we get:
```
ip=google.com | true(1) && echo Q1NDVEZ7c0hhcms1X0RPX04wdF9IQXYzX2JPbjM1fQ== > /dev/null 2>&1 && ls -al&submit=submit
```
6) Copy the text after echo and base64 decode it.
7) Flag: `CSCTF{sHark5_DO_N0t_HAv3_bOn35}`