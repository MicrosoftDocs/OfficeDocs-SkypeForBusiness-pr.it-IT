---
title: Report riepilogativo conferenze PSTN in Skype for Business Server
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
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Riepilogo: informazioni sul rapporto riepilogativo conferenze PSTN in Skype for Business Server.'
ms.openlocfilehash: aab91995a2c987e1a6e3a10d1f6fc8791b19a4b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814376"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Report riepilogativo conferenze PSTN in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto riepilogativo conferenze PSTN in Skype for Business Server.
  
In Skype for Business Server, una conferenza PSTN è una conferenza in cui almeno un partecipante compone la parte audio tramite un telefono PSTN (Public Switched Telephone Network). (Un telefono PSTN è una "rete fissa", un telefono cellulare o qualsiasi altro telefono che non utilizza il Voice over IP). Anche se denominate conferenze PSTN nei rapporti di monitoraggio, queste conferenze sono forse più comunemente note come conferenze telefoniche con accesso esterno.
  
Il Rapporto riepilogativo conferenze PSTN offre informazioni su tutte le conferenze PSTN tenutesi nell'organizzazione, ovvero tutte le conferenze con almeno un utente in accesso esterno. Il rapporto include informazioni sul numero totale di conferenze PSTN, il numero totale di utenti che vi hanno preso parte e (probabilmente il dato più importante) il numero totale di utenti con accesso esterno (metrica Totale partecipanti PSTN).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Accesso al Rapporto riepilogativo conferenze PSTN

Il Rapporto riepilogativo conferenze PSTN è accessibile solo dalla home page Rapporti di monitoraggio. Questo rapporto non è collegato ad altri rapporti. Tenere presente che non è possibile recuperare informazioni dettagliate sulle chiamate per una conferenza PSTN, in parte perché i singoli endpoint sono responsabili dell'invio di tali informazioni. I telefoni PSTN non sono in grado di registrare o inviare informazioni dettagliate sulle chiamate.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Uso ottimale del Rapporto riepilogativo conferenze PSTN

Per determinare la percentuale di tutte le conferenze che includono gli utenti con accesso esterno, confrontare il valore della metrica totale conferenze PSTN con le metriche delle conferenze totali trovate [nel rapporto riepilogativo conferenze in Skype for Business Server](conference-summary-report.md).
  
Se non è disponibile il dato previsto sul numero di conferenze PSTN, tenere presente che la capacità di organizzare una conferenza che consenta gli utenti con accesso esterno dipende dai criteri di conferenza assegnati a un utente: se a un numero estremamente esiguo di utenti è consentito tenere conferenze PSTN di conseguenza vi saranno poche conferenze PSTN. È possibile verificare rapidamente quali dei criteri di conferenza (se presenti) consentono agli utenti di pianificare le conferenze PSTN eseguendo il comando seguente da in Skype for Business Server Management Shell:
  
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
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Intervallo** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio pari a 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni da 8/7/2015 12:00 a 9/7/2015 12:00 (ovvero un totale di dati di 31 giorni). <br/> |
   
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel Rapporto riepilogativo conferenze PSTN.
  
**Metriche del Rapporto riepilogativo conferenze PSTN**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Orario** <br/> **Giornaliero** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Ad esempio, se si utilizza l'intervallo giornaliero e si fa clic su 7/7/2015, viene visualizzata una ripartizione oraria dell'attività di registrazione degli utenti per tale data.  <br/> |
|**Totale conferenze PSTN** <br/> |No  <br/> |Numero totale di conferenze telefoniche con accesso esterno.  <br/> |
|**Totale partecipanti** <br/> |No  <br/> |Numero totale di persone che hanno partecipato a conferenze telefoniche con accesso esterno.  <br/> |
|**Totale minuti di conferenza audio/video** <br/> |No  <br/> |Durata totale delle conferenze audio/video.  <br/> |
|**Totale minuti partecipante di conferenza audio/video** <br/> |No  <br/> |Totale minuti di partecipazione a conferenze audio/video. Ad esempio, se un partecipante ha trascorso cinque minuti in una conferenza audio/video e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il totale sarà otto minuti.  <br/> |
|**Totale partecipanti PSTN** <br/> |No  <br/> |Numero totale di utenti che si sono connessi a conferenze telefoniche con accesso esterno.  <br/> |
|**Totale minuti partecipante PSTN** <br/> |No  <br/> |Tempo totale trascorso in conferenza da utenti connessi tramite chiamata in ingresso. Ad esempio, se un partecipante connesso tramite chiamata in ingresso ha trascorso cinque minuti in una conferenza e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il totale sarà otto minuti.  <br/> |
|**Organizzatori conferenza univoci** <br/> |No  <br/> |Numero totale di utenti che hanno organizzato almeno una conferenza telefonica con accesso esterno. Gli utenti che hanno organizzato più conferenze vengono considerati come un organizzatore unico, come gli utenti che hanno organizzato una sola conferenza.  <br/> |
   

