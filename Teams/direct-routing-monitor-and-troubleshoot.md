---
title: Monitorare l'instradamento diretto
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
description: Informazioni su come monitorare e risolvere i problemi relativi alla configurazione del routing diretto, inclusi i controller dei confini della sessione, i componenti Direct Routing e i trunk telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657246"
---
# <a name="monitor-direct-routing"></a>Monitorare l'instradamento diretto

Questo articolo descrive come monitorare e risolvere i problemi relativi alla configurazione del routing diretto. 

La possibilità di effettuare e ricevere chiamate utilizzando l'instradamento diretto prevede i componenti seguenti: 

- Session Border Controller (SBC) 
- Componenti di routing diretto in Microsoft Cloud 
- Tronchi di telecomunicazioni 

In caso di problemi di risoluzione dei problemi, è possibile aprire un caso di supporto con il fornitore di SBC o Microsoft. 

Microsoft sta lavorando per fornire altri strumenti per la risoluzione dei problemi e il monitoraggio. Consulta periodicamente la documentazione per gli aggiornamenti. 

## <a name="troubleshoot-direct-routing"></a>Risolvere i problemi relativi al routing diretto

Per risolvere i problemi relativi al routing diretto, vedere [Diagnosticare i problemi relativi al routing diretto](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitoraggio della disponibilità dei controller dei confini della sessione tramite i messaggi delle opzioni SIP (Session Initiation Protocol)

Il routing diretto utilizza le opzioni SIP inviate dai controller dei confini della sessione per monitorare l'integrità di SBC. Non sono necessarie azioni da parte dell'amministratore del tenant per abilitare il monitoraggio delle opzioni SIP. Le informazioni raccolte vengono prese in considerazione quando vengono prese le decisioni di routing. 

Ad esempio, se per un utente specifico sono disponibili diversi SBC per instradare una chiamata, Direct Routing considera le informazioni sulle opzioni SIP ricevute da ogni SBC per determinare il routing. 

Il diagramma seguente mostra un esempio di configurazione: 

![Esempio di configurazione delle opzioni SIP.](media/sip-options-config-example.png)

Quando un utente effettua una chiamata al numero +1 425 \<any seven digits>, il routing diretto valuta il percorso. Ci sono due SBC nel percorso: sbc1.contoso.com e sbc2.contoso.com. Entrambi gli SBC hanno la stessa priorità nel percorso. Prima di selezionare una scheda SBC, il meccanismo di routing valuta l'integrità degli SBC in base a quando l'SBC ha inviato le opzioni SIP l'ultima volta. 

Un SBC è considerato integro se le statistiche al momento dell'invio della chiamata mostrano che il SBC invia opzioni ogni minuto.  

Quando viene effettuata una chiamata, si applica la logica seguente:

- Il codice SBC è stato associato alle 11:00.  
- La scheda SBC invia le opzioni alle 11:01, alle 11:02 e così via.  
- Alle 11:15, un utente effettua una chiamata e il meccanismo di routing seleziona questo SBC. 

Il routing diretto accetta tre volte le opzioni relative all'intervallo regolare (l'intervallo regolare è di un minuto). Se le opzioni sono state inviate negli ultimi tre minuti, SBC è considerato integro.

Se la scheda SBC nell'esempio ha inviato opzioni in qualsiasi periodo compreso tra le 11:12 e le 11:15 (l'ora in cui è stata effettuata la chiamata), viene considerata integra. In caso contrario, l'SBC verrà abbassato di livello dal percorso. 

Abbassare di livello significa che la scheda SBC non verrà prima provata. Ad esempio, abbiamo sbc1.contoso.com e sbc2.contoso.com con uguale priorità.  

Se sbc1.contoso.com non invia le opzioni SIP a intervalli regolari come descritto in precedenza, viene abbassato di livello. Quindi, sbc2.contoso.com tenta la chiamata. Se sbc2.contoso.con non riesce a recapitare la chiamata, il sbc1.contoso.com (abbassato di livello) viene riprovato prima di generare un errore. 

Se due (o più) SBC in una route sono considerati integri e uguali, Fisher-Yates shuffle viene applicato per distribuire le chiamate tra gli SBC.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitorare il dashboard di Call Quality Analytics e i log SBC 
 
In alcuni casi, in particolare durante l'associazione iniziale, potrebbero verificarsi problemi relativi a una configurazione errata degli SBC o del servizio Di routing diretto. 

È possibile utilizzare gli strumenti seguenti per monitorare la configurazione:  
 
- Dashboard qualità delle chiamate 
- Registri SBC 

Il servizio Direct Routing include codici di errore descrittivi segnalati a Call Analytics o ai log SBC.

Call Quality Dashboard fornisce informazioni sulla qualità e sull'affidabilità delle chiamate. Per altre informazioni su come risolvere i problemi relativi all'uso di Call Analytics, vedere [Attivazione e utilizzo di Call Quality Dashboard per Microsoft Teams e Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e [Usare Call Analytics per risolvere problemi di bassa qualità delle chiamate](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

In caso di errori di chiamata, Call Analytics fornisce codici SIP standard per facilitare la risoluzione dei problemi. 

![Codice SIP di esempio per un errore di chiamata.](media/failed-response-code.png)

Tuttavia, Call Analytics può aiutare solo quando le chiamate raggiungono i componenti interni del routing diretto e non riescono. In caso di problemi di associazione SBC o di rifiuto di "Invito" SIP (ad esempio, il nome fqdn del trunk non è configurato correttamente), Call Analytics non consente di risolvere il problema. In questo caso, fare riferimento ai log SBC. Direct Routing invia una descrizione dettagliata dei problemi agli SBC; questi problemi possono essere letti dai log di SBC.
