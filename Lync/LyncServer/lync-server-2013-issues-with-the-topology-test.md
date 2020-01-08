---
title: 'Lync Server 2013: problemi relativi al test della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d416aac6460870ab14d5296bcc6c7944ecf699e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="ce2fa-102">Problemi relativi al test della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2fa-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce2fa-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ce2fa-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ce2fa-104">Come il cmdlet **Test-CsTopology** , Best Practice Analyzer offre un modo per verificare che Lync Server 2013 funzioni correttamente a livello globale.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="ce2fa-105">Per impostazione predefinita, Best Practice Analyzer, come il cmdlet, controlla l'intera infrastruttura di Lync Server 2013, verificando che i servizi necessari siano in corso e che siano stati impostati i diritti e le autorizzazioni degli utenti appropriati per questi servizi e per l'universale gruppi di sicurezza creati durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="ce2fa-106">Oltre a verificare la validità di Lync Server nel suo insieme, **Test-CsTopology** controlla anche la validità di un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="ce2fa-107">Per informazioni dettagliate sull'uso del cmdlet per testare servizi specifici, vedere [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="ce2fa-108">Usare le informazioni seguenti per risolvere i problemi relativi alla topologia.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce2fa-109">A seconda della configurazione degli Edge Server e delle impostazioni di rete perimetrale correlate, incluse le impostazioni e le autorizzazioni del firewall, l'Analizzatore procedure consigliate potrebbe non essere in grado di accedere e analizzare i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-109">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="ce2fa-110">Se si include Edge Server nella scansione e i report indicano che si è verificato un problema di accesso a Edge Server, deselezionare la casella di controllo <STRONG>Edge Server</STRONG> ed eseguire di nuovo l'analisi per evitare che il problema venga visualizzato nei report.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-110">If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="ce2fa-111">Risoluzione dei problemi relativi alla topologia</span><span class="sxs-lookup"><span data-stu-id="ce2fa-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="ce2fa-112">Se il test della topologia ha rilevato problemi relativi alla topologia, questi problemi sono probabilmente causati da problemi che si sono verificati quando è stata pubblicata o abilitata la topologia.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="ce2fa-113">Quando si apportano modifiche alla topologia, le modifiche hanno effetto solo quando sono state pubblicate e abilitate.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="ce2fa-114">Per apportare modifiche alla topologia, è necessario usare generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="ce2fa-115">Dopo avere apportato le modifiche, è possibile pubblicarle e abilitarle usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="ce2fa-116">Quando si pubblicano le modifiche, le nuove informazioni, ad esempio un nuovo sito o un nuovo ruolo del server, vengono scritte in Central Management store.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="ce2fa-117">Tuttavia, questi nuovi oggetti (o appena modificati) non entrano immediatamente nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="ce2fa-118">Gli oggetti si uniscono alla topologia solo quando si Abilita la topologia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="ce2fa-119">Se si seleziona l'opzione pubblica in Generatore di topologie, si verificano entrambe le operazioni seguenti: le modifiche vengono pubblicate, ovvero vengono scritte in Central Management store, quindi la nuova topologia è abilitata.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="ce2fa-120">Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins sono autorizzati a eseguire il cmdlet **Publish-CsTopology** e il cmdlet **Enable-CsTopology** .</span><span class="sxs-lookup"><span data-stu-id="ce2fa-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="ce2fa-121">Tuttavia, se le autorizzazioni di configurazione non sono state delegate, è necessario aver effettuato l'accesso come amministratore di dominio per eseguire **Publish-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="ce2fa-122">Per concedere a RTCUniversalServerAdmins il diritto di usare effettivamente il cmdlet **Publish-CsTopology** , è necessario eseguire il cmdlet **Grant-CsSetupPermission** in ogni contenitore di Active Directory che contiene computer che eseguono servizi Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="ce2fa-123">Per assegnare a RTCUniversalServerAdmins il diritto di usare il cmdlet **Enable-CsTopology** , è necessario eseguire il cmdlet **Set-CsSetupPermission** per ogni contenitore di servizi di dominio Active Directory che contiene computer che eseguono servizi Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="ce2fa-124">Tieni presente che questo si applica all'abilitazione e alla pubblicazione di una topologia usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="ce2fa-125">Se non sono state delegate le autorizzazioni tramite **Set-CsSetupPermission**, solo un amministratore di dominio può abilitare e pubblicare una topologia tramite Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

