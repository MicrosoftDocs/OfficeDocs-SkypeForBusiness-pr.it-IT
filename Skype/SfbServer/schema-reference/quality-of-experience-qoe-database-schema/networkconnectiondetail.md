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
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194600"
---
# <a name="networkconnectiondetail-table"></a>Tabella NetworkConnectionDetail
 
La tabella NetworkConnectionDetail esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco per il tipo di connessione di rete.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Univoci  <br/> |Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:  <br/> 0--Wired  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--altro  <br/> 5--tunnel  <br/> |
   

