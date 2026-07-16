# Esecuzione — manuale, sempre

> ⚠️ TEMPLATE — `/setup` compila broker e costi. La regola di fondo non è configurabile.

## Il fatto strutturale

**L'esecuzione è al 100% manuale.** Il sistema non ha alcun percorso tecnico per
piazzare, modificare o annullare un ordine — e non deve cercarlo.

Se colleghi il broker (es. Interactive Brokers via MCP), l'accesso è in **sola lettura**:
il sistema legge il conto, non lo tocca. Se non lo colleghi, gli dai tu lo stato del
conto: cambia solo la comodità, non il metodo.

## Separazione dei dati (architettura)

| Cosa | Da dove | Perché |
|---|---|---|
| Prezzi, storia, segnali | **Fonte pubblica gratuita**, scaricata al momento e salvata in `memoria/dati/` | Riproducibile da chiunque, anche senza broker |
| Stato del conto: posizioni, cash, P&L, costi reali | **Broker in sola lettura**, oppure lo fornisci tu al comitato | È il denaro vero: non deve essere gonfiabile |
| Esecuzione | **Le tue mani** | Nessuna delega, nessuna eccezione |

Se le due fonti divergono in modo rilevante, si indaga **prima** di decidere.

## Configurazione (da `/setup`)

- **Broker**: `[…]`
- **Lettura del conto**: `[collegato in sola lettura / fornito a mano al comitato]`
- **Costo per operazione**: `[commissione + spread stimato]`
- **Importo minimo per operazione**: `[…]`
- **Valuta di riferimento**: `[…]`

## Cosa l'AI NON può fare — mai

- Eseguire, pre-caricare o instradare ordini in qualunque forma. Non cercare API
  alternative, altri broker o script per aggirare il limite.
- **Sollecitare** l'esecuzione ("conviene farlo subito", "sbrigati"): l'urgenza non è un
  dato. Il comitato è mensile per costruzione.
- Muovere denaro, prelevare, depositare, cambiare impostazioni del conto.
- Usare leva, derivati o prodotti fuori mandato, anche se il conto li consentisse.

## Il ciclo

1. **Lettura** — stato del conto + **snapshot nel journal**: la decisione dev'essere
   auditabile a posteriori coi dati di allora.
2. **Comitato** — si delibera. Default: **nessuna azione**.
3. **Proposta** — lista ordini in chiaro, max `[6]`, copiabile senza ambiguità.
4. **Esecuzione** — **la fai tu**, sul tuo broker. Se scarti un ordine o lo esegui
   diverso, va a journal **col motivo**: è informazione sul sistema, non un capriccio.
5. **Riconciliazione** — al comitato dopo, l'AI rilegge il conto e verifica:
   - strumenti eseguiti = strumenti deliberati?
   - pesi ottenuti = target (tolleranza ±1 punto)?
   - **costi reali vs stimati**? Se sistematicamente sottostimati, il metodo si corregge
     alla review trimestrale.
   - esposizione dentro le bande?

## L'attrito è una funzionalità

Eseguire a mano è lento e noioso: **è un pregio.** È l'ultima difesa contro il churn e
contro te stesso in una giornata storta. Perciò: cadenza mensile, default nessuna azione,
e una regola personale — **se ti accorgi di eseguire senza aver letto il perché, fermati.
Il sistema è già rotto.**

## Messa in servizio (una volta sola)

1. **A secco**: un ciclo completo (comitato + lista ordini + riconciliazione) senza
   eseguire nulla, per vedere se i numeri tornano.
2. Verifica che la lista ordini corrisponda ai pesi deliberati.
3. Solo dopo, il conto reale — col capitale del mandato e nient'altro.
