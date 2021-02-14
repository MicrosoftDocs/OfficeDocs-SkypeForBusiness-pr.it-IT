---
title: Dashboard integrità per l'instradamento diretto
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come usare il dashboard di integrità per monitorare la connessione tra il controller dei confini della sessione e l'instradamento diretto.
ms.openlocfilehash: a75510340815489921a5dd67a204b6914a9539d4
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229112"
---
# <a name="health-dashboard-for-direct-routing"></a>Dashboard integrità per l'instradamento diretto

Il dashboard di integrità per l'instradamento diretto consente di monitorare la connessione tra il controller dei confini della sessione (SBC) e l'interfaccia di routing diretto.  Health Dashboard consente di monitorare le informazioni su SBC, il servizio di telefonia e i parametri di rete tra SBC e l'interfaccia di routing diretto. Queste informazioni possono aiutarti a identificare i problemi, incluso il motivo delle chiamate eliminate. Ad esempio, il servizio SBC potrebbe interrompere l'invio di chiamate se un certificato nel dispositivo SBC è scaduto o se ci sono problemi di rete. Vedere i [ruoli di amministratore](using-admin-roles.md) per sapere chi ha accesso al dashboard dell'integrità.

Health Dashboard monitora due livelli di informazioni:

- Integrità complessiva dei pc connessi
- Informazioni dettagliate sugli SBC connessi

Puoi visualizzare il dashboard integrità nell'interfaccia di amministrazione di Microsoft Teams e Skype for Business.

## <a name="overall-health"></a>Integrità generale

Dashboard integrità fornisce le seguenti informazioni relative allo stato generale dei pc connessi:

 ![Mostra le statistiche del dashboard integrità](media/direct-routing-dashboard-stats1.png)

- **Riepilogo routing diretto** - Mostra il numero totale di SBC registrati nel sistema. La registrazione indica che l'amministratore del tenant ha aggiunto un database SBC usando il comando New-CsOnlinePSTNGateway tenant. Se il servizio SBC è stato aggiunto in PowerShell, ma non è mai connesso, il dashboard integrità lo mostra in stato non integro.

- **SBC:** nome di dominio completo del dominio SBC associato.

- **Network Effectiveness Ratio (NER)** - L'ENER misura la capacità di una rete di effettuare chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate effettuate a un destinatario.  

   La funzione NER misura la capacità delle reti di effettuare chiamate al terminale di distanza, escludendo le azioni dell'utente che causano il rifiuto delle chiamate.  Se il destinatario ha rifiutato una chiamata o lo ha inviato alla segreteria telefonica, la chiamata viene conteggiata come una consegna riuscita. Questo significa che un messaggio di risposta, un segnale di occupato o uno squillo senza risposta sono tutti considerati chiamate di successo.
  
   Ad esempio, si supponga che l'instradamento diretto abbia inviato una chiamata a SBC e che SBC restituisca il codice SIP "Timeout 504 Server - Il server ha provato ad accedere a un altro server nel tentativo di elaborare la richiesta e non ha ricevuto una risposta tempestiva". Questa risposta indica un problema sul lato SBC e l'operazione ridurrà il valore NER nel dashboard integrità per questo SBC.
  
   Poiché l'azione che si può eseguire dipende dal numero di chiamate interessate, il dashboard Integrità mostra quante chiamate sono state analizzate per calcolare un parametro. Se il numero di chiamate è inferiore a 100, il valore di NER potrebbe essere piuttosto basso, ma comunque normale.

   La formula utilizzata per calcolare NER è:

   NER = 100 x (Chiamate con risposta + Utente Occupato + Squillo senza risposta + Rifiutare in terminale)/Totale chiamate

- **Durata media delle chiamate** - Le informazioni sulla durata media delle chiamate possono aiutarti a monitorare la qualità delle chiamate. La durata media di una chiamata PSTN 1:1 è da quattro a cinque minuti.  Tuttavia, per ogni azienda, questa media può variare.  Microsoft consiglia di definire una base di riferimento per la durata media delle chiamate per l'azienda. Se questo parametro scende notevolmente al di sotto della linea di base, potrebbe indicare che gli utenti hanno problemi con la qualità delle chiamate o l'affidabilità e si stanno finisce a unirsi prima del solito. Se si inizia a vedere una durata di chiamata estremamente bassa, ad esempio 15 secondi, i chiamanti potrebbero riagganciare perché il servizio non sta eseguendo in modo affidabile.

   Poiché l'azione che si può eseguire dipende dal numero di chiamate interessate, il dashboard Integrità mostra quante chiamate sono state analizzate per calcolare un parametro.

- **Stato della connettività** TLS: la connettività TLS (Transport Layer Security) mostra lo stato delle connessioni TLS tra routing diretto e SBC. Dashboard integrità analizza anche la data di scadenza del certificato e segnala se un certificato è impostato per scadere entro 30 giorni in modo che gli amministratori possano rinnovare il certificato prima che il servizio venga interrotto.

   Facendo clic sul messaggio di avviso è possibile visualizzare una descrizione dettagliata del problema in una finestra popup a destra e suggerimenti su come risolverlo.

