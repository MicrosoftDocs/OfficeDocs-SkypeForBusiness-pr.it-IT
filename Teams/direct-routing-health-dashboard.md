---
title: Dashboard integrità per il routing diretto
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come usare Health Dashboard per monitorare la connessione tra Session Border Controller e Direct Routing.
ms.openlocfilehash: 4927f6473e74a6fc14add9105022fc8efbade260
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728215"
---
# <a name="health-dashboard-for-direct-routing"></a>Dashboard integrità per il routing diretto

Health Dashboard for Direct Routing consente di monitorare la connessione tra session border controller (SBC) e l'interfaccia Direct Routing.  Con Health Dashboard è possibile monitorare le informazioni su SBC, il servizio di telefonia e i parametri di rete tra SBC e l'interfaccia di routing diretto. Queste informazioni consentono di identificare i problemi, incluso il motivo delle chiamate perse. Ad esempio, L'SBC potrebbe interrompere l'invio di chiamate se un certificato sul SBC è scaduto o se ci sono problemi di rete. Per informazioni [su chi](using-admin-roles.md) ha accesso al dashboard integrità, vedere i ruoli di amministratore.

Health Dashboard monitora due livelli di informazioni:

- Integrità generale degli SBC connessi
- Informazioni dettagliate sugli SBC connessi

È possibile visualizzare il dashboard integrità nell'Microsoft Teams e Skype for Business di amministrazione.

## <a name="overall-health"></a>Integrità generale

Dashboard integrità fornisce le informazioni seguenti relative all'integrità generale degli SBC connessi:

 ![Mostra le statistiche del dashboard integrità.](media/direct-routing-dashboard-stats1.png)

- **Riepilogo routing diretto:** mostra il numero totale di SBC registrati nel sistema. La registrazione significa che l'amministratore del tenant ha aggiunto un SBC usando il comando New-CsOnlinePSTNGateway database. Se il valore SBC è stato aggiunto in PowerShell, ma non è mai stato connesso, il dashboard integrità lo mostra in uno stato non integro.

- **SBC:** FQDN dell'SBC associato.

- **Network Effectiveness Ratio (NER)** - Il NER misura la capacità di una rete di effettuare chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate recapitate a un destinatario.  

   L'NER misura la capacità delle reti di effettuare chiamate al terminale remoto, escludendo le azioni degli utenti che causano il rifiuto delle chiamate.  Se il destinatario ha rifiutato una chiamata o ha inviato la chiamata alla segreteria telefonica, la chiamata viene conteggiata come recapito riuscito. Questo significa che un messaggio di risposta, un segnale di occupato o un anello senza risposta sono tutti considerati chiamate riuscite.
  
   Si supponga, ad esempio, che Routing diretto abbia inviato una chiamata a SBC e che SBC restituisca il codice SIP "Timeout del server 504 - Il server ha tentato di accedere a un altro server nel tentativo di elaborare la richiesta e non ha ricevuto una risposta rapida". Questa risposta indica che c'è un problema sul lato SBC e questo ridurrà il valore NER nel dashboard integrità per questo SBC.
  
   Poiché l'azione eseguita può dipendere dal numero di chiamate interessate, dashboard integrità mostra quante chiamate sono state analizzate per calcolare un parametro. Se il numero di chiamate è inferiore a 100, il valore NER potrebbe essere piuttosto basso, ma comunque normale.

   La formula usata per calcolare NER è:

   NER = 100 x (Chiamate con risposta + Utente occupato + Chiama senza risposta + Rifiuta convulsioni terminali)/Totale chiamate

- **Durata media delle chiamate:** le informazioni sulla durata media delle chiamate possono aiutare a monitorare la qualità delle chiamate. La durata media di una chiamata PSTN 1:1 è di 4-5 minuti.  Tuttavia, per ogni società, questa media può variare.  Microsoft consiglia di stabilire una previsione per la durata media delle chiamate per l'azienda. Se questo parametro scende significativamente al di sotto della linea di base, potrebbe indicare che gli utenti hanno problemi con la qualità o l'affidabilità delle chiamate e che si sono sospesi prima del solito. Se si inizia a vedere una durata media delle chiamate estremamente bassa, ad esempio 15 secondi, i chiamanti potrebbero essere sospesi perché il servizio non esegue in modo affidabile.

   Poiché l'azione eseguita può dipendere dal numero di chiamate interessate, dashboard integrità mostra quante chiamate sono state analizzate per calcolare un parametro.

- **Stato connettività TLS** : la connettività TLS (Transport Layer Security) mostra lo stato delle connessioni TLS tra Routing diretto e SBC. Dashboard integrità analizza anche la data di scadenza del certificato e avvisa se un certificato è impostato per scadere entro 30 giorni, in modo che gli amministratori possano rinnovare il certificato prima dell'interruzione del servizio.

   Facendo clic sul messaggio Avviso, è possibile visualizzare una descrizione dettagliata del problema in una finestra popup a destra e suggerimenti su come risolvere il problema.

