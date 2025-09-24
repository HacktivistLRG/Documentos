# Sistema Unificado de Magnitudes

**Algoritmo:**

```py

def rightGroupBlocks(s: str, size: int = 3):
    """Agrupa una cadena en bloques de tamaño 'size' desde la derecha."""
    return [s[max(i - size, 0) : i] for i in range(len(s), 0, -size)][::-1]


def fromIntegerToString(n: int, first_sep: str = ".", rest_sep: str = ",") -> str:
    """
    Formatea un entero insertando separadores de miles.
    - first_sep: separador para el primer grupo (más a la izquierda)
    - rest_sep: separador para los demás grupos (si hay más de uno)
    """
    s = str(n)
    groups = rightGroupBlocks(s, 3)
    if len(groups) <= 1:
        return s
    return groups[0] + first_sep + rest_sep.join(groups[1:])


def fromFloatToString(dec_str: str, group_sep: str = ",") -> str:
    """Agrupa los dígitos decimales en bloques de 3 usando el separador especificado."""
    groups = rightGroupBlocks(dec_str, 3)
    return group_sep.join(groups)


def calculatePowerOfTen(e: int, first_sep=".", rest_sep=",") -> str:
    """Devuelve 10^e formateado con separadores de miles personalizados."""
    if e < 0:
        return None
    return fromIntegerToString(10**e, first_sep=first_sep, rest_sep=rest_sep)


def calculateSubpowerOfTen(e: int, int_sep=".", frac_group_sep=",") -> str:
    """Devuelve 1/10^e formateado con agrupación de decimales personalizada."""
    if e < 1:
        return None
    numero_str = f"{1 / 10**e:.{e}f}"
    parte_entera, parte_decimal = numero_str.split(".")
    parte_decimal_formateada = fromFloatToString(
        parte_decimal, group_sep=frac_group_sep
    )
    return parte_entera + int_sep + parte_decimal_formateada


def getDataTable(header, rows, columns):
    """Genera una tabla Markdown a partir de filas y columnas definidas."""
    th = "| " + " | ".join(f"{col:<{width}}" for col, width in columns) + " |"
    tr = "|" + "|".join("-" * (width + 2) for _, width in columns) + "|"
    print(header)
    print(th)
    print(tr)
    for row in rows:
        td = (
            "| "
            + " | ".join(f"{str(row[key]):<{width}}" for key, width in columns)
            + " |"
        )
        print(td)


# --- TABLAS ---
h1 = "# Sistema Unificado de Magnitudes\n"

short_scale = [
    {
        "Año": 1795,
        "Potencia": "$10^{1}$",
        "Símbolo": "`da`",
        "Prefijo": "deca",
        "Nombre": "Diez",
        "Cantidad entera": calculatePowerOfTen(1),
    },
    {
        "Año": 1795,
        "Potencia": "$10^{2}$",
        "Símbolo": "`h`",
        "Prefijo": "hecto",
        "Nombre": "Cien",
        "Cantidad entera": calculatePowerOfTen(2),
    },
    {
        "Año": 1795,
        "Potencia": "$10^{3}$",
        "Símbolo": "`k`",
        "Prefijo": "kilo",
        "Nombre": "Mil",
        "Cantidad entera": calculatePowerOfTen(3),
    },
    {
        "Año": 1960,
        "Potencia": "$10^{6}$",
        "Símbolo": "`M`",
        "Prefijo": "mega",
        "Nombre": "Millón",
        "Cantidad entera": calculatePowerOfTen(6),
    },
    {
        "Año": 1960,
        "Potencia": "$10^{12}$",
        "Símbolo": "`G`",
        "Prefijo": "giga",
        "Nombre": "Billón",
        "Cantidad entera": calculatePowerOfTen(12),
    },
    {
        "Año": 1960,
        "Potencia": "$10^{18}$",
        "Símbolo": "`T`",
        "Prefijo": "tera",
        "Nombre": "Trillón",
        "Cantidad entera": calculatePowerOfTen(18),
    },
    {
        "Año": 1975,
        "Potencia": "$10^{24}$",
        "Símbolo": "`P`",
        "Prefijo": "peta",
        "Nombre": "Cuatrillón",
        "Cantidad entera": calculatePowerOfTen(24),
    },
    {
        "Año": 2022,
        "Potencia": "$10^{30}$",
        "Símbolo": "`Q`",
        "Prefijo": "quetta",
        "Nombre": "Quintillón",
        "Cantidad entera": calculatePowerOfTen(30),
    },
    {
        "Año": 1975,
        "Potencia": "$10^{36}$",
        "Símbolo": "`E`",
        "Prefijo": "exa",
        "Nombre": "Sextillón",
        "Cantidad entera": calculatePowerOfTen(36),
    },
    {
        "Año": 1991,
        "Potencia": "$10^{42}$",
        "Símbolo": "`Z`",
        "Prefijo": "zetta",
        "Nombre": "Septillón",
        "Cantidad entera": calculatePowerOfTen(42),
    },
    {
        "Año": 1991,
        "Potencia": "$10^{48}$",
        "Símbolo": "`Y`",
        "Prefijo": "yotta",
        "Nombre": "Octillón",
        "Cantidad entera": calculatePowerOfTen(48),
    },
    {
        "Año": 2022,
        "Potencia": "$10^{54}$",
        "Símbolo": "`R`",
        "Prefijo": "ronna",
        "Nombre": "Nonillón",
        "Cantidad entera": calculatePowerOfTen(54),
    },
]

long_scale = [
    {
        "Año": 1795,
        "Fracción": "$\\frac{1}{10^{1}}$",
        "Símbolo": "`d`",
        "Prefijo": "deci",
        "Nombre": "Décimo",
        "Cantidad flotante": calculateSubpowerOfTen(1),
    },
    {
        "Año": 1795,
        "Fracción": "$\\frac{1}{10^{2}}$",
        "Símbolo": "`c`",
        "Prefijo": "centi",
        "Nombre": "Centésimo",
        "Cantidad flotante": calculateSubpowerOfTen(2),
    },
    {
        "Año": 1795,
        "Fracción": "$\\frac{1}{10^{3}}$",
        "Símbolo": "`m`",
        "Prefijo": "mili",
        "Nombre": "Milésimo",
        "Cantidad flotante": calculateSubpowerOfTen(3),
    },
    {
        "Año": 1960,
        "Fracción": "$\\frac{1}{10^{6}}$",
        "Símbolo": "`µ`",
        "Prefijo": "micro",
        "Nombre": "Millonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(6),
    },
    {
        "Año": 1960,
        "Fracción": "$\\frac{1}{10^{12}}$",
        "Símbolo": "`n`",
        "Prefijo": "nano",
        "Nombre": "Billonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(12),
    },
    {
        "Año": 1960,
        "Fracción": "$\\frac{1}{10^{18}}$",
        "Símbolo": "`p`",
        "Prefijo": "pico",
        "Nombre": "Trillonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(18),
    },
    {
        "Año": 1964,
        "Fracción": "$\\frac{1}{10^{24}}$",
        "Símbolo": "`f`",
        "Prefijo": "femto",
        "Nombre": "Cuatrillonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(24),
    },
    {
        "Año": 2022,
        "Fracción": "$\\frac{1}{10^{30}}$",
        "Símbolo": "`q`",
        "Prefijo": "quecto",
        "Nombre": "Quintillonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(30),
    },
    {
        "Año": 1964,
        "Fracción": "$\\frac{1}{10^{36}}$",
        "Símbolo": "`a`",
        "Prefijo": "atto",
        "Nombre": "Sextillonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(36),
    },
    {
        "Año": 1991,
        "Fracción": "$\\frac{1}{10^{42}}$",
        "Símbolo": "`z`",
        "Prefijo": "zepto",
        "Nombre": "Septillonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(42),
    },
    {
        "Año": 1991,
        "Fracción": "$\\frac{1}{10^{48}}$",
        "Símbolo": "`y`",
        "Prefijo": "yocto",
        "Nombre": "Octillonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(48),
    },
    {
        "Año": 2022,
        "Fracción": "$\\frac{1}{10^{54}}$",
        "Símbolo": "`r`",
        "Prefijo": "ronto",
        "Nombre": "Nonillonésimo",
        "Cantidad flotante": calculateSubpowerOfTen(54),
    },
]

print(h1)

print("### Escala corta\n")
getDataTable(
    "",
    short_scale,
    columns=[
        ("Año", 4),
        ("Potencia", 10),
        ("Símbolo", 7),
        ("Prefijo", 7),
        ("Nombre", 12),
        ("Cantidad entera", 74),
    ],
)

print("\n### Escala larga\n")
getDataTable(
    "",
    long_scale,
    columns=[
        ("Año", 4),
        ("Fracción", 20),
        ("Símbolo", 7),
        ("Prefijo", 7),
        ("Nombre", 16),
        ("Cantidad flotante", 74),
    ],
)

```


