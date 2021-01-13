---
title: Rapporto tempo di partecipazione alla conferenza in Skype for Business Server
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
ms.assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
description: 'Riepilogo: informazioni sul rapporto riepilogativo per la conferenza di join Time in Skype for Business Server.'
ms.openlocfilehash: c84ea3f72aa4ed76ddb2bc11d40801aa1a9f6d59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827906"
---
# <a name="conference-join-time-report-in-skype-for-business-server"></a>Rapporto tempo di partecipazione alla conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto riepilogativo del tempo di partecipazione alla conferenza in Skype for Business Server.
  
Il rapporto Tempo di partecipazione alla conferenza consente di determinare il tempo richiesto agli utenti per partecipare a una conferenza. Nel rapporto viene visualizzato il tempo medio di partecipazione (in millisecondi) e sono inoltre disponibili informazioni suddivise che indicano il numero di utenti in grado di partecipare a una conferenza in massimo 2 secondi, il numero di utenti che hanno impiegato tra 2 e 5 secondi per partecipare e così via.
  
## <a name="accessing-the-conference-join-time-report"></a>Accesso al rapporto Tempo di partecipazione alla conferenza

È possibile accedere al rapporto Tempo di partecipazione alla conferenza dalla home page Relazioni monitoraggio.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il rapporto Tempo di partecipazione alla conferenza.
  
**Filtri del rapporto Tempo di partecipazione alla conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Intervallo** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio pari a 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni da 8/7/2015 12:00 a 9/7/2015 12:00 (ovvero un totale di dati di 31 giorni). <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su **[Tutto]** per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.<br/> |
|**Sessioni conferenza** <br/> | Tipo di sessione. I valori consentiti sono: <br/>  Tutti <br/>  Sessioni di messa a fuoco (lo stato attivo è il criterio centrale e il responsabile dello stato per le riunioni online e coordina tutti gli aspetti di una conferenza <br/>  Condivisione applicazioni <br/>  Conferenze audio/video <br/>  Se si seleziona [Tutto], nella parte superiore del rapporto verrà visualizzato il tempo totale di partecipazione alla conferenza. Si noti che questi totali sono riferiti solo alle conferenze pianificate tramite Microsoft Exchange o Microsoft Outlook. <br/> |
   
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel rapporto Tempo di partecipazione alla conferenza.
  
**Metriche del rapporto Tempo di partecipazione alla conferenza**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Data** <br/> Il titolo effettivo di questa metrica varia in base all'intervallo selezionato.  <br/> |No  <br/> |Data e ora in cui ha avuto luogo la conferenza.  <br/> |
|**Totale sessioni** <br/> |No  <br/> |Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.  <br/> |
|**Media (ms)** <br/> |No  <br/> |Quantità media di tempo (in millisecondi) impiegato dai partecipanti per partecipare alla conferenza.  <br/> |
|* * Sessioni \< 2 seconds, Volume** <br/> |No  <br/> |Numero di partecipanti che sono riusciti a partecipare alla conferenza in meno di 2 secondi.  <br/> |
|* * Sessioni \< 2 seconds, Percentage** <br/> |No  <br/> ||
|**Sessioni 2-5 secondi, Volume** <br/> |No  <br/> |Numero di partecipanti che hanno impiegato da 2 a 5 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni 2-5 secondi, Percentuale** <br/> |No  <br/> |Percentuale del numero totale di partecipanti che hanno impiegato da 2 a 5 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni 5-10 secondi, Volume** <br/> |No  <br/> |Numero di partecipanti che hanno impiegato da 5 a 10 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni 5-10 secondi, Percentuale** <br/> |No  <br/> |Percentuale del numero totale di partecipanti che hanno impiegato da 5 a 10 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni \> 10 secondi, volume** <br/> |No  <br/> |Numero di partecipanti che hanno impiegato più di 10 secondi per partecipare alla conferenza.  <br/> |
|**Sessioni \> 10 secondi, percentuale** <br/> |No  <br/> |Percentuale del numero totale di partecipanti che hanno impiegato più di 10 secondi per partecipare alla conferenza.  <br/> |
   