- **Stato delle opzioni SIP:** per impostazione predefinita, SBC invia messaggi di opzioni ogni minuto. Questa configurazione può variare per i diversi fornitori SBC. Routing diretto avvisa se le opzioni SIP non vengono inviate o non sono configurate. Per altre informazioni sul monitoraggio delle opzioni SIP e sulle condizioni in cui un SBC può essere contrassegnato come non funzionante, vedere Monitorare e risolvere [i problemi relativi al routing diretto.](direct-routing-monitor-and-troubleshoot.md)

- Stato dettagliato delle opzioni **SIP:** oltre a mostrare che esiste un problema con il flusso delle opzioni SIP, il dashboard integrità fornisce anche descrizioni dettagliate degli errori. È possibile accedere alla descrizione facendo clic sul messaggio "Avviso". Una finestra popup a destra mostrerà la descrizione dettagliata dell'errore.

   I valori possibili per i messaggi di stato delle opzioni SIP sono i seguenti:

    - Attivo: il servizio SBC è attivo: il servizio Microsoft Direct Routing vede le opzioni che scorrono a intervalli regolari.

    - Avviso, nessuna opzione SIP: il session border controller è presente nel database (l'amministratore l'ha creato usando il comando New-CsOnlinePSTNGateway). È configurato per l'invio di opzioni SIP, ma il servizio Routing diretto non ha mai visto le opzioni SIP che tornavano da questo SBC.

    - Avviso: i messaggi SIP non sono configurati: il monitoraggio trunk con le opzioni SIP non è attivato. Microsoft Calling System usa le opzioni SIP e il monitoraggio dell'handshake Transport Layer Security (TLS) per rilevare l'integrità dei session border controller (SBC) connessi a livello di applicazione. Si verificano problemi se questo trunk può essere raggiunto a livello di rete (tramite ping), ma il certificato è scaduto o lo stack SIP non funziona. Per identificare in anticipo questi problemi, Microsoft consiglia di abilitare le opzioni SIP di invio. Consultare la documentazione del produttore SBC per configurare le opzioni SIP di invio.

- **Capacità chiamate simultanee:** è possibile specificare il limite di chiamate simultanee che un SBC può gestire usando il comando New o Set-CsOnlinePSTNGateway con il parametro -MaxConcurrentSessions. Questo parametro calcola il numero di chiamate inviate o ricevute da Direct Routing usando uno specifico SBC e le confronta con il limite impostato. Nota: se SBC gestisce anche le chiamate a diversi PBX, questo numero non mostrerà le chiamate simultanee effettive.

## <a name="detailed-information-for-each-sbc"></a>Informazioni dettagliate per ogni SBC

È anche possibile visualizzare le informazioni dettagliate per uno specifico SBC, come illustrato nello screenshot seguente:

![Dettagli SBC del dashboard integrità.](media/direct-routing-dashboard-SBC-detail1.png)

La visualizzazione dettagliata mostra i parametri aggiuntivi seguenti:

- **Stato connettività TLS:** questa è la stessa metrica della pagina "Integrità generale".

- **Ultimo stato della connettività TLS:** mostra l'ora in cui il servizio SBC ha effettuato una connessione TLS al servizio routing diretto.

- **Stato delle opzioni SIP:** la stessa metrica della pagina "Integrità generale".

- **Opzioni SIP selezionate per l'ultima** volta: l'ora in cui le opzioni SIP sono state ricevute l'ultima volta.

- **Stato SBC:** stato generale della SBC, in base a tutti i parametri monitorati.

- **Chiamata simultanea:** mostra il numero di chiamate simultanee gestite da SBC. Queste informazioni sono utili per prevedere il numero di canali simultanei necessari e visualizzare la tendenza. È possibile scorrere i dati in base al numero di giorni e alla direzione della chiamata (in ingresso/uscita/tutti i flussi).

- **Parametri di rete:** tutti i parametri di rete vengono misurati dall'interfaccia Di routing diretto al Session Border Controller. Per informazioni sui valori consigliati, vedere Preparare la rete [dell'organizzazione](./prepare-network.md)per Microsoft Teams e osservare Customer Edge per Microsoft Edge valori consigliati.

   - Instabilità: misura in millisecondo della variazione del tempo di ritardo della propagazione della rete calcolata tra due endpoint usando RTCP (RtP Control Protocol).

   - Perdita di pacchetti: misura del pacchetto che non è riuscito ad arrivare. viene calcolato tra due endpoint.

   - Latenza- (noto anche come tempo di andata e ritorno) è il tempo necessario per l'invio di un segnale più il tempo necessario per la ricezione del riconoscimento del segnale. Questo ritardo è costituito dai tempi di propagazione tra i due punti di un segnale.

   È possibile scorrere i dati in base al numero di giorni e alla direzione della chiamata (in ingresso/uscita/tutti i flussi).

**Rapporto efficacia rete:** questo è lo stesso parametro visualizzato nel dashboard Integrità generale, ma con l'opzione per suddividere i dati in base alla serie temporale o alla direzione della chiamata.