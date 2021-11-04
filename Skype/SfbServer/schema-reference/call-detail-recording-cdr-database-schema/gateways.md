---
title: Tabella Gateways in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabella Gateways è una tabella di supporto. In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
ms.openlocfilehash: 35b552239d272f47d1f21c0940620dda4e6f075d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777756"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabella Gateways in Skype for Business Server 2015
 
La tabella Gateways è una tabella di supporto. In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome gateway.  <br/> |
   

