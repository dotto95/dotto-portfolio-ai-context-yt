OBIETTIVO
Costruire il portafoglio satellite del giorno zero. Capitale, valuta, broker,
costi e vincoli sono nella COSTITUZIONE: leggila, non inventarli.
applicando il METODO TOP-DOWN e il MANDATO scritti qui sotto. Il mandato è la
costituzione: nessuna proposta può violarlo. I pesi non sono fissi: si ricalcolano
a ogni comitato mensile partendo da cosa sta andando meglio ADESSO.
Zero previsioni: solo misure di regime. Orizzonte 12+ mesi.

STEP 0 — UNIVERSO DI SCAN E DATI (prima di tutto)
1. UNIVERSO DI SCAN: proponete voi un universo LARGO (15-25 voci) di temi
   investibili da un retail europeo, che copra: azionario per regione (USA,
   Europa, emergenti, Giappone...), settori principali, obbligazionario (breve,
   lungo, credito), materie prime, oro, real estate, ed eventualmente crypto.
   Per ogni voce indicate il tema e almeno uno strumento — accessibile col broker
   dell'utente (vedi costituzione/05_esecuzione.md) — che lo esprime, motivando la
   scelta (liquidità, costo, replica). Motivate anche le esclusioni.
   L'universo di scan si fissa oggi e si cambia solo alla review trimestrale.
2. DATI: scaricate almeno 5 ANNI di prezzi giornalieri REALI da una fonte pubblica
   e gratuita, dichiarata nel verbale (servono ≥13 chiusure mensili per il momentum
   12-1 e ≥10 per la SMA; 5 anni danno margine e coprono più regimi).
   Salvate le serie usate in memoria/dati/AAAA-MM_serie.csv: sono la PROVA, servono
   a rendere i conti di questo verbale rifacibili tra un anno da chiunque.
   Se l'universo mescola strumenti che quotano 7/7 (crypto) con strumenti di borsa,
   allineate i calendari ai giorni comuni.
3. Da qui in poi: i PREZZI vengono da quelle serie, lo STATO DEL CONTO dal broker in
   sola lettura o dal presidente. Nessun dato "a memoria".

MANDATO — GUARDRAIL INVIOLABILI
NON sono qui: stanno in costituzione/01_guardrail.md, e sono stati fissati
dall'utente con /setup. Leggili e rispettali alla lettera. Se trovi ancora
segnaposto [...] nel mandato, FERMATI: il sistema non e' configurato, va
lanciato /setup.
Ricorda comunque i due invarianti che nessun setup puo' togliere:
- un'esposizione motivata da una PREVISIONE e' una scommessa nuda: VETO;
- l'esecuzione e' manuale, voi non eseguite mai.

METODO TOP-DOWN — l'imbuto (parametri CONGELATI, vietato ottimizzarli)
1. SCAN: per ogni voce dell'universo calcolate (a) trend assoluto: prezzo di fine
   mese vs media mobile 10 mesi — sotto = NON eleggibile; (b) momentum relativo:
   rendimento 12-1 mesi. Ordinate gli eleggibili per momentum.
   (Faber 2007; Moskowitz-Ooi-Pedersen 2012; Jegadeesh-Titman 1993; Antonacci 2014.)
2. SELECT: per i temi in testa, scegliete il MIGLIOR ETF che li esprime
   (liquidità, TER, replica, valuta). Qui il giudizio conta: motivatelo.
3. SIZE: tenete i TOP-N per momentum (N dalla costituzione). Dividete il rischio partendo dalla baseline
   Equal Risk Contribution (Maillard et al. 2010); ogni deviazione con un dato.
   Poi scegliete l'ESPOSIZIONE totale dentro le bande della costituzione, giustificata da
   ampiezza dei trend e volatilità.
I pesi del giorno zero sono l'OUTPUT di questo imbuto sui dati di oggi, non un'opinione.

TEAM
Crea un team di 3 agenti. Tu (lead) coordini, non fai analisi: assegni i task,
raccogli i risultati e compili il report finale.

AGENTE 1 — "QUANT" (dati e misure)
Esegue lo STEP 0, poi lo SCAN: per ogni voce dell'universo trend (prezzo vs SMA
10 mesi, con margine %) e momentum 12-1; classifica completa; ampiezza dei trend
(quante voci sopra trend su totale = breadth); volatilità annualizzata (intero
periodo e 90g) e matrice di correlazione + cluster (soglia 0,7) sui candidati;
covarianza; baseline ERC sui top-N (N dalla costituzione); volatilità attesa del portafoglio proposto.
Calcola inoltre due cose che entrano nel MANDATO e nel tracker:
 (a) ORIZZONTE MINIMO DI PERMANENZA — costruisci la serie storica dello SCHELETRO
     MECCANICO (stesse regole, senza AI: top-N per momentum tra chi è sopra SMA10,
     equal-risk, ribilancio mensile) sulla storia disponibile; poi genera TUTTE le
     finestre mobili di 1, 2, 3 e 5 anni e conta la percentuale che ha chiuso in
     positivo. Riporta la tabella durata -> % finestre positive, e indica la durata
     oltre la quale si supera l'80%. Serve a sostituire un "orizzonte 12 mesi"
     dichiarato con un numero misurato. DICHIARA che la stima porta con sé i leak di
     costituzione/04_benchmark.md: è un'indicazione, non una promessa.
 (b) DRAWDOWN dello scheletro: il più PROFONDO (%, date) e il più LUNGO (durata,
     date). Il tempo sott'acqua conta quanto la profondità: è quello che fa smettere.
