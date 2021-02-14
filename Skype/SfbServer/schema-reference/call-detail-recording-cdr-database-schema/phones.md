---
title: Tabella Phones
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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabella Phones è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un numero di telefono coinvolto nelle chiamate VoIP con record nel database.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823266"
---
# <a name="phones-table"></a>Tabella Phones
 
La tabella Phones è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un numero di telefono coinvolto nelle chiamate VoIP con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il telefono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Numero di telefono.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Timestamp (solo per uso interno).  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

