# Stinging
*** 
1000 points

Author@c!0

## Description
<a href="">misc.txt</a>

## Solve
Файл -г .txt болгон ороод MUSTCTF гэж хайхад random text дотор хуурамч flag ууд байсан тул эхлээд MUSTCTF{ } 
дотор байгаа бүх утгуудыг цуглуулсан ба.

``

import re
file_path = 'misc.txt'
pattern = re.compile(r'MUSTCTF{.*?}')
with open(file_path, 'r', encoding='utf-8') as file:
    content = file.read()
matches = re.findall(pattern, content)
for match in matches:
    print(match)
    
``
script -г гүйлгээд харахад ганц flag нь бусдаасаа урт байсан.

Flag : MUSTCTF{!h44hth4tsj4st4n0th3r5tr1ng5}
