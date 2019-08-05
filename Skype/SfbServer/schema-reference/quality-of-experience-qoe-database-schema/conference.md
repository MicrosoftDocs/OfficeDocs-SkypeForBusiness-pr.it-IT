---
title: Tabella Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabella conferenze è una tabella di supporto. Ogni record rappresenta una conferenza o una sessione peer-to-peer.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194629"
---
# <a name="conference-table"></a>Tabella Conference
 
La tabella conferenze è una tabella di supporto. Ogni record rappresenta una conferenza o una sessione peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo record della conferenza.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |univoci  <br/> |URI conferenza se si tratta di una conferenza o di DialogID se si tratta di una sessione peer-to-peer.  <br/> |
|**Checksum** <br/> |int  <br/> |Indice  <br/> |Checksum dell'URI della conferenza. Viene usato internamente.  <br/> |
|**NextUpdateTS** <br/> |DateTime  <br/> ||Solo per uso interno.  <br/> |
   

