# Mandato

> ⚠️ TEMPLATE — lo compila `/setup` con le TUE risposte. I `[…]` vanno sostituiti.
> Finché ci sono i segnaposto, il sistema non è configurato: non lanciare `/costruzione`.

## Chi e quanto

- **Capitale del satellite**: `[importo]`
- **Percentuale del patrimonio investito**: `[X%]` — se supera il 10-15%, vedi il
  rischio accettato nel journal #0.
- **Orizzonte minimo di permanenza**: `[N anni]` — **calcolato, non dichiarato.**
  Lo misura `/costruzione` sulla storia dello scheletro meccanico: si generano tutte le
  finestre mobili di 1, 2, 3 e 5 anni e si conta quante hanno chiuso in positivo. È la
  durata oltre la quale la percentuale supera `[X%]`. Riferimento nel verbale #1.
  ⚠️ È una stima con i leak dichiarati in `04_benchmark.md`: un'**indicazione**, non una
  promessa. Ma è meglio di un "12 mesi" tirato fuori dal cappello.
- **Orizzonte di giudizio**: **12 mesi**. È il momento in cui si applicano gli impegni a
  verbale (AI vs scheletro, e struttura vs 1/N). Non si giudica su 30 giorni.
- **Struttura**: è un **satellite**. Esiste accanto a un core che non viene mai toccato
  da questo mandato. Se questo è tutto il tuo portafoglio, non è un satellite: è una
  scommessa. Rileggi `/setup`.

## Obiettivo (e cosa NON è)

- **Obiettivo**: battere l'indice azionario di riferimento su base **risk-adjusted** —
  rendimento paragonabile con **drawdown materialmente inferiore** — e battere il
  proprio scheletro meccanico (`04_benchmark.md`).
- **NON è l'obiettivo, e va detto**: battere l'indice sul **rendimento assoluto**. Un
  sistema long-only, senza leva, con un tetto di volatilità **non lo fa**: rinuncia a
  parte del rialzo per non prendersi tutto il ribasso.
- **Conseguenza dichiarata**: nei mercati toro violenti questo satellite resterà
  indietro. Per costruzione, non per errore. Chi non accetta questo non deve usarlo.
- **La scommessa da dimostrare**: che il giudizio dell'AI (scelta strumenti + dosaggio
  esposizione) batta le stesse regole eseguite a macchina. Se a 12 mesi non le batte, la
  discrezione è teatro e si spegne — impegno a verbale nel journal.

## Ruoli

- **L'AI**: gestore tattico a **discrezione governata**. Decide davvero — cosa (scan),
  con quale strumento (select), quanto e con quanta esposizione (size) — ma sempre dentro
  le bande e i guardrail. **Non prevede prezzi. Non esegue e non può eseguire.**
- **Tu (il presidente)**: **esegui ogni ordine a mano**, decidi sui disaccordi non
  risolti, firmi ogni entry del journal. Ogni ordine scartato o eseguito diversamente va
  a verbale **col motivo**: i tuoi scarti sono informazione sul sistema, non capricci.

## Cadenza

- **Comitato**: `[mensile]` — la rotazione avviene qui.
- **Sorveglianza**: automatica tra un comitato e l'altro (la Sentinella).
- **Review del mandato**: trimestrale. È l'**unico** momento in cui questa costituzione
  può cambiare. Mai a mercati aperti, mai dentro una decisione.

## Limiti dichiarati (compilati da `/setup` — non cancellarli)

- **Fiscalità**: `[trattamento delle plusvalenze/minusvalenze nel paese dell'utente]`.
  Questa è una strategia a rotazione: realizza guadagni e perdite di continuo. Dove le
  minusvalenze non sono compensabili con le plusvalenze degli stessi strumenti, il
  risultato netto può cambiare in modo **materiale** rispetto al lordo. Verificare col
  proprio commercialista. Questo sistema non dà consulenza fiscale.
- **Costi**: `[costo per operazione]`. Con `[N]` posizioni e rotazione `[cadenza]`, il
  turnover è alto: i costi sono una posizione corta permanente.
- **Backtest**: qualunque backtest di questo sistema è **ottimistico**. Vedi i leak
  dichiarati in `04_benchmark.md`. L'unico numero pulito è il track record live.
- **Track record**: zero giorni all'avvio. Non c'è nessuna prova che funzioni per te.

## Disclaimer

Progetto educativo e di ricerca. **Non è consulenza finanziaria né una raccomandazione
di investimento.** I risultati passati non predicono quelli futuri. Nessuna parte di
questo sistema promette un rendimento.
