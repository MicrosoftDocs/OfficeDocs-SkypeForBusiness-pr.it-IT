---
title: Media table
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Ogni record rappresenta un tipo di supporto multimediale utilizzato in una sessione peer-to-peer. Una sessione viene rappresentata da più record nella tabella se viene utilizzato più di un tipo di supporto multimediale.
ms.openlocfilehash: 98c849c4ecde8e1c3be40d0aab3af606a400fb0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629428"
---
# <a name="media-table"></a>Media table
 
Ogni record rappresenta un tipo di supporto multimediale utilizzato in una sessione peer-to-peer. Una sessione viene rappresentata da più record nella tabella se viene utilizzato più di un tipo di supporto multimediale.
  
> [!NOTE]
> Non utilizzare la tabella Media per calcolare la durata media di una sessione. Questa tabella contiene i dettagli di segnalazione dello scambio multimediale in una sessione. Lo scambio multimediale viene eseguito dalla richiesta INVITE e StartTime indica l'ora di invio di tale richiesta. L'ora di invito non corrisponde necessariamente all'ora di inizio dello scambio multimediale, poiché questo inizia solo dopo che il destinatario ha accettato la sessione. EndTime in genere indica l'ora di fine della sessione. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primaria, esterna  <br/> |Numero univoco che identifica il tipo di elemento multimediale. Per ulteriori informazioni, vedi la [tabella MediaList.](medialist.md) <br/> |
|**StartTime** <br/> |datetime  <br/> |Principale  <br/> |Indica l'ora di invio di una richiesta di scambio multimediale e non l'ora di inizio dello scambio multimediale effettivo. **StartTime** include il tempo di configurazione della sessione.<br/> |
|**EndTime** <br/> |datetime  <br/> ||Ora di fine della sessione.  <br/> |
   

