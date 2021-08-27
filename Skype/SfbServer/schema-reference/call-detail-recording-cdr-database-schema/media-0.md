---
title: Visualizzazione elementi multimediali
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Nella visualizzazione Media vengono archiviate le informazioni sul tipo di supporto utilizzato in una sessione peer-to-peer. Qualora si utilizzino più supporti, nella tabella saranno presenti più record per una sessione. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 7297e3c0e4d8839fc820334ee4dabb7412242245
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617682"
---
# <a name="media-view"></a>Visualizzazione elementi multimediali
 
Nella visualizzazione Media vengono archiviate le informazioni sul tipo di supporto utilizzato in una sessione peer-to-peer. Qualora si utilizzino più supporti, nella tabella saranno presenti più record per una sessione. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione Media non deve essere utilizzata per calcolare la durata di utilizzo del supporto in una sessione. Questa visualizzazione contiene i dettagli di segnalazione dello scambio di supporti in una sessione. Lo scambio dei supporti viene effettuato mediante la richiesta INVITE, mentre StartTime indica l'ora in cui la richiesta INVITE è stata inviata. L'ora dell'invito non corrisponde necessariamente all'ora di inizio del supporto poiché questo viene avviato solo dopo che la sessione è stata accettata. 
  
La visualizzazione Media contiene tutte le colonne nella [visualizzazione SessionDetails](sessiondetails-0.md) oltre a quelle elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**Contenuti multimediali** <br/> |nvarchar(256)  <br/> |Tipo di supporto. Per ulteriori informazioni, vedi la [tabella MediaList.](medialist.md) <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Ora di invio di una richiesta di supporto.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Ora di fine della sessione.  <br/> |
   

