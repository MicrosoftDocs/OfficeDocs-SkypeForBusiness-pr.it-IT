---
title: Rapporto errori principali in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Riepilogo: informazioni sul rapporto errori principali in Skype for Business Server.'
ms.openlocfilehash: bd03dc921e8df122f4e1ac3ca5cf15195a84b13e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816686"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Rapporto errori principali in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto errori principali in Skype for Business Server.
  
Nel Rapporto errori principali vengono esaminati gli errori rilevati più di frequente con la relativa tendenza nel tempo. Gli errori sono basati su una combinazione delle due metriche seguenti:
  
- **ID diagnostica**. Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi relativi alle chiamate.
    
- **Codice di risposta**. I codici di risposta vengono utilizzati nelle sessioni di comunicazione SIP per rispondere alle richieste SIP. Ad esempio, si supponga che Ken invii la richiesta di invito a Pilar Ackerman (ovvero, supponiamo che Ken remario chiami Pilar Ackerman). Se le risposte di Pilar, il suo telefono invierà il codice di risposta 200 (OK), lasciando che il telefono di Ken sappia che Pilar ha risposto. Il rapporto errori principali include solo codici di risposta inviati in risposta a un errore di chiamata; Skype for Business Server non tiene conto di tutti i codici di risposta rilasciati durante il corso di una chiamata.
    
Le informazioni vengono registrate nel rapporto non solo per il numero totale di sessioni in cui si è verificato un errore, ma anche per il numero totale di utenti che hanno subito l'errore.
  
## <a name="accessing-the-top-failures-report"></a>Accesso al Rapporto errori principali

È possibile accedere al Rapporto errori principali dalla home page Relazioni monitoraggio. Se si fa clic sulla metrica sessioni segnalate, verrà visualizzato il [rapporto distribuzione errori in Skype for Business Server](failure-distribution-report.md).
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Utilizzo ottimale del Rapporto errori principali

Il rapporto errori principali è inusuale in un aspetto: consente di filtrare contemporaneamente su un massimo di 5 ID diagnostici. In genere è possibile filtrare solo su un elemento, ad esempio un indirizzo SIP dell'utente, alla volta. Per filtrare su più ID di diagnostica, è sufficiente immettere ogni ID nella casella ID di diagnostica, separando gli ID tramite virgole. Se si desidera, è possibile lasciare uno spazio vuoto dopo ogni virgola. Per esempio:
  
1011, 2412, 1033, 52116, 1008
  
Così facendo verranno visualizzate solo le chiamate non riuscite che hanno riportato almeno uno dei cinque ID diagnostica indicati.
  
Se si tiene il mouse posizionato su un codice di risposta, viene visualizzata una descrizione comando che ne spiega il significato. Se ad esempio si tiene il mouse posizionato sul codice di risposta 486, verrà visualizzato il messaggio seguente:
  
Non disponibile qui.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto errori principali ad esempio consente di filtrare i dati restituiti in base a fattori come il tipo di attività, ovvero sessione peer-to-peer o di conferenza, oppure in base al codice di risposta SIP associato alla sessione in cui si è verificato l'errore. È inoltre possibile scegliere come raggruppare i dati. In questo caso, gli utilizzi vengono raggruppati per ora, giorno, settimana o mese.
  
Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto errori principali.
  
**Filtri del Rapporto errori principali**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vengono calcolate sempre dal lunedì alla domenica.  <br/> |
|**Tipo di attività** <br/> | Tipo di attività. Selezionare uno dei valori seguenti: <br/>  Tutti <br/>  Peer-to-peer <br/>  Conferenza <br/> |
|**Modalità** <br/> |L'unica opzione disponibile attualmente è **[Tutto]**.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su **[Tutto]** per visualizzare i dati relativi a tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.<br/> |
|**Categoria** <br/> | Tipo di errore. Selezionare uno dei tipi seguenti: <br/>  Errore sia previsto che imprevisto <br/>  Errore imprevisto <br/>  Per "errore previsto" si intende un errore che si prevede si verificherà. Se ad esempio un utente ha impostato il proprio stato su Non disturbare, è previsto che le chiamate effettuate per tale utente abbiano esito negativo. Per "errore imprevisto" si intende un errore che si verifica in un sistema considerato integro. Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa. Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto. <br/> |
|**Codice di risposta** <br/> |Codice di risposta SIP inviato quando si è verificato l'errore di conferenza. Immettere l'intero codice di risposta, ad esempio:  <br/> 400  <br/> |
|**ID diagnostica** <br/> |Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.  <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto errori principali.
  
**Metrica del Rapporto errori principali**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |Sì  <br/> |Classificazione relativa basata sul numero di sessioni segnalate.  <br/> |
|**Sessioni segnalate** <br/> |Sì  <br/> |Numero totale di sessioni non riuscite in base all'ID diagnostica e al codice di risposta SIP.  <br/> |
|**Utenti interessati** <br/> |Sì  <br/> |Numero totale di utenti interessati dalla sessione non riuscita.  <br/> |
|**Informazioni sull'errore** <br/> |No  <br/> |Informazioni dettagliate sull'errore, tra cui l'ID diagnostica, il codice di risposta SIP e la descrizione del motivo per cui la sessione ha avuto esito negativo.  <br/> |
|**Tendenza passato** <br/> |No  <br/> |Rappresentazione grafica delle sessioni non riuscite nel tempo.  <br/> |
   

