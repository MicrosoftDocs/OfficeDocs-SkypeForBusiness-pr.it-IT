---
title: Sottoreport riepilogo conferenze in Skype for Business Server
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
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 'Riepilogo: informazioni sul sottoreport riepilogo conferenza in Skype for Business Server.'
ms.openlocfilehash: 0d0b8fdc3971d60e326e59dd5417458533a10a31
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818066"
---
# <a name="conference-summary-subreport-in-skype-for-business-server"></a>Sottoreport riepilogo conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni sul sottoreport di riepilogo delle conferenze in Skype for Business Server.
  
Il sottoreport riepilogo conferenze offre una visualizzazione complessiva delle sessioni di conferenza non riuscite. Queste sessioni non riuscite sono ulteriormente suddivise per tipo di sessione: sessioni di stato di attivazione e sessioni MCU.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il sottoreport di riepilogo conferenza.
  
**Filtri per i sottoreport di riepilogo conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel sottoreport di riepilogo conferenza.
  
**Metriche del sottoreport di riepilogo conferenza**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Totale conferenze** <br/> |No  <br/> |Numero totale di conferenze organizzate.  <br/> |
|**Totale delle sessioni di conferenza** <br/> |No  <br/> |Numero totale di sessioni di conferenza. Una singola conferenza può avere più sessioni; ad esempio, una conferenza può includere sia una sessione dello stato di attivazione che una sessione MCU.  <br/> |
|**Tasso di errore complessivo della sessione** <br/> |No  <br/> |Percentuale di tutte le conferenze non riuscite.  <br/> |
|**Sessioni di stato attiva** <br/> |No  <br/> |Numero totale di sessioni di stato attivate.  <br/> |
|**Tasso di errore dello stato di avanzamento** <br/> |No  <br/> |Percentuale delle sessioni di stato di attivazione non riuscite.  <br/> |
|Sessioni MCU  <br/> |No  <br/> |Numero totale di sessioni MCU.  <br/> |
|**Tasso di errore MCU** <br/> |No  <br/> |Percentuale di sessioni MCU non riuscite.  <br/> |
|**Sessioni MCU per modalità** <br/> |No  <br/> |Numero totale di sessioni MCU, raggruppate per modalità (ad esempio, servizi di conferenza di messaggistica istantanea).  <br/> |
|**Tasso di errore per modalità** <br/> |No  <br/> |Percentuale di sessioni MCU non riuscite, raggruppate per modalità (ad esempio, servizi di conferenza di messaggistica istantanea).  <br/> |
   

