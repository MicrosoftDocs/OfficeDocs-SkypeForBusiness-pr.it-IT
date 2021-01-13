---
title: Sottoreport riepilogativo P2P in Skype for Business Server
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
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Riepilogo: informazioni sul sottoreport riepilogativo P2P in Skype for Business Server.'
ms.openlocfilehash: 518047fbca3c46cdc9b99299b8222d4f4fbd48ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816816"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Sottoreport riepilogativo P2P in Skype for Business Server
 
**Riepilogo:** Informazioni sul sottoreport riepilogativo P2P in Skype for Business Server.
  
Nel sottoreport riepilogativo P2P viene fornita una panoramica delle sessioni di comunicazione peer-to-peer non riuscite.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il sottoreport riepilogativo P2P.
  
**Filtri del sottoreport riepilogativo P2P**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su **[Tutto]** per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.<br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel sottoreport riepilogativo P2P.
  
**Metriche del sottoreport riepilogativo P2P**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Totale sessioni** <br/> |No  <br/> |Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.  <br/> |
|**Frequenza errori** <br/> |No  <br/> |Percentuale delle sessioni peer-to-peer non riuscite.  <br/> |
|**Sessioni per modalità** <br/> |No  <br/> |Numero totale di sessioni raggruppate per modalità (ad esempio, messaggistica istantanea).  <br/> |
|**Frequenza errori per modalità** <br/> |No  <br/> |Numero totale di sessioni non riuscite raggruppate per modalità (ad esempio, messaggistica istantanea).  <br/> |
   

