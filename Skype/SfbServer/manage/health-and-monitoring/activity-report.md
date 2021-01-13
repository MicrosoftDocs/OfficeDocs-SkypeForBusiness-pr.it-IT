---
title: Report attività conferenze in Skype for Business Server
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
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Riepilogo: informazioni sul rapporto attività conferenza utilizzato in Skype for Business Server.'
ms.openlocfilehash: 74cc303fc4347b81e66d855a3ca5a71e58cb9649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817136"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Report attività conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto attività conferenza utilizzato in Skype for Business Server.
  
Con il Rapporto attività conferenza è semplice rispondere a domande come queste: quante conferenze si tengono ogni giorno e quando hanno luogo? Informazioni di questo tipo non sono solo utili di per sé, ma anche come strumenti di risoluzione dei problemi. Si supponga ad esempio che gli utenti si lamentino del fatto che la rete sia particolarmente lenta a metà giornata. Un rapido sguardo ai report sulle attività di conferenza potrebbe suggerire un possibile motivo: molte più conferenze vengono pianificate tra le ore 10:00 e 2:00 poi in qualsiasi altro momento.
  
Se la lentezza della rete crea problemi, è possibile chiedere agli utenti di riprogrammare alcune delle conferenze in orari di minor traffico.
  
## <a name="accessing-the-conference-activity-report"></a>Accesso al Rapporto attività conferenza

Il rapporto attività conferenza è accessibile dal [rapporto riepilogativo conferenze in Skype for Business Server](conference-summary-report.md) facendo clic su una delle metriche seguenti:
  
- Totale conferenze
    
- Totale partecipanti
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Utilizzo ottimale del Rapporto attività conferenza

Per impostazione predefinita, il Rapporto attività conferenza mostra il numero totale di conferenze per il periodo di tempo specificato (ad esempio il numero totale di conferenze al giorno oppure il numero totale di conferenze all'ora). È tuttavia anche possibile scegliere di visualizzare il numero totale di partecipanti per il periodo di tempo specificato o il numero totale di minuti partecipante. A tale scopo, fare clic sul pulsante Mostra/Nascondi parametri per visualizzare le opzioni di filtro, quindi selezionare una delle seguenti opzioni dall'elenco a discesa Rapporto di:
  
- Numero partecipanti
    
- Minuti partecipante
    
- Numero conferenze
    
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto attività conferenza.
  
**Filtri per il Rapporto attività conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare uno dei valori seguenti: <br/>  Orario (è possibile visualizzare al massimo 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio pari a 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni da 8/7/2015 12:00 a 9/7/2015 12:00 (ovvero un totale di dati di 31 giorni). <br/> |
|**Rapporto di** <br/> | Indica i valori da utilizzare nel rapporto. È possibile selezionare uno dei valori seguenti: <br/>  Numero partecipanti <br/>  Minuti partecipante <br/>  Numero conferenze <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Metrica delle conferenze per pool

Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni pool.
  
**Metrica delle conferenze per pool**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Pool** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale utilizzato nella conferenza.  <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui è stata tenuta la conferenza.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Metrica delle conferenze per tipo di server

Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni tipo di server.
  
**Metrica delle conferenze per tipo di server**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo server per conferenze** <br/> |No  <br/> | Tipo di server utilizzato nella conferenza, in genere uno dei tipi seguenti: <br/>  Web Conferencing Server <br/>  IM Conferencing Server <br/>  Telephony Conferencing Server <br/>  AV Conferencing Server <br/>  Condivisione applicazioni <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui è stata tenuta la conferenza.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.  <br/> |
   

