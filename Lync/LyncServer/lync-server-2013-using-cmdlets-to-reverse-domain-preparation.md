---
title: 'Lync Server 2013: Utilizzo di cmdlet per ripristinare la preparazione del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b03ab3218a1568613731efe60eaa95b05a91ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="cc256-102">Utilizzo di cmdlet per ripristinare la preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc256-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc256-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="cc256-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="cc256-104">Usa il cmdlet **Disable-CsAdDomain** per invertire il passaggio di preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="cc256-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="cc256-105">Per usare i cmdlet per invertire la preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="cc256-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="cc256-106">Accedere a qualsiasi server del dominio come membro del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="cc256-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="cc256-107">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cc256-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cc256-108">Eseguire</span><span class="sxs-lookup"><span data-stu-id="cc256-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="cc256-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cc256-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="cc256-110">Se il parametro Force è presente, viene eseguito il rollback della preparazione del dominio, anche se vengono attivati uno o più server front-end o un/V Conferencing Servers nel dominio.</span><span class="sxs-lookup"><span data-stu-id="cc256-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="cc256-111">Se il parametro Force non è presente, il rollback della preparazione del dominio viene terminato se i server front-end o i server di conferenza a/V nel dominio vengono attivati.</span><span class="sxs-lookup"><span data-stu-id="cc256-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc256-112">Il parametro GlobalSettingsDomainController consente di indicare dove sono archiviate le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="cc256-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="cc256-113">Se le impostazioni sono archiviate nel contenitore di sistema (tipico delle distribuzioni di aggiornamento che non hanno eseguito la migrazione dell'impostazione globale al contenitore di configurazione), si definisce un controller di dominio nella radice della foresta di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc256-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="cc256-114">Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta.</span><span class="sxs-lookup"><span data-stu-id="cc256-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="cc256-115">Se non specifichi questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e faccia riferimento a qualsiasi controller di dominio in&nbsp;Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc256-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc256-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc256-116">See Also</span></span>


[<span data-ttu-id="cc256-117">Esecuzione della preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc256-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="cc256-118">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc256-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

