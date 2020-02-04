---
title: Configurazione di federazione SIP, federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="91658-102">Configurazione di federazione SIP, federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91658-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91658-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="91658-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="91658-104">Federazione, connettività di messaggistica istantanea pubblica e protocollo XMPP (Extensible Messaging and Presence Protocol) definiscono una classe diversa di utenti esterni: utenti federati.</span><span class="sxs-lookup"><span data-stu-id="91658-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="91658-105">Gli utenti di una distribuzione di Lync Server federata o di una distribuzione XMPP hanno accesso a un set limitato di servizi e vengono autenticati dalla distribuzione esterna.</span><span class="sxs-lookup"><span data-stu-id="91658-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="91658-106">Gli utenti remoti sono membri della distribuzione di Lync Server e hanno accesso a tutti i servizi offerti dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="91658-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="91658-107">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="91658-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="91658-108">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="91658-108">has been announced.</span></span> <span data-ttu-id="91658-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="91658-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="91658-110">La connettività di messaggistica istantanea pubblica è un tipo speciale di federazione che consente a un client Lync Server di accedere ai partner di messaggistica istantanea pubblica configurati tramite Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="91658-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="91658-111">I partner di connettività di messaggistica istantanea pubblica correnti sono:</span><span class="sxs-lookup"><span data-stu-id="91658-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="91658-112">America Online</span><span class="sxs-lookup"><span data-stu-id="91658-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="91658-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="91658-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="91658-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="91658-114">Yahoo\!</span></span>

<span data-ttu-id="91658-115">Una configurazione della connettività di messaggistica istantanea pubblica consente agli utenti di Lync di accedere agli utenti di connettività di messaggistica istantanea pubblica tramite:</span><span class="sxs-lookup"><span data-stu-id="91658-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="91658-116">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="91658-116">IM and Presence</span></span>

  - <span data-ttu-id="91658-117">Visibilità dei contatti della connettività di messaggistica istantanea pubblica nel client Lync</span><span class="sxs-lookup"><span data-stu-id="91658-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="91658-118">Conversazioni ISTANTANEe da persona a persona con contatti</span><span class="sxs-lookup"><span data-stu-id="91658-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="91658-119">Chiamate audio e video con utenti Windows Live</span><span class="sxs-lookup"><span data-stu-id="91658-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="91658-120">La Federazione di Lync Server definisce un accordo tra la distribuzione di Lync Server e altre distribuzioni di Office Communications Server 2007 R2 o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91658-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="91658-121">Una configurazione federata di Lync Server consente agli utenti di Lync di accedere agli utenti federati:</span><span class="sxs-lookup"><span data-stu-id="91658-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="91658-122">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="91658-122">IM and Presence</span></span>

  - <span data-ttu-id="91658-123">Creazione di contatti federati nel client Lync</span><span class="sxs-lookup"><span data-stu-id="91658-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="91658-124">La Federazione XMPP definisce una distribuzione esterna basata sul protocollo di messaggistica e presenza estensibile.</span><span class="sxs-lookup"><span data-stu-id="91658-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="91658-125">Una configurazione XMPP consente agli utenti di Lync di accedere agli utenti di domini XMPP consentiti:</span><span class="sxs-lookup"><span data-stu-id="91658-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="91658-126">Messaggistica istantanea e presenza: solo persona a persona</span><span class="sxs-lookup"><span data-stu-id="91658-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="91658-127">Creazione di contatti federati XMPP nel client Lync</span><span class="sxs-lookup"><span data-stu-id="91658-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="91658-128">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="91658-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="91658-129">Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="91658-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="91658-130">Federazione esterna Edge Server, connettività di messaggistica istantanea pubblica e processo di distribuzione degli utenti XMPP</span><span class="sxs-lookup"><span data-stu-id="91658-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91658-131">Fase</span><span class="sxs-lookup"><span data-stu-id="91658-131">Phase</span></span></th>
