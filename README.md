# CFTEC — Instaladores

Armazém de ficheiros de distribuição do software CFTEC / PalancaSoft
via **GitHub Releases**: até **2 GB por ficheiro** (asset), bandwidth
de download **grátis** e releases ilimitadas.

## Regras

| Regra | Valor |
|---|---|
| Cada lançamento | Nova **Release** com tag por software (`palanca-gestao-v2.1.4`) |
| Máx. por ficheiro (asset) | **2 GB** |
| Nome do ficheiro | `NOME-VERSÃO.ext` (ex.: `palanca-gestao-2.1.4.exe`) |
| Comprovativo / trava no ficheiro? | NENHUM — o cliente baixa sem travas |
| Ligação à ficha do painel | URL do asset como `file_url` (modo externo) |

## Como publicar um instalador

1. Releases → **Draft a new release** → tag nova (ex.: `palanca-gestao-v2.1.5`)
2. Título: `PalancaSoft Gestão 2.1.5` · descrição: changelog curto
3. **Attach files**: arrasta o .zip / .exe (2 GB máx)
4. **Publish release** → copia o URL do asset (botão direito → Copy link)
5. No painel CFTEC → Software → ficha com esse URL

No servidor, o modo externoubsere: `POST /api/admin/software` com
`{ ..., file_url: "https://github.com/telsioisidoro786-crypton/cftec-instaladores/releases/download/.../ficheiro.exe" }`.

Os downloads do portal continuam a contar nos `download_events`
(a rota devolve o URL; o contador é independente de onde o ficheiro mora).
