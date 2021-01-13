---
title: Rapporto riepilogativo di diagnostica chiamate in Skype for Business Server
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
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Riepilogo: informazioni sul rapporto riepilogativo di diagnostica chiamata utilizzato in Skype for Business Server.'
ms.openlocfilehash: a0e024abfc083588a755a0d922c0eca23e526058
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810156"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Rapporto riepilogativo di diagnostica chiamate in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto riepilogativo di diagnostica chiamate utilizzato in Skype for Business Server.
  
Il Rapporto riepilogativo di diagnostica chiamate offre un quadro generale delle sessioni di conferenza e peer-to-peer non riuscite. Il rapporto illustra la percentuale generale degli errori per entrambi i tipi di sessioni e ulteriori dettagli sui problemi in base al tipo di modalità della sessione:
  
- Messaggistica istantanea
    
- Condivisione applicazioni
    
- Trasferimento di file
    
- Audio
    
- Video
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Accesso al Rapporto riepilogativo di diagnostica chiamate

Il Rapporto riepilogativo di diagnostica chiamate è accessibile dalla home page Rapporti di monitoraggio. Dal rapporto riepilogativo di diagnostica chiamate è possibile accedere al [rapporto di diagnostica attività peer-to-peer in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) facendo clic sulla metrica di frequenza di errore nella sezione peer-to-peer Session summary del report. È inoltre possibile accedere al [rapporto di diagnostica conferenze in Skype for Business Server](conference-diagnostic-report.md) facendo clic su una delle metriche di conferenza seguenti:
  
- Frequenza generale errori sessione
    
- Frequenza errori Focus
    
- Frequenza errori MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Uso ottimale del Rapporto riepilogativo di diagnostica chiamate

Il rapporto riepilogativo di diagnostica chiamata include grafici che confrontano i tassi di errore per le varie modalità utilizzate in Skype for Business Server. Le colonne di questi grafici sono in realtà hotlinks; ad esempio, se si fa clic sulla colonna messaggistica istantanea per le sessioni peer-to-peer, è possibile eseguire il drill-down in un'istanza del [rapporto di diagnostica attività peer-to-peer in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md), un report che fornisce ulteriori dettagli su tutte le sessioni di messaggistica istantanea incluse nel rapporto riepilogativo di diagnostica chiamate.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il rapporto riepilogativo di diagnostica chiamate consente di filtrare in base al pool di registrazione o al server perimetrale utilizzato nella sessione. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppabili per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo di diagnostica chiamate.
  
**Filtri del Rapporto riepilogativo di diagnostica chiamate**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Intervallo** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio pari a 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni da 8/7/2015 12:00 a 9/7/2015 12:00 (ovvero un totale di dati di 31 giorni). <br/> |
|**Pool** <br/> |Nome di dominio completo del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su **[Tutto]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record presenti nel database.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

La tabella seguente elenca le informazioni disponibili nel Rapporto riepilogativo di diagnostica chiamate per le sessioni peer-to-peer di conferenza, ovvero le sessioni che coinvolgono solo due partecipanti.
  
**Metriche per le sessioni peer-to-peer**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Totale sessioni** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer condotte.  <br/> |
|**Frequenza errori** <br/> |No  <br/> |Percentuale delle sessioni peer-to-peer non riuscite. Facendo clic su questo elemento verrà visualizzato il Rapporto di diagnostica attività peer-to-peer, che mostra informazioni più dettagliate sulle sessioni peer-to-peer non riuscite.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

La tabella seguente elenca le informazioni disponibili nel rapporto di diagnostica chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.
  
**Metriche per le sessioni di conferenza**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Totale conferenze** <br/> |No  <br/> |Numero totale di conferenze condotte.  <br/> |
|**Totale sessioni conferenza** <br/> |No  <br/> |Numero totale di sessioni di conferenza condotte.  <br/> |
|**Frequenza generale errori sessione** <br/> |No  <br/> |Percentuale del totale di sessioni di conferenza non riuscite.  <br/> |
|**Sessioni Focus** <br/> |No  <br/> |Numero totale di sessioni di conferenza basate su Focus non riuscite.  <br/> |
|**Frequenza errori Focus** <br/> |No  <br/> |Percentuale delle sessioni di conferenza basate su Focus non riuscite.  <br/> |
|**Sessioni MCU** <br/> |No  <br/> |Numero totale di conferenze basate su server per conferenze (in precedenza MCU, Multipoint Control Unit) non riuscite.  <br/> |
|**Frequenza errori MCU** <br/> |No  <br/> |Percentuale di totale di conferenze basate su server per conferenze (in precedenza MCU, Multipoint Control Unit) non riuscite.  <br/> |
   

