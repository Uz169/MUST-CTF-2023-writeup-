# Password manager
*** 
500 points

Author@tush1g 

## Description
Are Password Managers Safe to Use in 2023?
/critical_secrets

## Solve
Эхлээд file critical_secrets хийж үзэхэд
<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/password%20manager/step1.png">
</p>
Keepass password database болохыг нь таних ба Database-г үзэхэд шаардах түлхүүрийг crack-даж авах шаардлагатай үүний тулд : 
<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/password%20manager/step2.png">
</p>
коммандыг хийх ба Keepasshash.txt file -г доорх коммандаар rockyou.txt ээр bruteforce хийж олно.
<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/password%20manager/step2a.png">
</p>
Урт удаан хугацааны дараа master key нь ``sunflower`` гэж олдоно.
Олсон master keyee ашиглан KeePass-д нэвтрэхэд
<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/password%20manager/step3.png">
</p>
сошиал хаягууд харагдах ба
<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/password%20manager/step4.png">
</p>
Youtube-н password хэсэгээс flag олдоно.
<p align="center">
  <img src="https://github.com/Uz169/MUST-CTF-2023-writeup-/blob/main/Round%201%20/Cryptography/password%20manager/step5.png">
</p>

Flag нь ```MUSTCTF{3v3ry_PM_n0t_s4fe}```


