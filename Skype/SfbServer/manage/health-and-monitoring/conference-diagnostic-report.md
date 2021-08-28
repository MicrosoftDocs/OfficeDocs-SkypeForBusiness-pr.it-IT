---
title: Rapporto di diagnostica conferenze in Skype for Business Server
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
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Riepilogo: informazioni sul Rapporto di diagnostica conferenze utilizzato in Skype for Business Server.'
ms.openlocfilehash: 578f4f2a60ca5dd1706d3b366e4decc35effeb7b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630640"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Rapporto di diagnostica conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto di diagnostica conferenze usato in Skype for Business Server.
  
Il Rapporto di diagnostica conferenze fornisce informazioni sull'esito positivo o negativo di tutte le sessioni di conferenza. Si noti Skype for Business Server distingue tra diversi tipi di errore:
  
- **Errore previsto**. Un errore previsto è tipicamente un errore solo in senso strettamente tecnico. Si immagini ad esempio che qualcuno avvii una conferenza, ma poi riagganci prima che qualcuno possa parteciparvi. Tecnicamente parlando, si tratta di un errore: la conferenza è stata avviata, ma non completata. Si tratta tuttavia di un errore previsto: se l'organizzatore annulla la conferenza prima che qualcuno possa parteciparvi, non ci si può aspettare che la conferenza venga completata.
    
- **Errore imprevisto**. Un errore imprevisto è esattamente tale, ovvero un errore che, in determinate circostanze, non ci si aspetterebbe. Si immagini ad esempio una conferenza che non possa essere tenuta perché non è possibile recuperare il criterio riunione dell'organizzatore. Questo è un errore imprevisto: dopotutto, dovrebbe essere sempre possibile recuperare il criterio riunione di un utente.
    
Si noti che le metriche di successo, errore previsto ed errore imprevisto potrebbero non sommarsi alla metrica totale delle sessioni. È ad esempio possibile che il report contenga i valori seguenti:
  
|**Operazioni riuscite**|**Errori previsti**|**Errori imprevisti**|**Totale sessioni**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16   <br/> |2521  <br/> |
   
Se si somma 2024 + 469 + 16 si ottiene un totale di 2.509 sessioni, tuttavia, nella colonna Totale sessioni viene indicato un totale di 2.521 sessioni. Le 12 sessioni "mancanti" sono quelle il cui esito non è stato definito come positivo o negativo. Questo a volte si verifica quando un prodotto di terze parti introduce un nuovo codice di diagnostica che non ha familiarità con Monitoring Server. In questi casi le chiamate fatte utilizzando tale prodotto, che presentano quel codice diagnostico, non possono essere categorizzate con Esito positivo, Errore previsto o Errore imprevisto.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Accesso al Rapporto di diagnostica conferenze

È possibile accedere al Rapporto di diagnostica conferenze dalla home page di Relazioni monitoraggio. Puoi accedere al [Rapporto distribuzione errori in Skype for Business Server](failure-distribution-report.md) facendo clic su una delle metriche seguenti:
  
- Quantità di errori imprevisti
    
- Quantità di errori previsti
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Utilizzare al meglio il Rapporto di diagnostica conferenze

Il Rapporto di diagnostica conferenze include una serie di grafici. Ogni colonna del grafico è un collegamento ipertestuale. Se si fa clic su una colonna, si eseguirà il [drill-down](failure-distribution-report.md) al Rapporto distribuzione errori in Skype for Business Server per quel periodo di tempo e per quel tipo di conferenza.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto di diagnostica conferenze consente di filtrare in base al tipo di conferenza condotto (ad esempio, una conferenza basata su Focus) o al server perimetrale utilizzato nella conferenza. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.
  
Nella tabella che segue sono elencati i filtri applicabili al Rapporto di diagnostica conferenze.
  
**Filtri del Rapporto di diagnostica conferenze**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con data di inizio 7/07/2015 e data di fine 28/02/2015, verranno visualizzati i dati per i giorni 07/08/2015 12.00 alle 07.00.00 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su **[Tutto]** per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.<br/> |
|**Sessioni conferenza** <br/> | Indica il tipo di sessione di conferenza. Selezionare una delle opzioni seguenti: <br/>  [All] <br/>  Sessioni Focus <br/>  Tutte le sessioni MCU <br/>  IM Conferencing <br/>  Condivisione applicazioni <br/>  Conferenze audio/video <br/> |
   
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel Rapporto di diagnostica conferenza per tipo di sessione.
  
**Metriche del Rapporto di diagnostica conferenze**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Success volume** <br/> |No  <br/> |Numero totale di conferenze riuscite.  <br/> |
|**Success percentage** <br/> |No  <br/> |Percentuale di conferenze completate con problemi significativi. Questo valore viene calcolato dividendo la quantità di conferenze con esito positivo per il numero totale delle sessioni.  <br/> |
|**Expected failure volume** <br/> |No  <br/> |Numero totale di conferenze in cui si è verificato un errore previsto.  <br/> Per errore previsto si intende un errore che è previsto che si verifichi. Se ad esempio un utente imposta il proprio stato su Non disturbare, è previsto che qualsiasi chiamata effettuata a tale utente non riesca.  <br/> |
|**Expected failure percentage** <br/> |No  <br/> |Percentuale di conferenze in cui si è verificato un errore previsto. Questo valore viene calcolato dividendo la quantità totale di errori previsti per il numero totale di sessioni.  <br/> |
|**Unexpected failure volume** <br/> |No  <br/> |Numero totale di conferenze in cui si è verificato un errore non previsto.  <br/> Per errore non previsto si intende un errore che si verifica in un sistema che sembrerebbe altrimenti integro. Ad esempio, una chiamata non dovrebbe essere terminata se il chiamante la mette in attesa. Se questo errore si verifica, viene contrassegnato come imprevisto.  <br/> |
|**Unexpected failure percentage** <br/> |No  <br/> |Percentuale di conferenze in cui si è verificato un errore imprevisto. Questo valore viene calcolato dividendo la quantità totale di errori imprevisti per il numero totale di sessioni.  <br/> |
|**Totale sessioni** <br/> |No  <br/> |Numero totale di conferenze, incluse quelle riuscite, non riuscite (per errori previsti e imprevisti) e non categorizzate.  <br/> |
   

