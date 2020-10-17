---
title: Configurazione di federazione SIP, Federazione XMPP e messaggistica istantanea pubblica
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
ms.openlocfilehash: 7f3fa4f3b78f53df101da42a2e6b7630cdfb71dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537073"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="5115a-102">Configurazione di federazione SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5115a-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5115a-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="5115a-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="5115a-104">La federazione, la connettività per la messaggistica istantanea pubblica e il protocollo XMPP (Extensible Messaging and Presence Protocol) definiscono una classe diversa di utenti esterni, ovvero gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="5115a-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="5115a-105">Gli utenti di una distribuzione di Lync Server federata o di una distribuzione XMPP dispongono dell'accesso a un insieme limitato di servizi e vengono autenticati dalla distribuzione esterna.</span><span class="sxs-lookup"><span data-stu-id="5115a-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="5115a-106">Gli utenti remoti sono membri della distribuzione di Lync Server e hanno accesso a tutti i servizi offerti dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5115a-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5115a-107">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5115a-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5115a-108">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="5115a-108">has been announced.</span></span> <span data-ttu-id="5115a-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5115a-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="5115a-110">La connettività per la messaggistica istantanea pubblica è un tipo speciale di federazione che consente a un client di Lync Server di accedere ai partner di messaggistica istantanea pubblica configurati utilizzando Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5115a-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="5115a-111">I partner di connettività per la messaggistica istantanea pubblica correnti sono:</span><span class="sxs-lookup"><span data-stu-id="5115a-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="5115a-112">America Online</span><span class="sxs-lookup"><span data-stu-id="5115a-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="5115a-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="5115a-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="5115a-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="5115a-114">Yahoo\!</span></span>

<span data-ttu-id="5115a-115">Una configurazione di connettività per la messaggistica istantanea pubblica consente agli utenti di Lync di accedere agli utenti di connettività per la messaggistica istantanea pubblica mediante:</span><span class="sxs-lookup"><span data-stu-id="5115a-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="5115a-116">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="5115a-116">IM and Presence</span></span>

  - <span data-ttu-id="5115a-117">Visibilità dei contatti di connettività per la messaggistica istantanea pubblica nel client Lync</span><span class="sxs-lookup"><span data-stu-id="5115a-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="5115a-118">Conversazioni di messaggistica istantanea dirette con i contatti</span><span class="sxs-lookup"><span data-stu-id="5115a-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="5115a-119">Chiamate audio e video con utenti di Windows Live</span><span class="sxs-lookup"><span data-stu-id="5115a-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="5115a-p104">La federazione di Lync Server definisce un accordo tra la distribuzione locale di Lync Server e altre distribuzioni di Office Communications Server 2007 R2 o Lync Server. Una configurazione federata di Lync Server consente agli utenti di Lync di accedere agli utenti federati mediante:</span><span class="sxs-lookup"><span data-stu-id="5115a-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="5115a-122">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="5115a-122">IM and Presence</span></span>

  - <span data-ttu-id="5115a-123">Creazione di contatti federati nel client Lync</span><span class="sxs-lookup"><span data-stu-id="5115a-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="5115a-p105">La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (Extensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di Lync di accedere agli utenti di dominio XMPP consentiti mediante:</span><span class="sxs-lookup"><span data-stu-id="5115a-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="5115a-126">Messaggistica istantanea e presenza (solo diretta)</span><span class="sxs-lookup"><span data-stu-id="5115a-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="5115a-127">Creazione di contatti federati XMPP nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="5115a-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5115a-p106">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="5115a-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="5115a-130">Processo di distribuzione della federazione esterna dei server perimetrali, della connettività per la messaggistica istantanea pubblica e degli utenti XMPP</span><span class="sxs-lookup"><span data-stu-id="5115a-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5115a-131">Fase</span><span class="sxs-lookup"><span data-stu-id="5115a-131">Phase</span></span></th>
