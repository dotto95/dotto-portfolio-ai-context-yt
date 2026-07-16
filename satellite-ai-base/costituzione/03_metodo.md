# Metodo — Top-down momentum a discrezione governata

> **File invariante.** Questo è il metodo, non una preferenza: `/setup` non lo tocca.
> Se lo cambi, stai usando un altro sistema — legittimo, ma allora cambia anche il
> benchmark e riparti da un journal nuovo.

## L'imbuto mensile: SCAN → SELECT → SIZE

### 1. SCAN — "cosa sta andando meglio adesso"
Classifica l'universo largo (classi di attivo, regioni, settori, temi) su due misure,
calcolate su dati pubblici:
- **Trend assoluto**: prezzo di fine mese vs media mobile a **10 mesi**. Sotto = fuori,
  senza discussione. (Faber 2007; Moskowitz-Ooi-Pedersen 2012.)
- **Momentum relativo**: rendimento **12-1 mesi** (12 mesi saltando l'ultimo).
  (Jegadeesh-Titman 1993; Antonacci 2014.)
Eleggibili = chi è sopra trend. Si ordinano per momentum.

### 2. SELECT — lo strumento migliore per il tema vincente
Per i temi in testa, l'AI sceglie lo strumento che li esprime meglio: liquidità, costo,
qualità di replica, valuta, accessibilità col tuo broker. **È giudizio vero** — ed è uno
dei due punti in cui l'AI può battere la macchina.

### 3. SIZE — pesi ed esposizione
- Si tengono i **top-N** per momentum tra gli eleggibili (N dal setup).
- Il rischio si divide tra i sopravvissuti partendo dalla baseline **Equal Risk
  Contribution** (Maillard-Roncalli-Teïletche 2010); ogni deviazione con un dato.
- **Esposizione totale**: decisa dall'AI dentro le bande, giustificata da ampiezza dei
  trend e volatilità. **Mai da una previsione.** È il secondo punto in cui l'AI può
  battere la macchina — o farsi male.

## Parametri congelati (regola anti-overfitting, vincolante)

Trend SMA **10 mesi** · momentum **12-1** · ribilancio a fine mese.
Vengono dalla letteratura e **non si ottimizzano mai sul backtest**. Cambiare un
parametro perché "il backtest migliora" è overfitting: l'AVVOCATO lo boccia citando
questa regola. Si toccano solo alla review trimestrale, con una motivazione indipendente
dai risultati recenti.

> Nota di onestà: anche così, **la scelta stessa di questi parametri è un leak**. Sono
> famosi *perché* hanno funzionato nei backtest pubblicati: adottarli oggi per giudicare
> il passato usa informazione posteriore. Non è rimovibile. È dichiarato.

## Il principio che regge tutto: availability vs reference time

Ogni dato ha due coordinate temporali: **quale istante descrive** (reference time) e
**quando è diventato conoscibile** (availability). Il look-ahead è usare un dato la cui
availability viene *dopo* l'istante della decisione. (Fonseca, ACM TOSEM 2026.)

Conseguenza operativa, non negoziabile:
- **I segnali sono meccanici e vengono dai dati storici**, con availability ≤ istante
  della decisione. Punto.
- **La conoscenza dell'AI è a vintage illimitato**: il modello ha letto il futuro
  rispetto a qualunque data passata. Può informare la **spiegazione**, mai il **segnale**.
  Se un agente giustifica una scelta con "so che quel settore ha fatto bene" invece che
  con un numero del CSV, è look-ahead travestito: **veto**.

## Principi

- **Budget di rischio, non di capitale.** I pesi sono un output.
- **Stime rumorose**: finestre corte = indicazioni, non certezze (Ledoit-Wolf 2004).
  Robusto batte ottimo.
- **I costi sono una posizione corta permanente** (Perold 1988). Con la rotazione
  mensile contano: cost hurdle 2× (`01_guardrail.md` #8).
- **Attribuzione ogni mese** (Brinson-Hood-Beebower 1986): *cosa* spiega il risultato
  prima di *quanto* è il risultato. È ciò che separa la fortuna dal processo.
- **Falsificazione o niente**: cosa smentirebbe la scelta, scritto **prima**.
- **Il backtest testa lo scheletro, non il giudizio.** La discrezione dell'AI non è nei
  dati storici: il suo valore si misura solo live (`04_benchmark.md`).

## Riferimenti

Faber (2007) QTAA · Moskowitz, Ooi & Pedersen (2012) JFE · Jegadeesh & Titman (1993) JF ·
Antonacci (2014) Dual Momentum · Maillard, Roncalli & Teïletche (2010) JPM ·
DeMiguel, Garlappi & Uppal (2009) RFS · Ledoit & Wolf (2004) JPM · Moreira & Muir (2017) JF ·
Brinson, Hood & Beebower (1986) FAJ · Perold (1988) JPM ·
Fonseca (2026), *Look-Ahead-Freedom as Temporal Non-Interference*, ACM TOSEM (arXiv:2607.04958).
