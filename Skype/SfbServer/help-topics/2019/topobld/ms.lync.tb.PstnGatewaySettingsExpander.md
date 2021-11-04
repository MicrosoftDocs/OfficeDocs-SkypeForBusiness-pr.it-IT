---
title: Espansione delle impostazioni del gateway PSTN
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:'
ms.openlocfilehash: f26bc66b771b872f8601a7c9d6c8928781beca64
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769204"
---
# <a name="pstn-gateway-settings-expander"></a>Espansione delle impostazioni del gateway PSTN
 
Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:
  
FQDN gateway o Indirizzo IP è una voce obbligatoria e indica se il **Nome di dominio completo (FQDN)** del gateway PSTN è definito da un record (A) dell'host DNS (Domain Name System), da una immissione di file HOSTS statico o dall'indirizzo IP del gateway PSTN.
  
Il protocollo di trasporto SIP può essere TCP (Transmission Control Protocol) o TLS (Transport Layer Security). TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, fare riferimento alla documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.
  
Selezionare se abilitare IPv4 e IPv6 per il gateway.
  
**Indirizzo IP supporto alternativo** è una definizione per Mediation Server, in base a cui il gateway PSTN distribuito dispone di un indirizzo IP diverso per il traffico multimediale rispetto all'indirizzo IP configurato predefinito, che è in genere dedicato al traffico SIP. Se si definisce questo parametro, il gateway PSTN supporterà un percorso o un'interfaccia di rete diversa per i dati multimediali. Se il campo relativo a questo indirizzo viene lasciato vuoto, il gateway PSTN non supporterà il percorso alternativo per i dati multimediali.
  