### Escala corta


| Año  | Potencia   | Símbolo | Prefijo | Nombre       | Cantidad entera                                                            |
|------|------------|---------|---------|--------------|----------------------------------------------------------------------------|
| 1795 | $10^{1}$   | `da`    | deca    | Diez         | 10                                                                         |
| 1795 | $10^{2}$   | `h`     | hecto   | Cien         | 100                                                                        |
| 1795 | $10^{3}$   | `k`     | kilo    | Mil          | 1.000                                                                      |
| 1960 | $10^{6}$   | `M`     | mega    | Millón       | 1.000,000                                                                  |
| 1960 | $10^{12}$  | `G`     | giga    | Billón       | 1.000,000,000,000                                                          |
| 1960 | $10^{18}$  | `T`     | tera    | Trillón      | 1.000,000,000,000,000,000                                                  |
| 1975 | $10^{24}$  | `P`     | peta    | Cuatrillón   | 1.000,000,000,000,000,000,000,000                                          |
| 2022 | $10^{30}$  | `Q`     | quetta  | Quintillón   | 1.000,000,000,000,000,000,000,000,000,000                                  |
| 1975 | $10^{36}$  | `E`     | exa     | Sextillón    | 1.000,000,000,000,000,000,000,000,000,000,000,000                          |
| 1991 | $10^{42}$  | `Z`     | zetta   | Septillón    | 1.000,000,000,000,000,000,000,000,000,000,000,000,000,000                  |
| 1991 | $10^{48}$  | `Y`     | yotta   | Octillón     | 1.000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000          |
| 2022 | $10^{54}$  | `R`     | ronna   | Nonillón     | 1.000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000  |

