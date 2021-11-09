---
title: Tabella PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: "Nella tabella PurgeSettings sono contenute informazioni che specificano se e quando i record QoE (qualità percepita dagli utenti) obsoleti verranno eliminati automaticamente dal database QoE. Tenere presente che le informazioni relative all'eliminazione possono essere ottenute anche dall'interno di Skype for Business Server Management Shell eseguendo il comando seguente:"
ms.openlocfilehash: ec89cdfbd634c32ab7a51265ed28e9ee89207892
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858083"
---
# <a name="purgesettings-table-qoe"></a>Tabella PurgeSettings (QoE)
 
Nella tabella PurgeSettings sono contenute informazioni che specificano se e quando i record QoE (qualità percepita dagli utenti) obsoleti verranno eliminati automaticamente dal database QoE. Tenere presente che le informazioni relative all'eliminazione possono essere ottenute anche dall'interno di Skype for Business Server Management Shell eseguendo il comando seguente:
  
```PowerShell
Get-CsQoEConfiguration
```

Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per la raccolta delle impostazioni di eliminazione QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Se impostato su True (1) Microsoft Lync Server 2013 elimina periodicamente i record non aggiornati dal database QoE. L'eliminazione verrà eseguita ogni giorno all'ora specificata dall'impostazione PurgeHour. Se impostato su False (0), i record non verranno eliminati automaticamente dal database. Il valore predefinito è True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Specifica la giacenza dei record QoE (in giorni) che verranno eliminati dal database. Se l'eliminazione è abilitata, i record QoE precedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 1 (1 del mattino). Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 1 (1 del mattino).  <br/> |
   

