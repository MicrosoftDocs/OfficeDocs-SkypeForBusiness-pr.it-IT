---
title: Tabella Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabella telefoni è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un numero di telefono coinvolto in chiamate VoIP che includono record nel database.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815004"
---
# <a name="phones-table"></a>Tabella Phones
 
La tabella telefoni è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un numero di telefono coinvolto in chiamate VoIP che includono record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il telefono.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Numero di telefono.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Indicatore di data e ora (solo per uso interno).  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

