# Verbale del comitato — MODELLO

> Copia questo file in `memoria/comitati/AAAA-MM.md` a ogni comitato e compilalo **tutto**.
> Questo è il cuore del sistema: non il riassunto della decisione, ma la **catena completa**
> che l'ha prodotta. Se tra un anno non riesci a ricostruire *perché* hai fatto una cosa
> leggendo solo questo file, il verbale è scritto male.
>
> Regole del verbale:
> - **Ogni numero ha una fonte.** Se non sai dire da dove viene, non entra.
> - **Le obiezioni si riportano testuali**, non parafrasate. Anche quelle respinte.
> - **Si scrive anche quando non si fa niente.** Anzi: soprattutto.
> - **Non si riscrive mai.** Se dopo scopri che era sbagliato, lo scrivi nel verbale dopo.
> - **Ogni tabella dice due cose**: *cosa mostra* e *cosa implica*. Un dato senza la
>   sua conseguenza è arredamento.

---

# Comitato AAAA-MM

**Data**: · **Presenti**: QUANT, ARCHITETTO, AVVOCATO, presidente

## COSA RICORDARE

> Il riquadro per l'umano di fretta. **Una idea sola, detta piatta.** Se il presidente
> legge solo questo, deve sapere cos'è successo e cosa deve fare. Niente gergo, niente
> sfumature: quelle stanno sotto, nelle dodici sezioni.

- **Decisione**:
- **Perché** (una riga, col dato che la regge):
- **Cosa devo fare io**:
- **Il rischio numero uno del mese**:

---

## 1. Stato del conto (snapshot di partenza)

| Voce | Valore |
|---|---|
| Fonte (broker in sola lettura / inserito a mano) | |
| Valore totale | |
| Posizioni e pesi effettivi | |
| Cash ed esposizione | |
| P&L del mese | |
| Costi sostenuti nel mese | |

## 2. Riconciliazione del mese precedente

> Cosa era stato deliberato vs cosa è stato eseguito davvero.

| Ordine deliberato | Eseguito? | Differenza | Motivo (se scartato o cambiato) |
|---|---|---|---|
| | | | |

- Pesi ottenuti vs target (tolleranza ±1 punto):
- **Costi reali vs stimati**:
- Scostamenti da segnalare:

## 3. I dati usati

- **Fonte**:
- **Periodo**:
- **File salvato in**: `memoria/dati/AAAA-MM_serie.csv`
- Anomalie o buchi riscontrati:

> Chiunque, ripartendo da questo file, deve poter rifare gli stessi conti.

## 4. SCAN — la classifica (QUANT)

| # | Tema | Trend vs SMA10 (sopra/sotto, margine) | Momentum 12-1 | Eleggibile |
|---|---|---|---|---|
| | | | | |

- **Breadth** (quante voci sopra trend su totale):
- Volatilità dei candidati:
- Cluster di correlazione (chi è di fatto la stessa scommessa):
- Cosa è cambiato rispetto al mese scorso (entrati / usciti / rafforzati):

## 5. Verifica delle falsificazioni — una per una

> Nessuna proposta si discute prima di aver chiuso questa tabella.

| # | Trigger dichiarato | Valore oggi | Scattato? | Azione conseguente |
|---|---|---|---|---|
| | | | | |

## 6. Proposta dell'ARCHITETTO

| Strumento | Peso proposto | Contributo al rischio | Motivazione (con il dato) |
|---|---|---|---|
| | | | |

- **Esposizione totale proposta**: ___ % — **giustificazione con dati** (ampiezza dei
  trend, volatilità). *Se qui compare una previsione, l'AVVOCATO deve porre il veto.*
- Deviazioni dalla baseline ERC e perché:
- Costi stimati del ribilancio e beneficio atteso (cost hurdle ≥ 2×):

## 7. Esame dell'AVVOCATO

**Veti** (guardrail violati — non negoziabili):
| Guardrail | Verifica indipendente | Esito |
|---|---|---|
| | | |

**Obiezioni** (testuali, non parafrasate, più gravi prima):
> 1. «…»
> 2. «…»

**Stress test**:
| Scenario | Perdita/vol stimata |
|---|---|
| Peggior finestra 30g del periodo | |
| Crollo −50% della componente più volatile | |
| Correlazioni tra rischiosi a 0,9 | |

**Giudizio sulle falsificazioni proposte** (bocciate quelle vaghe o in AND):

## 8. Revisione e verdetto

| Obiezione | Accolta / Respinta | Cosa è cambiato / con quale dato |
|---|---|---|
| | | |

- **Firma dell'AVVOCATO**: FIRMO / NON FIRMO — decide il presidente su: …
- **Resta aperto per il presidente**:

## 9. Decisione finale

- [ ] **NESSUNA AZIONE** (default)
- [ ] Ribilancio

**Pesi finali**:

**Lista ordini** (max da costituzione — li esegue il presidente a mano):
| # | Strumento | Lato | Quantità/importo | Tipo | Motivazione |
|---|---|---|---|---|---|
| | | | | | |

## 10. Verdetto sui benchmark

| | Mese | Da inizio (base 100) |
|---|---|---|
| Satellite | | |
| Scheletro meccanico | | |
| Benchmark 1/N | | |
| Indice di contesto | | |

**Attribuzione** — *cosa* spiega il risultato, non solo quanto:

**La discrezione dell'AI questo mese ha aggiunto o tolto valore rispetto allo scheletro?**
(rispondere col numero, non con un'impressione):

## 11. Nuove falsificazioni dichiarate

| Scelta | Trigger (soglia numerica, 30g) | Azione se scatta |
|---|---|---|
| | | |

## 12. Auto-critica

- Cosa ci ha insegnato questo mese che un **principio generale** catturerebbe?
- Lezione aggiunta/corretta in `lezioni.md`:
- **Il rischio numero uno dei prossimi 30 giorni** (una frase):

---

**Firma del presidente**: ___________  **Data**: ___________
