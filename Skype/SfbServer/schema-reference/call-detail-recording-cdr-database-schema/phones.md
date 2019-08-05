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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabella telefoni è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un numero di telefono coinvolto in chiamate VoIP che includono record nel database.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194763"
---
# <a name="phones-table"></a>Tabella Phones
 
La tabella telefoni è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un numero di telefono coinvolto in chiamate VoIP che includono record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il telefono.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Numero di telefono.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Indicatore di data e ora (solo per uso interno).  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