### Escala larga


| Año  | Fracción             | Símbolo | Prefijo | Nombre           | Cantidad flotante                                                          |
|------|----------------------|---------|---------|------------------|----------------------------------------------------------------------------|
| 1795 | $\frac{1}{10^{1}}$   | `d`     | deci    | Décimo           | 0.1                                                                        |
| 1795 | $\frac{1}{10^{2}}$   | `c`     | centi   | Centésimo        | 0.01                                                                       |
| 1795 | $\frac{1}{10^{3}}$   | `m`     | mili    | Milésimo         | 0.001                                                                      |
| 1960 | $\frac{1}{10^{6}}$   | `µ`     | micro   | Millonésimo      | 0.000,001                                                                  |
| 1960 | $\frac{1}{10^{12}}$  | `n`     | nano    | Billonésimo      | 0.000,000,000,001                                                          |
| 1960 | $\frac{1}{10^{18}}$  | `p`     | pico    | Trillonésimo     | 0.000,000,000,000,000,001                                                  |
| 1964 | $\frac{1}{10^{24}}$  | `f`     | femto   | Cuatrillonésimo  | 0.000,000,000,000,000,000,000,001                                          |
| 2022 | $\frac{1}{10^{30}}$  | `q`     | quecto  | Quintillonésimo  | 0.000,000,000,000,000,000,000,000,000,001                                  |
| 1964 | $\frac{1}{10^{36}}$  | `a`     | atto    | Sextillonésimo   | 0.000,000,000,000,000,000,000,000,000,000,000,001                          |
| 1991 | $\frac{1}{10^{42}}$  | `z`     | zepto   | Septillonésimo   | 0.000,000,000,000,000,000,000,000,000,000,000,000,000,001                  |
| 1991 | $\frac{1}{10^{48}}$  | `y`     | yocto   | Octillonésimo    | 0.000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,001          |
| 2022 | $\frac{1}{10^{54}}$  | `r`     | ronto   | Nonillonésimo    | 0.000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,001  |
