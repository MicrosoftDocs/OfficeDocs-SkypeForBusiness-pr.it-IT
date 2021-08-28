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
ms.localizationpriority: medium
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili (Mcx) in Skype for Business Server 2015 per i client legacy.'
ms.openlocfilehash: 3a07279a099df44e72b65475af63340f27dc35d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632880"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server 2015
 
**Riepilogo:** Informazioni sul servizio per dispositivi mobili (Mcx) in Skype for Business Server 2015 per i client legacy.
  
Questo argomento si applica alle distribuzioni che supportano solo i client Lync Mobile di Lync 2010 ed è destinato al servizio per dispositivi mobili (Mcx).

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
Quando si abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio per dispositivi mobili di Skype for Business Server (Mcx), i file di registro generati possono consumare fino a tre gigabyte di spazio su disco al giorno. La registrazione della traccia IIS è abilitata per impostazione predefinita. È consigliabile monitorare i Front End Server per assicurarsi che non si esercitino spazio su disco. 
  
Per impostazione predefinita, in IIS i file di registro vengono archiviati in %SystemDrive%\inetpub\logs\LogFiles.
  
Per disattivare la traccia delle richieste di IIS per un intero server, digitare il comando seguente alla riga di comando:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Per informazioni dettagliate sul **comando httpLogging,** vedere [il riferimento al comando](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).
