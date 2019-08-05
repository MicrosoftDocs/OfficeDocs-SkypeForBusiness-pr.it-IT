---
title: Monitorare e risolvere i problemi di routing diretto
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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Questo articolo descrive come monitorare e risolvere i problemi di configurazione del routing diretto.
ms.openlocfilehash: d20a409c7a5e902149ff20e72dde90850f0f5d12
ms.sourcegitcommit: 9751f34318119991b1bd32b384b8e1479c83cb0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2019
ms.locfileid: "36184861"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Monitorare e risolvere i problemi di routing diretto

Questo articolo descrive come monitorare e risolvere i problemi di configurazione del routing diretto. 

La possibilità di effettuare e ricevere chiamate tramite routing diretto include i componenti seguenti: 

- Controller bordo sessione (SBCs) 
- Componenti di routing diretto in Microsoft Cloud 
- Trunks Telecom 

In caso di difficoltà di risoluzione dei problemi, aprire una causa di supporto con il fornitore SBC o Microsoft. 

Microsoft sta lavorando per fornire altri strumenti per la risoluzione dei problemi e il monitoraggio. Verificare periodicamente la documentazione relativa agli aggiornamenti. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Monitoraggio della disponibilità dei controller di bordo della sessione con i messaggi delle opzioni SIP (Session Initiation Protocol)

Il routing diretto USA le opzioni SIP inviate dai controller di bordo della sessione per monitorare l'integrità di SBC. L'amministratore del tenant non deve eseguire alcuna azione per abilitare il monitoraggio delle opzioni SIP. Le informazioni raccolte vengono prese in considerazione quando vengono apportate decisioni di routing. 

Ad esempio, se per un utente specifico sono disponibili diverse SBCs per instradare una chiamata, il routing diretto considera le informazioni sulle opzioni SIP ricevute da ogni SBC per determinare il routing. 

Il diagramma seguente mostra un esempio di configurazione: 

![Esempio di configurazione delle opzioni SIP](media/sip-options-config-example.png)

Quando un utente effettua una chiamata al numero + 1 425 \<le sette cifre>, il routing diretto valuta la route. Nella route sono presenti due SBCs: sbc1.contoso.com e sbc2.contoso.com. Entrambe le SBCs hanno la stessa priorità nella route. Prima di selezionare un SBC, il meccanismo di routing valuta lo stato di SBCs in base al momento in cui il SBC ha inviato le opzioni SIP l'ultima volta. 

Un SBC viene considerato integro se le statistiche al momento dell'invio della chiamata indicano che il SBC Invia le opzioni ogni minuto.  

Quando viene eseguita una chiamata, viene applicata la logica seguente:

- Il SBC è stato associato a 11,00 AM.  
- Il SBC Invia le opzioni in 11,01 AM, 11,02 AM e così via.  
- In 11,15, un utente effettua una chiamata e il meccanismo di routing seleziona questo SBC. 

Il routing diretto richiede tre volte le opzioni di intervalli regolari (l'intervallo regolare è di un minuto). Se le opzioni sono state inviate durante gli ultimi tre minuti, l'SBC viene considerato integro.

Se il SBC nell'esempio ha inviato le opzioni in qualsiasi periodo compreso tra 11,12 AM e 11,15 AM (l'ora in cui è stata effettuata la chiamata), viene considerato integro. In caso contrario, l'SBC verrà retrocesso dalla route. 

L'abbassamento indica che l'SBC non verrà provato per primo. Ad esempio, abbiamo sbc1.contoso.com e sbc2.contoso.com con priorità uguale.  

Se sbc1.contoso.com non invia le opzioni SIP in un intervallo regolare come descritto in precedenza, viene retrocesso. Sbc2.contoso.com Cerca quindi la chiamata. Se sbc2. contoso. con non riesce a eseguire la chiamata, il sbc1.contoso.com (retrocesso) viene riprovato prima che venga generato un errore. 

Se due (o più) SBCs in un'unica route vengono contrattate in un ambiente sano e uguale, Fisher-Yates shuffle applicato a distrubuire le chiamate tra SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Monitorare i log di dashboard e SBC di Call Quality Analytics 
 
In alcuni casi, soprattutto durante l'associazione iniziale, potrebbero esserci problemi relativi alla configurazione errata di SBCs e/o del servizio di routing diretto. 

Per monitorare la configurazione, è possibile usare gli strumenti seguenti:  
 
- Dashboard qualità chiamata 
- Registri SBC 

Il servizio di routing diretto contiene codici di errore molto descrittivi segnalati per l'analisi delle chiamate o per i registri SBC. 

Il dashboard qualità chiamata offre informazioni su qualità e affidabilità delle chiamate. Per altre informazioni su come risolvere i problemi con l'uso di analisi delle chiamate, vedere [attivazione e utilizzo di Call Quality dashboard per Microsoft teams e Skype for business online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e [usare la chiamata analitica per la risoluzione dei problemi di qualità delle chiamate](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

In caso di errori di chiamata, l'analisi delle chiamate fornisce codici SIP standard per facilitare la risoluzione dei problemi. 

![Esempio di codice SIP per l'errore di chiamata](media/failed-response-code.png)

Tuttavia, l'analisi delle chiamate può aiutare solo quando le chiamate raggiungono i componenti interni del routing diretto e non riescono. In caso di problemi con l'associazione di SBC o i problemi in cui il SIP "invite" è stato rifiutato, ad esempio il nome dell'FQDN del trunk non è configurato correttamente, l'analisi delle chiamate non sarà utile. In questo caso, consultare i registri SBC. Il routing diretto Invia una descrizione dettagliata dei problemi relativi a SBCs; questi problemi possono essere letti dai log SBC. 
