# Guardrail inviolabili

> ⚠️ TEMPLATE — i numeri li fissa `/setup` con te. I default proposti sono tra parentesi.
> Sui limiti non si dibatte: guardrail violato = **veto**, la proposta torna indietro.
> Si cambiano solo alla review trimestrale.

1. **Max per singola posizione**: `[30%]`.
2. **Cap crypto**: `[0% — default: crypto escluse]`. Se incluse, mai oltre `[20%]`.
3. **Almeno 3 classi di attivo** rappresentate quando l'esposizione supera il 60%.
4. **Bande di esposizione**: `[30%]` — `[90%]` investito (cash tra `[10%]` e `[70%]`).
   Dentro la banda l'AI decide, ma il livello va giustificato con **dati** (ampiezza dei
   trend, volatilità). Un'esposizione motivata da una previsione ("mi aspetto un crollo")
   è una **scommessa nuda: veto**.
   Drift: fuori banda a fine mese → rientro entro 3 giorni di borsa.
5. **Tetto di volatilità**: `[X%]` annualizzata (solo tetto, nessun minimo).
   Derivato dal drawdown che hai dichiarato di reggere: `tetto ≈ drawdown_tollerato / 1,8`.
   Nei regimi negativi il sistema riduce l'esposizione e la volatilità scende: **è voluto**.
   Trigger ex-ante: vol attesa > `[tetto - 1 punto]` → riduzione preventiva.
   Trigger ex-post: vol realizzata 30g > `[tetto]` → riduzione meccanica.
6. **No leva, no derivati, no strumenti illiquidi.** Solo long, ordini market o limit.
7. **Esecuzione manuale, sempre.** L'AI propone una lista ordini (max `[6]` per comitato);
   li esegui tu; poi l'AI riconcilia l'eseguito col deliberato. Cercare o costruire una
   via di esecuzione automatica è **violazione del mandato**.
8. **Cost hurdle**: nessun ribilancio se il beneficio di rischio atteso non supera di
   almeno **2×** i costi stimati (commissioni + spread reali dichiarati nel setup).
9. **Ogni raccomandazione cita il dato che la sostiene.** Senza dato = opinione,
   dichiarata come tale.
10. **Ogni scelta rilevante dichiara la sua falsificazione**: evidenza osservabile a 30
    giorni, con **soglia numerica** e azione definita, registrata in
    `memoria/falsificazioni.md`. Falsificazione vaga o in AND "costruita per non
    scattare" = bocciata.
