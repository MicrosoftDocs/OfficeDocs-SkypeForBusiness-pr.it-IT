---
title: Rapporto di diagnostica attività peer-to-peer in Skype for Business Server
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
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Riepilogo: informazioni sul Rapporto di diagnostica attività peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 1988dbbc6cf1e2bc54eeafee95756e7633d0ffde
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827736"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Rapporto di diagnostica attività peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto di diagnostica attività peer-to-peer in Skype for Business Server.
  
Il Rapporto di diagnostica attività peer-to-peer fornisce informazioni sull'esito positivo o negativo delle sessioni di comunicazione peer-to-peer. Skype for Business Server distingue tra diversi tipi di errore:
  
- **Errore previsto**. Un errore previsto è in genere un errore solo nel senso più tecnico del termine. Si supponga ad esempio di chiamare un utente, che però non è in ufficio e dunque non può rispondere al telefono. Poiché la chiamata non ha ricevuto risposta, tecnicamente viene considerata un errore. D'altra parte, si è verificato un errore previsto: Skype for Business Server non prevede che tu risponda al telefono se non sei disponibile a rispondere al telefono. Analogamente, si verificherà un errore previsto se si tenta di inviare un messaggio istantaneo a un utente offline, oppure connesso a un telefono che non supporta la messaggistica istantanea.
    
- **Errore imprevisto**. Un errore imprevisto è esattamente tale, ovvero un errore che, in determinate circostanze, non ci si aspetterebbe. Si supponga, ad esempio, di chiamare qualcuno e che sia disponibile a rispondere alla chiamata. Tuttavia, quando Skype for Business Server tenta di instradare la chiamata alla segreteria telefonica, la chiamata non riesce perché la connettività alla messaggistica unificata di Exchange è stata persa. Si tratta di un errore imprevisto: ci si aspetterebbe che le chiamate siano sempre instradati alla segreteria telefonica. Come regola generale, gli errori imprevisti sono errori veri: si tratta di problemi che probabilmente non possono essere corretti tramite l'istruzione degli utenti o misure simili.
    
Tenere presente che la somma delle metriche relative a esiti positivi, errori previsti ed errori imprevisti potrebbe non corrispondere al valore della metrica Totale sessioni. Ad esempio, nell'illustrazione precedente sono presenti i valori seguenti:
  
|**Operazioni riuscite**|**Errori previsti**|**Errori imprevisti**|**Totale sessioni**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16   <br/> |2521  <br/> |
   
Sommando 2024 + 469 + 16 si ottiene un totale di 2.509 sessioni, ma la colonna Totale sessioni mostra un totale di 2.521 sessioni. Le 12 sessioni "mancanti" sono quelle che il sistema non è riuscito a classificare come riuscite o non riuscite. Questo può capitare quando un prodotto di terze parti introduce un nuovo codice di diagnostica che non ha familiarità con Skype for Business Server. Quando ciò accade, le chiamate effettuate usando tale prodotto e contrassegnate da tale codice diagnostico non sempre possono essere correttamente classificate come un esito positivo, un errore previsto o un errore imprevisto.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Accesso al Rapporto di diagnostica attività peer-to-peer

Il rapporto di diagnostica peer-to-peer è accessibile dalla home page dei rapporti di monitoraggio. È possibile accedere al [Rapporto distribuzione errori in Skype for Business Server](failure-distribution-report.md) facendo clic su una delle metriche seguenti:
  
- Quantità di errori imprevisti
    
- Expected failure volume
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Uso ottimale del Rapporto di diagnostica attività peer-to-peer

È possibile filtrare il Rapporto di diagnostica attività peer-to-peer in vari modi, ma per impostazione predefinita le impostazioni di filtro sono nascoste. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante Mostra/Nascondi parametri nell'angolo superiore destro della finestra del rapporto. Fatto questo, le opzioni di filtro saranno disponibili per l'utilizzo.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più mirato o di visualizzare i dati restituiti in diversi modi. Il rapporto di diagnostica attività peer-to-peer ad esempio consente di filtrare i dati in base ad aspetti come la modalità della sessione, ovvero messaggistica istantanea, trasferimento di file o condivisione applicazioni. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In tal caso, le chiamate vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.
  
Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto di diagnostica attività peer-to-peer.
  
**Filtri per il rapporto di diagnostica attività peer-to-peer**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con data di inizio 7/7/2015 e data di fine 28/02/2015, i dati verranno visualizzati per i giorni 07/08/2015 12.00 al 7/09/2015 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su **[Tutto]** per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.<br/> |
|**Modality** <br/> | Indica il tipo di attività di comunicazione verificatasi. Selezionare una delle impostazioni seguenti: <br/>  [All] <br/>  Messaggistica istantanea <br/>  Trasferimento di file <br/>  Condivisione applicazioni <br/>  Audio <br/>  Video <br/> |
   
## <a name="metrics-per-modality"></a>Metrica (per modalità)

Nella tabella seguente sono riportate le informazioni fornite nel rapporto di diagnostica attività peer-to-peer per le singole modalità.
  
**Metrica (per modalità)**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Success volume** <br/> |No  <br/> |Numero totale di sessioni peer-to-peer con esito positivo.  <br/> |
|**Success percentage** <br/> |No  <br/> |Percentuale di sessioni peer-to-peer completate con problemi significativi. Viene calcolata dividendo il valore Success volume per il valore Total sessions.  <br/> |
|**Expected failure volume** <br/> |No  <br/> |Numero totale di sessioni in cui si è verificato un "errore previsto".  <br/> Per errore previsto si intende un problema che si prevedeva potesse verificarsi. Ad esempio, se un utente ha impostato il proprio stato su Non disturbare, è prevedibile che tutte le chiamate dirette a tale utente avranno esito negativo.  <br/> |
|**Expected failure percentage** <br/> |No  <br/> |Percentuale di sessioni peer-to-peer in cui si è verificato un errore previsto. Viene calcolata dividendo il valore Expected failure volume per il valore Total sessions.  <br/> |
|**Unexpected failure volume** <br/> |No  <br/> |Numero totale di sessioni in cui si è verificato un "errore imprevisto".  <br/> Per errore imprevisto si intende un problema che si verifica in un sistema apparentemente integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posto in attesa. Se si verifica tale problema, viene segnalato un errore imprevisto.  <br/> |
|**Unexpected failure percentage** <br/> |No  <br/> |Percentuale di sessioni peer-to-peer in cui si è verificato un errore imprevisto. Viene calcolata dividendo il valore Unexpected failure volume per il valore Total sessions.  <br/> |
|**Total sessions** <br/> |No  <br/> |Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.  <br/> |
   

