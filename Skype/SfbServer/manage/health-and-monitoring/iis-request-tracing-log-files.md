---
title: Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server 2015
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
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili (Mcx) nel supporto di Skype for Business Server 2015 per i client legacy.'
ms.openlocfilehash: 7d0d15b4c3db3d768117d73ed610b38c7a819196
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118635"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server 2015
 
**Riepilogo:** Informazioni sul servizio per dispositivi mobili (Mcx) nel supporto di Skype for Business Server 2015 per i client legacy.
  
Questo argomento si applica alle distribuzioni che supportano solo i client Lync Mobile di Lync 2010 ed è destinato al servizio per dispositivi mobili (Mcx).

> [!NOTE]
> Il supporto MCX (Servizio per dispositivi mobili) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client mobili Skype for Business correnti usano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Quando si abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio Per dispositivi mobili di Skype for Business Server (Mcx), i file di registro generati possono consumare fino a tre gigabyte di spazio su disco al giorno. La registrazione della traccia IIS è abilitata per impostazione predefinita. È consigliabile monitorare i Front End Server per assicurarsi che non si esercitino spazio su disco. 
  
Per impostazione predefinita, in IIS i file di registro vengono archiviati in %SystemDrive%\inetpub\logs\LogFiles.
  
Per disattivare la traccia delle richieste di IIS per un intero server, digitare il comando seguente alla riga di comando:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Per informazioni dettagliate sul **comando httpLogging,** vedere [il riferimento al comando](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).
