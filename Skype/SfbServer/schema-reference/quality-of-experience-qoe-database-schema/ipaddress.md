---
title: Tabella IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194616"
---
# <a name="ipaddress-table"></a>Tabella IPAddress
 
La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per l'indirizzo IP specificato.  <br/> |
|**IPAddress** <br/> |varchar (50)  <br/> |Univoci  <br/> |Indirizzo IP univoco, ad esempio 189.168.1.1, che esegue il mapping a IpAddressKey. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
   

