---
title: Rapporto attività conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Riepilogo: informazioni sul Rapporto attività conferenza utilizzato in Skype for Business Server.'
ms.openlocfilehash: d422f86789c8a488f6a1bbe954689a3e422e990f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612225"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Rapporto attività conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto attività conferenza usato in Skype for Business Server.
  
Con il Rapporto attività conferenza è semplice rispondere a domande come queste: quante conferenze si tengono ogni giorno e quando hanno luogo? Informazioni di questo tipo non sono solo utili di per sé, ma anche come strumenti di risoluzione dei problemi. Si supponga ad esempio che gli utenti si lamentino del fatto che la rete sia particolarmente lenta a metà giornata. Un rapido sguardo ai rapporti attività di conferenza potrebbe suggerire un possibile motivo: molte più conferenze vengono pianificate tra le 10.00 e le 14.00 in qualsiasi altro momento.
  
Se la lentezza della rete crea problemi, è possibile chiedere agli utenti di riprogrammare alcune delle conferenze in orari di minor traffico.
  
## <a name="accessing-the-conference-activity-report"></a>Accesso al Rapporto attività conferenza

Il Rapporto attività conferenza è accessibile dal Rapporto riepilogativo [conferenze in Skype for Business Server](conference-summary-report.md) facendo clic su una delle metriche seguenti:
  
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
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Intervallo di tempo. Selezionare uno dei valori seguenti: <br/>  Orario (è possibile visualizzare al massimo 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con data di inizio 7/07/2015 e data di fine 28/02/2015, verranno visualizzati i dati per i giorni 07/08/2015 12.00 alle 07.00.00 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
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
   

