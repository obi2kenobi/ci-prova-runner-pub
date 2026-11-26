---
repo: ci-prova-runner-pub
linguaggi: GitHub Actions (YAML)
stato: documentazione attiva
aggiornato: 2026-11-26
---

# Scheda tecnica — ci-prova-runner-pub

## Scopo
Repo di prova per un workflow GitHub Actions minimo: job `prova` su `ubuntu-latest` che stampa `runner assegnato` e `uname -a` al push o al `workflow_dispatch`. Nessun codice applicativo.

## Architettura
Workflow unico `.github/workflows/prova.yml`, trigger `push` e `workflow_dispatch`, `permissions: contents: read`, un solo job `prova` con un solo step senza checkout né dipendenze. Documentazione solo in `docs/` e file root.

## Componenti
| Nome | Ruolo | File |
|------|-------|------|
| prova (workflow) | Trigger e job unico | .github/workflows/prova.yml |
| README | Scopo, requisiti, uso, struttura | README.md |
| LLM-GUIDA | Guida per LLM | docs/LLM-GUIDA.md |
| ISTRUZIONI | Istruzioni d'uso | docs/ISTRUZIONI.md |
| Inventario/revisione/lista | Tabelle di lavoro | docs/_inventario.tsv, docs/_revisione.tsv, docs/_guida-lista.txt |

## Dati e interfacce
Nessun dato persistente, nessuna API, nessun input utente. Output: log del job GitHub Actions (`runner assegnato` + `uname -a`). Interfaccia: nessuna.

## Dipendenze
Nessuna dipendenza locale. GitHub Actions runner `ubuntu-latest`; `gh` CLI per avvio/verifica manuale (non verificato in locale).

## Configurazione
Nessuna variabile d'ambiente. Permessi minimi `contents: read`. Niente secrets.

## Build e test
Nessun build, nessun test locale. Verifica manuale: `gh workflow run prova` e `gh run list --workflow=prova` (non verificato in locale).

## Deploy
Non applicabile: nessun artifact, nessun deploy.

## Rischi e debito tecnico
- Workflow senza checkout: non dipende dal contenuto del repo.
- Comandi `gh` richiedono autenticazione (non verificata qui).
- Tabelle `docs/_*.tsv` contengono dati reali di lavoro; non sono intestazioni vuote.
