---
title: Rapporto riepilogativo attività peer-to-peer in Skype for Business Server
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
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Riepilogo: informazioni sul Rapporto riepilogativo attività peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 0614e113ad258bd66f436d0dc74106ddd35a26cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774826"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Rapporto riepilogativo attività peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto riepilogativo attività peer-to-peer in Skype for Business Server.
  
Il Rapporto riepilogativo attività peer-to-peer offre informazioni generali sulle sessioni di comunicazione peer-to-peer. Una sessione peer-to-peer in genere coinvolge solo due utenti e non richiede l'utilizzo dei servizi di Skype for Business Server conferencing. In genere, una conferenza coinvolge più di due utenti e richiede l'utilizzo di servizi di Skype for Business Server conferenza. Le attività relative alle conferenze sono riepilogate nel Rapporto riepilogativo conferenze.
  
Nel Rapporto riepilogativo attività peer-to-peer è possibile trovare risposte a domande come le seguenti:
  
- Quanti messaggi istantanei peer-to-peer si scambiano quotidianamente gli utenti?
    
- Alcuni utenti sfruttano effettivamente le funzionalità di condivisione Skype for Business Server e trasferimento di file?
    
- Gli utenti si lamentano della lentezza della rete in periodi specifici del giorno. Quanti minuti sono dedicati alle sessioni audio e video peer-to-peer durante tali periodi?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Accesso al Rapporto riepilogativo attività peer-to-peer

Il Rapporto riepilogativo attività peer-to-peer è accessibile dalla home page dei rapporti di monitoraggio. È possibile aprire il rapporto di messaggistica istantanea [peer-to-peer in Skype for Business Server](im-report.md) facendo clic su una delle metriche seguenti:
  
- Totale sessioni di messaggistica istantanea peer-to-peer
    
- Totale messaggi istantanei peer-to-peer
    
In modo analogo, è possibile aprire il Rapporto voce e video peer-to-peer facendo clic su una delle metriche seguenti:
  
- Totale sessioni audio peer-to-peer
    
- Totale minuti sessioni audio peer-to-peer
    
- Totale sessioni audio peer-to-peer
    
- Totale minuti sessioni audio peer-to-peer
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Utilizzo ottimale del Rapporto riepilogativo attività peer-to-peer

Nella parte inferiore del Rapporto riepilogativo attività peer-to-peer sono disponibili i totali per le metriche, come Totale sessioni di messaggistica istantanea peer-to-peer e Totale messaggi istantanei peer-to-peer. Questi valori offrono un rapido riepilogo delle informazioni dettagliate disponibili nel corpo del rapporto.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il Rapporto riepilogativo attività peer-to-peer consente ad esempio di scegliere la modalità di raggruppamento dei dati. In questo caso le attività sono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il Rapporto riepilogativo attività peer-to-peer.
  
**Filtri del Rapporto riepilogativo attività peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:  <br/> 17/07/12015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:  <br/> 17/07/12015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio del 17/07/12015 e una data di fine del 28/02/2015, vengono visualizzati i dati per i giorni 07/08/12015 12.00 alle 07.00.00 del 9/07/12015 (ovvero un totale di 31 giorni di dati). <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono indicate le informazioni fornite nel Rapporto riepilogativo attività peer-to-peer.
  
**Metriche del Rapporto riepilogativo attività peer-to-peer**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Orario** <br/> **Giornaliero** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato sulla barra degli strumenti dei filtri. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Ad esempio, se si utilizza l'intervallo Giornaliero e si fa clic su 17/07/12015, verrà visualizzata una suddivisione oraria dell'attività di registrazione degli utenti per tale data.  <br/> |
|**Totale sessioni peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer condotte, indipendentemente dal tipo.  <br/> |
|**Totale sessioni di messaggistica istantanea peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni di messaggistica istantanea condotte. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.  <br/> |
|**Totale messaggi istantanei peer-to-peer** <br/> |No  <br/> |Numero totale di messaggi istantanei inviati in sessioni peer-to-peer. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.  <br/> |
|**Totale sessioni audio peer-to-peer audio** <br/> |No  <br/> |Numero totale di chiamate audio peer-to-peer. Se si fa clic su questo campo, verrà visualizzato il Rapporto voce e video peer-to-peer relativo al periodo di tempo selezionato.  <br/> |
|**Totale minuti sessioni audio peer-to-peer** <br/> |No  <br/> |Quantità totale di tempo impiegato in sessioni audio peer-to-peer. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.  <br/> |
|**Media minuti sessioni audio peer-to-peer** <br/> |No  <br/> |Quantità media di tempo impiegato in sessioni audio peer-to-peer. Il valore viene calcolato dividendo il tempo totale per il numero totale delle sessioni audio.  <br/> |
|**Totale sessioni video peer-to-peer** <br/> |No  <br/> |Numero totale di videochiamate peer-to-peer. Si noti che le sessioni video vengono conteggiate anche come sessioni audio. Ogni sessione video viene conteggiata come una sessione video e una sessione audio. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.  <br/> |
|**Totale minuti sessioni video peer-to-peer** <br/> |No  <br/> |Quantità totale di tempo impiegato in sessioni video peer-to-peer. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.  <br/> |
|**Media minuti sessioni video peer-to-peer** <br/> |No  <br/> |Quantità media di tempo impiegato in sessioni video peer-to-peer. Il valore viene calcolato dividendo il tempo totale per il numero totale delle sessioni video.  <br/> |
|**Totale sessioni di trasferimento di file peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer che includono trasferimenti di file.  <br/> |
|**Totale sessioni di condivisione applicazioni peer-to-peer** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer che includono la condivisione di applicazioni.  <br/> |
   

