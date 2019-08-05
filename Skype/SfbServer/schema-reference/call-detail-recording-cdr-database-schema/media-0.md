---
title: Visualizzazione multimediale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La visualizzazione multimediale archivia le informazioni su un tipo di elemento multimediale usato in una sessione peer-to-peer. Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194772"
---
# <a name="media-view"></a>Visualizzazione multimediale
 
La visualizzazione multimediale archivia le informazioni su un tipo di elemento multimediale usato in una sessione peer-to-peer. Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione multimediale non deve essere usata per calcolare la durata del supporto per una sessione. Questa visualizzazione contiene i dettagli di segnalazione dello scambio multimediale in una sessione. Lo scambio multimediale viene eseguito dalla richiesta di invito e StartTime indica l'ora in cui è stato inviato l'invito. Il tempo di invito non significa necessariamente l'ora di inizio del supporto, perché il supporto viene avviato solo dopo l'accettazione della sessione. 
  
La visualizzazione multimediale contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre a quelle elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar (256)  <br/> |Tipo di elemento multimediale. Per altre informazioni, vedere la [tabella degli elementi multimediali](medialist.md) . <br/> |
|**MediaStartTime** <br/> |DateTime  <br/> |Ora in cui è stata inviata una richiesta multimediale.  <br/> |
|**MediaEndTime** <br/> |DateTime  <br/> |Ora di fine della sessione.  <br/> |
   

