---
title: Tabella Conferenze
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
ms.openlocfilehash: 6dfe60a28e8279f7b4c469c61cddc28912db261eedf4754588de4bd8f5852728
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309155"
---
# <a name="conference-table"></a>Tabella Conferenze
 
La tabella Conference è una tabella di supporto. Ogni record rappresenta una sessione di conferenza o peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il record della conferenza.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.  <br/> |
|**Checksum** <br/> |int  <br/> |index  <br/> |Checksum dell'URI conferenza. Per uso interno.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo per uso interno.  <br/> |
   

