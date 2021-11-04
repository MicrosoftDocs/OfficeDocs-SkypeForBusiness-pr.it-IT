---
title: Rapporto di messaggistica istantanea peer-to-peer in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Riepilogo: informazioni sul rapporto di messaggistica istantanea peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 999750f039b2ca57cc31198bcf1599f042763ed3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767664"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Rapporto di messaggistica istantanea peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto di messaggistica istantanea peer-to-peer in Skype for Business Server.
  
Nel rapporto di messaggistica istantanea peer-to-peer vengono fornite informazioni sulla tendenza delle sessioni di messaggistica istantanea suddivise per pool e per tipo di autenticazione. Il rapporto può inoltre indicare il numero totale di sessioni organizzate oppure segnalare il numero complessivo di messaggi istantanei inviati nel periodo specificato (ad esempio, Giorno o Ora).
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Accesso al rapporto di messaggistica istantanea peer-to-peer

È possibile accedere al rapporto di messaggistica istantanea peer-to-peer solo aprendo il Rapporto riepilogativo attività [peer-to-peer in Skype for Business Server](peer-to-peer-activity-summary-report.md) e quindi facendo clic su una delle metriche seguenti:
  
- Totale sessioni di messaggistica istantanea peer-to-peer
    
- Totale messaggi istantanei peer-to-peer
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Utilizzo ottimale del rapporto di messaggistica istantanea peer-to-peer

Nel rapporto di messaggistica istantanea peer-to-peer vengono mostrati, per impostazione predefinita, il numero di messaggi per ora (o giorno, a seconda dell'impostazione configurata). Tuttavia, è anche possibile scegliere di visualizzare il giorno in base alle sessioni per ora. In tal caso, fare clic su **Nascondi/mostra parametri** nell'angolo superiore destro della finestra relativa ai rapporti e quindi fare clic su **Numero di sessioni** nell'elenco **Rapporto di**.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più mirato o di visualizzare i dati restituiti in diversi modi. Nella tabella seguente sono riportati i filtri utilizzabili con il rapporto di messaggistica istantanea peer-to-peer.
  
**Filtri per il rapporto di messaggistica istantanea peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientri nella settimana o nel mese desiderato (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (possono essere visualizzati al massimo 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 7/07/2015 e data di fine 28/02/2015, verranno visualizzati i dati relativi ai giorni 07/08/2015 12.00 alle 07.00.00 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
|**Rapporto di** <br/> | Indica i valori da utilizzare nel rapporto. Selezionare una delle impostazioni seguenti: <br/>  Numero di sessioni <br/>  Numero messaggi <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al pool

Nella tabella seguente vengono riportate le informazioni fornite nel rapporto di messaggistica istantanea peer-to-peer.
  
**Metrica del rapporto di messaggistica istantanea peer-to-peer in base al pool**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Pool** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale.  <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui hanno avuto luogo le sessioni.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o di messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al tipo di autenticazione

Nella tabella seguente vengono riportate le informazioni fornite nel rapporto di messaggistica istantanea peer-to-peer per ogni tipo di autenticazione utilizzato dai partecipanti a una sessione peer-to-peer.
  
**Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al tipo di autenticazione**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di autenticazione** <br/> |No  <br/> | Tipo di autenticazione utilizzato dai partecipanti alla sessione. I valori validi in genere sono i seguenti: <br/>  Enterprise <br/>  Federato <br/>  PIC <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui hanno avuto luogo le sessioni.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o di messaggi.  <br/> |
   

