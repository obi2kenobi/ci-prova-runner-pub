# CLAUDE.md — ci-prova-runner-pub

Repo di prova: workflow GitHub Actions minimo. Nessun codice applicativo.

## Scopo
Workflow `prova` su `ubuntu-latest`: al push e al workflow_dispatch stampa `runner assegnato` e `uname -a`. Permessi `contents: read`.

## Struttura
- `.github/workflows/prova.yml` — workflow unico.
- `README.md` — scopo, requisiti, installazione, uso, struttura.
- `docs/LLM-GUIDA.md` — guida LLM (scopo, mappa, comandi, punti delicati).
- `docs/_inventario.tsv`, `docs/_revisione.tsv`, `docs/_guida-lista.txt` — tabelle di lavoro.

## Comandi
- Avvio/test: nessun test locale. Solo: `gh workflow run prova` (manuale, fuori perimetro se non autorizzato).
- Nessun build, nessun package.json, nessun Makefile.
- Comandi non verificati: niente da eseguire in locale che produca output atteso.

## Convenzioni
- Permessi minimi: `contents: read`.
- Workflow senza checkout, senza dipendenze.
- Solo file ammessi: CLAUDE.md, README.md, AGENTS.md, .env.example, docs/**. Mai codice.

## Cosa non toccare
- `.github/workflows/prova.yml` e tutto il codice/workflow (fuori perimetro).
- Niente secrets nel repo: nessun file con valori reali; usare solo segnaposto in `.env.example`.

## Rimandi
Guida estesa: `docs/LLM-GUIDA.md`.
