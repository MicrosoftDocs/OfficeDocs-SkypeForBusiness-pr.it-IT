---
title: Espansione delle impostazioni del server per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Ecco come fare per modificare le proprietà per questo computer:'
ms.openlocfilehash: 8b05fa82bcfeb10caa201ce303ddbbd8e8378b7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806656"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2f6e9-103">Espansione delle impostazioni del server per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2f6e9-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2f6e9-104">Ecco come fare per modificare le proprietà per questo computer:</span><span class="sxs-lookup"><span data-stu-id="2f6e9-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="2f6e9-p101">Modificare l'impostazione **Nome di dominio completo (FQDN)** per questo computer. Questa voce deve corrispondere al nome del computer così come è stato definito in DNS (Domain Name System) e nei nomi alternativi del soggetto (SAN) o nel nome soggetto (SN) del certificato associato al computer.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-p101">Edit the **Fully qualified domain name (FQDN)** for this computer. This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="2f6e9-107">Selezionare una di queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="2f6e9-107">You select one of the following:</span></span>
    
    <span data-ttu-id="2f6e9-108">**Usa tutti gli indirizzi IP configurati**: selezionare questa opzione per usare tutti gli indirizzi IP configurati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2f6e9-p102">Se il computer ha più indirizzi IP, è necessario tenere presente che i servizi associati al computer useranno tutti gli indirizzi IP per tutti i servizi. Se un server o un servizio di attesa attende le comunicazioni di una porta e un indirizzo IP specifici, il servizio potrebbe non selezionare nel modo migliore l'indirizzo IP su cui restare in attesa.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-p102">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services. If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="2f6e9-p103">**Limita utilizzo servizio a indirizzi IP selezionati**: selezionare questa opzione se si vuole definire indirizzi IP specifici in **Indirizzo IP primario** per l'indirizzo IP primario su cui il computer resterà in attesa delle comunicazioni da altri computer e pool nella distribuzione. Definire **Indirizzo IP PSTN** per l'indirizzo IP specifico su cui il computer o il servizio resteranno in attesa delle comunicazioni e invieranno le comunicazioni al gateway PSTN o all'IP-PBX definito.</span><span class="sxs-lookup"><span data-stu-id="2f6e9-p103">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment. Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

