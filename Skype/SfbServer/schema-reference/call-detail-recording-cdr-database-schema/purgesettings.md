---
title: Tabella PurgeSettings
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: "La tabella PurgeSettings contiene informazioni che specificano se (e quando) i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database CDR. Tieni presente che le informazioni correlate all'eliminazione possono essere ottenute anche da Skype for Business Server 2015 eseguendo il comando seguente:"
ms.openlocfilehash: 6aac92555dda6875f23a177bb09384f453369846
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194757"
---
# <a name="purgesettings-table"></a>Tabella PurgeSettings
 
La tabella PurgeSettings contiene informazioni che specificano se (e quando) i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database CDR. Tieni presente che le informazioni correlate all'eliminazione possono essere ottenute anche da Skype for Business Server 2015 eseguendo il comando seguente:
  
```
Get-CsCdrConfiguration
```

Gli amministratori devono considerare la tabella PurgeSettings come di sola lettura: le modifiche alle impostazioni di eliminazione dei dettagli delle chiamate devono essere effettuate solo usando i cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) o [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per la raccolta di impostazioni di ripulitura CDR.  <br/> |
|**EnablePurge** <br/> |po'  <br/> ||Se impostato su true (1) Skype for Business Server 2015 eliminerà periodicamente i record obsoleti dal database CDR. L'eliminazione verrà applicata ogni giorno al tomo specificato dall'impostazione PurgeHour. Se impostato su false (0), i record non verranno eliminati automaticamente dal database. Il valore predefinito è True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Specifica l'età dei record CDR (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record CDR più vecchi di questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Specifica l'età dei record di report sugli errori (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record dei report di errore antecedenti al valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera. Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita. Il valore predefinito è 2 (2.00).  <br/> |
   

