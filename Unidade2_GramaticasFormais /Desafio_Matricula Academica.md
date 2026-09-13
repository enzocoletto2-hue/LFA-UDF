# Desafio: Matrícula Acadêmica

## 1. Regras da matrícula

O formato da matrícula acadêmica deve ser:

`CURSO-ANO-NÚMERO-TURNO`

Onde:

- **CURSO:** CCO, ESW ou SIS
- **ANO:** de 2024 a 2029
- **NÚMERO:** exatamente quatro algarismos
- **TURNO:** M, T ou N
- Os blocos devem ser separados por hífens.
- Não são permitidos caracteres extras antes ou depois da matrícula.

---

## 2. Regex

```regex
^(CCO|ESW|SIS)-(202[4-9])-[0-9]{4}-(M|T|N)$
