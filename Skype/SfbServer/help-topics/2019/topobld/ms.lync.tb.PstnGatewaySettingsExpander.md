---
title: Espansione delle impostazioni del gateway PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:'
ms.openlocfilehash: 7b0d823a21f2e0e9eb1e75a37365095877885cac
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794174"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="d0f38-103">Espansione delle impostazioni del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="d0f38-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="d0f38-104">Per modificare o cambiare le impostazioni per un gateway PSTN (Public Switched Telephone Network), modificare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0f38-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="d0f38-105">FQDN gateway o Indirizzo IP è una voce obbligatoria e indica se il **Nome di dominio completo (FQDN)** del gateway PSTN è definito da un record (A) dell'host DNS (Domain Name System), da una immissione di file HOSTS statico o dall'indirizzo IP del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d0f38-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="d0f38-p101">Il protocollo di trasporto SIP può essere TCP (Transmission Control Protocol) o TLS (Transport Layer Security). TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, fare riferimento alla documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.</span><span class="sxs-lookup"><span data-stu-id="d0f38-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="d0f38-110">Selezionare se abilitare IPv4 e IPv6 per il gateway.</span><span class="sxs-lookup"><span data-stu-id="d0f38-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="d0f38-111">L' **indirizzo IP multimediale alternativo** è una definizione per il Mediation Server per cui il gateway PSTN distribuito ha un indirizzo IP diverso per il traffico multimediale rispetto all'indirizzo IP configurato predefinito, che in genere è dedicato al traffico SIP.</span><span class="sxs-lookup"><span data-stu-id="d0f38-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="d0f38-112">Se si definisce questo parametro, il gateway PSTN supporterà un percorso o un'interfaccia di rete diversa per i dati multimediali.</span><span class="sxs-lookup"><span data-stu-id="d0f38-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="d0f38-113">Se il campo relativo a questo indirizzo viene lasciato vuoto, il gateway PSTN non supporterà il percorso alternativo per i dati multimediali.</span><span class="sxs-lookup"><span data-stu-id="d0f38-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

