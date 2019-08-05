---
title: Report Riepilogo conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Riepilogo: informazioni sul report di riepilogo delle conferenze in Skype for Business Server.'
ms.openlocfilehash: 7bc3c1c33f50d53b0243060cd84b823e0734afb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195706"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Report Riepilogo conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di riepilogo delle conferenze in Skype for Business Server.
  
Il report Riepilogo conferenze offre una panoramica complessiva delle sessioni di conferenza online. Una conferenza in genere coinvolge più di 2 utenti e richiede l'uso di servizi di conferenza. In confronto, una sessione peer-to-peer in genere coinvolge solo 2 utenti e non richiede l'uso di servizi di conferenza di Skype for Business Server. Le attività peer-to-peer sono segnalate nel [report di riepilogo attività peer-to-peer in Skype for Business Server](peer-to-peer-activity-summary-report.md).
  
Il report Riepilogo conferenza non solo indica il numero di conferenze svolte durante un determinato periodo di tempo (ogni ora, ogni giorno, ogni settimana, ogni mese), ma indica anche il totale delle persone che hanno partecipato a tali conferenze e il numero totale di conferenze esclusive organizzatori.
  
Un organizzatore "univoco" è chiunque abbia pianificato almeno una conferenza. Ad esempio, se Pilar Ackerman pianifica una conferenza che conta come unica organizzazione. Se Ken REQUESTO programma le conferenze di 148, conta anche come unico organizzatore. Ad esempio, la tabella seguente mostra le 8 conferenze programmate, ma solo tre organizzatori unici (Ken, Pilar Ackerman e David AHS).
  
|**Organizzatore di conferenze**|**Data conferenza**|
|:-----|:-----|
|Ken  <br/> |7/7/2015 10:00 AM  <br/> |
|David AHS  <br/> |7/7/2015 10:00 AM  <br/> |
|Ken  <br/> |7/7/2015 11:00 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00 AM  <br/> |
|Ken  <br/> |7/7/2015 1:00 PM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 2:00 PM  <br/> |
|Ken  <br/> |7/2/2015 10:00 AM  <br/> |
|Pilar Ackerman  <br/> |7/2/2015 10:00 AM  <br/> |
   
Il report Riepilogo conferenza indica anche il numero di conferenze incluse audio e/o video.
  
## <a name="accessing-the-conference-summary-report"></a>Accesso al report di riepilogo conferenza

È possibile accedere al report di riepilogo conferenza dalla Home page dei report di monitoraggio. È possibile eseguire il drill-down nel report attività conferenza facendo clic su una delle metriche seguenti:
  
- Totale conferenze
    
- Totale partecipanti
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Uso ottimale del report di riepilogo conferenza

I valori totali per la maggior parte delle metriche usate nel report di riepilogo conferenza possono essere trovati nella parte inferiore del report. scorrere verso il basso per visualizzare i valori, ad esempio il numero totale di conferenze detenute durante il periodo di tempo specificato, e il numero totale di persone che hanno partecipato a tali conferenze. Una metrica non totalizzata nella parte inferiore del report è totale organizzatori di conferenze univoci. Perché no? Ecco un motivo. Supponiamo che tu stia esaminando il valore di un mese di dati. Il giorno 1 hai avuto 34 organizzatori di conferenze univoci; il giorno 2 si sono organizzati 27 organizzatori di conferenze univoci. Vuol dire che hai avuto 61 organizzatori di conferenze univoci per questi due giorni? Non necessariamente. Dopo tutto, tutte le 27 persone che hanno organizzato conferenze il giorno 2 potrebbero essere tra le 34 persone che hanno organizzato conferenze il giorno 1. In questo semplice report, ad esempio, si noti che Ken Rein e Pilar Ackerman hanno programmato le conferenze sia in 7/7/2015 che in 7/2/2015:
  
|**Organizzatore di conferenze**|**Data conferenza**|
|:-----|:-----|
|Ken  <br/> |7/7/2015 10:00 AM  <br/> |
|David AHS  <br/> |7/7/2015 10:00 AM  <br/> |
|Ken  <br/> |7/7/2015 11:00 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00 AM  <br/> |
|Ken  <br/> |7/7/2015 1:00 PM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 2:00 PM  <br/> |
|Ken  <br/> |7/2/2015 10:00 AM  <br/> |
|Pilar Ackerman  <br/> |7/2/2015 10:00 AM  <br/> |
   
Per avere un'idea migliore del numero totale di utenti univoci che hanno organizzato conferenze, modificare l'intervallo di tempo; ad esempio, esamina i dati per mese anziché per giorno.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report Riepilogo conferenza consente di scegliere la modalità di raggruppamento dei dati. In questo caso, le conferenze sono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo conferenza.
  
**Filtri di report Riepilogo conferenze**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, vengono visualizzati solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
   
## <a name="metrics"></a>Metriche

Tabella seguente le informazioni fornite dal report di riepilogo conferenze.
  
**Metriche report Riepilogo conferenze**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Oraria** <br/> **Quotidiana** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2015, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.  <br/> |
|**Totale conferenze** <br/> |No  <br/> |Numero totale di conferenze (indipendentemente dal tipo di conferenza) che si sono svolte. Quando si fa clic su questo elemento, nel report viene visualizzato il report attività conferenza per il periodo di tempo selezionato.  <br/> |
|**Totale partecipanti** <br/> |No  <br/> |Numero totale di persone che hanno partecipato alle conferenze. Quando si fa clic su questo elemento, nel report viene visualizzato il report attività conferenza per il periodo di tempo selezionato.  <br/> |
|**Partecipanti medi per conferenza** <br/> |No  <br/> |Numero medio di persone che hanno partecipato a una conferenza. Determinato dividendo le conferenze totali per il totale dei partecipanti.  <br/> |
|**Totale conferenze A/V** <br/> |No  <br/> |Numero totale di conferenze che includono audio o video.  <br/> |
|**Totale minuti di conferenza A/V** <br/> |No  <br/> |Numero totale di minuti dedicati alle conferenze audio/video.  <br/> La metrica totale minuti conferenze A/V riepiloga tutti i tipi di conferenze audio/visive, tra cui: conferenze A/V; Conferenze di messaggistica istantanea; Conferenze di condivisione delle app; Conferenze dati; e conferenze PSTN.  <br/> |
|**Totale minuti partecipanti alla conferenza A/V** <br/> |No  <br/> |Numero totale di minuti per i partecipanti dedicati alle conferenze audio/video. Supponiamo ad esempio che un utente spenda 5 minuti in una conferenza audio/video e un secondo utente passi 3 minuti alla stessa conferenza. Il che rende un totale di 8 minuti per i partecipanti: 5 minuti più 3 minuti.  <br/> |
|**Minuti media di conferenza A/V** <br/> |No  <br/> |Numero medio di minuti per conferenza audio/video.  <br/> |
|**Numero totale di organizzatori univoci delle conferenze** <br/> |No  <br/> |Numero totale di utenti che hanno organizzato almeno una conferenza. Gli utenti che hanno organizzato più di una conferenza vengono conteggiati come un unico organizzatore, proprio come gli utenti che hanno organizzato una singola conferenza.  <br/> |
|**Totale messaggi conferenza** <br/> |No  <br/> |Numero totale di messaggi istantanei inviati durante le conferenze.  <br/> |
   

