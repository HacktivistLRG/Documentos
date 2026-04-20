# Día

### Horas del amanecer

| №    | Horario impar | Nombre en español    | Horario par | Nombre en español  | Valor |
|------|---------------|----------------------|-------------|--------------------|-------|
| 1ª   | 05:00:00      | Primera hora impar   | 06:00:00    | Primera hora par   | −6    |
| 2ª   | 07:00:00      | Segunda hora impar   | 08:00:00    | Segunda hora par   | −5    |
| 3ª   | 09:00:00      | Tercera hora impar   | 10:00:00    | Tercera hora par   | −4    |
| 4ª   | 11:00:00      | Cuarta hora impar    | 12:00:00    | Cuarta hora par    | −3    |
| 5ª   | 13:00:00      | Quinta hora impar    | 14:00:00    | Quinta hora par    | −2    |
| 6ª   | 15:00:00      | Sexta hora impar     | 16:00:00    | Sexta hora par     | −1    |

### Horas del anochecer

| №    | Horario impar | Nombre en español    | Horario par | Nombre en español  | Valor |
|------|---------------|----------------------|-------------|--------------------|-------|
| 7ª   | 17:00:00      | Séptima hora impar   | 18:00:00    | Séptima hora par   | ∓0    |
| 8ª   | 19:00:00      | Octava hora impar    | 20:00:00    | Octava hora par    | +1    |
| 9ª   | 21:00:00      | Novena hora impar    | 22:00:00    | Novena hora par    | +2    |
| 10ª  | 23:00:00      | Décima hora impar    | 00:00:00    | Décima hora par    | +3    |
| 11ª  | 01:00:00      | Undécima hora impar  | 02:00:00    | Undécima hora par  | +4    |
| 12ª  | 03:00:00      | Duodécima hora impar | 04:00:00    | Duodécima hora par | +5    |


**codigo fuente:**

```py
# =========================
# CONFIGURACIÓN
# =========================

def es_impar(h):
    return h % 2 != 0

# anchos de columnas (UNA SOLA FUENTE DE VERDAD)
W_NUM = 4
W_HORA = 13
W_NOMBRE = 20
W_HORA_PAR = 11
W_NOMBRE_PAR = 18
W_VALOR = 5

# =========================
# GENERADORES DE CABECERA
# =========================

def header():
    return (
        f"| {'№':{W_NUM}} | "
        f"{'Horario impar':{W_HORA}} | "
        f"{'Nombre en español':{W_NOMBRE}} | "
        f"{'Horario par':{W_HORA_PAR}} | "
        f"{'Nombre en español':{W_NOMBRE_PAR}} | "
        f"{'Valor':{W_VALOR}} |"
    )

def separator():
    return (
        f"|{'-'*(W_NUM+2)}"
        f"|{'-'*(W_HORA+2)}"
        f"|{'-'*(W_NOMBRE+2)}"
        f"|{'-'*(W_HORA_PAR+2)}"
        f"|{'-'*(W_NOMBRE_PAR+2)}"
        f"|{'-'*(W_VALOR+2)}|"
    )

# =========================
# DATOS
# =========================

day_hours = [5,6,7,8,9,10,11,12,13,14,15,16]
night_hours = [17,18,19,20,21,22,23,0,1,2,3,4]

nombres_amanecer = ["Primera","Segunda","Tercera","Cuarta","Quinta","Sexta"]
valores_amanecer = ["−6","−5","−4","−3","−2","−1"]

nombres_anochecer = ["Séptima","Octava","Novena","Décima","Undécima","Duodécima"]
valores_anochecer = ["∓0","+1","+2","+3","+4","+5"]

# =========================
# CLASIFICACIÓN
# =========================

def clasificar(horas):
    impares, pares = [], []
    for h in horas:
        if es_impar(h):
            impares.append(f"{h:02d}:00:00")
        else:
            pares.append(f"{h:02d}:00:00")
    return impares, pares

odd_dawn, even_dawn = clasificar(day_hours)
odd_nights, even_nights = clasificar(night_hours)

# =========================
# FILA
# =========================

def fila(num, h_impar, nombre, h_par, valor):
    return (
        f"| {num:{W_NUM}} | "
        f"{h_impar:{W_HORA}} | "
        f"{nombre + ' hora impar':{W_NOMBRE}} | "
        f"{h_par:{W_HORA_PAR}} | "
        f"{nombre + ' hora par':{W_NOMBRE_PAR}} | "
        f"{valor:{W_VALOR}} |"
    )

# =========================
# IMPRESIÓN
# =========================

def imprimir_tabla(titulo, impares, pares, nombres, valores, inicio):
    print(f"\n### {titulo}\n")
    print(header())
    print(separator())
    
    for i in range(6):
        num = f"{inicio + i}ª"
        print(fila(num, impares[i], nombres[i], pares[i], valores[i]))

# =========================
# EJECUCIÓN
# =========================

print("# Día")

imprimir_tabla(
    "Horas del amanecer",
    odd_dawn, even_dawn,
    nombres_amanecer, valores_amanecer,
    1
)

imprimir_tabla(
    "Horas del anochecer",
    odd_nights, even_nights,
    nombres_anochecer, valores_anochecer,
    7
)
```
