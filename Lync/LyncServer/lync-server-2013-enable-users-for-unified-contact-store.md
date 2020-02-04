---
title: "Lync Server 2013: Abilitare gli utenti per l'archivio contatti unificato"
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
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="c5057-102">Abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5057-102">Enable users for unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5057-103">_**Argomento Ultima modifica:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="c5057-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="c5057-104">Quando si distribuisce Lync Server 2013 e si pubblica la topologia, per impostazione predefinita l'archivio contatti unificato è abilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c5057-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="c5057-105">Non è necessario eseguire altre azioni per abilitare l'archiviazione di contatti unificati dopo la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5057-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="c5057-106">Tuttavia, puoi usare il cmdlet **Set-CsUserServicesPolicy** per personalizzare gli utenti che dispongono di un archivio contatti unificato disponibile.</span><span class="sxs-lookup"><span data-stu-id="c5057-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="c5057-107">Puoi abilitare questa funzionalità a livello globale, per sito, per tenant o per singoli o gruppi di persone.</span><span class="sxs-lookup"><span data-stu-id="c5057-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="c5057-108">Per abilitare gli utenti per l'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="c5057-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="c5057-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c5057-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c5057-110">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5057-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="c5057-111">Per abilitare l'archivio contatti unificato a livello globale per tutti gli utenti di Lync Server, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c5057-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="c5057-112">Per abilitare l'archivio contatti unificato per gli utenti di un sito specifico, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c5057-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="c5057-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c5057-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="c5057-114">Per abilitare l'archivio contatti unificato dal tenant, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c5057-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="c5057-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c5057-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="c5057-116">Per abilitare l'archivio contatti unificato per utenti specifici, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="c5057-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c5057-117">È anche possibile usare l'alias utente o l'URI SIP anziché il nome visualizzato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c5057-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="c5057-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c5057-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c5057-119">Nell'esempio precedente il primo comando crea un nuovo criterio per utente denominato <EM>UCS abilitato agli utenti</EM> con il flag UcsAllowed impostato su true.</span><span class="sxs-lookup"><span data-stu-id="c5057-119">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="c5057-120">Il secondo comando assegna i criteri all'utente con il nome visualizzato Ken di riferimento, il che significa che Ken è ora abilitato per l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="c5057-120">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

