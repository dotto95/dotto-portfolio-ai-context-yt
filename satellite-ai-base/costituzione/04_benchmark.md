# Benchmark e criteri di verdetto

> **File invariante.** Il benchmark non si sceglie per farsi belli: si sceglie perché
> sia scomodo.

## Benchmark primario: LO SCHELETRO MECCANICO

Le stesse regole di `03_metodo.md` eseguite **a macchina, senza AI**: top-N per momentum
tra chi è sopra trend, equal-risk, esposizione da regola fissa.
Si calcola e si traccia in parallelo, live, dal giorno zero: la colonna dedicata in
`memoria/tracker.md`.

**È il benchmark che conta.** L'intera scommessa del sistema è che il giudizio dell'AI
faccia meglio delle stesse regole senza giudizio. Se non lo batte, la discrezione non
serve: è teatro, e si spegne.

## Benchmark secondario: equal-weight 1/N

Stesso universo, pesi uguali, base 100 dal giorno 0. Fondamento: DeMiguel, Garlappi &
Uppal (2009) — fuori campione l'1/N batte la maggior parte delle ottimizzazioni.
L'avversario più scomodo che esista, e va tenuto in campo apposta.

## Riferimento di contesto: l'indice azionario

S&P 500 (o l'indice della tua valuta/area) e un 60/40, **per dare la scala** — non come
bersaglio del rendimento assoluto (vedi `00_mandato.md`). Il confronto che conta con
l'indice è **il drawdown** e il risk-adjusted, non il rendimento nudo.

## Criteri di verdetto

- Confronto **risk-adjusted**: rendimento, volatilità realizzata, **max drawdown**,
  Sharpe, Calmar. **Al netto dei costi reali** e, dove rilevante, delle tasse.
- Orizzonte: **12 mesi**. Un mese non dimostra niente, in nessuna direzione.
- **Impegni a verbale** (journal #0), vincolanti a 12 mesi:
  1. Se lo **scheletro meccanico** batte l'AI su base risk-adjusted → si abbandona la
     discrezione e si esegue il sistema a macchina.
  2. Se il **benchmark naive 1/N** li batte entrambi → si abbandona la struttura attiva.
- Il tracker registra **tutte e tre** le serie in base 100, sempre. Anche quando fa male.

## Perché non ci si fida dei backtest (leggere prima di guardare qualunque numero storico)

Qualunque backtest prodotto da questo sistema è **ottimistico**. I leak sono noti e
dichiarati, non nascosti:

| Leak | Perché c'è | Rimovibile? |
|---|---|---|
| **Universo scelto col senno di poi** | Gli strumenti che metti nell'universo oggi sono quelli sopravvissuti e noti | **No** |
| **Parametri dalla letteratura** | SMA 10m e momentum 12-1 sono famosi perché hanno funzionato | **No** |
| **Costi** | Vanno inclusi esplicitamente, e spesso non lo sono | Sì — falli includere |
| **Esecuzione al close del segnale** | Si assume di eseguire al prezzo che genera il segnale | Sì — usa il prossimo prezzo negoziabile |
| **Prezzi ri-aggiustati** | Le serie "adjusted" sono la vista di oggi sul passato, non quella di allora | Parzialmente |

E il più profondo, che riguarda ogni sistema con dentro un'AI:

> Un agente può far trapelare il futuro attraverso i dati con cui è stato addestrato,
> anche se il codice riceve solo input contemporanei — e **l'ispezione del codice non può
> escluderlo**, perché la falla è nei pesi. (Fonseca, ACM TOSEM 2026, arXiv:2607.04958.)

**Conseguenza**: il backtest di un'AI non è certificabile. Chiunque ti mostri il backtest
del suo agente ti sta mostrando qualcosa che non può dimostrare. L'unica evidenza pulita
sul giudizio di un'AI è il **test in avanti**, live — che è esattamente ciò che questo
sistema fa, mese per mese, contro il suo scheletro.
