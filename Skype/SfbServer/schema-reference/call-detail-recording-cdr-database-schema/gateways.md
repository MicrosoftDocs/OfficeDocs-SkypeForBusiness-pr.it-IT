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
ms.localizationpriority: medium
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabella Gateways è una tabella di supporto. In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
ms.openlocfilehash: 7d0481def0d8693563b2558f6fa605c12d69ddfe
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601301"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabella Gateways in Skype for Business Server 2015
 
La tabella Gateways è una tabella di supporto. In ogni record vengono archiviate informazioni su un gateway coinvolto in chiamate PSTN (Public Switched Telephone Network) con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome gateway.  <br/> |
   

