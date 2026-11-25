---
repo: ci-prova-runner-pub
software:
  - prova (GitHub Actions workflow)
aggiornato: 2026-11-25
---

# Istruzioni d'uso — ci-prova-runner-pub

## prova

### Requisiti
- Repository con GitHub Actions abilitato.
- Trigger: push su qualsiasi ramo + `workflow_dispatch`.
- Nessuna dipendenza locale: nessun codice applicativo, package.json, Makefile o test.

### Installazione
Nessun passo di installazione: il workflow non usa checkout né dipendenze.
```bash
git clone <url-repo>
cd ci-prova-runner-pub
```

### Avvio
Automatico al push. Manuale:
```bash
gh workflow run prova
```

### Uso
Il job `prova` (runner `ubuntu-latest`) esegue un singolo step:
`echo "runner assegnato" && uname -a`.
Output atteso nel log del job: riga `runner assegnato` seguita dall'output di `uname -a`.

### Verifica
`gh run list --workflow=prova` e ispezione del log del job. Verifica locale non applicabile: nessun test locale.

### Problemi noti
- Nessun checkout step: il workflow non fa `actions/checkout` e non dipende dal contenuto del repo.
- Nessun segredo richiesto: permissions `contents: read`, nessun `env`/`secrets`.
- I comandi `gh` richiedono autenticazione `gh` (non verificato in locale qui).
