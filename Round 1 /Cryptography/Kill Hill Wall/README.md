# Kill Hill Wall
*** 
1000 points

Author@T6X9G

## Description
  In order to obtain the Key of the House, it was necessary to climb a high Hill
<a href="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/Kill%20Hill%20Wall/pics/cipher.txt">cipher.txt</a>
<a href="[mountain.jpeg](https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/Kill%20Hill%20Wall/pics/mountain.jpeg)">mountain.jpeg</a>

## Solve
Cipher.txt ээ нээгээд харвал
``
cipher: BIAMUWEKHABKFWAHSDTJQXGZCSWYRSJS_SXEO_X
a = 0

``
гэсэн утга байх ба уг challenge -н нэрнээс Hill Cipher гэдэг нь танигдана.

Bruteforce хийн тайлах оролдлого хийхэд амжилт олоогүй учир хамт байсан mountain.jpeg файлыг шинжилж үзэхэд

<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/Kill%20Hill%20Wall/pics/hilla.png">
</p>
Comment маягаар доорх утгыг агуулсан байсан

``MTEgMzQgMTUgMjEgMzIgMjMgNDMgMjggMjE=``
ба base64-өөс задлаж үзэхэд 

`` 11 34 15 21 32 23 43 28 21 ``

гэсэн утга гарна нийт 9н тоо байгаа нь Hill cipher тайлахад 3x3 матрикс байна гэсэн үг.
Уг бодлогыг бодохдоо би хувьдаа dcode ашигласан тул доорх байдлаар хийсэн.
анх cipher дотор ``a = 0`` гэсэн байсан учир 
□ Alphabet (27 char. A=0) ABCDEFGHIJKLMNOPQRSTUVWXYZ_ 

-г сонгож доорх маягаар тайлна гэсэн үг.
<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/Kill%20Hill%20Wall/pics/hillb.png">
</p>

`` Flag : HILLCIPHERISINTERESTINGANDADVENTUROUS__ `` 
