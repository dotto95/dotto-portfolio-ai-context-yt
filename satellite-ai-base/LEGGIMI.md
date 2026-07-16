# Satellite AI — un portafoglio a rotazione mensile, gestito da un team di agenti

Questo non è un bot che fa trading. È un **sistema di governo**: una costituzione scritta,
un team di tre agenti AI che litiga sotto quelle regole, una memoria che non dimentica, e
un umano — tu — che esegue e ha l'ultima parola.

Ogni mese il sistema riparte da una domanda sola: **cosa sta andando meglio adesso?**
La misura (trend + forza relativa), sceglie gli strumenti migliori per esprimerlo, dosa
l'esposizione, e ti consegna una lista di ordini. Li esegui tu, a mano. Il mese dopo
controlla se hai fatto quello che era stato deciso, e ricomincia.

> ⚠️ **Non è consulenza finanziaria.** È un progetto educativo e di ricerca. Se lo usi,
> lo fai coi tuoi soldi, i tuoi limiti e il tuo rischio. Nessuna parte di questo sistema
> promette un rendimento. I risultati passati non predicono quelli futuri.

## Cosa promette e cosa no (leggi questo prima di tutto)

**L'obiettivo**: battere l'indice azionario su base **risk-adjusted** — cioè arrivare a
un rendimento paragonabile con **molto meno drawdown** — e batterlo in modo *misurabile*,
non a parole.

**Cosa NON promette, ed è importante**: di battere l'indice sul **rendimento assoluto**.
Un sistema long-only, senza leva, con un tetto di volatilità, non lo fa: rinuncia a parte
del rialzo per non prendersi tutto il ribasso. Nei mercati toro violenti **resterà
indietro**. Per costruzione, non per errore. Se cerchi il sistema che fa più dell'indice
in ogni condizione, non è questo — e diffida di chi te lo vende.

## Come si parte (15 minuti)

**Prerequisiti**: [Claude Code](https://claude.com/claude-code) installato e loggato
(serve un piano a pagamento), e Python installato.

```
1. Estrai questa cartella dove vuoi
2. Apri il terminale dentro la cartella
3. Lancia:  claude
4. Scrivi:  /setup
```

`/setup` è **un'intervista**. Ti fa una decina di domande — quanto capitale, quale
drawdown ti farebbe smettere davvero, cosa puoi comprare col tuo broker, quanto ti costa
un'operazione, come funziona la tassazione da te — e con le tue risposte **scrive la tua
costituzione**. Non ci sono i miei numeri qui dentro: ci saranno i tuoi.

Poi:

```
/costruzione     una volta sola: sceglie l'universo, scarica i dati, costruisce il portafoglio
/ribilancio      una volta al mese: il comitato. Default: non fare niente.
```

## Il ritmo

| Quando | Cosa |
|---|---|
| **Una volta** | `/setup` → `/costruzione` → esegui gli ordini a mano |
| **Ogni mese** | `/ribilancio` → leggi → esegui a mano quello che condividi |
| **Ogni settimana** | la Sentinella controlla le soglie in automatico (facoltativo) |
| **Ogni giorno** | **niente.** Il conto non si guarda. Guardarlo è il modo più rapido per rovinarlo. |
| **Ogni 3 mesi** | review della costituzione: l'unico momento in cui le regole cambiano |

## Com'è fatto

```
satellite-ai/
├── LEGGIMI.md        questo file
├── CLAUDE.md         le regole che gli agenti leggono da soli entrando qui
├── costituzione/     le tue regole. 00 mandato · 01 guardrail · 02 processo
│                     03 metodo · 04 benchmark · 05 esecuzione
├── prompts/          00_setup (l'intervista) · 01_costruzione · 02_ribilancio
├── memoria/          ← IL PRODOTTO VERO
│   ├── comitati/     il VERBALE di ogni comitato: perché e come si è deciso
│   ├── journal.md    l'indice: una riga per decisione
│   ├── tracker.md    la tabella base 100 (satellite / meccanico / 1N)
│   ├── falsificazioni.md · lezioni.md · universo.md
│   └── dati/         le serie usate ogni mese: la prova
└── .claude/          comandi /setup /costruzione /ribilancio /sentinella
```

**Non è un software.** Non ci sono programmi da installare o mantenere: i conti li fa
l'AI quando servono, e quello che resta non è il codice — è il **verbale**. Ogni
comitato produce un documento che spiega, passo per passo: quali dati ha usato, cosa
ha misurato, cosa ha proposto l'architetto, cosa ha obiettato l'avvocato (testualmente,
anche le obiezioni respinte), cosa hai deciso tu e cosa hai scartato. Tra un anno devi
poter riaprire quel file e capire *perché* — o il verbale è scritto male.

## Le tre idee che lo tengono in piedi

1. **Le regole si scrivono da lucidi.** La costituzione esiste per proteggerti dal te
   di domani: quello euforico dopo un mese buono, quello spaventato dopo una settimana
   rossa. Si cambia solo ogni tre mesi, mai nel mezzo di una decisione.
2. **Ogni scelta dichiara cosa la smentirebbe.** Non "vediamo come va": una soglia
   numerica, scritta prima, che il mese dopo si controlla. Se non è falsificabile non è
   un'analisi, è un'opinione vestita bene.
3. **L'AI non ha la mano.** Legge, misura, propone, verifica. Non esegue: esegui tu.
   Non è un permesso negato per prudenza — è come è costruito il sistema.

## Il benchmark (la parte che nessuno mette)

Il sistema non si misura contro il mercato. Si misura contro **se stesso eseguito a
macchina**: le stesse regole, senza il giudizio dell'AI. Se l'AI non batte la propria
versione meccanica, la sua discrezione è teatro — e va spenta. È scritto negli impegni
del `journal`, con una scadenza: 12 mesi.

Perché tanta severità: c'è un risultato in letteratura (Fonseca, ACM TOSEM 2026) che
dimostra che **il backtest di un'AI non è certificabile** — il modello ha già letto come
è andata a finire, attraverso i dati con cui è stato addestrato, e nessuna ispezione del
codice può escluderlo. L'unica evidenza pulita sul giudizio di un'AI è un test **in
avanti**, live. Per questo qui si misura mese per mese, e non si crede ai backtest.

*Dati prima, opinioni dopo.*
