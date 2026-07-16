# Satellite AI — regole di questo repository

Qui vive un portafoglio satellite a **rotazione mensile**, gestito da un team di tre
agenti sotto una costituzione scritta. Il conto si legge (sola lettura o a mano), **gli
ordini li esegue l'umano**. Chi lavora qui — umano o AI — segue queste regole.

## Struttura

- `costituzione/` — le regole. `00_mandato` e `01_guardrail` e `05_esecuzione` sono
  **personali** (li scrive `/setup`); `02_processo`, `03_metodo`, `04_benchmark` sono
  **invarianti**. Si cambiano SOLO alla review trimestrale, mai dentro una decisione.
- `prompts/` — `00_setup.md` (intervista), `01_costruzione.md` (giorno zero),
  `02_ribilancio.md` (comitato mensile).
- `memoria/` — **il prodotto vero del sistema**:
  - `comitati/AAAA-MM.md` — il **verbale** di ogni comitato: la catena completa che ha
    prodotto la decisione. `MODELLO.md` è il template, si compila tutto.
  - `journal.md` — l'indice: una riga per decisione, col link al verbale.
  - `tracker.md` — la tabella base 100: satellite / scheletro meccanico / 1N.
  - `falsificazioni.md` + `trigger.json` — i trigger vivi.
  - `lezioni.md` — i principi distillati, vincolanti.
  - `universo.md` — l'universo di scan.
  - `dati/AAAA-MM_serie.csv` — le serie **effettivamente usate**: sono la prova.

## Regole per qualsiasi agente che opera qui

1. **La costituzione vince su tutto.** Prima di agire leggi `costituzione/01_guardrail.md`.
   Guardrail violato = stop. Se trovi segnaposto `[…]` nel mandato, il sistema non è
   configurato: **fermati e di' di lanciare `/setup`**.
2. **Niente dati a memoria.** I prezzi vengono da fonte pubblica, scaricati al momento e
   **salvati in `memoria/dati/`**: sono la prova, non un file di lavoro. Lo stato del
   conto si legge dal broker in sola lettura, o lo fornisce il presidente. Se un numero
   non viene da lì o da una fonte citata, non esiste.
3. **Availability prima di tutto.** Un dato si può usare solo se era conoscibile
   all'istante della decisione. **La tua conoscenza è a vintage illimitato**: puoi usarla
   per *spiegare*, mai per *decidere*. Se giustifichi una scelta con "so che quel settore
   è andato bene" invece che con un numero del CSV, è look-ahead: veto.
4. **Non esegui: non puoi e non devi.** Proponi una lista ordini (max 6 per comitato), la
   esegue l'umano a mano, poi tu **riconcilia** l'eseguito col deliberato. Non cercare vie
   alternative di esecuzione, non sollecitare: il comitato è mensile.
5. **Ogni decisione — anche "nessuna azione" — produce un VERBALE completo** in
   `memoria/comitati/`, compilato in ogni sezione: dati usati, scan, falsificazioni
   verificate una per una, obiezioni **testuali**, revisione, decisione, ordini, aperti.
   Il journal ne è solo l'indice. Append-only: il passato non si riscrive mai.
   Se dal verbale non si può ricostruire *perché* si è deciso così, è scritto male.
6. **Le falsificazioni si verificano a OGNI review**, una per una, PRIMA di proporre
   qualsiasi cosa. Le **lezioni** sono vincolanti: se una proposta ripete un errore già
   catalogato, l'AVVOCATO la boccia citando la lezione.
7. **I parametri del metodo sono congelati** (SMA 10 mesi, momentum 12-1). Non si
   ottimizzano mai sul backtest: è overfitting, si boccia.
8. **Un movimento va giustificato, la calma no.** Default: nessuna azione. Si muove solo
   per: segnale cambiato, guardrail violato, falsificazione scattata, deriva fuori banda.
   E solo se il beneficio atteso supera **2×** i costi stimati.
9. **Nessuna previsione di prezzi o rendimenti. Mai.** Un'esposizione motivata da una
   previsione è una scommessa nuda: veto.

## Comandi

- `/setup` — l'intervista che scrive la costituzione. **Da fare per primo.**
- `/costruzione` — giorno zero: universo, dati, primo portafoglio, lista ordini.
- `/ribilancio` — il comitato mensile. Produce il verbale.
- `/sentinella` — controllo rapido dei trigger tra un comitato e l'altro. **Non decide
  niente**: se scatta qualcosa, si convoca il comitato.

## Questo non è un progetto software

Non ci sono programmi da mantenere, e non vanno costruiti. I conti li fai tu, quando
servono, con gli strumenti che hai — e quello che resta non è il codice: è il **verbale**.
Se ti ritrovi a proporre una dashboard, una libreria o un'infrastruttura, ti sei perso:
il prodotto è la catena di ragionamento tracciata in `memoria/`, leggibile da un umano
tra dieci anni.

## Disclaimer

Progetto educativo e di ricerca. **Non è consulenza finanziaria né una raccomandazione di
investimento.** Chi lo usa lo fa a proprio rischio, coi propri soldi. I risultati passati
non predicono quelli futuri. Nessuna parte di questo sistema promette un rendimento.
