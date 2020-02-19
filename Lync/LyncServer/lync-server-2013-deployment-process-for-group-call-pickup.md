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
ms.openlocfilehash: 150434b57aa90048c1009851473349093435c116
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="ff0f6-102">Processo di distribuzione per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff0f6-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff0f6-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="ff0f6-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="ff0f6-104">In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione del prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="ff0f6-105">Prima di configurare il prelievo delle chiamate di gruppo, è necessario distribuire Enterprise Edition o Standard Edition con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="ff0f6-106">I componenti richiesti dal ritiro delle chiamate di gruppo vengono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="ff0f6-107">Processo di distribuzione del prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="ff0f6-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff0f6-108">Fase</span><span class="sxs-lookup"><span data-stu-id="ff0f6-108">Phase</span></span></th>
<th><span data-ttu-id="ff0f6-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="ff0f6-109">Steps</span></span></th>
<th><span data-ttu-id="ff0f6-110">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="ff0f6-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="ff0f6-111">Documentazione sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="ff0f6-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff0f6-112">Abilitare lo strumento Resource Kit di SEFAUtil nella topologia</span><span class="sxs-lookup"><span data-stu-id="ff0f6-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ff0f6-113">Utilizzare il cmdlet <strong>New-CsTrustedApplicationPool</strong> per creare un nuovo pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="ff0f6-114">Utilizzare il cmdlet <strong>New-CsTrustedApplication</strong> per specificare lo strumento SEFAUtil come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="ff0f6-115">Eseguire il cmdlet <strong>Enable-CsTopology</strong> per abilitare la topologia.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="ff0f6-116">Installare gli strumenti del Resource Kit in un front end server nel pool di applicazioni attendibili creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="ff0f6-117">Verificare che SEFAUtil sia in esecuzione correttamente eseguendolo per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ff0f6-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff0f6-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ff0f6-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Distribuire lo strumento SEFAUtil in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ff0f6-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff0f6-120">Configurare gli intervalli di numeri di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="ff0f6-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="ff0f6-121">Utilizzare il cmdlet <strong>New-CsCallParkOrbit</strong> per creare intervalli di numeri di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata e assegnare gli intervalli di prelievo delle chiamate di tipo GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ff0f6-122">È necessario utilizzare Lync Server Management Shell per creare, modificare, rimuovere e visualizzare gli intervalli di numeri di prelievo delle chiamate di gruppo nella tabella orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="ff0f6-123">Gli intervalli di numeri di prelievo delle chiamate di gruppo non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="ff0f6-124">Per una perfetta integrazione con i dial plan esistenti, gli intervalli di numeri vengono in genere configurati come blocco di estensioni virtuali.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="ff0f6-125">L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di intervallo nella tabella orbit del parcheggio di chiamata non è supportata.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="ff0f6-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff0f6-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff0f6-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff0f6-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ff0f6-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff0f6-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff0f6-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff0f6-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff0f6-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ff0f6-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff0f6-131">Assegnare un numero di prelievo delle chiamate agli utenti e abilitare il prelievo delle chiamate di gruppo per gli utenti</span><span class="sxs-lookup"><span data-stu-id="ff0f6-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="ff0f6-132">Utilizzare il parametro/enablegrouppickup nello strumento Resource Kit di SEFAUtil per abilitare il prelievo delle chiamate di gruppo e assegnare un numero di prelievo di chiamata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ff0f6-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Abilitazione del prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnazione di un numero di gruppo</a></span><span class="sxs-lookup"><span data-stu-id="ff0f6-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff0f6-134">Notificare agli utenti il numero di prelievo di chiamata assegnato e qualsiasi altro numero di interesse</span><span class="sxs-lookup"><span data-stu-id="ff0f6-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="ff0f6-135">Poiché qualsiasi utente può recuperare una chiamata effettuata a un utente di prelievo delle chiamate di gruppo, gli utenti possono eseguire il monitoraggio di più di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ff0f6-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicare le assegnazioni di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ff0f6-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff0f6-137">Verificare la distribuzione del prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="ff0f6-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="ff0f6-138">Provare a inserire e recuperare le chiamate per assicurarsi che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="ff0f6-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ff0f6-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional Verificare la distribuzione del prelievo delle chiamate di gruppo in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ff0f6-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

