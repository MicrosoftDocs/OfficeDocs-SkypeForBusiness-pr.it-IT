---
title: Chiamata Analitica e Dashboard qualità chiamata
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Informazioni sulle chiamate Analitica e Dashboard di qualità delle chiamate e quando vengono utilizzati per monitorare e risolvere i problemi di qualità delle chiamate.
ms.openlocfilehash: a929f88d502d7a1a999114a42093b389f6d3cdfb
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211033"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Chiamata Analitica e Dashboard qualità chiamata

Microsoft Teams e Skype per le aziende consentono di due modi per monitorare e risolvere i problemi di qualità delle chiamate: Analitica delle chiamate e il Dashboard di qualità delle chiamate. Questo articolo li descrive entrambi e indica quando usare l'uno o l'altro.
  
**Chiamata Analitica è ora disponibile in Microsoft Teams e Skype per Business Admin Center.** Per visualizzare tutte le informazioni sulle chiamate e dati per un utente, utilizzare la scheda **Cronologia delle chiamate** . Tale scopo, la ricerca nella pagina del profilo dell'utente per una ricerca per l'utente nel dashboard di o individuare l'utente dagli **utenti** nel riquadro di spostamento sinistro.

> [!IMPORTANT]
> Autorizzazioni di agenti help desk e il caricamento di topologia di rete sarà disponibile nel portale di amministrazione di nuovo nei prossimi mesi. Nel frattempo, è possibile continuare a utilizzare https://adminportal.services.skypeforbusiness.com per l'accesso livello 1 e Tier 2 help desk.
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Che cos'è Call Analytics e quando è consigliabile usarlo?

Chiamata Analitica Visualizza informazioni dettagliate sui dispositivi, reti e connettività relative alle chiamate specifiche e riunioni per ogni utente in un Teams Microsoft Skype per conto di Business. Se si è un amministratore di Office 365, è possibile utilizzare chiamate Analitica risoluzione dei problemi di qualità e la connessione telefonica in Microsoft Teams e Skype per le aziende.

Per visualizzare queste informazioni per un utente in Microsoft Teams e Skype per Business Admin Center, fare clic sulla scheda **Cronologia delle chiamate** per l'utente nella pagina di dettagli utente, che mostra tutte le chiamate e le riunioni che ha partecipato a tale utente negli ultimi 30 giorni.

![Dati utente chiamata analitica.](../images/call-analytics-user-data.png)

Per ottenere ulteriori informazioni su una determinata sessione, compresi i supporti dettagliati e le statistiche di rete, fare clic su una sessione di visualizzare i dettagli.

![Chiamare analitica dati della sessione utente.](../images/call-analytics-user-data-session.png)

Se desideri che gli utenti non amministratori, come gli agenti di helpdesk di fornitori esterni, possano usare Call Analytics, puoi assegnare loro autorizzazioni in modo che possano usare Call Analytics ma non possano accedere al resto dell'interfaccia di amministrazione di Skype for Business. 
  
- **Agenti helpdesk con autorizzazioni di Livello 1**: gli agenti vendono un sottoinsieme limitato di dati e di informazioni personali identificabili (personally identifiable information, PII) in Call Analytics. Possono risolvere i problemi delle chiamate, ma inoltreranno i problemi di riunione a un agente di Livello 2.
    
- **Agenti helpdesk con autorizzazioni di Livello 2**: gli agenti vedono tutti i dati disponibili in Call Analytics e risolvono i problemi di chiamate e riunioni. hanno accesso completo ai registri chiamate e alle informazioni del cliente.

> [!IMPORTANT]
> Autorizzazioni di agenti help desk e il caricamento di topologia di rete sarà disponibile nel portale di amministrazione di nuovo nei prossimi mesi. Nel frattempo, è possibile continuare a utilizzare https://adminportal.services.skypeforbusiness.com per l'accesso livello 1 e Tier 2 help desk.
    
Per i dettagli sull'installazione di Call Analytics, vedi [Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md). Per ulteriori informazioni sul funzionamento di agenti help desk con chiamata Analitica, vedere [Utilizzo delle chiamate Analitica per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Che cos'è Call Quality Dashboard e quando è consigliabile usarlo?

Call Analytics offre informazioni dettagliate e specifiche sulla qualità della chiamata dal punto di vista dell'utente. Perché la chiamata dell'utente Antonio Rossi aveva un audio di bassa qualità oggi pomeriggio? Mediante chiamata Analitica, un Microsoft Teams o Skype per agente help desk adeguatamente formati o amministratore aziendale può esaminare il dispositivo, rete, connettività e altri fattori legati alle chiamate di Tony.
  
Se da una parte CA è progettato per aiutare amministratori e agenti helpdesk a risolvere i problemi di qualità per specifiche chiamate, Call Quality Dashboard (CQD) è progettato per aiutare gli amministratori di Skype for Business e i tecnici di rete a ottimizzare una rete. CQD non è focalizzato sui singoli utenti, bensì sulle informazioni in aggregato di un'intera organizzazione di Skype for Business. 
  
Forse la bassa qualità della chiamata di Antonio è dovuta a un problema di rete che colpisce anche molti altri utenti. La singola esperienza di chiamata di Antonio non è visibile in CQD, ma viene dato un quadro generale della qualità complessiva delle chiamate effettuate tramite Skype for Business. Con CQD possono emergere degli schemi generali, che permettono ai tecnici di rete di fare una valutazione informata sulla qualità delle chiamate. CQD mette a disposizione report basati sulle metriche di chiamata che danno un'idea più dettagliata della qualità generale della chiamata, dei flussi di dati server-client e client-client e della qualità vocale a livello di [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Per maggiori dettagli, consulta [Funzionalità di Call Quality Dashboard per Skype for Business online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Call Analytics e CQD funzionano parallelamente l'uno all'altro e possono essere usati come programmi indipendenti oppure insieme. Per esempio, ipotizziamo che un agente di Livello 1 decida che ha bisogno d'aiuto per risolvere un problema di chiamata. L'agente di Livello 1 trasferisce la chiamata a un agente di Livello 2, che ha accesso a più informazioni in Call Analytics rispetto all'agente di Livello 1. A sua volta, l'agente di Livello 2 può segnalare un problema a un tecnico di rete. Il tecnico di rete potrà consultare CQD per verificare se un problema generale relativo al sito sta contribuendo ai problemi di chiamata.
  
Per ulteriori informazioni su CQD, vedere [attivazione e l'utilizzo del Dashboard di qualità delle chiamate per team di Microsoft e Skype Business online](turning-on-and-using-call-quality-dashboard.md) e [dimensioni e misure disponibile nel Dashboard di qualità delle chiamate per team di Microsoft e Skype Business online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>See also
[Impostare le chiamate Analitica](set-up-call-analytics.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)