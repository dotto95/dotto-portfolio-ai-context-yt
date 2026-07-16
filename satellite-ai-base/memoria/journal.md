# Journal delle decisioni — append-only

> La memoria del sistema. Una entry per comitato, **anche quando la decisione è "non
> faccio niente"** (soprattutto allora). **Mai riscrivere il passato**: solo aggiungere.
> È ciò che ti permette, tra un anno, di giudicare le decisioni con le informazioni di
> allora invece che col senno di poi. Una buona decisione può perdere; una pessima può
> guadagnare. Distinguerle è il mestiere.

Formato di ogni entry: data · snapshot del conto · riconciliazione del mese precedente ·
scan e segnali · decisione · razionale (max 5 righe) · falsificazioni dichiarate ·
lista ordini · firma.

---

## Entry #0 — Setup (la scrive `/setup`)

- **Data**:
- **Capitale e % del patrimonio**:
- **Drawdown dichiarato come sopportabile** → **tetto di volatilità derivato**:
- **Broker, costi per operazione, importo minimo, valuta**:
- **Trattamento fiscale dichiarato** (e conseguenze sulla cadenza):
- **Default accettati / cambiati** (con motivo):
- **Rischi accettati contro il parere del sistema** (se ce ne sono):
- **Impegni a verbale (12 mesi)**:
  1. Se lo **scheletro meccanico** batte l'AI su base risk-adjusted → si abbandona la
     discrezione e si esegue il sistema a macchina.
  2. Se il **benchmark naive 1/N** li batte entrambi → si abbandona la struttura attiva.
- **Firma**:

---

## Entry #1 — Costruzione (la scrive `/costruzione`)

- **Data**:
- **Universo di scan fissato** (e fonte dati):
- **SCAN**: classifica trend/momentum · breadth:
- **Portafoglio**: top-N, pesi, esposizione totale, cash:
- **Giustificazione dell'esposizione** (dati, non previsioni):
- **Falsificazioni dichiarate**: vedi `falsificazioni.md`
- **Lista ordini deliberata**:
- **Eseguito davvero** (da compilare dopo: scarti e differenze, col motivo):
- **Costi reali vs stimati**:
- **Firma**:
