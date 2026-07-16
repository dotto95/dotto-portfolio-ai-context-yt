# Lezioni distillate — la memoria che impara

> Non la cronaca (quella è `journal.md`): i **principi** che l'esperienza conferma o
> smentisce. Gli agenti le rileggono **prima di ogni decisione** e sono vincolanti: se una
> proposta ripete un errore già catalogato, l'AVVOCATO la boccia citando la lezione.
> A ogni comitato l'auto-critica ne aggiunge/corregge una. Max ~15: se entra la 16ª, la
> meno utile esce (motivando).
> Le prime otto sono il **seme**: non vengono dalla tua esperienza ma da errori già
> pagati da altri. Cancellale solo se hai una prova che siano sbagliate.

## Lezioni attive (seme)

1. **Un backtest che coinvolge un'AI non è evidenza.** Il modello ha già letto come è
   andata a finire, e nessuna ispezione del codice può escluderlo: la falla è nei pesi
   (Fonseca, ACM TOSEM 2026). Solo il test in avanti, live, conta.
2. **Se un backtest brilla, togli l'asset più fortunato del periodo e rifallo.** Se il
   vantaggio sparisce, non era metodo: era il campione.
3. **Un sistema long-only, senza leva, con tetto di volatilità NON batte l'indice in
   rendimento assoluto.** Converge su un rendimento inferiore con una frazione del
   drawdown. Chi promette entrambi sta mentendo o usando leva nascosta.
4. **Le falsificazioni in AND "costruite per non scattare" sono pseudo-falsificazioni.**
   Ogni trigger va spezzato in condizioni indipendenti (OR) con una soglia numerica sola.
5. **Il budget di rischio non speso non è sicurezza: è rendimento regalato.** Un sistema
   che gira al 6% di volatilità con un tetto al 12% è a metà motore. Controllare a ogni
   review quanto budget si usa davvero.
6. **Lo stesso criterio va applicato a tutti gli asset.** Se una misura penalizza uno
   strumento, deve penalizzare anche il tuo preferito. Le incoerenze di criterio sono il
   primo posto dove cercare il bias di chi insegue il rendimento.
7. **Gli LLM senza vincoli, su soldi veri, perdono.** Alpha Arena (nof1.ai, 2025): sei
   modelli di frontiera, 10.000 $ ciascuno, autonomia totale → quattro su sei in perdita,
   il peggiore −63%. I due salvi avevano le regole di rischio migliori. Il valore non è
   nel modello: è nei vincoli.
8. **I pesi statici non sono il mandato.** Gli stessi pesi, in regimi diversi, producono
   rischi molto diversi: la volatilità realizzata può raddoppiare senza che tu tocchi
   nulla. La rimisurazione periodica *è* il sistema.
9. **Questo sistema è puro momentum e non ha freni di valutazione.** A parità di dati,
   comprerebbe ciò che un gestore value venderebbe: se un asset è sul massimo perché è
   forte, il sistema lo compra — anche quando è caro. **È una scelta, non una svista**, e
   va ricordata quando il momentum ci porterà sul massimo di qualcosa. Aggiungere un
   filtro di valutazione non è banale: le soglie tipo "N deviazioni standard sopra il
   trend di lungo periodo" funzionano su asset con deriva reale ~nulla (l'oro: ~0,6%
   l'anno) e non trasferiscono alle azioni, che crescono in termini reali (~6,9% l'anno).
   Se un giorno lo si vuole fare sul serio, la strada è la letteratura su valore e
   momentum combinati come fattori distinti — e passa dalla review trimestrale, con un
   test, non da un'intuizione.
10. **Il tempo sott'acqua fa smettere le persone più della profondità.** Un −25%
    recuperato in tre mesi si sopporta; trenta mesi sotto il picco no. Misurare sempre
    il drawdown **più lungo**, non solo il più profondo.
11. **L'inflazione non è un dettaglio contabile.** Su orizzonti pluriennali mangia punti
    interi di rendimento (in un backtest ventennale bilanciato: 8,6% nominale → 6,3%
    reale). Un tracker solo nominale è una mezza bugia raccontata a se stessi.

## Lezioni tue (aggiunte dai tuoi comitati)

<!-- le scrive l'auto-critica di /ribilancio, una per volta, con data e contesto -->
