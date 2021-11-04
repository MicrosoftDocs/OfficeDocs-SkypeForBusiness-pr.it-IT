---
title: Tabella Conferenze
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabella Conference è una tabella di supporto. Ogni record rappresenta una sessione di conferenza o peer-to-peer.
ms.openlocfilehash: b5129fec73658d86fdb8d5cd7dd5c387cdadf4f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763214"
---
# <a name="conference-table"></a>Tabella Conferenze
 
La tabella Conference è una tabella di supporto. Ogni record rappresenta una sessione di conferenza o peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il record della conferenza.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.  <br/> |
|**Checksum** <br/> |int  <br/> |index  <br/> |Checksum dell'URI conferenza. Per uso interno.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo per uso interno.  <br/> |
   

