---
title: Tabella PurgeSettings
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: "La tabella PurgeSettings contiene informazioni che specificano se e quando i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database di registrazione dettagli chiamata. Si noti che le informazioni relative all'eliminazione possono essere ottenute anche dall'Skype for Business Server 2015 eseguendo il comando seguente:"
ms.openlocfilehash: 3f1f596bd6e8d61c491c93c3664e1f4d110ccf8b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623468"
---
# <a name="purgesettings-table"></a>Tabella PurgeSettings
 
La tabella PurgeSettings contiene informazioni che specificano se e quando i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database di registrazione dettagli chiamata. Si noti che le informazioni relative all'eliminazione possono essere ottenute anche dall'Skype for Business Server 2015 eseguendo il comando seguente:
  
```PowerShell
Get-CsCdrConfiguration
```

Gli amministratori devono considerare la tabella PurgeSettings di sola lettura: le modifiche alle impostazioni di eliminazione dei dettagli delle chiamate devono essere apportate solo utilizzando i cmdlet [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per la raccolta di impostazioni di eliminazione cdR.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Se impostato su True (1) Skype for Business Server 2015, i record non aggiornati verranno eliminati periodicamente dal database cdR. L'eliminazione verrà eseguita ogni giorno all'ora specificata dall'impostazione PurgeHour. Se impostato su False (0), i record non verranno eliminati automaticamente dal database. Il valore predefinito è True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Specifica il periodo di validità, in giorni, dei record cdR che verranno eliminati dal database: se l'eliminazione è abilitata, i record cdR precedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Specifica il periodo di validità, in giorni, dei record della segnalazione errori che verranno eliminati dal database: se l'eliminazione è abilitata, i record delle segnalazioni errori precedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 2 (2.00).  <br/> |
