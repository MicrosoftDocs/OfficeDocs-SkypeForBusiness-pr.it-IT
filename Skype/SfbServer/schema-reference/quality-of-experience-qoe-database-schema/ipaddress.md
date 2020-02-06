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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809544"
---
# <a name="ipaddress-table"></a>Tabella IPAddress
 
La tabella IPAddress esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati in un altro punto del database Quality of Experience. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per l'indirizzo IP specificato.  <br/> |
|**IPAddress** <br/> |varchar (50)  <br/> |Univoci  <br/> |Indirizzo IP univoco, ad esempio 189.168.1.1, che esegue il mapping a IpAddressKey. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
   

