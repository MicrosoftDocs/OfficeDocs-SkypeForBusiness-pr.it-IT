---
title: Report di messaggistica istantanea peer-to-peer in Skype for Business Server
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
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Riepilogo: informazioni sul report di messaggistica istantanea peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 7775e7dc4a6fc3cd36283decd12971ac0e0f780a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817916"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Report di messaggistica istantanea peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di messaggistica istantanea peer-to-peer in Skype for Business Server.
  
Il report di messaggistica istantanea peer-to-peer fornisce informazioni sulla tendenza sulle sessioni di messaggistica immediata (IM) peer-to-peer, suddivise per pool e per tipo di autenticazione. Il report può visualizzare il numero totale di sessioni consentite durante il periodo di tempo specificato, ad esempio giorno per giorno o ora per ora, oppure può visualizzare il numero totale di messaggi istantanei inviati durante il periodo di tempo.
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Accesso al report di messaggistica istantanea peer-to-peer

È possibile accedere al report di messaggistica istantanea peer-to-peer solo aprendo il [rapporto di riepilogo attività peer-to-peer in Skype for Business Server](peer-to-peer-activity-summary-report.md) e quindi facendo clic su una delle metriche seguenti:
  
- Totale sessioni di messaggistica istantanea peer-to-peer
    
- Totale messaggi di messaggistica istantanea peer-to-peer
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Sfruttare al meglio il report di messaggistica istantanea peer-to-peer

Per impostazione predefinita, il rapporto di messaggistica istantanea peer-to-peer Mostra il numero di messaggi per ora (o giorno), a seconda delle impostazioni. Tuttavia, puoi anche scegliere di visualizzare il giorno per sessioni per ora. A tale scopo, fare clic su **Nascondi/Mostra parametri** nell'angolo in alto a destra della finestra report e quindi fare clic su **conteggio sessioni** nell'elenco **segnala per** .
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report di messaggistica istantanea peer-to-peer.
  
**Filtri di report istantanei di messaggistica istantanea peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Report di** <br/> | Indica i valori da usare nel report. Selezionare una delle opzioni seguenti: <br/>  Conteggio sessioni <br/>  Numero di messaggi <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metriche per la sessione di messaggistica istantanea peer-to-peer per pool

Nella tabella seguente sono elencate le informazioni fornite nel report di messaggistica istantanea peer-to-peer.
  
**Metriche per la sessione di messaggistica istantanea peer-to-peer per pool**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Pool** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale.  <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui sono state svolte le sessioni.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o conteggio totale dei messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metriche per la sessione di messaggistica istantanea peer-to-peer per tipo di autenticazione

Nella tabella seguente sono elencate le informazioni fornite nel report di messaggistica istantanea peer-to-peer per ogni tipo di autenticazione usato dai partecipanti in una sessione peer-to-peer.
  
**Metriche per la sessione di messaggistica istantanea peer-to-peer per tipo di autenticazione**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di autenticazione** <br/> |No  <br/> | Tipo di autenticazione usato dai partecipanti alla sessione. I valori sono in genere uno degli elementi seguenti: <br/>  Enterprise <br/>  Federata <br/>  PIC <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui sono state svolte le sessioni.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o conteggio totale dei messaggi.  <br/> |
   

