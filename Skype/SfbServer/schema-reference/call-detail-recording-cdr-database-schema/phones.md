---
title: Tabella Telefoni
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 0dbe5065b4a0849b4538e77c05a846ed06f72da5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389808"
---
# <a name="phones-table"></a>Tabella Telefoni
 
La tabella Phones è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un numero di telefono coinvolto nelle chiamate VoIP con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il telefono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Telefono numero.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Timestamp (solo per uso interno).  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

