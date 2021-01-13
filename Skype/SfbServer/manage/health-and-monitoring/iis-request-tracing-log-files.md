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
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili (MCX) in Skype for Business Server 2015 supporto per i client legacy.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823506"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server 2015
 
**Riepilogo:** Informazioni sul servizio per dispositivi mobili (MCX) in Skype for Business Server 2015 supporto per i client legacy.
  
Questo argomento si applica alle distribuzioni che supportano solo client Lync 2010 Lync mobile ed è progettato per il servizio per dispositivi mobili (MCX).

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Quando si Abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio per dispositivi mobili di Skype for Business Server (MCX), i file di registro generati possono utilizzare fino a tre gigabyte di spazio su disco al giorno. La registrazione della traccia IIS è abilitata per impostazione predefinita. È necessario monitorare i Front End Server per assicurarsi che non si esaurisca lo spazio su disco. 
  
Per impostazione predefinita, in IIS i file di registro vengono archiviati in %SystemDrive%\inetpub\logs\LogFiles.
  
Per disattivare la traccia delle richieste di IIS per un intero server, digitare il comando seguente alla riga di comando:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Per informazioni dettagliate sul comando **HttpLogging** , vedere [la Guida di riferimento al comando](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

