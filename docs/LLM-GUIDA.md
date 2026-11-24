# Guida LLM — ci-prova-runner-pub

Stato: R4 (passi 6 e 9). Base: 0c4600e1e743232fbfaf79e4e6ecc501305709f0, ramo op/M-011-1.

## Struttura reale
- `.github/workflows/prova.yml` — workflow `prova`, trigger push e workflow_dispatch, permissions contents: read, job `prova` su ubuntu-latest che esegue `echo "runner assegnato" && uname -a`.
- `docs/_guida-lista.txt` — intestazione vuota (solo intestazione, 0 righe dati).
- `docs/_inventario.tsv` — solo intestazione `documento righe ultimo_commit`, 0 righe dati.
- `docs/_revisione.tsv` — solo intestazione `file classe affermazione atteso trovato esito`, 0 righe dati.
- Non esiste `docs/archivio/` (verificato: ls docs/archivio → nessun output / assente).

## Comandi eseguiti e esito
- `git status` → albero pulito, branch op/M-011-1 (VERDE).
- `git log --oneline -3` → 8fb035b docs: revisione documenti guida; 770b45e docs: inventario e selezione guide; 0c4600e prova runner (VERDE).
- `ls docs/` → _guida-lista.txt, _inventario.tsv, _revisione.tsv (VERDE).
- `ls docs/archivio/` → assente (non verificato come presente).
- Nessun comando di build/test eseguito: nessun test nel repo (nessun package.json/Makefile).

## Documenti superati
Nessun documento in `docs/archivio/` da elencare (directory assente).

## Note
- Workflow non esplorato altrove; usa `ubuntu-latest` e non ha step di checkout.
- Comandi di verifica non eseguiti oltre a quelli sopra: evitare affermazioni non verificate.
