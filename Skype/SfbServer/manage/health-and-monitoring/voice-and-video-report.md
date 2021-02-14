---
title: Rapporto voce e video peer-to-peer in Skype for Business Server
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
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Riepilogo: informazioni sul Rapporto voce e video peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 7e07c5778f43c3a0cac4ff162ed3d7dd1108eb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816616"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Rapporto voce e video peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto voce e video peer-to-peer in Skype for Business Server.
  
Il Rapporto voce e video peer-to-peer consente di esaminare in modo dettagliato la distribuzione delle chiamate voce e video per un periodo di tempo specificato, ad esempio le chiamate per ora o per giorno. Il rapporto offre inoltre la possibilità di visualizzare tutte le chiamate voce e video effettuate oppure solo quelle riuscite o non riuscite. Le informazioni sulle chiamate nel rapporto sono suddivise nei raggruppamenti seguenti:
  
- Chiamate per pool
    
- Chiamate per tipo di chiamata (ad esempio, una chiamata da Skype for Business a Skype for Business e una chiamata Skype for Business a una persona sulla rete PSTN)
    
- Chiamate per tipo di accesso (utenti connessi alla rete interna o alla rete esterna)
    
- Chiamate per Mediation Server
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Per accedere al rapporto voce e video peer-to-peer

L'unico modo per accedere al Rapporto voce e video peer-to-peer consiste nell'aprire il Rapporto riepilogativo attività peer-to-peer e fare clic su una delle metriche seguenti:
  
- Totale sessioni audio peer-to-peer
    
- Totale minuti sessioni audio peer-to-peer
    
- Totale sessioni audio peer-to-peer
    
- Totale minuti sessioni video peer-to-peer
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Per utilizzare in modo ottimale il rapporto voce e video peer-to-peer

È possibile filtrare il Rapporto voce e video peer-to-peer in vari modi. Le opzioni di filtro, tuttavia, sono nascoste dalla visualizzazione per impostazione predefinita. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante **Mostra/Nascondi parametri** nell'angolo in alto a destra della finestra Rapporto.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati. Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il Rapporto voce e video peer-to-peer.
  
**Filtri per il rapporto voce e video peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con data di inizio 7/7/2015 e data di fine 28/02/2015, i dati verranno visualizzati per i giorni 07/08/2015 12.00 al 7/09/2015 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
|**Tipo di supporto** <br/> | Indica il tipo di supporto utilizzato nella sezione. Selezionare una delle opzioni seguenti: <br/>  Entrambi <br/>  Audio <br/>  Video <br/> |
|**Disposizione chiamata** <br/> | Indica l'esito positivo o negativo della sezione. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  Chiamate riuscite <br/>  Chiamate non riuscite <br/> |
|**Rapporto di** <br/> | Indica i valori da utilizzare nel rapporto. Selezionare una delle impostazioni seguenti: <br/>  Numero di sessioni <br/>  Minuti chiamata <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Metriche per le attività voce e video peer-to-peer per pool

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto voce e video peer-to-peer per ogni pool.
  
**Metriche per le attività voce e video peer-to-peer per pool**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Pool** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale utilizzato per la chiamata.  <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui è stata effettuata la chiamata.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o di messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Metriche per le attività voce e video peer-to-peer per tipo di chiamata

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto voce e video peer-to-peer per ogni tipo di chiamata effettuata.
  
**Metriche per le attività voce e video peer-to-peer per tipo di chiamata**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di chiamata** <br/> |No  <br/> | Indica il tipo di chiamata che è stata effettuata. I valori sono uno dei seguenti: <br/>  Da UC a UC <br/>  Da UC a PSTN <br/>  Da PSTN a UC <br/>  Da PSTN a PSTN <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui è stata effettuata la chiamata.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o di messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Metriche per le attività voce e video peer-to-peer per tipo di accesso

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto voce e video peer-to-peer per ogni tipo di accesso di rete.
  
**Metriche per le attività voce e video peer-to-peer per tipo di accesso**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tipo di attività** <br/> |No  <br/> | Indica se al momento dell'esecuzione della chiamata i client sono connessi alla rete interna o a quella esterna. I valori sono in genere i seguenti: <br/>  Interno <br/>  Esterno <br/>  Misto <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui è stata effettuata la chiamata.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o di messaggi.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Metriche per le attività voce e video peer-to-peer per Mediation Server

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto voce e video peer-to-peer per ogni Mediation Server.
  
**Metriche per le attività voce e video peer-to-peer per Mediation Server**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Mediation Server** <br/> |No  <br/> |Nome del Mediation Server.  <br/> |
|**Data/ora** <br/> |No  <br/> |Data e ora in cui è stata effettuata la chiamata.  <br/> |
|**Totale** <br/> |No  <br/> |Numero totale di sessioni o di messaggi.  <br/> |
   

