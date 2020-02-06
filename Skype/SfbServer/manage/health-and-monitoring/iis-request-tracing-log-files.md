---
title: Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business
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
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Riepilogo: informazioni sul servizio mobilità (MCX) nel supporto di Skype for Business Server 2015 per i client legacy.'
ms.openlocfilehash: 982e5842499e5cb2f6ff21ff884d1baa45075627
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817926"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business
 
**Riepilogo:** Informazioni sul servizio mobilità (MCX) nel supporto di Skype for Business Server 2015 per i client legacy.
  
Questo argomento si applica alle distribuzioni che supportano solo client Lync 2010 Lync mobile ed è destinato al servizio mobilità (MCX).

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Quando si Abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio mobilità di Skype for Business Server (MCX), i file di log generati possono utilizzare fino a tre gigabyte di spazio su disco al giorno. La registrazione della traccia di IIS è abilitata per impostazione predefinita. È consigliabile monitorare i server front-end per assicurarsi che non finiscano nello spazio su disco. 
  
Per impostazione predefinita, IIS archivia i file di log in%SystemDrive%\inetpub\logs\LogFiles.
  
Per disattivare la traccia delle richieste di IIS per un intero server, nella riga di comando digitare quanto segue:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Per informazioni dettagliate sul comando **HttpLogging** , Vedi [la pagina di riferimento del comando](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