<th><span data-ttu-id="91658-132">Passaggi</span><span class="sxs-lookup"><span data-stu-id="91658-132">Steps</span></span></th>
<th><span data-ttu-id="91658-133">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="91658-133">Permissions</span></span></th>
<th><span data-ttu-id="91658-134">Documentazione</span><span class="sxs-lookup"><span data-stu-id="91658-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91658-135">Determinare le opzioni da aggiungere alla distribuzione di Edge esistente</span><span class="sxs-lookup"><span data-stu-id="91658-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="91658-136">Eseguire Generatore di topologie per modificare le impostazioni del server perimetrale e creare e pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="91658-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="91658-137">La topologia di Edge esistente ripeterà le modifiche da Central Management store a Edge Server.</span><span class="sxs-lookup"><span data-stu-id="91658-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="91658-138">Gruppo amministratori di dominio e gruppo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="91658-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="91658-139">È possibile modificare una topologia usando un account che è un membro del gruppo utenti locali, ma la pubblicazione di una topologia richiede un account membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="91658-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="91658-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia di server perimetrali e server Director in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91658-141">Preparare la configurazione</span><span class="sxs-lookup"><span data-stu-id="91658-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="91658-142">Verificare che i prerequisiti di sistema vengano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="91658-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="91658-143">Configurare i record DNS interni ed esterni per supportare la connettività di messaggistica istantanea pubblica, la federazione Lync e la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="91658-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="91658-144">Configurare le porte e i protocolli nel firewall per supportare i tipi di federazione che si stanno distribuendo</span><span class="sxs-lookup"><span data-stu-id="91658-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="91658-145">Ottenere e installare i certificati pubblici.</span><span class="sxs-lookup"><span data-stu-id="91658-145">Obtain and install public certificates.</span></span> <span data-ttu-id="91658-146">Il tempo necessario per ottenere i certificati dipende dall'autorità di certificazione (CA) che emette il certificato.</span><span class="sxs-lookup"><span data-stu-id="91658-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="91658-147">Questo passaggio è facoltativo a questo punto della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="91658-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="91658-148">Se non si esegue questo passaggio a questo punto, è necessario eseguire questa operazione durante la configurazione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="91658-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="91658-149">Impossibile avviare il servizio Edge Server fino a quando non vengono ottenuti i certificati</span><span class="sxs-lookup"><span data-stu-id="91658-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="91658-150">Come appropriato per l'organizzazione, poiché questi ruoli sono in genere divisi tra numerosi gruppi di lavoro</span><span class="sxs-lookup"><span data-stu-id="91658-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="91658-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91658-152">Configurare Edge Server per gli scenari federativi</span><span class="sxs-lookup"><span data-stu-id="91658-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="91658-153">Trasportare il file di configurazione della topologia esportata in ogni Edge Server o consentire il completamento della replica</span><span class="sxs-lookup"><span data-stu-id="91658-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="91658-154">Eseguire di nuovo la distribuzione guidata per installare i componenti di supporto per la Federazione</span><span class="sxs-lookup"><span data-stu-id="91658-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="91658-155">Configurare gli Edge Server</span><span class="sxs-lookup"><span data-stu-id="91658-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="91658-156">Richiedere e installare certificati per ogni server perimetrale</span><span class="sxs-lookup"><span data-stu-id="91658-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="91658-157">Riavviare i servizi Edge Server</span><span class="sxs-lookup"><span data-stu-id="91658-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="91658-158">Gruppo amministratori</span><span class="sxs-lookup"><span data-stu-id="91658-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="91658-159"><a href="lync-server-2013-setting-up-lync-federation.md">Configurazione della federazione di Lync in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="91658-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="91658-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurazione della federazione di XMPP in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91658-162">Configurare il supporto per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="91658-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="91658-163">Usare l'accesso degli utenti esterni del pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="91658-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="91658-164">Configurare i criteri di accesso esterno per abilitare le comunicazioni con utenti federati o utenti pubblici</span><span class="sxs-lookup"><span data-stu-id="91658-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="91658-165">Configurare i domini federati SIP per consentire o bloccare i domini</span><span class="sxs-lookup"><span data-stu-id="91658-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="91658-166">Abilitare i provider federati SIP per i provider di connettività di messaggistica istantanea pubblici</span><span class="sxs-lookup"><span data-stu-id="91658-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="91658-167">Configurare partner federati XMPP per dominio XMPP</span><span class="sxs-lookup"><span data-stu-id="91658-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="91658-168">Gruppo RTCUniversalServerAdmins o account utente assegnato al ruolo CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="91658-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="91658-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="91658-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91658-171">Verificare la configurazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="91658-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="91658-172">Verificare la connettività del server e la replica dei dati di configurazione dai server interni</span><span class="sxs-lookup"><span data-stu-id="91658-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="91658-173">Per la verifica della replica, il gruppo RTCUniversalServerAdmins o l'account utente assegnato alla verifica CSAdministrator roleFor della connettività degli utenti, un utente per ogni tipo di utente federato</span><span class="sxs-lookup"><span data-stu-id="91658-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="91658-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifica della distribuzione dei componenti perimetrali in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="91658-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="91658-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="91658-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

