# Ticket generator
*** 
1000 points

Author@bilgee

## Description
Бид байгууллагынхнаа тасалбар худалддаг вэбсайтад 26 оронтой давтагдашгүй id бүхий тасалбаруудыг хэрэглэгчдэд олгодог ба 
энэ id-гаар захиалагчийн хувийн мэдээллийг харах эмзэг байдал илэрсэн ба үүнийг засах даалгаврыг шинээр орсон хөгжүүлэгчид
даалгасан юм. Түүний нэвтрүүлсэн тасалбар нууцлах шийдлийг сонирхооч ?

## Solve
Юун түрүүнд бидэнд crypto_sensei.py өгөгдсөн ба орж үзэхэд

``
from secret import tug
def encr(msg, x, y):
    msg2 = int.from_bytes(msg, byteorder='big')
    ct = pow(msg2, y, x)
    return ct

chosen = 65537
seat_token = 882564595536224140639625987659416029426239230804614613279163
encd = hex(encr(tug, seat_token, chosen))[2:]
with open('ct.txt','w') as f:
	f.write(encd)
print("your_ticket",encd)

#your_ticket='0x5dc3e1d09a42233cc160a1c5bba4100f2556b5ef933d20c5ca'
``
гэсэн python script байх ба ерөнхийдөө RSA гэдэг нь харагдана.

your_ticket гэдэг нь RSA -н C буюу Cipheredtext-тэй тэнцүү гэхдээ hex утгаар байсан болхоор int болгох хэрэгтэй.
``
hex_string = "0x5dc3e1d09a42233cc160a1c5bba4100f2556b5ef933d20c5ca "
decimal_number = int(hex_string, 16)
print(decimal_number)  #588573476244494326791251181810924652076731008274212604397002
``
Үүний дараа утгуудаа цуглуулах ба 
N = 882564595536224140639625987659416029426239230804614613279163
e = 65537
C = 588573476244494326791251181810924652076731008274212604397002 болно.

n тоогоо n = p*q гэсэн томьёоны дагуу factordb.com -р задлаж үзэхэд 
``
p = 857504083339712752489993810777
q = 1029224947942998075080348647219
``
Үүний дараа 
"phi = (P - 1) * (Q - 1)" томьёогоор phi-г олоод дараагаар нь d буюу private key-г олох ёстой 

``
import gmpy2
import binascii
<br>
N = 882564595536224140639625987659416029426239230804614613279163
E = 65537
C = 588573476244494326791251181810924652076731008274212604397002
P = 857504083339712752489993810777
Q = 1029224947942998075080348647219
<br>

#Calculate the private exponent D
phi = (P - 1) * (Q - 1)
D = gmpy2.invert(E, phi)

#Decrypt the ciphertext
M = pow(C, D, N)

#Convert the plaintext to bytes
plaintext_hex = hex(M)
plaintext_bytes = bytes.fromhex(plaintext_hex[2:])  # Remove '0x' prefix

print("Decrypted Plaintext:", plaintext_bytes.decode('utf-8'))

``
Script-н үр дүнд da59ec40ce31b9c46ef2a8ff5 гэсэн утга гарах ба 
<br>
Flag нь ``MUSTCTF{da59ec40ce31b9c46ef2a8ff5}``





