---
title: Report di diagnostica per conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Riepilogo: informazioni sul report di diagnostica per le conferenze usato in Skype for Business Server.'
ms.openlocfilehash: bfe84c50b3aaee53da1dc460f501e3c9a82528af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191372"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Report di diagnostica per conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di diagnostica per le conferenze usato in Skype for Business Server.
  
Il report di diagnostica conferenza fornisce informazioni sull'esito positivo e negativo di tutte le sessioni di conferenza. Tieni presente che Skype for Business Server distingue i diversi tipi di errore:
  
- **Errore previsto**. Un errore previsto è in genere un errore solo in senso più tecnico. Ad esempio, supponiamo che qualcuno inizi una conferenza, ma si riaggancia prima che tutti possano partecipare. Tecnicamente si tratta di un errore: la conferenza è stata avviata, ma non è stata completata. Tuttavia, questo è un errore che ci si aspetterebbe di avere: se l'organizzatore Annulla la conferenza prima che tutti possano partecipare, non si prevede che la conferenza venga completata.
    
- **Errore imprevisto**. Un errore imprevisto è esattamente quello che il nome implica: un errore che, in base alle circostanze, non si aspetterebbe che si verifichi. Supponiamo ad esempio che non sia possibile tenere una conferenza perché non è stato possibile recuperare i criteri della riunione dell'organizzatore. Si tratta di un errore imprevisto: dopo tutto, dovresti sempre essere in grado di recuperare i criteri di riunione di un utente.
    
Tieni presente che l'esito positivo, l'errore previsto e le metriche degli errori imprevisti potrebbero non essere sommati alla metrica totale delle sessioni. Ad esempio, è possibile che nel report vengano visualizzati i valori seguenti:
  
|**Successi**|**Errori previsti**|**Errori imprevisti**|**Totale sessioni**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Se si aggiunge 2024 + 469 + 16 si ottengono complessivamente 2.509 sessioni, ma la colonna Total Sessions Mostra un totale di 2.521 sessioni. Le sessioni "mancanti" di 12 sono sessioni che il sistema non è in grado di categorizzare in modo riuscito o fallito. A volte succede quando un prodotto di terze parti introduce un nuovo codice diagnostico che non conosce il server di monitoraggio. In questo caso, le chiamate effettuate tramite tale prodotto e segnalando il codice diagnostico non possono sempre essere categorizzate come un successo, un errore previsto o un errore imprevisto.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Accesso al report di diagnostica conferenza

È possibile accedere al report di diagnostica della conferenza dalla Home page dei report di monitoraggio. Per accedere al [report di distribuzione dell'errore in Skype for Business Server](failure-distribution-report.md) , fare clic su una delle metriche seguenti:
  
- Volume di errore imprevisto
    
- Volume di errore previsto
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Uso ottimale del report di diagnostica conferenza

Il report di diagnostica conferenza include una serie di grafici. Ognuna delle colonne visualizzate nel grafico è in realtà un collegamento ipertestuale. Se si fa clic su una colonna, è possibile eseguire il drill-down [nel report di distribuzione dell'errore in Skype for Business Server](failure-distribution-report.md) per il periodo di tempo e il tipo di conferenza.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report di diagnostica per le conferenze consente di filtrare in base al tipo di conferenza che viene eseguita, ad esempio una conferenza basata su stato attivo, o dall'Edge Server usato nella conferenza. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le conferenze vengono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report di diagnostica conferenza.
  
**Filtri di report di diagnostica conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
|**Sessioni di conferenza** <br/> | Indica il tipo di sessione di conferenza. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Sessioni di stato attiva <br/>  Tutte le sessioni MCU <br/>  Conferenza di messaggistica istantanea <br/>  Condivisione applicazioni <br/>  Servizi di conferenza A/V <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica conferenza per ogni tipo di sessione di conferenza.
  
**Metriche del report di diagnostica conferenza**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Volume di successo** <br/> |No  <br/> |Numero totale di conferenze di successo.  <br/> |
|**Percentuale di successo** <br/> |No  <br/> |Percentuale di conferenze completate con problemi significativi. Calcolata dividendo il volume di successo per il totale delle sessioni.  <br/> |
|**Volume di errore previsto** <br/> |No  <br/> |Numero totale di conferenze in cui si è verificato un "errore previsto".  <br/> Un errore previsto è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.  <br/> |
|**Percentuale di errore prevista** <br/> |No  <br/> |Percentuale di conferenze con un errore previsto. Calcolata dividendo il volume di errore previsto per le sessioni totali.  <br/> |
|**Volume di errore imprevisto** <br/> |No  <br/> |Numero totale di conferenze in cui si è verificato un "errore imprevisto".  <br/> Un errore imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto.  <br/> |
|**Percentuale di errore imprevisto** <br/> |No  <br/> |Percentuale di conferenze in cui si è verificato un errore imprevisto. Calcolata dividendo il volume di errore imprevisto per le sessioni totali.  <br/> |
|**Totale sessioni** <br/> |No  <br/> |Numero totale di conferenze, tra cui conferenze di successo, conferenze non riuscite (errori previsti e errori imprevisti) e conferenze Uncategorized.  <br/> |
   

