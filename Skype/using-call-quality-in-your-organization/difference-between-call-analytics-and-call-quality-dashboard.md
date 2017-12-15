---
title: "Qual è la differenza tra Call Analytics e Call Quality Dashboard?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
description: "Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business."
---

# Qual è la differenza tra Call Analytics e Call Quality Dashboard?

Skype for Business offre due modi per monitorare e risolvere i problemi di qualità delle chiamate: Call Analytics e Call Quality Dashboard. Questo articolo li descrive entrambi e indica quando usare l'uno o l'altro.
  
> [!NOTE]
> Call Analytics è attualmente in fase di anteprima. Il testo e le immagini qui riportati possono non corrispondere alla tua esperienza di utilizzo. 
  
## Che cos'è Call Analytics e quando è consigliabile usarlo?

Call Analytics mostra informazioni dettagliate sui dispositivi, le reti e la connettività relativamente alle specifiche chiamate e riunioni di ciascun utente in un account Skype for Business. Se sei un amministratore di Skype for Business, puoi usare Call Analytics per risolvere i problemi di qualità delle chiamate e di connessione di Skype for Business.
  
Se desideri che gli utenti non amministratori, come gli agenti di helpdesk di fornitori esterni, possano usare Call Analytics, puoi assegnare loro autorizzazioni in modo che possano usare Call Analytics ma non possano accedere al resto dell'interfaccia di amministrazione di Skype for Business. 
  
- **Agenti helpdesk con autorizzazioni di Livello 1**: gli agenti vendono un sottoinsieme limitato di dati e di informazioni personali identificabili (personally identifiable information, PII) in Call Analytics. Possono risolvere i problemi delle chiamate, ma inoltreranno i problemi di riunione a un agente di Livello 2.
    
- **Agenti helpdesk con autorizzazioni di Livello 2**: gli agenti vedono tutti i dati disponibili in Call Analytics e risolvono i problemi di chiamate e riunioni. hanno accesso completo ai registri chiamate e alle informazioni del cliente.
    
Per i dettagli sull'installazione di Call Analytics, vedi [Configurazione di Skype for Business Call Analytics](set-up-skype-for-business-call-analytics.md). Per maggiori informazioni su come gli agenti helpdesk possono lavorare con Call Analytics, vedi [Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate in Skype for Business](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md).
  
## Che cos'è Call Quality Dashboard e quando è consigliabile usarlo?

Call Analytics offre informazioni dettagliate e specifiche sulla qualità della chiamata dal punto di vista dell'utente. Perché la chiamata dell'utente Antonio Rossi aveva un audio di bassa qualità oggi pomeriggio? Usando Call Analytics, un amministratore di Skype for Business o un agente helpdesk con adeguata formazione può indagare su dispositivo, rete, connettività e altri fattori relativi alla chiamata di Antonio.
  
Se da una parte CA è progettato per aiutare amministratori e agenti helpdesk a risolvere i problemi di qualità per specifiche chiamate, Call Quality Dashboard (CQD) è progettato per aiutare gli amministratori di Skype for Business e i tecnici di rete a ottimizzare una rete. CQD non è focalizzato sui singoli utenti, bensì sulle informazioni in aggregato di un'intera organizzazione di Skype for Business. 
  
Forse la bassa qualità della chiamata di Antonio è dovuta a un problema di rete che colpisce anche molti altri utenti. La singola esperienza di chiamata di Antonio non è visibile in CQD, ma viene dato un quadro generale della qualità complessiva delle chiamate effettuate tramite Skype for Business. Con CQD possono emergere degli schemi generali, che permettono ai tecnici di rete di fare una valutazione informata sulla qualità delle chiamate. CQD mette a disposizione report basati sulle metriche di chiamata che danno un'idea più dettagliata della qualità generale della chiamata, dei flussi di dati server-client e client-client e della qualità vocale a livello di [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Per maggiori dettagli, consulta [Funzionalità di Call Quality Dashboard per Skype for Business online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_FeaturesOfTheCQD).
  
Call Analytics e CQD funzionano parallelamente l'uno all'altro e possono essere usati come programmi indipendenti oppure insieme. Per esempio, ipotizziamo che un agente di Livello 1 decida che ha bisogno d'aiuto per risolvere un problema di chiamata. L'agente di Livello 1 trasferisce la chiamata a un agente di Livello 2, che ha accesso a più informazioni in Call Analytics rispetto all'agente di Livello 1. A sua volta, l'agente di Livello 2 può segnalare un problema a un tecnico di rete. Il tecnico di rete potrà consultare CQD per verificare se un problema generale relativo al sito sta contribuendo ai problemi di chiamata.
  
Per maggiori informazioni su CQD, consulta [Attivare e l'utilizzo di Dashboard di qualità di chiamata per Microsoft Teams e Skype for Business Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md) e[Dimensioni e misure disponibili nel Dashboard di qualità di chiamata per Teams Microsoft e Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  

