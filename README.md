# Satellite AI — il kit

Un portafoglio **satellite a rotazione mensile** governato da una costituzione scritta e
da un team di tre agenti AI che discute sotto quelle regole. L'AI misura, propone e
verbalizza; **gli ordini li esegui tu, a mano**. Questo repository contiene il kit base:
solo template e regole, nessun dato personale — la *tua* costituzione la scrivi tu, con
l'intervista di setup.

> ⚠️ **Non è consulenza finanziaria.** Progetto educativo e di ricerca. Se lo usi, lo fai
> coi tuoi soldi e a tuo rischio. Nessuna parte di questo sistema promette un rendimento.
> I risultati passati non predicono quelli futuri.

Il kit completo è nella cartella [`satellite-ai-base/`](satellite-ai-base/) — per la
filosofia del sistema (cosa promette, cosa NON promette, le tre idee che lo tengono in
piedi) leggi prima [`satellite-ai-base/LEGGIMI.md`](satellite-ai-base/LEGGIMI.md).

---

## Cosa ti serve

- Un account **Claude** a pagamento (il sistema è pensato per Claude Code o per l'app
  desktop Claude con Cowork; vedi sotto per le alternative)
- Un **broker** qualsiasi con cui puoi comprare ETF UCITS (il sistema non tocca il conto:
  legge, propone, e basta)
- **Zero programmazione**: non c'è codice da scrivere né software da mantenere. I conti
  li fa l'AI quando servono; quello che resta sono i verbali.

## 1. Scarica il kit

Due strade:

- **Senza git**: pulsante verde **Code → Download ZIP** qui sopra, poi estrai la cartella
  `satellite-ai-base` dove preferisci (es. `Documenti\mio-satellite\`).
- **Con git**: `git clone https://github.com/dotto95/dotto-portfolio-ai-context-yt.git`

La cartella estratta diventa **la tua copia personale**: lì dentro l'AI scriverà la tua
costituzione e i tuoi verbali. Non servirà più toccare questo repository.

## 2. Dai il contesto all'AI

Il kit è costruito perché l'AI si orienti **da sola**: il file `CLAUDE.md` dentro la
cartella contiene le regole che qualsiasi agente Claude legge automaticamente quando
lavora lì. Tu non devi spiegare niente — devi solo aprire l'AI *dentro la cartella*.

**Opzione A — Claude Code (terminale)**

```
cd percorso/della/cartella/satellite-ai-base
claude
```

Poi scrivi `/setup` e rispondi alle domande. I comandi `/setup`, `/costruzione`,
`/ribilancio` e `/sentinella` sono già configurati (stanno in `.claude/commands/`).

**Opzione B — App desktop Claude (Cowork)**

Apri una sessione Cowork e **connetti la cartella** `satellite-ai-base` come contesto
(pulsante "Aggiungi cartella"). Poi scrivi: *"iniziamo con il setup"*. L'AI legge
`CLAUDE.md`, capisce dov'è, e conduce l'intervista. Stessa cosa per i passi successivi:
*"costruzione"*, *"ribilancio"*, *"sentinella"*.

**Opzione C — Altre AI (ChatGPT, Gemini, ecc.)**

Possibile ma artigianale: a inizio conversazione incolla il contenuto di `CLAUDE.md`,
dei sei file di `costituzione/` e del prompt che ti serve (`prompts/00_setup.md` per
l'intervista, poi `01_costruzione.md`, poi `02_ribilancio.md` ogni mese). Dovrai salvare
a mano i file che l'AI produce (costituzione compilata, verbali, journal). Funziona, ma
perdi i comandi automatici e la comodità della memoria su disco.

## 3. Il flusso

| Passo | Comando | Quando | Cosa succede |
|---|---|---|---|
| 1 | `/setup` | una volta | Intervista: capitale, drawdown che reggi davvero, broker, costi, fiscalità. Scrive **la tua costituzione** e l'Entry #0 del journal |
| 2 | `/costruzione` | una volta | Giorno zero: fissa l'universo di scan, scarica 5+ anni di dati reali, il team (QUANT, ARCHITETTO, AVVOCATO) costruisce il primo portafoglio e ti consegna la **lista ordini** |
| 3 | *(tu)* | — | Esegui gli ordini **a mano** sul tuo broker. È voluto: l'attrito è una difesa |
| 4 | `/ribilancio` | ogni fine mese | Il comitato: riconcilia l'eseguito, verifica le falsificazioni una per una, rifà lo scan, decide. **Default: nessuna azione.** Produce il verbale |
| 5 | `/sentinella` | quando vuoi tra un comitato e l'altro | Controllo rapido delle soglie. Non decide niente: se scatta qualcosa, convoca il comitato |

E ogni giorno? **Niente.** Il conto non si guarda: guardarlo è il modo più rapido per
rovinare il sistema (e te stesso).

## Cosa viene scritto, e dove

- `costituzione/00_mandato.md`, `01_guardrail.md`, `05_esecuzione.md` — **personali**:
  li compila `/setup` con le tue risposte (qui nel repo sono template con i segnaposto).
- `costituzione/02_processo.md`, `03_metodo.md`, `04_benchmark.md` — **invarianti**: il
  metodo. Non si toccano, né tu né l'AI. Si cambiano solo alla review trimestrale.
- `memoria/` — **il prodotto vero**: i verbali dei comitati (`comitati/`), il journal
  (una riga per decisione), il tracker a base 100 (satellite vs scheletro meccanico vs
  1/N), le falsificazioni attive coi trigger, le lezioni distillate, e in `dati/` le
  serie di prezzo effettivamente usate — la prova che rende ogni verbale ricontrollabile.

## Se versioni la tua copia (consigliato ma privato)

Mettere la **tua** cartella sotto git è un'ottima idea: la memoria è il prodotto, e la
storia dei commit ne è la garanzia. Ma fallo in un **repository privato**: dopo il setup
quei file contengono il tuo capitale, la tua tolleranza al rischio, il tuo broker e ogni
tua decisione. Questo repo pubblico è il template, non il posto per i tuoi dati.

## Domande frequenti

**È un bot che fa trading?** No. L'AI non ha alcun accesso di esecuzione — non è un
permesso negato, è una mano che non esiste. Propone una lista ordini; la esegui tu.

**Devo saper programmare?** No. Non c'è codice da scrivere. Serve solo seguire il ritmo:
un comitato al mese, esecuzione a mano, e la disciplina di non toccare niente nel mezzo.

**Promette di battere il mercato?** No — e chi te lo promette mente. L'obiettivo è il
rendimento *aggiustato per il rischio* (meno drawdown), e il sistema si misura contro
la propria versione meccanica: se l'AI non la batte in 12 mesi, la discrezione si spegne.
È scritto negli impegni del journal.

**Quanto costa?** Un piano Claude a pagamento e le commissioni del tuo broker. I dati di
mercato vengono da fonti pubbliche gratuite.

---

Damiano