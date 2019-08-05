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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Leggere questo argomento per informazioni su come gestire i failover trunk sulle chiamate in uscita da Teams a session border controller (SBC).
ms.openlocfilehash: 5c456aab52159859112b44c19c1b15fe81bc6293
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183739"
---
# <a name="trunk-failover-on-outbound-calls"></a>Failover trunk sulle chiamate in uscita

Questo argomento descrive come evitare i failover trunk sulle chiamate in uscita, da Teams a session border controller (SBC).

## <a name="failover-on-network-errors"></a>Failover sugli errori di rete

Se non è possibile connettere un trunk per qualsiasi motivo, la connessione allo stesso trunk verrà provata da un Data Center Microsoft diverso. Un trunk potrebbe non essere connesso, ad esempio se è stata rifiutata una connessione, se è presente un timeout TLS o se sono presenti altri problemi relativi al livello di rete.
Ad esempio, una connessione potrebbe non riuscire se un amministratore limita l'accesso a SBC solo da indirizzi IP noti, ma dimentica di inserire gli indirizzi IP di tutti i datacenter di routing Microsoft Direct nell'elenco di controllo di accesso (ACL) di SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover di codici SIP specifici ricevuti da Session Border Controller (SBC)

Se il routing diretto riceve qualsiasi codice di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita. In uscita si intende una chiamata da un client teams alla rete PSTN (Public Switched Telephone Network) con il flusso di traffico seguente: teams client-> Direct routing-> SBC-> rete di telefonia.

L'elenco dei codici SIP può essere trovato nella [RFC SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3261).

Si presuppone una situazione in cui un SBC ha risposto in un invito in arrivo con il codice "408 Request Timeout: il server non ha potuto produrre una risposta entro un periodo di tempo appropriato, ad esempio se non è in grado di determinare la posizione dell'utente nel tempo. Il client può ripetere la richiesta senza apportare modifiche in un secondo momento. "

Questo particolare SBC potrebbe avere difficoltà a connettersi al chiamato, magari a causa di una disconfigurazione della rete o di un altro errore. Tuttavia, c'è un altro SBC nella route che potrebbe essere in grado di raggiungere il chiamato.

Nel diagramma seguente, quando un utente effettua una chiamata a un numero di telefono, esistono due SBCs nella route che possono potenzialmente recapitare la chiamata. Inizialmente, SBC1.contoso.com è selezionato per la chiamata, ma SBC1.contoso.com non è in grado di raggiungere una rete PTSN a causa di un problema di rete.
Per impostazione predefinita, la chiamata verrà completata in questo momento. 
 
![Diagramma che mostra SBC che non riesce a raggiungere la rete PSTN a causa di un problema](media/direct-routing-failover-response-codes1.png)

Ma c'è un altro SBC nella route che può potenzialmente consegnare la chiamata.
Se si configura il parametro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, verrà provato il secondo SBC--SBC2.contoso.com nel diagramma seguente:

![Diagramma che mostra il routing per il secondo SBC](media/direct-routing-failover-response-codes2.png)

Impostando il parametro-FailoverResponseCodes e specificando i codici è possibile ottimizzare il routing ed evitare potenziali problemi quando un SBC non può effettuare una chiamata a causa di problemi di rete o altri.

Valori predefiniti: 408, 503, 504

