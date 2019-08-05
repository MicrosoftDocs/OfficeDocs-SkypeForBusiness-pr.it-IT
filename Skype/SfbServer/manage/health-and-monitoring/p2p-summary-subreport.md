---
title: Sottoreport di riepilogo P2P in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Riepilogo: informazioni sul sottoreport di riepilogo P2P in Skype for Business Server.'
ms.openlocfilehash: 5238e910896a6af956285235d7e1234fe17fe005
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188753"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Sottoreport di riepilogo P2P in Skype for Business Server
 
**Riepilogo:** Informazioni sul sottoreport di riepilogo P2P in Skype for Business Server.
  
Il sottoreport di riepilogo P2P offre una visualizzazione complessiva delle sessioni di comunicazione peer-to-peer non riuscite.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il sottoreport di riepilogo P2P.
  
**Filtri per i sottoreport di riepilogo P2P**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
   
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni fornite nel sottoreport di riepilogo P2P.
  
**Metriche per il sottoreport di riepilogo P2P**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Totale sessioni** <br/> |No  <br/> |Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.  <br/> |
|**Tasso di errore** <br/> |No  <br/> |Percentuale di sessioni peer-to-peer non riuscite.  <br/> |
|**Sessioni per modalità** <br/> |No  <br/> |Numero totale di sessioni raggruppate per modalità, ad esempio la messaggistica istantanea.  <br/> |
|**Tasso di errore per modalità** <br/> |No  <br/> |Numero totale di sessioni non riuscite raggruppate per modalità, ad esempio la messaggistica istantanea.  <br/> |
   

