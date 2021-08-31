---
title: Monitorare e risolvere i problemi di Instradamento diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come monitorare e risolvere i problemi di configurazione del routing diretto, inclusi i controller dei bordi delle sessioni, i componenti di routing diretto e i trunk di Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aeff22bf3558c64111f0d1b66c2fd76288f81477
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726885"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Monitorare e risolvere i problemi di Instradamento diretto

Questo articolo descrive come monitorare e risolvere i problemi relativi alla configurazione del routing diretto. 

La possibilità di effettuare e ricevere chiamate tramite Routing diretto implica i componenti seguenti: 

- Session Border Controller (SBC) 
- Componenti di Routing diretto in Microsoft Cloud 
- Tronchi di telecomunicazione 

In caso di problemi di risoluzione dei problemi, è possibile aprire un caso di supporto con il fornitore SBC o Microsoft. 

Microsoft sta lavorando alla fornitura di altri strumenti per la risoluzione dei problemi e il monitoraggio. Controllare periodicamente la documentazione per gli aggiornamenti. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitoraggio della disponibilità dei session border controller tramite i messaggi di opzioni SIP (Session Initiation Protocol)

Il routing diretto usa le opzioni SIP inviate dai session border controller per monitorare l'integrità di SBC. Non sono necessarie azioni da parte dell'amministratore tenant per abilitare il monitoraggio delle opzioni SIP. Le informazioni raccolte vengono prese in considerazione quando si prendono decisioni relative al routing. 

Ad esempio, se per un utente specifico sono disponibili diversi SBC per instradare una chiamata, Direct Routing considera le informazioni sulle opzioni SIP ricevute da ogni SBC per determinare il routing. 

Il diagramma seguente mostra un esempio della configurazione: 

![Esempio di configurazione delle opzioni SIP.](media/sip-options-config-example.png)

Quando un utente effettua una chiamata al numero +1 425, \<any seven digits> Direct Routing valuta il percorso. Ci sono due SBC nel percorso: sbc1.contoso.com e sbc2.contoso.com. Entrambi gli SBC hanno la stessa priorità nel percorso. Prima di scegliere un SBC, il meccanismo di routing valuta l'integrità degli SBC in base all'ultima volta in cui il servizio SBC ha inviato le opzioni SIP. 

Un SBC è considerato integro se le statistiche al momento dell'invio della chiamata mostrano che SBC invia opzioni ogni minuto.  

Quando viene effettuata una chiamata, si applica la logica seguente:

- Il valore SBC è stato associato alle 11:00.  
- L'SBC invia le opzioni alle 11:01, alle 11:02 e così via.  
- Alle 11:15, un utente effettua una chiamata e il meccanismo di routing seleziona questo SBC. 

Routing diretto accetta le opzioni di intervallo normale tre volte (l'intervallo normale è di un minuto). Se le opzioni sono state inviate negli ultimi tre minuti, il valore SBC è considerato integro.

Se l'SBC nell'esempio ha inviato opzioni in qualsiasi periodo compreso tra le 11:12 e le 11:15 (ora in cui è stata effettuata la chiamata), viene considerato integro. In caso contrario, il valore SBC verrà abbassato di livello dal percorso. 

L'abbassamento di livello indica che il valore SBC non verrà provato prima. Ad esempio, abbiamo sbc1.contoso.com e sbc2.contoso.com con la stessa priorità.  

Se sbc1.contoso.com le opzioni SIP non vengono inviate a intervalli regolari come descritto in precedenza, viene abbassata di livello. Quindi, sbc2.contoso.com la chiamata. Se sbc2.contoso.con non riesce a recapitare la chiamata, il sbc1.contoso.com (abbassato di livello) viene riprovato prima che venga generato un errore. 

Se due (o più) SBC in un percorso sono considerati integri e uguali, viene applicato Fisher-Yates shuffle per distribuire le chiamate tra gli SBC.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitorare il dashboard di Call Quality Analytics e i log SBC 
 
In alcuni casi, in particolare durante l'associazione iniziale, potrebbero verificarsi problemi relativi a una configurazione errata degli SBC o del servizio di routing diretto. 

Per monitorare la configurazione, è possibile usare gli strumenti seguenti:  
 
- Dashboard qualità delle chiamate 
- Log SBC 

Il servizio Routing diretto ha codici di errore molto descrittivi riportati nei log di Call Analytics o SBC. 

Il dashboard qualità chiamata fornisce informazioni sulla qualità e l'affidabilità delle chiamate. Per altre informazioni su come risolvere i problemi con Call Analytics, vedere Attivare e usare Call Quality Dashboard per Microsoft Teams e [Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e Usare Call Analytics per risolvere i problemi di qualità scarsa delle [chiamate.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

In caso di errori di chiamata, Call Analytics fornisce codici SIP standard per facilitare la risoluzione dei problemi. 

![Codice SIP di esempio per l'errore di chiamata.](media/failed-response-code.png)

Tuttavia, Call Analytics può essere utile solo quando le chiamate raggiungono i componenti interni di Direct Routing e non riescono. In caso di problemi con l'associazione SBC o problemi in cui "Invito" SIP è stato rifiutato (ad esempio, il nome dell'FQDN del trunk non è configurato correttamente), Call Analytics non aiuterà. In questo caso, fare riferimento ai log SBC. Il routing diretto invia una descrizione dettagliata dei problemi agli SBC; questi problemi possono essere letti dai log SBC.