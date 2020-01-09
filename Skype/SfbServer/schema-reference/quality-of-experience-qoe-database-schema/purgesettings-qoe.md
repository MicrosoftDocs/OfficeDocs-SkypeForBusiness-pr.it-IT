---
title: Tabella PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: "La tabella PurgeSettings contiene informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE. Tieni presente che le informazioni correlate all'eliminazione possono essere ottenute anche da Skype for Business Server Management Shell eseguendo il comando seguente:"
ms.openlocfilehash: db102a84d58f03fb92a69a301b6906c4b146602c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992141"
---
# <a name="purgesettings-table-qoe"></a>Tabella PurgeSettings (QoE)
 
La tabella PurgeSettings contiene informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE. Tieni presente che le informazioni correlate all'eliminazione possono essere ottenute anche da Skype for Business Server Management Shell eseguendo il comando seguente:
  
```PowerShell
Get-CsQoEConfiguration
```

Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per la raccolta di impostazioni di ripulitura QoE.  <br/> |
|**EnablePurge** <br/> |po'  <br/> ||Se impostato su true (1) Microsoft Lync Server 2013 eliminerà periodicamente i record obsoleti dal database QoE. L'eliminazione verrà applicata ogni giorno al tomo specificato dall'impostazione PurgeHour. Se impostato su false (0), i record non verranno eliminati automaticamente dal database. Il valore predefinito è True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Specifica l'età dei record QoE (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record QoE antecedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera. Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita. Il valore predefinito è 1 (1:00 AM). Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera. Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita. Il valore predefinito è 1 (1:00 AM).  <br/> |
   

