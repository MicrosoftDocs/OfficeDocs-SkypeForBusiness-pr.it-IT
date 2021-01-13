---
title: Report riepilogativo conferenze in Skype for Business Server
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
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Riepilogo: informazioni sul rapporto riepilogativo conferenze in Skype for Business Server.'
ms.openlocfilehash: eaaa97c54a9183beda40848795b454e7dec92c6f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817046"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Report riepilogativo conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto riepilogativo conferenze in Skype for Business Server.
  
Il Rapporto riepilogativo conferenze offre una visuale generale delle sessioni di conferenza online. Una conferenza in genere coinvolge più di 2 utenti e richiede l'utilizzo di servizi di conferenza. In base al confronto, una sessione peer-to-peer in genere coinvolge solo 2 utenti e non richiede l'uso di Skype for Business Server Conferencing Services. Le attività peer-to-peer sono segnalate nel [rapporto riepilogativo attività peer-to-peer in Skype for Business Server](peer-to-peer-activity-summary-report.md).
  
Il rapporto riepilogativo conferenze non solo indica quante conferenze sono state tenute durante un determinato periodo di tempo (ogni ora, giornaliero, settimanale, mensile) ma indica anche il numero totale di persone che hanno partecipato a tali conferenze e il numero totale di organizzatori di conferenze univoci.
  
Un organizzatore "univoco" è chiunque abbia pianificato almeno una conferenza. Se Luisa Cazzaniga pianifica una conferenza, ad esempio, sarà conteggiata come organizzatore univoco. Se Davide Garghentini pianifica 148 conferenze, anche lui sarà conteggiato come singolo organizzatore univoco. Ad esempio, nella tabella seguente sono riportate 8 conferenze pianificate, ma solo tre organizzatori unici (Ken, Pilar Ackerman e David AHS).
  
|**Organizzatore conferenza**|**Data conferenza**|
|:-----|:-----|
|Davide Garghentini  <br/> |7/7/2015 10:00 AM  <br/> |
|Luca Argentiero  <br/> |7/7/2015 10:00 AM  <br/> |
|Davide Garghentini  <br/> |7/7/2015 11:00 AM  <br/> |
|Daniela Cazzaniga  <br/> |7/7/2015 11:00 AM  <br/> |
|Davide Garghentini  <br/> |7/7/2015 1:00 PM  <br/> |
|Daniela Cazzaniga  <br/> |7/7/2015 2:00 PM  <br/> |
|Davide Garghentini  <br/> |7/2/2015 10:00 AM  <br/> |
|Daniela Cazzaniga  <br/> |7/2/2015 10:00 AM  <br/> |
   
Il Rapporto riepilogativo conferenze indica inoltre il numero di conferenze con audio e video.
  
## <a name="accessing-the-conference-summary-report"></a>Accesso al rapporto riepilogativo conferenze

È possibile accedere al rapporto riepilogativo conferenze dalla home page Relazioni monitoraggio. È possibile eseguire il drill-down al Rapporto attività conferenza facendo clic su una delle metriche seguenti:
  
- Totale conferenze
    
- Totale partecipanti
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Utilizzo ottimale del rapporto riepilogativo conferenze

I valori totali per la maggior parte delle metriche utilizzate nel rapporto riepilogativo conferenze sono disponibili nella parte inferiore del report. scorrere verso il basso per visualizzare i valori, ad esempio il numero totale di conferenze detenute durante il periodo di tempo specificato, e il numero totale di persone che hanno partecipato a tali conferenze. Una metrica che non è totalizzata nella parte inferiore del report è Total Unique Conference Organizer. Perché? Ecco un motivo. Si supponga di essere alla ricerca del valore di un mese di dati. Il giorno 1 si sono avuti 34 organizzatori di conferenze univoci; il giorno 2 hai avuto 27 organizzatori conferenza unici. Significa che sono stati 61 organizzatori di conferenze univoci per quei due giorni? Non necessariamente. Dopo tutto, tutte le 27 persone che hanno organizzato conferenze il giorno 2 potrebbero essere tra le 34 persone che hanno organizzato conferenze il giorno 1. Ad esempio, in questa semplice relazione, si noti che Ken remario e Pilar Ackerman hanno pianificato conferenze sia su 7/7/2015 che su 7/2/2015:
  
