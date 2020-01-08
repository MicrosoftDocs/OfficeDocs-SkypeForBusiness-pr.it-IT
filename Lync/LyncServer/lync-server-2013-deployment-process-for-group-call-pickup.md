---
title: 'Lync Server 2013: processo di distribuzione per il ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="d0e65-102">Processo di distribuzione per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0e65-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0e65-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d0e65-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d0e65-104">In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione della raccolta di chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="d0e65-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="d0e65-105">È necessario distribuire Enterprise Edition o Standard Edition con Enterprise Voice prima di configurare il ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="d0e65-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="d0e65-106">I componenti necessari per il ritiro delle chiamate di gruppo sono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d0e65-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="d0e65-107">Processo di distribuzione del pickup della chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="d0e65-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0e65-108">Fase</span><span class="sxs-lookup"><span data-stu-id="d0e65-108">Phase</span></span></th>
<th><span data-ttu-id="d0e65-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="d0e65-109">Steps</span></span></th>
<th><span data-ttu-id="d0e65-110">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="d0e65-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="d0e65-111">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d0e65-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0e65-112">Abilitare lo strumento SEFAUtil Resource Kit nella topologia</span><span class="sxs-lookup"><span data-stu-id="d0e65-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d0e65-113">Usa il cmdlet <strong>New-CsTrustedApplicationPool</strong> per creare un nuovo pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="d0e65-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="d0e65-114">Usa il cmdlet <strong>New-CsTrustedApplication</strong> per specificare lo strumento SEFAUtil come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="d0e65-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="d0e65-115">Eseguire il cmdlet <strong>Enable-CsTopology</strong> per abilitare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d0e65-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="d0e65-116">Installare gli strumenti del Resource Kit in un server front-end che si trova nel pool di applicazioni attendibile creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d0e65-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="d0e65-117">Verificare che SEFAUtil sia in corso correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d0e65-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d0e65-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d0e65-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="d0e65-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Distribuire lo strumento SEFAUtil in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d0e65-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0e65-120">Configurare intervalli di numeri di raccolta chiamate nella tabella Orbit di Call Park</span><span class="sxs-lookup"><span data-stu-id="d0e65-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="d0e65-121">Usa il cmdlet <strong>New-CsCallParkOrbit</strong> per creare intervalli di numeri di prelievo delle chiamate nella tabella Orbit di Call Park e assegnare gli intervalli di prelievo delle chiamate per il tipo GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="d0e65-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d0e65-122">È necessario usare Lync Server Management Shell per creare, modificare, rimuovere e visualizzare intervalli di numeri di prelievo delle chiamate di gruppo nella tabella Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="d0e65-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="d0e65-123">Gli intervalli di numeri di raccolta delle chiamate di gruppo non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0e65-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="d0e65-124">Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri sono in genere configurati come blocco di estensioni virtuali.</span><span class="sxs-lookup"><span data-stu-id="d0e65-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="d0e65-125">L'assegnazione di numeri DID (Direct inwarding Dialing) come numeri di intervallo nella tabella Orbit di parcheggio delle chiamate non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d0e65-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="d0e65-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d0e65-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d0e65-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d0e65-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d0e65-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d0e65-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d0e65-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d0e65-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d0e65-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d0e65-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0e65-131">Assegnare un numero di prelievo delle chiamate agli utenti e abilitare il ritiro delle chiamate di gruppo per gli utenti</span><span class="sxs-lookup"><span data-stu-id="d0e65-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="d0e65-132">Usa il parametro/enablegrouppickup nello strumento Resource Kit di SEFAUtil per abilitare il ritiro delle chiamate di gruppo e assegnare un numero di prelievo chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d0e65-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="d0e65-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnare un numero di gruppo</a></span><span class="sxs-lookup"><span data-stu-id="d0e65-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0e65-134">Informare gli utenti del numero di prelievo delle chiamate assegnate e di qualsiasi altro numero di interesse</span><span class="sxs-lookup"><span data-stu-id="d0e65-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="d0e65-135">Poiché qualsiasi utente può recuperare una chiamata effettuata a un utente di un pick-up di chiamata di gruppo, gli utenti potrebbero voler monitorare più di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="d0e65-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="d0e65-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicare le assegnazioni di ritiro delle chiamate di gruppo agli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d0e65-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0e65-137">Verificare la distribuzione del ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="d0e65-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="d0e65-138">Testare il posizionamento e il recupero delle chiamate per verificare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="d0e65-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="d0e65-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Opzionale Verificare la distribuzione del ritiro delle chiamate di gruppo in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d0e65-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