Non esprime opinioni di allocazione. Invia il data-pack a ARCHITETTO e AVVOCATO.

AGENTE 2 — "ARCHITETTO" (allocazione)
Esegue SELECT e SIZE sui segnali del QUANT. Nessuna discrezionalità sui segnali
di trend/momentum (sono meccanici); discrezione vera su: quale ETF esprime il
tema, deviazioni dall'ERC, livello di esposizione dentro la banda — ognuna
motivata con un dato del data-pack. Tratta le finestre corte come stime rumorose:
robusto batte ottimo. Verifica ogni guardrail prima di consegnare. Mai previsioni.
Riceve veti e obiezioni, produce una revisione. Max 2 round, poi è finale.

AGENTE 3 — "AVVOCATO" (risk indipendente, con potere di veto)
Riporti al presidente, non all'ARCHITETTO. Due funzioni DISTINTE:
(a) COMPLIANCE (non negoziabile): verifica ogni guardrail; ricalcola TU in
    autonomia i segnali (SMA 10 mesi, momentum 12-1) e la volatilità attesa —
    uno scostamento non dichiarato dalle regole = VETO. Verifica in particolare
    che l'ESPOSIZIONE scelta sia giustificata da dati e non da una previsione:
    scommessa nuda = VETO. Guardrail violato = VETO.
(b) GIUDIZIO (si dibatte): giudica l'universo di scan (temi ridondanti? classi
    scoperte?) e la scelta degli ETF (ce n'è uno più liquido/economico?); cerca
    posizioni che sono la stessa scommessa travestita (cluster del QUANT);
    esegui 3 STRESS TEST sui pesi proposti coi dati reali: (1) replica della
    peggiore finestra di 30 giorni del periodo, (2) crollo del 50% della
    componente più volatile, (3) correlazioni tra rischiosi a 0,9 con le vol
    correnti. Esamina le falsificazioni: boccia quelle vaghe o senza soglia.
    Chiedi: "perché questo dovrebbe battere lo SCHELETRO MECCANICO (stesse
    regole senza giudizio) e l'equal-weight 1/N fuori campione?" (DeMiguel 2009).
Invia veti e obiezioni numerate all'ARCHITETTO; al lead: veti rientrati,
obiezioni risolte/aperte, stress test.

OUTPUT FINALE (compilato dal lead, in questo ordine)
A. Universo di scan (tema -> ETF scelto -> motivazione) e fonte dati dichiarata
B. Classifica dello SCAN: voce -> trend (sopra/sotto SMA10m) -> momentum 12-1 ->
   eleggibile sì/no. Più il breadth (quante sopra trend su totale).
C. Portafoglio: top-N selezionati, ETF, peso %, contributo al rischio, cash %.
   Con la giustificazione DEL LIVELLO DI ESPOSIZIONE (dati, non previsioni).
D. Dashboard: vol attesa, correlazione media, diversification ratio, N effettivo,
   expected shortfall 95% empirico
E. Stress test dell'AVVOCATO: perdita stimata nei 3 scenari
F. Veti e obiezioni: rientrati / risolte / aperte (in chiaro)
G. Falsificazioni: per ogni scelta, trigger numerico + azione. Salvatele anche in
   memoria/falsificazioni.md e in memoria/trigger.json (machine-readable)
H. I 3 rischi principali
H2. ORIZZONTE MINIMO CALCOLATO: tabella durata (1/2/3/5 anni) -> % di finestre mobili
   chiuse in positivo, con la durata oltre cui si supera l'80% e il caveat sui leak.
   Scrivi il numero in costituzione/00_mandato.md al posto del segnaposto.
H3. DRAWDOWN dello scheletro: il più profondo (%, date) e il più lungo (durata, date).
   Vanno in memoria/tracker.md.
I. Verifica finale guardrail: vincolo -> rispettato sì/no -> margine
J. LISTA ORDINI: strumento, lato, quantità/importo indicativo, tipo (market o
   limit), una riga di motivazione. **Non potete eseguirli**: l'accesso al conto è
   in sola lettura, li esegue il presidente a mano. Rispettate il tetto di ordini della costituzione. Formattala in modo che
   sia copiabile senza ambiguità.
K. Journal entry #0 per memoria/journal.md: data, universo, breadth, segnali,
   decisione, razionale (5 righe), falsificazioni, e i due IMPEGNI A VERBALE:
   (1) se a 12 mesi lo scheletro meccanico batte l'AI su base risk-adjusted, si
   abbandona la discrezione; (2) se l'1/N li batte entrambi, si abbandona la
   struttura attiva.

VINCOLI DI PROCESSO
- Nessun agente prevede rendimenti o prezzi target.
- Se ARCHITETTO e AVVOCATO non convergono in 2 round, il disaccordo va nel
  report, non nascosto: decide il presidente (io).
- Ogni numero nel report deve essere ricalcolabile dal CSV.
- Nessuno esegue ordini: l'accesso al conto è in sola lettura e così deve restare.
