---
title: Tabella NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d1aa430f821233fcbf89f166bf76d3d8fadf76a9f7401ce5c9009629fccea70a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306697"
---
# <a name="networkconnectiondetail-table"></a>Tabella NetworkConnectionDetail
 
Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco del tipo di connessione di rete.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Univoco  <br/> |Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:  <br/> 0 - Cablata  <br/> 1 - Wi-Fi  <br/> 2 - Ethernet  <br/> 3 -- MobileBB  <br/> 4 - Altro  <br/> 5 - Tunnel  <br/> |
   

