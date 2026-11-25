# ci-prova-runner-pub

Repo di prova per un workflow GitHub Actions minimo: su ogni push (e su `workflow_dispatch`) esegue un job `prova` su `ubuntu-latest` che stampa `runner assegnato` e `uname -a`.

## Requisiti
- Repo con GitHub Actions abilitato.
- Nessuna dipendenza locale: non è presente codice, package.json, Makefile o test.

## Installazione
```bash
git clone <url-repo>
cd ci-prova-runner-pub
```
Nessun comando di installazione di dipendenze: il workflow non usa checkout né dipendenze.

## Uso
Il workflow `prova` (.github/workflows/prova.yml) si scatena automaticamente al push o manualmente:
```bash
gh workflow run prova
```
Output atteso nel log del job: riga `runner assegnato` seguita dall'output di `uname -a`.

## Struttura delle cartelle
- `.github/workflows/prova.yml` — workflow `prova` (trigger push + workflow_dispatch, permissions: contents: read).
- `docs/LLM-GUIDA.md` — guida per LLM (struttura, comandi, punti delicati).
- `docs/_inventario.tsv`, `docs/_revisione.tsv`, `docs/_guida-lista.txt` — tabelle di lavoro (inventario 2 righe dati, revisione 6 righe dati, lista 2 righe).
