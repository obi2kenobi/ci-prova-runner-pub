# Guida LLM — ci-prova-runner-pub

Stato: guida revisata (ramo docs/g7-giro2-2026-11). Base: origin/main.

## Scopo
Repo di prova per un workflow GitHub Actions minimo: job `prova` su `ubuntu-latest` che esegue `echo "runner assegnato" && uname -a` al push o al workflow_dispatch.

## Mappa dei file
- `.github/workflows/prova.yml` — workflow `prova`, trigger `push` e `workflow_dispatch`, `permissions: contents: read`, job `prova` su `ubuntu-latest`, un solo step senza checkout.
- `README.md` — scopo, requisiti, installazione, uso, struttura (26 righe).
- `docs/LLM-GUIDA.md` — questa guida.
- `docs/_inventario.tsv` — intestazione + 2 righe dati (README.md 26 righe, docs/LLM-GUIDA.md 32 righe).
- `docs/_revisione.tsv` — intestazione + 6 righe dati (esito OK tranne una DA CORREGGERE).
- `docs/_guida-lista.txt` — 2 righe: README.md, docs/LLM-GUIDA.md.

## Entry point
Nessun codice eseguibile: l'unico entry point è il workflow `.github/workflows/prova.yml`. Non esiste package.json, Makefile, test o build.

## Comandi di test/avvio
Nessun test nel repo. Avvio manuale del workflow: `gh workflow run prova`. Verifica automatica: nessuna.

## Convenzioni
- Permesso minimo: `contents: read`.
- Nessun checkout step.
- Solo file ammessi: README.md, CLAUDE.md, AGENTS.md, .env.example, docs/**. Mai codice.

## Punti delicati
- Workflow senza checkout: non fa `actions/checkout`, non dipende dal contenuto del repo.
- Le tabelle `docs/_*.tsv` contengono dati reali (inventario: 2 righe; revisione: 6 righe). Non sono intestazioni vuote.

## Cosa non toccare
- Codice/workflow (fuori perimetro).
- Niente segreti: solo segnaposto.