- **Stato delle opzioni SIP:** per impostazione predefinita, il servizio SBC invia messaggi di opzioni ogni minuto. Questa configurazione può variare a seconda del fornitore. L'instradamento diretto segnala se le opzioni SIP non sono inviate o non sono configurate. Per altre informazioni sul monitoraggio delle opzioni SIP e sulle condizioni in cui un SBC può essere contrassegnato come non funzionante, vedere Monitorare e risolvere i problemi di [routing diretto.](direct-routing-monitor-and-troubleshoot.md)

- **Stato dettagliato delle opzioni SIP** - Oltre a mostrare che c'è un problema con il flusso delle opzioni SIP, il dashboard di integrità fornisce anche descrizioni dettagliate degli errori. È possibile accedere alla descrizione facendo clic sul messaggio "Avviso". Una finestra popup a destra mostrerà la descrizione dettagliata dell'errore.

   I valori possibili per i messaggi di stato delle opzioni SIP sono i seguenti:

    - Attivo: il servizio SBC è attivo: il servizio di instradamento diretto Microsoft vede le opzioni che scorrono a intervalli regolari.

    - Avviso, nessuna opzione SIP: il controller dei confini della sessione esiste nel database (l'amministratore l'ha creato usando il comando New-CsOnlinePSTNGateway). È configurato per inviare le opzioni SIP, ma il servizio di routing diretto non ha mai visto le opzioni SIP che tornavano da questo SBC.

    - Avviso: i messaggi SIP non sono configurati: il monitoraggio del trunk con le opzioni SIP non è attivato. Il Sistema di chiamate Microsoft utilizza le opzioni SIP e il monitoraggio dell'handshake TLS (Transport Layer Security) per rilevare l'integrità dei controller dei confini della sessione connessi a livello dell'applicazione. Si verificano problemi se il trunk può essere raggiunto a livello di rete (tramite ping), ma il certificato è scaduto o lo stack SIP non funziona. Per individuare in anticipo questi problemi, Microsoft consiglia di abilitare l'invio delle opzioni SIP. Per configurare le opzioni di invio SIP, consultare la documentazione del produttore del servizio SBC.

- **Capacità di chiamate** simultanee - È possibile specificare il limite di chiamate contemporanee che un SBC può gestire usando il comando New- o Set-CsOnlinePSTNGateway con il parametro -MaxConcurrentSessions. Questo parametro calcola il numero di chiamate inviate o ricevute dal routing diretto usando un SBC specifico e le confronta con il limite impostato. Nota: se il servizio SBC gestisce anche le chiamate a diversi PBX, questo numero non mostrerà le chiamate contemporanee effettive.

## <a name="detailed-information-for-each-sbc"></a>Informazioni dettagliate per ogni SBC

È anche possibile visualizzare le informazioni dettagliate per uno specifico SBC, come illustrato nello screenshot seguente:

![Dettagli SBC del dashboard integrità](media/direct-routing-dashboard-SBC-detail1.png)

La visualizzazione dettagliata mostra i parametri aggiuntivi seguenti:

- **Stato di connettività TLS:** si tratta della stessa metrica disponibile nella pagina "Integrità generale";

- **Ultimo stato della connettività TLS:** indica l'ora in cui SBC ha effettuato una connessione TLS al servizio di instradamento diretto;

- **Stato delle opzioni SIP,** la stessa metrica della pagina "Integrità generale".

- **Le opzioni SIP sono state controllate per** l'ultima volta: ora in cui le opzioni SIP sono state ricevute l'ultima volta.

- **Stato SBC:** stato complessivo dell'SBC, in base a tutti i parametri monitorati.

- **Chiamata simultanea:** mostra il numero di chiamate contemporanee gestite dal servizio SBC. Queste informazioni sono utili per prevedere il numero di canali simultanei necessari e visualizzare la tendenza. È possibile scorrere i dati in base al numero di giorni e alla direzione della chiamata (in ingresso/uscita/tutti i flussi).

- **Parametri di rete:** tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al controller dei confini della sessione. Per informazioni sui valori consigliati, vedere Preparare la rete [dell'organizzazione](https://docs.microsoft.com/microsoftteams/prepare-network)per Microsoft Teams e osservare i valori consigliati da Customer Edge a Microsoft Edge.

   - Instabilità: misura in millisecondi della variazione del tempo di ritardo di propagazione della rete calcolata tra due endpoint utilizzando RTCP (RtP Control Protocol).

   - Perdita pacchetti: misura del pacchetto che non è riuscito ad arrivare; viene calcolata tra due endpoint.

   - La latenza - (nota anche come tempo di round trip) è il tempo di invio di un segnale più il tempo necessario per la conferma di ricezione del segnale. Questo ritardo è costituito dai tempi di propagazione tra i due punti di un segnale.

   È possibile scorrere i dati in base al numero di giorni e alla direzione della chiamata (in ingresso/uscita/tutti i flussi).

**Rapporto di efficacia della rete** - Si tratta dello stesso parametro visualizzato nel dashboard integrità generale, ma con l'opzione per suddividere i dati in base a serie temporale o direzione della chiamata.
