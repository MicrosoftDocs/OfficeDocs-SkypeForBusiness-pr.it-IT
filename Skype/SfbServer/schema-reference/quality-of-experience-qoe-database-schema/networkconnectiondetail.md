---
title: Tabella NetworkConnectionDetail
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
---

# <a name="networkconnectiondetail-table"></a>Tabella NetworkConnectionDetail
 
Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco del tipo di connessione di rete.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Univoco  <br/> |Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:  <br/> 0 - Cablata  <br/> 1 - Wi-Fi  <br/> 2 - Ethernet  <br/> 3 -- MobileBB  <br/> 4 - Altro  <br/> 5 - Tunnel  <br/> |
   

