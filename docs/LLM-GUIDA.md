# Guida LLM — ci-prova-runner-pub

Stato: audit documenti (ramo docs/audit-g7-2026-11). Base: origin/main.

## Scopo
Repo di prova per un workflow GitHub Actions minimo: job `prova` su `ubuntu-latest` che esegue `echo "runner assegnato" && uname -a` al push o al workflow_dispatch.

## Mappa dei file
- `.github/workflows/prova.yml` — workflow `prova`, trigger `push` e `workflow_dispatch`, `permissions: contents: read`, job `prova` su `ubuntu-latest`, un solo step senza checkout.
- `docs/LLM-GUIDA.md` — questa guida.
- `docs/_inventario.tsv` — solo intestazione `documento righe ultimo_commit` (0 righe dati).
- `docs/_revisione.tsv` — solo intestazione `file classe affermazione atteso trovato esito` (0 righe dati).
- `docs/_guida-lista.txt` — solo intestazione (0 righe dati).
- `README.md` — scopo, requisiti, installazione, uso, struttura.

## Entry point
Nessun codice eseguibile: l'unico entry point è il workflow `.github/workflows/prova.yml`. Non esiste package.json, Makefile, test o build.

## Comandi di test/avvio
Nessun test nel repo. Avvio manuale del workflow: `gh workflow run prova`. Verifica automatica: nessuna.

## Convenzioni
- Permesso minimo: `contents: read`.
- Nessun checkout step (il workflow non usa codice nel repo).

## Punti delicati
- Workflow senza checkout: non fa `actions/checkout`, non dipende dal contenuto del repo.
- Le tabelle `docs/_*.tsv` sono in intestazione vuota: non vanno trattate come dati reali.

## Cosa non toccare
- Codice/workflow (non è nel perimetro di questo audit).
- File fuori dal perimetro: solo README.md, docs/**, CLAUDE.md, AGENTS.md, .env.example.
