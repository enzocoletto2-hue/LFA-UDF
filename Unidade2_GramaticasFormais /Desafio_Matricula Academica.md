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


## 2. Regex

**R:** `^(CCO|ESW|SIS)-202[4-9]-[0-9]{4}-(M|T|N)$`


## 3. Justificativa da Regex

```regex
^(CCO|ESW|SIS)-202[4-9]-[0-9]{4}-(M|T|N)$
```

- `^` e `$` → garantem que não existam caracteres extras antes ou depois.
- `(CCO|ESW|SIS)` → permite os cursos CCO, ESW ou SIS.
- `-` → representa os hífens obrigatórios.
- `202[4-9]` → permite os anos de 2024 até 2029.
- `[0-9]{4}` → exige exatamente quatro algarismos.
- `(M|T|N)` → permite os turnos M, T ou N.

## 4. Tabela de testes

| Entrada | Resultado |
|---|---|
| `CCO-2024-1234-M` | Válido |
| `ESW-2025-5678-T` | Válido |
| `SIS-2029-0001-N` | Válido |
| `CCO-2026-9999-M` | Válido |
| `CCO-2023-1234-M` | Inválido |
| `CCO-2030-1234-M` | Inválido |
| `ABC-2025-1234-M` | Inválido |
| `CCO-2025-123-M` | Inválido |
| `CCO-2025-12345-M` | Inválido |
| `CCO-2025-1234-X` | Inválido |
| `CCO2025-1234-M` | Inválido |
| `CCO-2025-1234-MM` | Inválido |

## 5. Casos de fronteira

- `CCO-2024-1234-M` → Válido, menor ano permitido.
- `CCO-2029-1234-M` → Válido, maior ano permitido.
- `CCO-2023-1234-M` → Inválido, ano abaixo do limite.
- `CCO-2030-1234-M` → Inválido, ano acima do limite.
- `CCO-2025-0000-M` → Válido, menor número possível.
- `CCO-2025-9999-M` → Válido, maior número possível.

## 6. Entradas quase corretas

- `CCO-2025-123-M` → Inválido, faltou um algarismo.
- `CCO-2025-12345-M` → Inválido, possui um algarismo a mais.
- `CCO-2030-1234-M` → Inválido, ano fora do permitido.
- `ABC-2025-1234-M` → Inválido, curso não permitido.
- `CCO-2025-1234-X` → Inválido, turno não permitido.
- `CCO2025-1234-M` → Inválido, falta um hífen.

## 7. Atividade no Regex Learn

A Regex foi construída a partir das regras da atividade e testada com exemplos válidos, inválidos, casos de fronteira e entradas quase corretas.

Regex utilizada:

```regex
^(CCO|ESW|SIS)-202[4-9]-[0-9]{4}-(M|T|N)$
```

Os testes confirmaram que a expressão segue as regras propostas.

## 8. Conclusão

A Regex criada atende às regras da matrícula acadêmica, permitindo os cursos, anos, números e turnos especificados e impedindo caracteres extras.
