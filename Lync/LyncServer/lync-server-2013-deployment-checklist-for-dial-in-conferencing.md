---
title: Elenco di controllo di distribuzione di Lync Server 2013 per le conferenze telefoniche con accesso esterno
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a81a4baee7062936144d0a6d066d59cf0a8ef1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522793"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="5e599-102">Elenco di controllo di distribuzione per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e599-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e599-103">_**Ultimo argomento modificato:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="5e599-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="5e599-104">I componenti necessari per le conferenze telefoniche con accesso esterno vengono distribuiti quando si distribuisce il carico di lavoro per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="5e599-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="5e599-105">Prima di poter configurare le conferenze telefoniche con accesso esterno, è necessario distribuire VoIP aziendale o Mediation Server e un gateway PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="5e599-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="5e599-106">Tutti i passaggi descritti nella tabella seguente devono essere eseguiti prima che gli utenti possano comporre dalla rete PSTN per partecipare a una conferenza audio/video.</span><span class="sxs-lookup"><span data-stu-id="5e599-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e599-107">Se si esegue la migrazione da Office Communications Server 2007 R2, è necessario applicare gli aggiornamenti più recenti all'ambiente Office Communications Server 2007 R2 prima di distribuire le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="5e599-108">Processo di distribuzione delle conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="5e599-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e599-109">Fase</span><span class="sxs-lookup"><span data-stu-id="5e599-109">Phase</span></span></th>
<th><span data-ttu-id="5e599-110">Passaggi</span><span class="sxs-lookup"><span data-stu-id="5e599-110">Steps</span></span></th>
<th><span data-ttu-id="5e599-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5e599-111">Permissions</span></span></th>
<th><span data-ttu-id="5e599-112">Documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="5e599-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e599-113"><strong>Creare una topologia che includa il carico di lavoro per le conferenze, tra cui un Mediation Server e un gateway PSTN, e distribuire il pool Front end o il server Standard Edition</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5e599-114">Eseguire Generatore di topologie per configurare la topologia.</span><span class="sxs-lookup"><span data-stu-id="5e599-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="5e599-115">Durante la configurazione della topologia, selezionare l'opzione per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="5e599-116">Pubblicare la topologia e distribuire il pool Front end o il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5e599-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="5e599-117">Se necessario, creare un Mediation Server autonomo e associarlo a un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="5e599-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5e599-118">Questo passaggio è obbligatorio solo se non si distribuisce VoIP aziendale e non si colloca il Mediation Server con l'Enterprise EditionFront End Server o il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5e599-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="5e599-119">Se si distribuisce VoIP aziendale, vengono installati e configurati Mediation Server e gateway PSTN come parte della distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="5e599-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="5e599-120">Se si colloca il Mediation Server, è necessario installare e configurare il Mediation Server come parte della distribuzione del pool Front end o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5e599-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="5e599-121">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="5e599-121">Domain Admins</span></span></p>
<p><span data-ttu-id="5e599-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-123">Amministratore</span><span class="sxs-lookup"><span data-stu-id="5e599-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5e599-124"><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="5e599-125">Per creare un pool di Mediation Server autonomo: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">distribuzione di Mediation Server e definizione di peer in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e599-126"><strong>Configurare i dial plan</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-127">Un dial plan è un insieme di regole di normalizzazione dei numeri di telefono che trasportano il numero di telefono composto da una posizione specifica a un singolo formato standard (E. 164) ai fini dell'autorizzazione del telefono e del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="5e599-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="5e599-128">Lo stesso numero di telefono composto da diverse posizioni può, in base ai rispettivi dial plan, risolvere i diversi numeri E. 164, a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="5e599-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="5e599-129">Se si distribuisce VoIP aziendale, si configurano i dial plan nell'ambito della distribuzione ed è necessario assicurarsi che i dial plan siano anche in grado di ospitare le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="5e599-130">Se non si esegue la distribuzione di VoIP aziendale, è necessario configurare i dial plan per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="5e599-131">Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i dial plan come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5e599-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="5e599-132">Creare uno o più dial plan per instradare i numeri di telefono di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="5e599-133">Assegnare un dial plan predefinito per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="5e599-133">Assign a default dial plan to each pool.</span></span> <span data-ttu-id="5e599-134">Impostare l' <strong>area di conferenza telefonica con accesso esterno</strong> sulla posizione geografica a cui si applica il dial plan.</span><span class="sxs-lookup"><span data-stu-id="5e599-134">Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies.</span></span> <span data-ttu-id="5e599-135">L'area associa il dial plan ai numeri di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-135">The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5e599-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5e599-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurare i dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e599-141"><strong>Verificare che i dial plan siano aree assegnate</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-142">Eseguire i cmdlet <strong>Get-CsDialPlan</strong> e <strong>Set-CsDialPlan</strong> per assicurarsi che tutti i dial plan dispongano di un'area geografica assegnata.</span><span class="sxs-lookup"><span data-stu-id="5e599-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="5e599-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5e599-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Assicurarsi che i dial plan Lync Server 2013 abbiano assegnato aree geografiche</a></span><span class="sxs-lookup"><span data-stu-id="5e599-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e599-148"><strong>Optional Verificare o modificare i requisiti del PIN (User Personal Identification Number)</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-149">Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per visualizzare o modificare il <strong>criterio PIN</strong>per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="5e599-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="5e599-150">È possibile specificare la lunghezza minima del PIN, il numero massimo di tentativi di accesso, la scadenza del PIN e la possibilità che i modelli comuni siano consentiti.</span><span class="sxs-lookup"><span data-stu-id="5e599-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="5e599-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Optional Verificare le impostazioni del criterio PIN in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e599-155"><strong>Configurare i criteri di conferenza per il supporto delle conferenze telefoniche con accesso esterno</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-156">Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni dei <strong>criteri di conferenza</strong> .</span><span class="sxs-lookup"><span data-stu-id="5e599-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="5e599-157">Specificare se:</span><span class="sxs-lookup"><span data-stu-id="5e599-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="5e599-158">L'accesso esterno alle conferenze PSTN è abilitato.</span><span class="sxs-lookup"><span data-stu-id="5e599-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="5e599-159">Gli utenti possono invitare partecipanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="5e599-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="5e599-160">Gli utenti non autenticati possono partecipare a una conferenza utilizzando la chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="5e599-160">Unauthenticated users can join a conference by using dial-out phoning.</span></span> <span data-ttu-id="5e599-161">Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.</span><span class="sxs-lookup"><span data-stu-id="5e599-161">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5e599-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e599-166"><strong>Configurare i numeri di accesso esterno</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-167">Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i numeri di accesso esterno che gli utenti chiamano per effettuare la chiamata in ingresso a una conferenza e specificare le aree che associano il numero di accesso ai dial plan corretti.</span><span class="sxs-lookup"><span data-stu-id="5e599-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="5e599-168">I primi tre numeri di accesso per l'area specificata dal dial plan dell'organizzatore sono inclusi nell'invito a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e599-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="5e599-169">Tutti i numeri di accesso sono disponibili nella pagina delle impostazioni per le conferenze telefoniche con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="5e599-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5e599-170">Dopo aver creato i numeri di accesso esterno, è possibile utilizzare il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato degli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto.</span><span class="sxs-lookup"><span data-stu-id="5e599-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="5e599-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurare i numeri di accesso per le conferenze telefoniche con chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e599-175"><strong>Optional Verificare le impostazioni delle conferenze telefoniche con accesso esterno</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-176">Utilizzare il cmdlet <strong>Get-CsDialInConferencingAccessNumber</strong> per cercare i dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di Access e per i numeri di accesso privi di aree assegnate.</span><span class="sxs-lookup"><span data-stu-id="5e599-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="5e599-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="5e599-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="5e599-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="5e599-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="5e599-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Optional Verificare le impostazioni delle conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e599-183"><strong>Optional Modificare il mapping dei tasti per i comandi DTMF</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-184">Utilizzare il cmdlet <strong>Set-CsDialInConferencingDtmfConfiguration</strong> per modificare le chiavi utilizzate per i comandi DTMF (Dual-Tone Multifrequency), che possono essere utilizzati dai partecipanti per controllare le impostazioni di conferenza (ad esempio, disattivare e riattivare o bloccare e sbloccare).</span><span class="sxs-lookup"><span data-stu-id="5e599-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="5e599-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Optional Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e599-189"><strong>Optional Modificare la modalità di partecipazione alle conferenze e lasciare l'annuncio</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-190">Utilizzare il <strong>Set-CsDialInConferencingConfiguration</strong> per modificare il modo in cui gli annunci interagiscono quando i partecipanti partecipano e lasciano conferenze.</span><span class="sxs-lookup"><span data-stu-id="5e599-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="5e599-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Optional Abilitare e disabilitare gli annunci di partecipazione alla conferenza e di uscita in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e599-195"><strong>Optional Verificare le conferenze telefoniche con accesso esterno</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-196">Utilizzare il cmdlet <strong>Test-CsDialInConferencing</strong> per verificare che i numeri di accesso per il pool specificato funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="5e599-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="5e599-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5e599-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Optional Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e599-201"><strong>Distribuire il componente aggiuntivo per riunioni online per Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-202">Distribuire il componente aggiuntivo per riunioni online per Lync 2013 in modo che gli utenti possano pianificare conferenze per il supporto delle conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="5e599-203">Il componente aggiuntivo per riunioni online per Lync 2013 viene installato automaticamente quando si installa Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5e599-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="5e599-204">Amministratori</span><span class="sxs-lookup"><span data-stu-id="5e599-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="5e599-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Distribuire il componente aggiuntivo per riunioni online per Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e599-206"><strong>Configurare le impostazioni degli account utente</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-207">Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare l' <strong>URI della linea</strong> di telefonia come un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="5e599-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="5e599-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5e599-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="5e599-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="5e599-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5e599-211"><a href="lync-server-2013-configure-user-account-settings.md">Configurare le impostazioni degli account utente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e599-212">Consigliato Configurare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="5e599-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="5e599-213">Utilizzare il cmdlet <strong>New-CsConferenceDirectory</strong> per creare una directory conferenze per ogni 999 utenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="5e599-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="5e599-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5e599-215">Requisiti per le conferenze telefoniche <a href="lync-server-2013-dial-in-conferencing-requirements.md">con accesso esterno in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(scelta consigliata) creare directory conferenze</a></span><span class="sxs-lookup"><span data-stu-id="5e599-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e599-216"><strong>Optional Accogliere gli utenti per le conferenze telefoniche con accesso esterno e impostare il PIN iniziale</strong></span><span class="sxs-lookup"><span data-stu-id="5e599-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="5e599-217">Utilizzare lo script <strong>Set-CsPinSendCAWelcomeMail</strong> per impostare i pin iniziali degli utenti e inviare un messaggio di posta elettronica di benvenuto che contiene il PIN iniziale e un collegamento alla pagina delle impostazioni per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5e599-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="5e599-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5e599-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5e599-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Optional Accogliere gli utenti per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e599-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

