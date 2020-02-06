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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabella conferenze è una tabella di supporto. Ogni record rappresenta una conferenza o una sessione peer-to-peer.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810304"
---
# <a name="conference-table"></a>Tabella Conference
 
La tabella conferenze è una tabella di supporto. Ogni record rappresenta una conferenza o una sessione peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo record della conferenza.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |univoci  <br/> |URI conferenza se si tratta di una conferenza o di DialogID se si tratta di una sessione peer-to-peer.  <br/> |
|**Checksum** <br/> |int  <br/> |Indice  <br/> |Checksum dell'URI della conferenza. Viene usato internamente.  <br/> |
|**NextUpdateTS** <br/> |DateTime  <br/> ||Solo per uso interno.  <br/> |
   

