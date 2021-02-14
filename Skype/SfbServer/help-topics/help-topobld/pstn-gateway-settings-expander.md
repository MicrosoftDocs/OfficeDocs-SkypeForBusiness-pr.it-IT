---
title: Espansione delle impostazioni del gateway PSTN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:'
ms.openlocfilehash: 56f26a4113841b7563e42180aa51a80eedb2f859
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823726"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="c7b8b-103">Espansione delle impostazioni del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="c7b8b-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="c7b8b-104">Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7b8b-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="c7b8b-105">FQDN gateway o Indirizzo IP è una voce obbligatoria e indica se il **Nome di dominio completo (FQDN)** del gateway PSTN è definito da un record (A) dell'host DNS (Domain Name System), da una immissione di file HOSTS statico o dall'indirizzo IP del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="c7b8b-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="c7b8b-p101">Il protocollo di trasporto SIP può essere TCP (Transmission Control Protocol) o TLS (Transport Layer Security). TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, fare riferimento alla documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.</span><span class="sxs-lookup"><span data-stu-id="c7b8b-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="c7b8b-110">Selezionare se abilitare IPv4 e IPv6 per il gateway.</span><span class="sxs-lookup"><span data-stu-id="c7b8b-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="c7b8b-p102">**Indirizzo IP supporto alternativo** è una definizione per Mediation Server, in base a cui il gateway PSTN distribuito dispone di un indirizzo IP diverso per il traffico multimediale rispetto all'indirizzo IP configurato predefinito, che è in genere dedicato al traffico SIP. Se si definisce questo parametro, il gateway PSTN supporterà un percorso o un'interfaccia di rete diversa per i dati multimediali. Se il campo relativo a questo indirizzo viene lasciato vuoto, il gateway PSTN non supporterà il percorso alternativo per i dati multimediali.</span><span class="sxs-lookup"><span data-stu-id="c7b8b-p102">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic. If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media. If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

