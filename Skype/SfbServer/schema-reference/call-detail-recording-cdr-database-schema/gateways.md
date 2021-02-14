---
title: Tabella Gateways in Skype for Business Server 2015
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabella Gateways è una tabella di supporto. In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821586"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabella Gateways in Skype for Business Server 2015
 
La tabella Gateways è una tabella di supporto. In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome gateway.  <br/> |
   