<th><span data-ttu-id="5115a-132">Passaggi</span><span class="sxs-lookup"><span data-stu-id="5115a-132">Steps</span></span></th>
<th><span data-ttu-id="5115a-133">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5115a-133">Permissions</span></span></th>
<th><span data-ttu-id="5115a-134">Documentazione</span><span class="sxs-lookup"><span data-stu-id="5115a-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5115a-135">Determinare le opzioni da aggiungere alla distribuzione di server perimetrali esistente</span><span class="sxs-lookup"><span data-stu-id="5115a-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="5115a-136">Eseguire Generatore di topologie per modificare le impostazioni del server perimetrale e creare e pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="5115a-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="5115a-137">La topologia perimetrale esistente consente di replicare le modifiche dall'archivio di gestione centrale al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5115a-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="5115a-138">Gruppi Domain Admins e RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5115a-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="5115a-139">È possibile modificare una topologia utilizzando un account membro del gruppo degli utenti locali, ma per la pubblicazione di una topologia è necessario un account membro dei gruppi Domain Admins e RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5115a-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="5115a-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia Edge e Director in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5115a-141">Effettuare la preparazione per l'impostazione</span><span class="sxs-lookup"><span data-stu-id="5115a-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5115a-142">Verificare che vengano soddisfatti i prerequisiti del sistema.</span><span class="sxs-lookup"><span data-stu-id="5115a-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="5115a-143">Configurare i record DNS interni ed esterni per supportare la connettività per la messaggistica istantanea pubblica, la federazione di Lync e la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="5115a-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="5115a-144">Configurare le porte e i protocolli sul firewall per supportare i tipi di federazione da distribuire</span><span class="sxs-lookup"><span data-stu-id="5115a-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="5115a-p108">Ottenere e installare certificati pubblici. Il tempo necessario per ottenere i certificati dipende dall'autorità di certificazione (CA) che emette il certificato. Tale passaggio è facoltativo a questo punto della distribuzione. Se non si esegue questo passaggio in questa fase, sarà necessario eseguirlo durante la configurazione dei server perimetrali. Il servizio del server perimetrale non può essere avviato finché non si ottengono i certificati.</span><span class="sxs-lookup"><span data-stu-id="5115a-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5115a-150">A seconda dell'organizzazione, in quanto questi ruoli in genere sono divisi tra numerosi gruppi di lavoro</span><span class="sxs-lookup"><span data-stu-id="5115a-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="5115a-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5115a-152">Impostare i server perimetrali per gli scenari di federazione</span><span class="sxs-lookup"><span data-stu-id="5115a-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5115a-153">Trasportare in ogni server perimetrale il file di configurazione della topologia esportato o consentire il completamento della replica.</span><span class="sxs-lookup"><span data-stu-id="5115a-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="5115a-154">Eseguire di nuovo la Distribuzione guidata per installare i componenti per il supporto della federazione</span><span class="sxs-lookup"><span data-stu-id="5115a-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="5115a-155">Configurare i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="5115a-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="5115a-156">Richiedere e installare i certificati per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5115a-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="5115a-157">Riavviare i servizi dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="5115a-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5115a-158">Gruppo Administrators</span><span class="sxs-lookup"><span data-stu-id="5115a-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="5115a-159"><a href="lync-server-2013-setting-up-lync-federation.md">Configurazione della Federazione di Lync in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5115a-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5115a-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurazione della Federazione XMPP in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5115a-162">Configurare il supporto per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="5115a-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5115a-163">Utilizzo dell'accesso utente esterno del pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5115a-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="5115a-164">Configurare i criteri di accesso esterno per consentire le comunicazioni con gli utenti federati o gli utenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="5115a-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="5115a-165">Configurare i domini federati SIP per consentire o bloccare i domini</span><span class="sxs-lookup"><span data-stu-id="5115a-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="5115a-166">Abilitare i provider federati SIP per i provider di connettività per la messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="5115a-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="5115a-167">Configurare i partner federati XMPP per ogni dominio XMPP.</span><span class="sxs-lookup"><span data-stu-id="5115a-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5115a-168">Gruppo RTCUniversalServerAdmins o account utente assegnato al ruolo CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="5115a-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="5115a-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5115a-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5115a-171">Verificare la configurazione dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="5115a-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="5115a-172">Verificare la connettività dei server e la replica dei dati di configurazione dai server interni.</span><span class="sxs-lookup"><span data-stu-id="5115a-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="5115a-173">Per la verifica della replica, gruppo RTCUniversalServerAdmins o account utente assegnato al ruolo CSAdministrator. Per la verifica della connettività degli utenti, un utente per ogni tipo di utente federato</span><span class="sxs-lookup"><span data-stu-id="5115a-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="5115a-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifica della distribuzione di Edge in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5115a-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5115a-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="5115a-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

