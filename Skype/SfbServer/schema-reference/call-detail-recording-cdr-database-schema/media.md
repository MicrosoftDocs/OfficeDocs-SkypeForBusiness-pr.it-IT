---
title: Tabella Media
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Ogni record rappresenta un tipo di elemento multimediale usato in una sessione peer-to-peer. Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale.
ms.openlocfilehash: 181a78a9fc3fabe8c166f4cdc8c452b5a16b016b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194771"
---
# <a name="media-table"></a>Tabella Media
 
Ogni record rappresenta un tipo di elemento multimediale usato in una sessione peer-to-peer. Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale.
  
> [!NOTE]
> La tabella multimediale non deve essere usata per calcolare la durata del supporto per una sessione. Questa tabella contiene i dettagli di segnalazione dello scambio multimediale in una sessione. Lo scambio multimediale viene eseguito dalla richiesta di invito e StartTime indica l'ora in cui è stato inviato l'invito. Il tempo di invito non significa necessariamente l'ora di inizio dell'elemento multimediale, perché il supporto viene avviato solo dopo che la sessione viene accettata. Il EndTime in genere indica l'ora di fine della sessione. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora della richiesta della sessione. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primaria, straniera  <br/> |Numero univoco che identifica questo tipo di elemento multimediale. Per altre informazioni, vedere la [tabella degli elementi multimediali](medialist.md) . <br/> |
|**StartTime** <br/> |DateTime  <br/> |Principale  <br/> |Questo è il momento in cui è stata inviata una richiesta multimediale, non l'ora di inizio del media reale. **StartTime** include il tempo di configurazione della sessione. <br/> |
|**EndTime** <br/> |DateTime  <br/> ||Questa è l'ora di fine della sessione.  <br/> |
   

