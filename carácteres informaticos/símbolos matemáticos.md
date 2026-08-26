### Símbolos matemáticos

| Número decimal | Codigo binario | Carácter literal | Tipo dato | Nombre en inglés        |
|----------------|----------------|------------------|-----------|-------------------------|
| 43             | 101011         | +                | Sm        | PLUS SIGN               |
| 60             | 111100         | <                | Sm        | LESS-THAN SIGN          |
| 61             | 111101         | =                | Sm        | EQUALS SIGN             |
| 62             | 111110         | >                | Sm        | GREATER-THAN SIGN       |
| 124            | 1111100        | \|               | Sm        | VERTICAL LINE           |
| 126            | 1111110        | ~                | Sm        | TILDE                   |
| 172            | 10101100       | ¬                | Sm        | NOT SIGN                |
| 177            | 10110001       | ±                | Sm        | PLUS-MINUS SIGN         |
| 215            | 11010111       | ×                | Sm        | MULTIPLICATION SIGN     |
| 247            | 11110111       | ÷                | Sm        | DIVISION SIGN           |


**codigo fuente:**

```py
from unicodedata import category
from unicodedata import name

h3 = "### Símbolos matemáticos\n"
th = f"| {'Número decimal':14} |"
th += f" {'Codigo binario':14} |"
th += f" {'Carácter literal':16} |"
th += f" {'Tipo dato':9} |"
th += f" {'Nombre en inglés':23} |"
tr = f"|{'-' * 16}|"
tr += f"{'-' * 16}|"
tr += f"{'-' * 18}|"
tr += f"{'-' * 11}|"
tr += f"{'-' * 25}|"
print(h3)
print(th)
print(tr)


for n in range(256):
    dec_num = n
    cod_bnr = bin(n)[2:]
    car_lit = chr(n)
    tip_dat = category(car_lit)
    try:
        eng_nom = name(car_lit)
    except ValueError:
        eng_nom = "UNNAMED"
        
    if dec_num == 124:
        car_lit = car_lit.replace("|", "\\|")

    if tip_dat == "Sm":
        td = f"| {dec_num:<14} |"
        td += f" {cod_bnr:14} |"
        td += f" {car_lit:16} |"
        td += f" {tip_dat:9} |"
        td += f" {eng_nom:23} |"
        print(td)
```