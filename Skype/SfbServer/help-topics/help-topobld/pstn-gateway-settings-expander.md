---
title: Espansione delle impostazioni del gateway PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:'
ms.openlocfilehash: d84cede93166a94b353134991143089702a0d2fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191615"
---
# <a name="pstn-gateway-settings-expander"></a>Espansione delle impostazioni del gateway PSTN
 
Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:
  
FQDN gateway o Indirizzo IP è una voce obbligatoria e indica se il **Nome di dominio completo (FQDN)** del gateway PSTN è definito da un record (A) dell'host DNS (Domain Name System), da una immissione di file HOSTS statico o dall'indirizzo IP del gateway PSTN.
  
Il protocollo di trasporto SIP può essere TCP (Transmission Control Protocol) o TLS (Transport Layer Security). TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, fare riferimento alla documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.
  
Selezionare se abilitare IPv4 e IPv6 per il gateway.
  
L' **indirizzo IP multimediale alternativo** è una definizione per il Mediation Server per cui il gateway PSTN distribuito ha un indirizzo IP diverso per il traffico multimediale rispetto all'indirizzo IP configurato predefinito, che in genere è dedicato al traffico SIP. Se si definisce questo parametro, il gateway PSTN supporterà un percorso o un'interfaccia di rete diversa per i dati multimediali. Se il campo relativo a questo indirizzo viene lasciato vuoto, il gateway PSTN non supporterà il percorso alternativo per i dati multimediali.
  

