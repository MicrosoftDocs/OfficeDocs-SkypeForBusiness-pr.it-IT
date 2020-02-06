---
title: Report tempo di partecipazione alla conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
description: "Riepilogo: informazioni sul report di riepilogo dell'ora di partecipazione alla conferenza in Skype for Business Server."
ms.openlocfilehash: 057d2bd756b866c1a01dd5fcd363a205deb8ecb8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817906"
---
# <a name="conference-join-time-report-in-skype-for-business-server"></a>Report tempo di partecipazione alla conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di riepilogo dell'ora di partecipazione alla conferenza in Skype for Business Server.
  
Il riepilogo dell'ora di partecipazione alla conferenza consente di determinare il tempo impiegato dagli utenti per partecipare a una conferenza. Il report Mostra il tempo medio di partecipazione (in millisecondi) e fornisce anche una ripartizione che consente di conoscere il numero di utenti che hanno potuto partecipare a una conferenza in 2 secondi o meno, il numero di utenti necessari tra 2 e 5 secondi per partecipare alla conferenza e così via.
  
## <a name="accessing-the-conference-join-time-report"></a>Accesso al report tempo di partecipazione alla conferenza

È possibile accedere al report Time join della conferenza dalla Home page dei report di monitoraggio.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report tempo di partecipazione alla conferenza.
  
**Filtri per i report sull'ora di conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
|**Sessioni di conferenza** <br/> | Tipo di sessione. I valori consentiti sono: <br/>  Tutti <br/>  Sessioni di stato attiva (lo stato principale è lo stato di policy e il gestore di stato per le riunioni online e coordina tutti gli aspetti di una conferenza <br/>  Condivisione applicazioni <br/>  Servizi di conferenza A/V <br/>  Se si seleziona [tutti], nella parte superiore del report verrà visualizzato il tempo totale di partecipazione alla conferenza. Tieni presente che questi totali sono solo per le conferenze pianificate con Microsoft Exchange o Microsoft Outlook. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report tempo di partecipazione alla conferenza.
  
**Metriche del report Time join conferenza**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Data** <br/> Il titolo effettivo per questa metrica sarà diverso a seconda dell'intervallo selezionato.  <br/> |No  <br/> |Data e ora in cui la conferenza ha avuto luogo.  <br/> |
|**Totale sessioni** <br/> |No  <br/> |Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.  <br/> |
|**Media (MS)** <br/> |No  <br/> |Intervallo di tempo medio (in millisecondi) che ha richiesto ai partecipanti di partecipare alla conferenza.  <br/> |
|**Sessioni \< 2 secondi, volume** <br/> |No  <br/> |Numero di partecipanti che hanno potuto partecipare alla conferenza in meno di 2 secondi.  <br/> |
|**Sessioni \< 2 secondi, percentuale** <br/> |No  <br/> ||
|**Sessioni 2-5 secondi, volume** <br/> |No  <br/> |Numero di partecipanti che hanno impiegato tra 2 secondi e 5 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni 2-5 secondi, percentuale** <br/> |No  <br/> |Percentuale dei partecipanti totali alle chiamate che hanno impiegato tra 2 secondi e 5 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni 5-10 secondi, volume** <br/> |No  <br/> |Numero di partecipanti che hanno impiegato tra 5 secondi e 10 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni 5-10 secondi, percentuale** <br/> |No  <br/> |Percentuale dei partecipanti totali alle chiamate che hanno impiegato tra 5 secondi e 10 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni \> di 10 secondi, volume** <br/> |No  <br/> |Numero di partecipanti che hanno richiesto più di 10 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni \> di 10 secondi, percentuale** <br/> |No  <br/> |Percentuale dei partecipanti totali alle chiamate che hanno richiesto più di 10 secondi per partecipare alla conferenza.  <br/> |
   

