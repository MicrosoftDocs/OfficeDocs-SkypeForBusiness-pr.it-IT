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
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: "La tabella PurgeSettings contiene informazioni che specificano se e quando i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database di registrazione dettagli chiamata. Tenere presente che le informazioni relative all'eliminazione possono essere ottenute anche da Skype for Business Server 2015 eseguendo il comando seguente:"
ms.openlocfilehash: 2e834f64ca5500f8d8bab1d89fb263d2708fa60c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098662"
---
# <a name="purgesettings-table"></a>Tabella PurgeSettings
 
La tabella PurgeSettings contiene informazioni che specificano se e quando i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database di registrazione dettagli chiamata. Tenere presente che le informazioni relative all'eliminazione possono essere ottenute anche da Skype for Business Server 2015 eseguendo il comando seguente:
  
```PowerShell
Get-CsCdrConfiguration
```

Gli amministratori devono considerare la tabella PurgeSettings di sola lettura: le modifiche alle impostazioni di eliminazione dei dettagli delle chiamate devono essere apportate solo utilizzando i cmdlet [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per la raccolta di impostazioni di eliminazione cdR.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Se impostato su True (1) Skype for Business Server 2015 elimina periodicamente i record non aggiornati dal database cdR. L'eliminazione verrà eseguita ogni giorno all'ora specificata dall'impostazione PurgeHour. Se impostato su False (0), i record non verranno eliminati automaticamente dal database. Il valore predefinito è True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Specifica la validità, in giorni, dei record cdR che verranno eliminati dal database: se l'eliminazione è abilitata, i record cdR precedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Specifica il periodo di validità, in giorni, dei record della segnalazione errori che verranno eliminati dal database: se l'eliminazione è abilitata, i record delle segnalazioni errori precedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 2 (2.00).  <br/> |
