---
title: Monitorare e risolvere i problemi di Instradamento diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come monitorare e risolvere i problemi di configurazione del routing diretto, inclusi i controller dei confini della sessione, i componenti di routing diretto e i trunk di Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901911"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Monitorare e risolvere i problemi di Instradamento diretto

Questo articolo descrive come monitorare e risolvere i problemi di configurazione del routing diretto. 

La possibilità di effettuare e ricevere chiamate con l'instradamento diretto implica l'uso dei seguenti componenti: 

- Controller dei confini della sessione (SBC) 
- Componenti di routing diretto in Microsoft Cloud 
- Trunks di telecomunicazioni 

In caso di difficoltà nella risoluzione dei problemi, è possibile aprire un caso di supporto con il fornitore SBC o Microsoft. 

Microsoft sta lavorando per fornire altri strumenti per la risoluzione dei problemi e il monitoraggio. Controlla periodicamente la documentazione per aggiornamenti. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitoraggio della disponibilità dei controller dei confini della sessione con i messaggi delle opzioni SIP (Session Initiation Protocol)

Il routing diretto usa le opzioni SIP inviate dai controller dei confini della sessione per monitorare l'integrità di SBC. Non sono necessarie azioni da parte dell'amministratore del tenant per abilitare il monitoraggio delle opzioni SIP. Le informazioni raccolte vengono prese in considerazione quando vengono prese decisioni di routing. 

Ad esempio, se per un utente specifico sono disponibili diversi SBC per instradare una chiamata, l'instradamento diretto considera le informazioni sulle opzioni SIP ricevute da ogni SBC per determinare il routing. 

Il diagramma seguente mostra un esempio della configurazione: 

![Esempio di configurazione delle opzioni SIP](media/sip-options-config-example.png)

Quando un utente effettua una chiamata al numero +1 425 qualsiasi sette>, l'instradamento diretto \< valuta il percorso. Nel percorso sono presenti due SBC: sbc1.contoso.com e sbc2.contoso.com. Entrambi gli SBC hanno la stessa priorità nel percorso. Prima di scegliere un valore SBC, il meccanismo di routing valuta l'integrità dei server SBC in base all'ultima volta in cui SBC ha inviato le opzioni SIP. 

Un SBC viene considerato integro se le statistiche al momento dell'invio della chiamata mostrano che SBC invia opzioni ogni minuto.  

Quando viene effettuata una chiamata, si applica la logica seguente:

- Il campo SBC è stato abbinato alle 11:00.  
- L'indirizzo SBC invia le opzioni alle 11:01, alle 11:02 e così via.  
- Alle 11:15 un utente effettua una chiamata e il meccanismo di routing seleziona questo SBC. 

L'instradamento diretto accetta le opzioni a intervalli regolari tre volte (l'intervallo regolare è di un minuto). Se le opzioni sono state inviate negli ultimi tre minuti, L'SBC è considerato integro.

Se il valore SBC nell'esempio ha inviato opzioni in qualsiasi periodo tra le 11:12 e le 11:15 (l'ora in cui è stata effettuata la chiamata), è considerato integro. In caso contrario, il valore SBC verrà abbassato di livello rispetto al percorso. 

L'abbassamento di livello indica che il valore SBC non verrà provato prima. Ad esempio, abbiamo sbc1.contoso.com e sbc2.contoso.com con la stessa priorità.  

Se sbc1.contoso.com opzioni SIP non vengono inviate a intervalli regolari come descritto in precedenza, le opzioni vengono abbassate di livello. Quindi, sbc2.contoso.com la chiamata. Se sbc2.contoso.con non riesce a recapitare la chiamata, il sbc1.contoso.com (abbassato di livello) viene riprovato prima che venga generato un errore. 

Se due (o più) SBC in un percorso sono considerati integri e uguali, viene Fisher-Yates chiamata casuale per distribuire le chiamate tra gli SBC.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitorare il dashboard Call Quality Analytics e i log SBC 
 
In alcuni casi, in particolare durante l'associazione iniziale, potrebbero verificarsi problemi relativi a una configurazione errata del servizio di routing diretto o SBCs. 

È possibile usare gli strumenti seguenti per monitorare la configurazione:  
 
- Dashboard qualità delle chiamate 
- Log SBC 

Il servizio di instradamento diretto ha codici di errore molto descrittivi segnalati ai log di Call Analytics o SBC. 

Call Quality Dashboard fornisce informazioni sulla qualità e l'affidabilità delle chiamate. Per ulteriori informazioni su come risolvere i problemi con Call Analytics, consulta Attivazione e utilizzo di Call Quality Dashboard per Microsoft Teams e [Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e Uso di Call Analytics per risolvere i problemi di bassa qualità delle [chiamate.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

In caso di errori di chiamata, Call Analytics fornisce codici SIP standard per facilitare la risoluzione dei problemi. 

![Esempio di codice SIP per l'errore di chiamata](media/failed-response-code.png)

Tuttavia, Call Analytics può essere utile solo quando le chiamate raggiungono i componenti interni dell'instradamento diretto e hanno esito negativo. In caso di problemi con l'associazione SBC o problemi in cui SIP "Invito" è stato rifiutato (ad esempio, il nome dell'FQDN trunk non è configurato correttamente), Call Analytics non sarà di aiuto. In questo caso, fare riferimento ai log SBC. Il routing diretto invia una descrizione dettagliata dei problemi agli SBC; questi problemi possono essere letti dai log SBC. 
