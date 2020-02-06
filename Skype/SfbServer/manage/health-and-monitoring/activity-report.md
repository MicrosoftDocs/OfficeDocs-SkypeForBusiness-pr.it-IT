---
title: Report attività conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Riepilogo: informazioni sul report attività conferenza usato in Skype for Business Server.'
ms.openlocfilehash: b9ea4112d144bff88ae72e5805d79f17e655d8f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818177"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Report attività conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni sul report attività conferenza usato in Skype for Business Server.
  
Il report attività conferenza consente di rispondere a domande di questo tipo: il numero di conferenze che si svolgono ogni giorno e quando si svolgono le conferenze? Informazioni come questa sono utili non solo per i propri diritti, ma anche come strumento di risoluzione dei problemi. Supponiamo ad esempio che gli utenti si lamentino che la rete sembra particolarmente lenta a metà giornata. Una breve panoramica dei report sulle attività di conferenza può suggerire un motivo: molte più conferenze vengono programmate tra le ore 10:00 AM e 2:00 PM in qualsiasi momento.
  
Se la rete lenta causa problemi, è possibile incoraggiare gli utenti a ripianificare alcune conferenze durante i periodi di traffico meno pesante del giorno.
  
## <a name="accessing-the-conference-activity-report"></a>Accesso al report attività conferenza

Il report attività conferenza è accessibile dal [report di riepilogo conferenza in Skype for Business Server](conference-summary-report.md) facendo clic su una delle metriche seguenti:
  
- Totale conferenze
    
- Totale partecipanti
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Sfruttare al meglio il report attività conferenza

Per impostazione predefinita, il report attività conferenza Mostra il numero totale di conferenze per il periodo di tempo specificato, ad esempio il numero totale di conferenze per giorno o il numero totale di conferenze per ora del giorno. Tuttavia, è anche possibile scegliere di visualizzare il numero totale di partecipanti per il periodo di tempo o il numero totale di minuti del partecipante. A tale scopo, fare clic sul pulsante Mostra/Nascondi parametri per visualizzare le opzioni di filtro e quindi selezionare una delle operazioni seguenti nell'elenco a discesa report per:
  
- Conteggio partecipanti
    
- Minuti per i partecipanti
    
- Conteggio conferenze
    
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report attività conferenza.
  
**Filtri di report attività conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Report di** <br/> | Indica i valori da usare nel report. È possibile selezionare una delle opzioni seguenti: <br/>  Conteggio partecipanti <br/>  Minuti per i partecipanti <br/>  Conteggio conferenze <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Metriche per le conferenze per pool

Nella tabella seguente sono elencate le informazioni nel report attività conferenza per ogni pool.
  
**Metriche per le conferenze per pool**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Pool** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale usato nella conferenza.  <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui si è tenuta la conferenza.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale partecipanti, minuti totali partecipanti o numero totale conferenza.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Metriche per le conferenze per tipo di server

Nella tabella seguente sono elencate le informazioni nel report attività conferenza per ogni tipo di server.
  
**Metriche per le conferenze per tipo di server**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di server conferenza** <br/> |No  <br/> | Tipo di server usato nella conferenza, in genere una delle opzioni seguenti: <br/>  Web Conferencing Server <br/>  Server di conferenza di messaggistica istantanea <br/>  Server delle conferenze telefoniche <br/>  AV Conferencing Server <br/>  Condivisione applicazioni <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui si è tenuta la conferenza.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale partecipanti, minuti totali partecipanti o numero totale conferenza.  <br/> |
   

