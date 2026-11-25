# BUG-G4 — candidati bug

CANDIDATO-1: docs/_inventario.tsv:3 — line count sbagliato: afferma docs/LLM-GUIDA.md = 32 righe, wc -l = 33. Dati incoerenti con il file reale.
CANDIDATO-2: docs/LLM-GUIDA.md:12 — stesso errore: "docs/LLM-GUIDA.md 32 righe" (riga 12) e riga 6 di _revisione.tsv ("wc -l: 26 e 32", esito OK) — guida e revisione riproducono il numero sbagliato anziché 33.
CANDIDATO-3: docs/_guida-lista.txt:1-2 — lista incompleta: non include CLAUDE.md né .github/workflows/prova.yml, file principali del repo (CLAUDE.md è citato solo in strutture, non in lista).
