---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per le conferenze telefoniche con accesso esterno'
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
ms.openlocfilehash: edf496dcb24c021246bfbb6e7a5ef7b3a3a5acc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="2a742-102">Elenco di controllo di distribuzione per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a742-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a742-103">_**Argomento Ultima modifica:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="2a742-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="2a742-104">I componenti necessari per i servizi di conferenza telefonica con accesso esterno vengono distribuiti quando si distribuisce il carico di lavoro di conferenza.</span><span class="sxs-lookup"><span data-stu-id="2a742-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="2a742-105">Prima di poter configurare i servizi di conferenza telefonica con accesso esterno, è necessario distribuire VoIP aziendale o Mediation Server e un gateway PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="2a742-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="2a742-106">Tutti i passaggi descritti nella tabella seguente devono essere eseguiti prima che gli utenti possano effettuare la chiamata dalla rete PSTN per partecipare a una conferenza audio/video.</span><span class="sxs-lookup"><span data-stu-id="2a742-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a742-107">Se si esegue la migrazione da Office Communications Server 2007 R2, è necessario applicare gli aggiornamenti più recenti all'ambiente Office Communications Server 2007 R2 prima di distribuire i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="2a742-108">Processo di distribuzione di servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="2a742-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a742-109">Fase</span><span class="sxs-lookup"><span data-stu-id="2a742-109">Phase</span></span></th>
<th><span data-ttu-id="2a742-110">Passaggi</span><span class="sxs-lookup"><span data-stu-id="2a742-110">Steps</span></span></th>
<th><span data-ttu-id="2a742-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2a742-111">Permissions</span></span></th>
<th><span data-ttu-id="2a742-112">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="2a742-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a742-113"><strong>Creare una topologia che includa il carico di lavoro per le conferenze, incluso un Mediation Server e un gateway PSTN, e distribuire il pool Front end o il server Standard Edition</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2a742-114">Eseguire Generatore di topologie per configurare la topologia.</span><span class="sxs-lookup"><span data-stu-id="2a742-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="2a742-115">Durante la configurazione della topologia, selezionare l'opzione per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="2a742-116">Pubblicare la topologia e distribuire il pool Front-end o il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2a742-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="2a742-117">Se necessario, creare un Mediation Server autonomo e associarlo a un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="2a742-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2a742-118">Questo passaggio è obbligatorio solo se non si distribuisce VoIP aziendale e non si colloca il Mediation Server con l'Enterprise EditionFront End Server o Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="2a742-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="2a742-119">Se si distribuisce VoIP aziendale, si installano e si configurano i server di mediazione e i gateway PSTN come parte della distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2a742-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="2a742-120">Se si colloca il Mediation Server, si installa e si configura il server Mediation come parte del pool Front-end o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2a742-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="2a742-121">Amministratori di dominio</span><span class="sxs-lookup"><span data-stu-id="2a742-121">Domain Admins</span></span></p>
<p><span data-ttu-id="2a742-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-123">Amministratore</span><span class="sxs-lookup"><span data-stu-id="2a742-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2a742-124"><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="2a742-125">Per creare un pool di Mediation Server autonomo: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">distribuzione di Mediation Server e definizione di peer in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a742-126"><strong>Configurare i dial plan</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-127">Un dial plan è un set di regole di normalizzazione per i numeri di telefono che traducono il numero di telefono composto da una posizione specifica a un singolo formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2a742-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="2a742-128">Lo stesso numero di telefono composto da posizioni diverse può, in base ai rispettivi piani di chiamata, risolvere i diversi numeri E. 164, come appropriato per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="2a742-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="2a742-129">Se si distribuisce VoIP aziendale, si configurano i dial plan come parte di tale distribuzione ed è necessario assicurarsi che i dial plan siano anche in grado di ospitare i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="2a742-130">Se non si distribuisce VoIP aziendale, è necessario configurare i dial plan per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="2a742-131">Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i piani di chiamata come segue:</span><span class="sxs-lookup"><span data-stu-id="2a742-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="2a742-132">Creare uno o più piani di chiamata per il routing dei numeri di telefono di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="2a742-133">Assegnare un dial plan predefinito a ogni pool.</span><span class="sxs-lookup"><span data-stu-id="2a742-133">Assign a default dial plan to each pool.</span></span> <span data-ttu-id="2a742-134">Impostare l'area dei servizi di <strong>conferenza telefonica con accesso esterno</strong> nella posizione geografica in cui si applica il dial plan.</span><span class="sxs-lookup"><span data-stu-id="2a742-134">Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies.</span></span> <span data-ttu-id="2a742-135">L'area associa il dial plan con i numeri di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-135">The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2a742-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2a742-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurare dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a742-141"><strong>Assicurarsi che i dial plan siano assegnati alle aree geografiche</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-142">Eseguire i cmdlet <strong>Get-CsDialPlan</strong> e <strong>Set-CsDialPlan</strong> per assicurarsi che tutti i dial plan abbiano un'area geografica assegnata.</span><span class="sxs-lookup"><span data-stu-id="2a742-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="2a742-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2a742-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Assicurarsi che i dial plan di Lync Server 2013 abbiano assegnato aree geografiche</a></span><span class="sxs-lookup"><span data-stu-id="2a742-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a742-148"><strong>Opzionale Verificare o modificare i requisiti del PIN (User Personal Identification Number)</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-149">Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per visualizzare o modificare i <strong>criteri PIN</strong>per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="2a742-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="2a742-150">Puoi specificare la lunghezza minima del PIN, il numero massimo di tentativi di accesso, la scadenza del PIN e se i modelli comuni sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="2a742-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="2a742-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Facoltativo) Verificare le impostazioni dei criteri per il PIN in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a742-155"><strong>Configurare i criteri di conferenza per supportare i servizi di conferenza telefonica con accesso esterno</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-156">Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni dei <strong>criteri di conferenza</strong> .</span><span class="sxs-lookup"><span data-stu-id="2a742-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="2a742-157">Specificare se:</span><span class="sxs-lookup"><span data-stu-id="2a742-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a742-158">L'accesso esterno a conferenza PSTN è abilitato.</span><span class="sxs-lookup"><span data-stu-id="2a742-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="2a742-159">Gli utenti possono invitare partecipanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="2a742-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="2a742-160">Gli utenti non autenticati possono partecipare a una conferenza tramite chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="2a742-160">Unauthenticated users can join a conference by using dial-out phoning.</span></span> <span data-ttu-id="2a742-161">Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.</span><span class="sxs-lookup"><span data-stu-id="2a742-161">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a742-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a742-166"><strong>Configurare i numeri di accesso per la chiamata in ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-167">Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i numeri di accesso esterno che gli utenti chiamano per connettersi a una conferenza e specificare le aree geografiche che associano il numero di accesso con i dial plan appropriati.</span><span class="sxs-lookup"><span data-stu-id="2a742-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="2a742-168">I primi tre numeri di accesso per l'area specificata dal dial plan dell'organizzatore sono inclusi nell'invito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="2a742-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="2a742-169">Tutti i numeri di accesso sono disponibili nella pagina delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2a742-170">Dopo aver creato i numeri di accesso esterno, è possibile usare il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato degli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto.</span><span class="sxs-lookup"><span data-stu-id="2a742-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="2a742-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurare i numeri di accesso per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a742-175"><strong>(Facoltativo) Verificare le impostazioni delle conferenze telefoniche con accesso esterno</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-176">Utilizzare il cmdlet <strong>Get-CsDialInConferencingAccessNumber</strong> per cercare piani di chiamata con un'area dei servizi di conferenza telefonica con accesso esterno che non viene usata da alcun numero di Access e per i numeri di accesso a cui non è assegnata alcuna area geografica.</span><span class="sxs-lookup"><span data-stu-id="2a742-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="2a742-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="2a742-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="2a742-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="2a742-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="2a742-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Facoltativo) Verificare le impostazioni delle conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a742-183"><strong>Opzionale Modificare il mapping delle chiavi dei comandi DTMF</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-184">Usare il cmdlet <strong>Set-CsDialInConferencingDtmfConfiguration</strong> per modificare le chiavi usate per i comandi DTMF (Dual-Tone Multifrequency), che i partecipanti possono usare per controllare le impostazioni della conferenza, ad esempio per disattivare e riattivare l'audio o bloccare e sbloccare.</span><span class="sxs-lookup"><span data-stu-id="2a742-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="2a742-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Facoltativo) Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a742-189"><strong>Opzionale Modificare il comportamento degli annunci di conferenza e di uscita</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-190">Usare il <strong>Set-CsDialInConferencingConfiguration</strong> per modificare la modalità di funzionamento degli annunci quando i partecipanti partecipano e lasciano conferenze.</span><span class="sxs-lookup"><span data-stu-id="2a742-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="2a742-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Facoltativo) Abilitare e disabilitare gli annunci di partecipazione e abbandono delle conferenze in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a742-195"><strong>(Facoltativo) Verificare le conferenze telefoniche con accesso esterno</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-196">Usa il cmdlet <strong>Test-CsDialInConferencing</strong> per verificare che i numeri di accesso per il pool specificato funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="2a742-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="2a742-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2a742-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Facoltativo) Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a742-201"><strong>Distribuire il componente aggiuntivo per riunioni online per Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-202">Distribuire il componente aggiuntivo riunione online per Lync 2013 in modo che gli utenti possano pianificare conferenze che supportano i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="2a742-203">Il componente aggiuntivo riunione online per Lync 2013 viene installato automaticamente durante l'installazione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2a742-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="2a742-204">Gli amministratori</span><span class="sxs-lookup"><span data-stu-id="2a742-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="2a742-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Distribuire il componente aggiuntivo per riunioni online per Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a742-206"><strong>Configurare le impostazioni degli account utente</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-207">Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare l' <strong>URI della linea</strong> di telefonia come numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="2a742-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="2a742-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2a742-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="2a742-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="2a742-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2a742-211"><a href="lync-server-2013-configure-user-account-settings.md">Configurare le impostazioni degli account utente in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a742-212">Consigliato Configurare le directory conferenza</span><span class="sxs-lookup"><span data-stu-id="2a742-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="2a742-213">Usa il cmdlet <strong>New-CsConferenceDirectory</strong> per creare una directory conferenza per ogni utente di 999 nel pool.</span><span class="sxs-lookup"><span data-stu-id="2a742-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="2a742-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a742-215">Requisiti per i servizi <a href="lync-server-2013-dial-in-conferencing-requirements.md">di conferenza telefonica con accesso esterno in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(scelta consigliata) creare directory conferenza</a></span><span class="sxs-lookup"><span data-stu-id="2a742-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a742-216"><strong>Opzionale Accogliere gli utenti nei servizi di conferenza telefonica con accesso esterno e impostare il PIN iniziale</strong></span><span class="sxs-lookup"><span data-stu-id="2a742-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="2a742-217">Usare lo script <strong>Set-CsPinSendCAWelcomeMail</strong> per impostare i pin iniziali degli utenti e inviare un messaggio di benvenuto contenente il PIN iniziale e un collegamento alla pagina delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a742-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="2a742-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2a742-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a742-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Facoltativo) Presentazione della funzionalità di conferenza telefonica con accesso esterno agli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a742-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

