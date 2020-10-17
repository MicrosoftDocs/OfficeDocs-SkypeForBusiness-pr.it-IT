---
title: "Lync Server 2013: abilitare gli utenti per l'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b4c060cfce4e45f4736abcbc0d4c9d02b1abc1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528553"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="8e459-102">Abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e459-102">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e459-103">_**Ultimo argomento modificato:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="8e459-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="8e459-104">Quando si distribuisce Lync Server 2013 e si pubblica la topologia, l'archivio contatti unificato è abilitato per tutti gli utenti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8e459-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="8e459-105">Non è necessario eseguire ulteriori operazioni per abilitare l'archivio contatti unificato dopo la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e459-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="8e459-106">Tuttavia, è possibile utilizzare il cmdlet **Set-CsUserServicesPolicy** per decidere a quali utenti rendere l'archivio unificato per i contatti disponibile.</span><span class="sxs-lookup"><span data-stu-id="8e459-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="8e459-107">È possibile abilitare questa caratteristica a livello globale, di sito, tenant, o per utenti singoli o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="8e459-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="8e459-108">Per abilitare gli utenti all'archivio unificato contatti</span><span class="sxs-lookup"><span data-stu-id="8e459-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="8e459-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8e459-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8e459-110">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e459-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="8e459-111">Per abilitare l'archivio contatti unificato a livello globale per tutti gli utenti di Lync Server, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8e459-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="8e459-112">Per abilitare l'archivio unificato per i contatti a livello globale per gli utenti di un sito specifico, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="8e459-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="8e459-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8e459-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="8e459-114">Per abilitare l'archivio unificato per tenant, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="8e459-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="8e459-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8e459-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="8e459-116">Per abilitare l'archivio unificato per utente specifico, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="8e459-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8e459-117">Al posto del nome visualizzato dell'utente, è inoltre possibile utilizzare alias utente o URI SIP.</span><span class="sxs-lookup"><span data-stu-id="8e459-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="8e459-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8e459-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8e459-p102">Nell'esempio precedente, il primo comando crea un nuovo criterio per utente chiamato <EM>UCS Enabled Users</EM>, con il contrassegno UcsAllowed impostato su True. Il secondo comando assegna il criterio all'utente con nome visualizzato Ken Myer, e pertanto Ken Myer è ora abilitato all'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="8e459-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

