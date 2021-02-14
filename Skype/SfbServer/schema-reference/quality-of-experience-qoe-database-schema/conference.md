---
title: Tabella Conference
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabella Conference è una tabella di supporto. Ogni record rappresenta una sessione di conferenza o peer-to-peer.
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802786"
---
# <a name="conference-table"></a>Tabella Conference
 
La tabella Conference è una tabella di supporto. Ogni record rappresenta una sessione di conferenza o peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il record della conferenza.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.  <br/> |
|**Checksum** <br/> |int  <br/> |index  <br/> |Checksum dell'URI conferenza. Per uso interno.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo per uso interno.  <br/> |
   

