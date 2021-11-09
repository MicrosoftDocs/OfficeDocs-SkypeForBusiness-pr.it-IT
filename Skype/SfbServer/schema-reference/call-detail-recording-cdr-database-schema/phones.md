---
title: Tabella Telefoni
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabella Phones è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un numero di telefono coinvolto nelle chiamate VoIP con record nel database.
ms.openlocfilehash: 249b2a08e0751b6e8746f2da27a13e1151c375f7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836104"
---
# <a name="phones-table"></a>Tabella Telefoni
 
La tabella Phones è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un numero di telefono coinvolto nelle chiamate VoIP con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il telefono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Telefono numero.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Timestamp (solo per uso interno).  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

