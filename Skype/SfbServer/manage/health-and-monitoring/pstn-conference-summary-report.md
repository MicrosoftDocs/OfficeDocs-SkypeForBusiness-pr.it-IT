---
title: Report di riepilogo conferenza PSTN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Riepilogo: informazioni sul report di riepilogo conferenza PSTN in Skype for Business Server.'
ms.openlocfilehash: 8b8b108243e257c414e9d6bb101e69fc9701d82e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188726"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Report di riepilogo conferenza PSTN in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di riepilogo delle conferenze PSTN in Skype for Business Server.
  
In Skype for Business Server, una conferenza PSTN è una conferenza in cui almeno un partecipante compone la parte audio tramite un telefono PSTN (Public Switched Telephone Network). (Un telefono PSTN è un "telefono fisso", un cellulare o un altro telefono che non fa uso di Voice over IP.) Anche se si fa riferimento a conferenze PSTN nei report di monitoraggio, queste conferenze sono forse più comunemente note come conferenze telefoniche con accesso esterno.
  
Il report Riepilogo conferenza PSTN contiene informazioni su tutte le conferenze PSTN svolte nell'organizzazione, ovvero tutte le conferenze con almeno un utente con accesso esterno. Il report include informazioni sul numero totale di conferenze PSTN, il numero totale di persone che hanno partecipato a tali conferenze e, forse, più importante, il numero totale di utenti con accesso esterno (la metrica totale dei partecipanti PSTN).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Accesso al report di riepilogo conferenza PSTN

Il report Riepilogo conferenza PSTN può essere accessibile solo dalla Home page dei report di monitoraggio. Questo report non è collegato ad altri report. Tieni presente che non puoi recuperare informazioni dettagliate sulle chiamate per una conferenza PSTN, in parte perché i singoli endpoint sono responsabili dell'invio di queste informazioni. I telefoni PSTN non sono in grado di tenere traccia o inviare informazioni dettagliate sulle chiamate.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Uso ottimale del report di riepilogo conferenza PSTN

Per determinare la percentuale di tutte le conferenze che includono utenti con accesso esterno, confrontare il valore della metrica totale conferenze PSTN con la metrica totale conferenze disponibile [nel report di riepilogo conferenza in Skype for Business Server](conference-summary-report.md).
  
Se non si vedono tutte le conferenze PSTN che si potrebbero prevedere, tenere presente che la possibilità di organizzare una conferenza che consente agli utenti di accesso esterno dipende dal criterio di conferenza assegnato a un utente: se pochissimi utenti sono autorizzati a tenere premuto PS Conferenze TN si vedranno ovviamente pochissime conferenze PSTN. È possibile verificare rapidamente quale dei criteri di conferenza (se presenti) consente agli utenti di pianificare conferenze PSTN eseguendo il comando seguente dall'interno di Skype for Business Server Management Shell:
  
```
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Che restituirà dati simili a questi:
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report Riepilogo conferenza PSTN consente di scegliere la modalità di raggruppamento dei dati. In questo caso, le conferenze vengono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo conferenza PSTN.
  
**Filtri report Riepilogo conferenza PSTN**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni nel report di riepilogo conferenza PSTN.
  
**Metriche report Riepilogo conferenza PSTN**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Oraria** <br/> **Quotidiana** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2015, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.  <br/> |
|**Totale conferenze PSTN** <br/> |No  <br/> |Numero totale di conferenze che hanno consentito l'accesso tramite chiamata in ingresso.  <br/> |
|**Totale partecipanti** <br/> |No  <br/> |Numero totale di persone che hanno partecipato a conferenze che hanno consentito l'accesso tramite chiamata in ingresso.  <br/> |
|**Totale minuti di conferenza A/V** <br/> |No  <br/> |Quantità totale di tempo per le conferenze audio/visive.  <br/> |
|**Totale minuti partecipanti alla conferenza A/V** <br/> |No  <br/> |Quantità totale di tempo dei partecipanti audio/visivi. Ad esempio, se un partecipante ha trascorso cinque minuti in una conferenza A/V e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il tempo totale per i partecipanti alla conferenza A/V sarebbe di otto minuti.  <br/> |
|**Totale partecipanti PSTN** <br/> |No  <br/> |Numero totale di utenti che hanno eseguito la chiamata a conferenze che hanno consentito l'accesso tramite chiamata in ingresso.  <br/> |
|**Minuti totali dei partecipanti PSTN** <br/> |No  <br/> |Importo totale del tempo di conferenza trascorso dagli utenti con accesso esterno. Ad esempio, se un partecipante con accesso esterno ha trascorso cinque minuti in una conferenza e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il tempo totale dei partecipanti PSTN sarebbe di otto minuti.  <br/> |
|**Organizzatori di conferenze univoci** <br/> |No  <br/> |Numero totale di utenti che hanno organizzato almeno una conferenza che consentiva l'accesso esterno. Gli utenti che hanno organizzato più di una conferenza vengono conteggiati come un unico organizzatore, proprio come gli utenti che hanno organizzato una singola conferenza.  <br/> |
   

