# BUG-G4 — bug corretti

## BUG-1
Dove: docs/_inventario.tsv:3
Gravità: bassa (dato incoerente)
Prova: `wc -l docs/LLM-GUIDA.md` → 33; inventario affermava 32
Correzione: commit 6f05f3f — inventario aggiornato a 33
Test: `wc -l docs/LLM-GUIDA.md` → 33; riga inventario: `docs/LLM-GUIDA.md\t33\t2026-11-24`

## BUG-2
Dove: docs/LLM-GUIDA.md:12 e docs/_revisione.tsv:6
Gravità: bassa (stessa incoerenza riprodotta)
Prova: `wc -l docs/LLM-GUIDA.md` → 33; guida e revisione citavano 32
Correzione: commit 84a87ed — guida e revisione aggiornati a 33
Test: `grep -n "33" docs/LLM-GUIDA.md docs/_revisione.tsv` conferma; `wc -l` → 33

CANDIDATO-3: docs/_guida-lista.txt:1-2 — lista incompleta (non include CLAUDE.md né .github/workflows/prova.yml). Fuori perimetro di questo mandato; non corretto.
