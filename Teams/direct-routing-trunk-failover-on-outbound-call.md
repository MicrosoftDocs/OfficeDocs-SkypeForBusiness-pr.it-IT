---
title: Failover trunk sulle chiamate in uscita
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leggere questo argomento per informazioni su come gestire il failover trunk sulle chiamate in uscita da Teams al controller dei confini della sessione (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836178"
---
# <a name="trunk-failover-on-outbound-calls"></a>Failover trunk sulle chiamate in uscita

Questo argomento descrive come evitare il failover trunk sulle chiamate in uscita, da Teams al controller dei confini della sessione (SBC).

## <a name="failover-on-network-errors"></a>Failover sugli errori di rete

Se non è possibile connettersi a un trunk per qualsiasi motivo, la connessione allo stesso trunk verrà provata da un data center Microsoft diverso. Un trunk potrebbe non essere connesso, ad esempio se una connessione viene rifiutata, se c'è un timeout TLS o se ci sono altri problemi a livello di rete.
Ad esempio, una connessione potrebbe non riuscire se un amministratore limita l'accesso a SBC solo da indirizzi IP noti, dimenticando di inserire gli indirizzi IP di tutti i data center microsoft Direct Routing nell'elenco di controllo di accesso (ACL) del database SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover di codici SIP specifici ricevuti dal controller dei confini della sessione (SBC)

Se l'instradamento diretto riceve codici di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita. In uscita significa una chiamata da un client di Teams alla rete PSTN (Public Switched Telephone Network) con il flusso di traffico seguente: Client Teams -> Direct Routing -> SBC -> Telephony network.

L'elenco dei codici SIP è disponibile in [RFC (Session Initiation Protocol) (SIP).](https://tools.ietf.org/html/rfc3261)

Si supponga che un database SBC ha risposto a un invito in arrivo con codice "Timeout richiesta 408: il server non è stato in grado di produrre una risposta entro un periodo di tempo appropriato, ad esempio se non è stato possibile determinare la posizione dell'utente in tempo. Il client POTREBBE ripetere la richiesta senza modifiche in qualsiasi momento."

Questo particolare SBC potrebbe avere difficoltà a connettersi al chiamato, ad esempio a causa di una configurazione errata della rete o di altro tipo. Tuttavia, nel percorso è presente un altro SBC che potrebbe essere in grado di raggiungere il chiamato.

Nel diagramma seguente, quando un utente effettua una chiamata a un numero di telefono, nel percorso sono presenti due SBC che potrebbero recapitare la chiamata. Inizialmente, SBC1.contoso.com è selezionata per la chiamata, ma SBC1.contoso.com non è in grado di raggiungere una rete PTSN a causa di un problema di rete.
Per impostazione predefinita, la chiamata verrà completata in questo momento. 
 
![Diagramma che mostra che SBC non riesce a raggiungere PSTN a causa di un problema di rete](media/direct-routing-failover-response-codes1.png)

Ma c'è un altro SBC nel percorso che potenzialmente può recapitare la chiamata.
Se si configura il parametro, verrà provato il secondo `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC, SBC2.contoso.com nel diagramma seguente:

![Diagramma che mostra il routing al secondo SBC](media/direct-routing-failover-response-codes2.png)

L'impostazione del parametro -FailoverResponseCodes e l'impostazione dei codici consente di ottimizzare il routing ed evitare potenziali problemi quando un servizio SBC non può effettuare una chiamata a causa di problemi di rete o di altro tipo.

Valori predefiniti: 408, 503, 504

