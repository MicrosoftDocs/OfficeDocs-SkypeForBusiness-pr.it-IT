---
title: Espansione delle impostazioni del server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Per modificare le proprietà di questo computer, eseguire le operazioni seguenti:'
ms.openlocfilehash: da1029b6298d85aab8a80af1c52b152e040fbd80
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684409"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="3258b-103">Espansione delle impostazioni del server per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3258b-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="3258b-104">Per modificare le proprietà di questo computer, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3258b-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="3258b-105">Modificare il **nome di dominio completo (FQDN)** per il computer.</span><span class="sxs-lookup"><span data-stu-id="3258b-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="3258b-106">Questa voce deve corrispondere al nome del computer in quanto è definita nel DNS (Domain Name System) e in nomi alternativi oggetto (SAN) o nome soggetto (SN) del certificato associato al computer.</span><span class="sxs-lookup"><span data-stu-id="3258b-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="3258b-107">Si seleziona una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3258b-107">You select one of the following:</span></span>
    
    <span data-ttu-id="3258b-108">**Usare tutti gli indirizzi IP configurati**: selezionare questa funzionalità per usare tutti gli indirizzi IP configurati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3258b-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3258b-109">Se nel computer sono presenti più indirizzi IP, è necessario tenere presente che i servizi associati al computer utilizzeranno tutti gli indirizzi IP per tutti i servizi.</span><span class="sxs-lookup"><span data-stu-id="3258b-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="3258b-110">Se un server o un servizio di ascolto si aspetta la comunicazione di un determinato indirizzo IP e una porta, il servizio potrebbe non eseguire la selezione ottimale dell'indirizzo IP da ascoltare.</span><span class="sxs-lookup"><span data-stu-id="3258b-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="3258b-111">**Limitare l'utilizzo del servizio agli indirizzi IP selezionati**: selezionare questa opzione se si desidera definire indirizzi IP specifici per l' **indirizzo IP principale** che questo computer potrà ascoltare per comunicare da altri computer e pool nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3258b-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="3258b-112">Definisci l' **indirizzo IP PSTN** per l'indirizzo IP specifico che il computer e il servizio ascolteranno per le comunicazioni e invieranno comunicazioni al gateway PSTN o IP-PBX definito.</span><span class="sxs-lookup"><span data-stu-id="3258b-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