|**Organizzatore conferenza**|**Data conferenza**|
|:-----|:-----|
|Davide Garghentini  <br/> |7/7/2015 10:00 AM  <br/> |
|Luca Argentiero  <br/> |7/7/2015 10:00 AM  <br/> |
|Davide Garghentini  <br/> |7/7/2015 11:00 AM  <br/> |
|Daniela Cazzaniga  <br/> |7/7/2015 11:00 AM  <br/> |
|Davide Garghentini  <br/> |7/7/2015 1:00 PM  <br/> |
|Daniela Cazzaniga  <br/> |7/7/2015 2:00 PM  <br/> |
|Davide Garghentini  <br/> |7/2/2015 10:00 AM  <br/> |
|Daniela Cazzaniga  <br/> |7/2/2015 10:00 AM  <br/> |
   
Per ottenere un'indicazione più precisa del numero totale di utenti univoci che hanno organizzato conferenze, modificare l'intervallo di tempo, ad esempio esaminare i dati su base mensile anziché giornaliera.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il rapporto riepilogativo conferenze consente di scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo conferenze.
  
**Filtri del rapporto riepilogativo conferenze**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Intervallo** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio pari a 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni da 8/7/2015 12:00 a 9/7/2015 12:00 (ovvero un totale di dati di 31 giorni). <br/> |
   
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel rapporto riepilogativo conferenze.
  
**Metriche del rapporto riepilogativo conferenze**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Orario** <br/> **Giornaliero** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato sulla barra degli strumenti dei filtri. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Ad esempio, se si utilizza l'intervallo giornaliero e si fa clic su 7/7/2015, viene visualizzata una ripartizione oraria dell'attività di registrazione degli utenti per tale data.  <br/> |
|**Totale conferenze** <br/> |No  <br/> |Numero totale di conferenze eseguite, indipendentemente dal tipo di conferenza. Facendo clic su questo elemento viene visualizzato il rapporto attività conferenza per il periodo di tempo selezionato.  <br/> |
|**Totale partecipanti** <br/> |No  <br/> |Numero totale di persone che hanno partecipato alle conferenze. Facendo clic su questo elemento viene visualizzato il rapporto attività conferenza per il periodo di tempo selezionato.  <br/> |
|**Numero medio di partecipanti per conferenza** <br/> |No  <br/> |Numero medio di persone che hanno preso parte a una specifica conferenza, determinato dividendo il numero totale di conferenze per il numero totale di partecipanti.  <br/> |
|**Totale conferenze audio/video** <br/> |No  <br/> |Numero totale di conferenze con audio o video.  <br/> |
|**Totale minuti di conferenza audio/video** <br/> |No  <br/> |Numero totale di minuti dedicati alle conferenze audio/video.  <br/> La metrica Total A/V Conference minutes riepiloga tutti i tipi di conferenze audio/video, tra cui: conferenze A/V. Conferenze di messaggistica istantanea; Conferenze di condivisione app; Conferenze dati; e conferenze PSTN.  <br/> |
|**Totale minuti partecipante di conferenza audio/video** <br/> |No  <br/> |Numero totale di minuti partecipante dedicati alle conferenze audio/video. Si supponga, ad esempio, che un utente dedichi 5 minuti a una conferenza audio/video e che un secondo utente ne dedichi 3 nella stessa conferenza. Si ottiene così un totale di 8 minuti partecipante (5+3).  <br/> |
|**Media minuti di conferenza audio/video** <br/> |No  <br/> |Numero medio di minuti per conferenza audio/video.  <br/> |
|**Totale organizzatori conferenza univoci** <br/> |No  <br/> |Numero totale di utenti che hanno organizzato almeno una conferenza. Gli utenti che hanno organizzato più conferenze vengono considerati come un organizzatore unico, come gli utenti che hanno organizzato una sola conferenza.  <br/> |
|**Totale messaggi conferenza** <br/> |No  <br/> |Numero totale di messaggi istantanei inviati durante le conferenze.  <br/> |
   

