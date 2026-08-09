# Guardrails Fiscal (`grf`)

Presidio fiscale e di finanza agevolata: requisiti, scadenze, spese ammissibili e rendicontazione, sempre con fonte primaria e data di verifica. Include un workflow di ricerca live sugli aggiornamenti fiscali, i bandi e gli incentivi.

Modulo BMad. È una porzione del bundle [Guardrails](https://github.com/mlarese/bmad-module-guardrails):
stesse figure, stesso comportamento, solo l'area fiscal.

> **Generato.** Questo repository è prodotto da `tools/build_modules.py` nel
> repository [bmad-module-guardrails](https://github.com/mlarese/bmad-module-guardrails).
> Le modifiche si fanno lì e poi si rigenera: qui vengono sovrascritte.

## Figure

| Figura | Ruolo | Skill | Cosa presidia |
| ------ | ----- | ----- | ------------- |
| 🧾 Marta | Fiscalista e Finanza Agevolata | `grl-agent-fiscal` | Ricerca fonti fiscali, contabili e di finanza agevolata italiane ed europee, verifica requisiti, scadenze, spese ammissibili e rendicontazione, e traduce tutto in un verdetto… |

## Skill e workflow

| Skill | Comando | Cosa fa |
| ----- | ------- | ------- |
| `grf-profile` | Profila il progetto | Raccoglie in pochi minuti gli otto campi che danno contesto a tutte e quattordici le figure, criticità inclusa. |
| `grf-profile` | Aggiorna il profilo | Riallinea il profilo quando il progetto cambia, e dice se il cambiamento invalida rischi già accettati. |
| `grf-board` | Convoca il collegio | Fa leggere lo stesso artefatto alle sole figure pertinenti e restituisce un riepilogo unico, conflitti compresi. |
| `grf-board` | Rischi già accettati | Mostra, raggruppato per figura, quello che il progetto ha consapevolmente scelto di accettare. |
| `grf-board` | Gate di rilascio | Verifica una release identificata e restituisce GO, GO_CON_CONDIZIONI, NO_GO o EVIDENZA_INSUFFICIENTE. |
| `grl-fiscal-updates` | Ultime novità fiscali | Recupera norme fiscali, circolari, bollettini, emendamenti, bandi e incentivi nel periodo indicato, con ricerca live, matrice di copertura, lineage di vigenza e due gate bmad-review. |
| `grl-automation` | Instrada un'automazione | Classifica lo scenario, sceglie agenti e workflow BMad e dichiara capability mancanti, scope e approvazioni. |
| `grl-automation` | Prepara un piano eseguibile | Costruisce passi idempotenti con input, output, precondizioni, rischio, approvazione e rollback. |
| `grl-automation` | Esegui controlli read-only | Raccoglie evidenze e confronti riproducibili senza modificare sistemi esterni. |
| `grl-automation` | Prepara un dry-run | Genera e valida diff o payload senza spendere, pubblicare o applicare side effect. |
| `grl-automation` | Esegui dopo approvazione | Applica solo lo scope approvato, registra prima/dopo e osserva il risultato; in caso di errore attiva il rollback. |
| `grl-automation` | Riprendi un'automazione | Riprende un run esistente dal primo passo non concluso senza duplicare scritture o side effect. |

## Installazione

```
bmad install grf
```

Poi, come primo passo, `grf-profile`: raccoglie il profilo di progetto — settore,
dati trattati, mercato, stack, criticità — e da lì ogni figura deriva quanto essere
severa. Senza profilo il default resta `normal` e le figure partono senza contesto.

## Memoria condivisa

Il profilo vive in `{project-root}/_bmad/memory/grl-shared/project-profile.md`, insieme
a `decisions.md` e `accepted-risks.md`. Il percorso è lo stesso per tutti i moduli
Guardrails: installandone due, il profilo resta uno solo e si compila una volta.

## Convivenza con il bundle

Questo modulo installa skill con **lo stesso nome** del bundle `grl` — `grl-agent-fiscal`
sta identica in entrambi. Bundle e moduli tematici non vanno installati insieme nello
stesso progetto: si sceglie il bundle completo, oppure i moduli delle aree che servono.

## Licenza

MIT.
