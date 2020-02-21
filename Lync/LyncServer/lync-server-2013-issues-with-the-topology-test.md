---
title: 'Lync Server 2013: problemi con il test della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3e9b587a286cdff2b7ef08ec217a420792b121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="c0bb2-102">Problemi relativi al test di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0bb2-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0bb2-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c0bb2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c0bb2-104">Analogamente al cmdlet **Test-CsTopology** , Best Practices Analyzer consente di verificare che Lync Server 2013 funzioni correttamente a livello globale.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="c0bb2-105">Per impostazione predefinita, l'Analizzatore procedure consigliate, come il cmdlet, controlla l'intera infrastruttura di Lync Server 2013, verificando che i servizi necessari siano in esecuzione e che siano stati impostati i diritti utente e le autorizzazioni appropriati per questi servizi e per l'universale gruppi di sicurezza creati quando si installa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="c0bb2-106">Oltre a verificare la validità di Lync Server nel suo complesso, **Test-CsTopology** verifica anche la validità di un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="c0bb2-107">Per informazioni dettagliate sull'utilizzo del cmdlet per testare servizi specifici, vedere [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="c0bb2-108">Utilizzare le seguenti informazioni per risolvere i problemi nella topologia.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0bb2-p103">A seconda della configurazione dei server perimetrali e delle relative impostazioni di rete, incluse le impostazioni e le autorizzazioni per i firewall, Best Practices Analyzer potrebbe non essere in grado di accedere ai server perimetrali e analizzarli. Se si includono server perimetrali nell'analisi, e i rapporti indicano un problema di accesso, deselezionare la casella di controllo <STRONG>Server perimetrali</STRONG> ed eseguire nuovamente la scansione per evitare che il problema compaia nei rapporti.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="c0bb2-111">Risoluzione dei problemi nella topologia</span><span class="sxs-lookup"><span data-stu-id="c0bb2-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="c0bb2-112">Se l'analisi della topologia riporta errori nella stessa, è possibile che gli errori siano stati originati da problemi occorsi al momento della pubblicazione o abilitazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="c0bb2-113">Quando si apportano modifiche alla propria topologia, queste non saranno effettive finché non saranno pubblicate e abilitate.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="c0bb2-114">Per apportare modifiche alla topologia, è necessario utilizzare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="c0bb2-115">Dopo aver apportato le modifiche, è possibile pubblicarle e abilitarle utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="c0bb2-116">Quando si pubblicano le modifiche, le nuove informazioni, ad esempio un nuovo sito o un nuovo ruolo del server, vengono scritte nell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="c0bb2-117">Tuttavia, questi nuovi oggetti (o modificati di recente) non aderiscono immediatamente alla topologia.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="c0bb2-118">Gli oggetti si uniscono alla topologia solo quando si Abilita la topologia aggiornata.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="c0bb2-119">Se si seleziona l'opzione pubblica in Generatore di topologie, vengono eseguiti entrambi i passaggi seguenti: le modifiche vengono pubblicate (ovvero vengono scritte nell'archivio di gestione centrale) e quindi viene abilitata la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="c0bb2-120">Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins sono autorizzati a eseguire il cmdlet **Publish-CsTopology** e il cmdlet **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="c0bb2-121">Se però le autorizzazioni di installazione non sono state delegate, sarà possibile eseguire **Publish-CsTopology** solo se si effettua l'accesso come amministratori di dominio.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="c0bb2-122">Per concedere a RTCUniversalServerAdmins il diritto di utilizzare effettivamente il cmdlet **Publish-CsTopology** , è necessario eseguire il cmdlet **Grant-CsSetupPermission** su ogni contenitore di Active Directory che contiene i computer che eseguono i servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="c0bb2-123">Per concedere a RTCUniversalServerAdmins il diritto di utilizzare il cmdlet **Enable-CsTopology** , è necessario eseguire il cmdlet **Set-CsSetupPermission** su ogni contenitore di servizi di dominio Active Directory che contiene i computer che eseguono i servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="c0bb2-124">Si noti che questo è valido per l'abilitazione e la pubblicazione di una topologia tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="c0bb2-125">Se non sono state delegate le autorizzazioni tramite **Set-CsSetupPermission**, solo un amministratore di dominio può abilitare e pubblicare una topologia tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c0bb2-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

