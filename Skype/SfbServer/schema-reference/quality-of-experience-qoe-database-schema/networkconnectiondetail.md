---
title: Tabella NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807504"
---
# <a name="networkconnectiondetail-table"></a>Tabella NetworkConnectionDetail
 
La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco per il tipo di connessione di rete.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Univoci  <br/> |Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:  <br/> 0--Wired  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--altro  <br/> 5--tunnel  <br/> |
   

