---
title: 'Lync Server 2013: processo di distribuzione per il ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="4513b-102">Processo di distribuzione per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4513b-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4513b-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="4513b-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="4513b-104">In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione della raccolta di chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="4513b-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="4513b-105">È necessario distribuire Enterprise Edition o Standard Edition con Enterprise Voice prima di configurare il ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="4513b-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="4513b-106">I componenti necessari per il ritiro delle chiamate di gruppo sono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="4513b-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="4513b-107">Processo di distribuzione del pickup della chiamata di gruppo</span><span class="sxs-lookup"><span data-stu-id="4513b-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4513b-108">Fase</span><span class="sxs-lookup"><span data-stu-id="4513b-108">Phase</span></span></th>
<th><span data-ttu-id="4513b-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="4513b-109">Steps</span></span></th>
<th><span data-ttu-id="4513b-110">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="4513b-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="4513b-111">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="4513b-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4513b-112">Abilitare lo strumento SEFAUtil Resource Kit nella topologia</span><span class="sxs-lookup"><span data-stu-id="4513b-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4513b-113">Usa il cmdlet <strong>New-CsTrustedApplicationPool</strong> per creare un nuovo pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="4513b-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="4513b-114">Usa il cmdlet <strong>New-CsTrustedApplication</strong> per specificare lo strumento SEFAUtil come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="4513b-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="4513b-115">Eseguire il cmdlet <strong>Enable-CsTopology</strong> per abilitare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4513b-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="4513b-116">Installare gli strumenti del Resource Kit in un server front-end che si trova nel pool di applicazioni attendibile creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="4513b-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="4513b-117">Verificare che SEFAUtil sia in corso correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4513b-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4513b-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4513b-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="4513b-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Distribuire lo strumento SEFAUtil in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4513b-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4513b-120">Configurare intervalli di numeri di raccolta chiamate nella tabella Orbit di Call Park</span><span class="sxs-lookup"><span data-stu-id="4513b-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="4513b-121">Usa il cmdlet <strong>New-CsCallParkOrbit</strong> per creare intervalli di numeri di prelievo delle chiamate nella tabella Orbit di Call Park e assegnare gli intervalli di prelievo delle chiamate per il tipo GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="4513b-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="4513b-122">È necessario usare Lync Server Management Shell per creare, modificare, rimuovere e visualizzare intervalli di numeri di prelievo delle chiamate di gruppo nella tabella Orbit di Call Park.</span><span class="sxs-lookup"><span data-stu-id="4513b-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="4513b-123">Gli intervalli di numeri di raccolta delle chiamate di gruppo non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4513b-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="4513b-124">Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri sono in genere configurati come blocco di estensioni virtuali.</span><span class="sxs-lookup"><span data-stu-id="4513b-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="4513b-125">L'assegnazione di numeri DID (Direct inwarding Dialing) come numeri di intervallo nella tabella Orbit di parcheggio delle chiamate non è supportata.</span><span class="sxs-lookup"><span data-stu-id="4513b-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="4513b-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4513b-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="4513b-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4513b-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="4513b-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4513b-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="4513b-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4513b-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4513b-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4513b-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4513b-131">Assegnare un numero di prelievo delle chiamate agli utenti e abilitare il ritiro delle chiamate di gruppo per gli utenti</span><span class="sxs-lookup"><span data-stu-id="4513b-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="4513b-132">Usa il parametro/enablegrouppickup nello strumento Resource Kit di SEFAUtil per abilitare il ritiro delle chiamate di gruppo e assegnare un numero di prelievo chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4513b-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="4513b-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnare un numero di gruppo</a></span><span class="sxs-lookup"><span data-stu-id="4513b-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4513b-134">Informare gli utenti del numero di prelievo delle chiamate assegnate e di qualsiasi altro numero di interesse</span><span class="sxs-lookup"><span data-stu-id="4513b-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="4513b-135">Poiché qualsiasi utente può recuperare una chiamata effettuata a un utente di un pick-up di chiamata di gruppo, gli utenti potrebbero voler monitorare più di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="4513b-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="4513b-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicare le assegnazioni di ritiro delle chiamate di gruppo agli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4513b-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4513b-137">Verificare la distribuzione del ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="4513b-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="4513b-138">Testare il posizionamento e il recupero delle chiamate per verificare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="4513b-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="4513b-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Opzionale Verificare la distribuzione del ritiro delle chiamate di gruppo in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4513b-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

