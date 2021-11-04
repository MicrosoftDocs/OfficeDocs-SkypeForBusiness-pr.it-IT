---
title: Rapporto riepilogativo conferenze PSTN in Skype for Business Server
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
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Riepilogo: informazioni sul Rapporto riepilogativo conferenze PSTN in Skype for Business Server.'
ms.openlocfilehash: 145207e296fb14462e204bb9c8091612ff89b7da
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754715"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Rapporto riepilogativo conferenze PSTN in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto riepilogativo conferenze PSTN in Skype for Business Server.
  
In Skype for Business Server, una conferenza PSTN è una conferenza in cui almeno un partecipante compone la parte audio utilizzando un telefono PSTN (public switched telephone network). Un telefono PSTN è un "telefono fisso", un cellulare o qualsiasi altro telefono che non utilizza Voice over IP. Sebbene siano note come conferenze PSTN nei rapporti di monitoraggio, queste conferenze sono forse più comunemente note come conferenze telefoniche con accesso remoto.
  
Il Rapporto riepilogativo conferenze PSTN offre informazioni su tutte le conferenze PSTN tenutesi nell'organizzazione, ovvero tutte le conferenze con almeno un utente in accesso esterno. Il rapporto include informazioni sul numero totale di conferenze PSTN, il numero totale di utenti che vi hanno preso parte e (probabilmente il dato più importante) il numero totale di utenti con accesso esterno (metrica Totale partecipanti PSTN).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Accesso al Rapporto riepilogativo conferenze PSTN

Il Rapporto riepilogativo conferenze PSTN è accessibile solo dalla home page Rapporti di monitoraggio. Questo rapporto non è collegato ad altri rapporti. Tenere presente che non è possibile recuperare informazioni dettagliate sulle chiamate per una conferenza PSTN, in parte perché i singoli endpoint sono responsabili dell'invio di tali informazioni. I telefoni PSTN non sono in grado di registrare o inviare informazioni dettagliate sulle chiamate.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Uso ottimale del Rapporto riepilogativo conferenze PSTN

Per determinare la percentuale di tutte le conferenze che includono utenti con accesso remoto, confrontare il valore della metrica Totale conferenze PSTN con la metrica Totale conferenze disponibile nel Rapporto riepilogativo conferenze [in Skype for Business Server](conference-summary-report.md).
  
Se non è disponibile il dato previsto sul numero di conferenze PSTN, tenere presente che la capacità di organizzare una conferenza che consenta gli utenti con accesso esterno dipende dai criteri di conferenza assegnati a un utente: se a un numero estremamente esiguo di utenti è consentito tenere conferenze PSTN di conseguenza vi saranno poche conferenze PSTN. È possibile verificare rapidamente quale dei criteri di conferenza (se presenti) consentire agli utenti di pianificare conferenze PSTN eseguendo il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Il comando restituisce dati analoghi a questi:
  
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

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Ad esempio, il rapporto riepilogativo conferenze PSTN consente di scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri applicabili al Rapporto riepilogativo conferenze PSTN.
  
**Filtri del Rapporto riepilogativo conferenze PSTN**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 7/07/2015 e data di fine 28/02/2015, verranno visualizzati i dati relativi ai giorni 07/08/2015 12.00 alle 07.00.00 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
   
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel Rapporto riepilogativo conferenze PSTN.
  
**Metriche del Rapporto riepilogativo conferenze PSTN**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Orario** <br/> **Giornaliero** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Ad esempio, se si utilizza l'intervallo Giornaliero e si fa clic su 7/07/07/2015, verrà visualizzata una suddivisione oraria dell'attività di registrazione degli utenti per tale data.  <br/> |
|**Totale conferenze PSTN** <br/> |No  <br/> |Numero totale di conferenze telefoniche con accesso esterno.  <br/> |
|**Totale partecipanti** <br/> |No  <br/> |Numero totale di persone che hanno partecipato a conferenze telefoniche con accesso esterno.  <br/> |
|**Totale minuti di conferenza audio/video** <br/> |No  <br/> |Durata totale delle conferenze audio/video.  <br/> |
|**Totale minuti partecipante di conferenza audio/video** <br/> |No  <br/> |Totale minuti di partecipazione a conferenze audio/video. Ad esempio, se un partecipante ha trascorso cinque minuti in una conferenza audio/video e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il totale sarà otto minuti.  <br/> |
|**Totale partecipanti PSTN** <br/> |No  <br/> |Numero totale di utenti che si sono connessi a conferenze telefoniche con accesso esterno.  <br/> |
|**Totale minuti partecipante PSTN** <br/> |No  <br/> |Tempo totale trascorso in conferenza da utenti connessi tramite chiamata in ingresso. Ad esempio, se un partecipante connesso tramite chiamata in ingresso ha trascorso cinque minuti in una conferenza e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il totale sarà otto minuti.  <br/> |
|**Organizzatori conferenza univoci** <br/> |No  <br/> |Numero totale di utenti che hanno organizzato almeno una conferenza telefonica con accesso esterno. Gli utenti che hanno organizzato più conferenze vengono considerati come un organizzatore unico, come gli utenti che hanno organizzato una sola conferenza.  <br/> |
   

