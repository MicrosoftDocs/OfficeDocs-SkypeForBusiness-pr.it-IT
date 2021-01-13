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
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806306"
---
# <a name="networkconnectiondetail-table"></a>Tabella NetworkConnectionDetail
 
Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco del tipo di connessione di rete.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Univoco  <br/> |Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:  <br/> 0 - Cablata  <br/> 1 - Wi-Fi  <br/> 2 - Ethernet  <br/> 3--MobileBB  <br/> 4--altre  <br/> 5-tunnel  <br/> |
   

