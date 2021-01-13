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
description: "La tabella PurgeSettings contiene informazioni che specificano se (e quando) i record dettagli chiamata obsoleti verranno eliminati automaticamente dal database CDR. Si noti che le informazioni relative all'eliminazione possono essere ottenute anche da Skype for Business Server 2015 eseguendo il comando seguente:"
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823166"
---
# <a name="purgesettings-table"></a>Tabella PurgeSettings
 
La tabella PurgeSettings contiene informazioni che specificano se (e quando) i record dettagli chiamata obsoleti verranno eliminati automaticamente dal database CDR. Si noti che le informazioni relative all'eliminazione possono essere ottenute anche da Skype for Business Server 2015 eseguendo il comando seguente:
  
```PowerShell
Get-CsCdrConfiguration
```

Gli amministratori devono considerare la tabella PurgeSettings come di sola lettura: le modifiche apportate alle impostazioni di eliminazione dei dettagli delle chiamate devono essere effettuate solo utilizzando i cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per la raccolta di impostazioni di eliminazione di registrazione dettagli chiamata.  <br/> |
|**EnablePurge** <br/> |po'  <br/> ||Se impostato su true (1) Skype for Business Server 2015 eliminerà periodicamente i record obsoleti dal database di registrazione dettagli chiamata. L'eliminazione verrà eseguita ogni giorno all'ora specificata dall'impostazione PurgeHour. Se impostato su False (0), i record non verranno eliminati automaticamente dal database. Il valore predefinito è True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Specifica l'età dei record di registrazione dettagli chiamata (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record CDR precedenti al valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Specifica l'età dei record di rapporto di errore (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record del rapporto errori precedenti al valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 2 (2.00).  <br/> |
   

