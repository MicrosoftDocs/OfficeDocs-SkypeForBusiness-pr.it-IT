---
title: Tabella IPAddress
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabella IPAddress mappa gli indirizzi IP agli identificatori di indirizzo IP univoci usati altrove nel database QoS (Quality of Experience). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802776"
---
# <a name="ipaddress-table"></a>Tabella IPAddress
 
La tabella IPAddress mappa gli indirizzi IP agli identificatori di indirizzo IP univoci usati altrove nel database QoS (Quality of Experience). Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco per l'indirizzo IP specificato.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Univoco  <br/> |Indirizzo IP univoco (ad esempio, 189.168.1.1) mappato a IpAddressKey. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
   

