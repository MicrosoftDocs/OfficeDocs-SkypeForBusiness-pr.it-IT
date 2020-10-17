---
title: 'Lync Server 2013: visualizzazione dello stato delle impostazioni globali per una foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7922fe79d97a1fa83fdaa5afbc1eeddee8523e37
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535583"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="0f29f-102">Visualizzazione dello stato delle impostazioni globali per una foresta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f29f-102">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f29f-103">_**Ultimo argomento modificato:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="0f29f-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="0f29f-104">Gli amministratori devono esaminare mensilmente le impostazioni globali per una distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f29f-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="0f29f-105">L'obiettivo è quello di esaminare le impostazioni implementate in base a un insieme di configurazioni note, ovvero una configurazione di base per garantire che le impostazioni siano valide e per determinare se la documentazione di base deve essere aggiornata.</span><span class="sxs-lookup"><span data-stu-id="0f29f-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="0f29f-106">Le modifiche apportate all'impostazione globale devono essere implementate tramite un processo di controllo delle modifiche che dovrebbe includere la documentazione delle nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0f29f-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="0f29f-107">Le impostazioni globali che devono essere rivedute sono descritte nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f29f-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="0f29f-108">Controllare le impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="0f29f-108">Check general settings</span></span>

<span data-ttu-id="0f29f-109">Controllare le impostazioni generali, inclusi i domini SIP (Session Initiation Protocol) per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f29f-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="0f29f-110">È possibile restituire le informazioni sul dominio SIP utilizzando Windows PowerShell e il cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="0f29f-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="0f29f-111">Per restituire queste informazioni, eseguire il `Get-CsSipDomain` comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f29f-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="0f29f-112">Get-CsSipDomain restituirà informazioni simili a quelle per tutti i domini SIP autorizzati:</span><span class="sxs-lookup"><span data-stu-id="0f29f-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="0f29f-113">Nome dell'identità predefinito</span><span class="sxs-lookup"><span data-stu-id="0f29f-113">Identity Name IsDefault</span></span>

<span data-ttu-id="0f29f-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="0f29f-114">\-------- ---- ---------</span></span>

<span data-ttu-id="0f29f-115">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="0f29f-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="0f29f-116">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="0f29f-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="0f29f-117">Se la proprietà IsDefault è impostata su true, il dominio corrispondente è il dominio SIP predefinito.</span><span class="sxs-lookup"><span data-stu-id="0f29f-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="0f29f-118">È possibile utilizzare il cmdlet Set-CsSipDomain per modificare il dominio SIP predefinito per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0f29f-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="0f29f-119">Tuttavia, non è possibile eliminare solo il dominio SIP predefinito, perché ciò non comporta un dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="0f29f-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="0f29f-120">Se si desidera eliminare il dominio fabrikam.com (come illustrato nell'esempio precedente), è necessario prima di tutto configurare na.fabrikam.com in modo che sia il dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="0f29f-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="0f29f-121">Controllare le impostazioni di riunione</span><span class="sxs-lookup"><span data-stu-id="0f29f-121">Check meeting settings</span></span>

<span data-ttu-id="0f29f-122">Le impostazioni delle riunioni includono le definizioni dei criteri di riunione e il supporto per la partecipazione degli utenti anonimi alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="0f29f-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="0f29f-123">È possibile recuperare le impostazioni di configurazione delle riunioni utilizzando Windows PowerShell e il cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0f29f-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="0f29f-124">Ad esempio, questo comando restituisce le informazioni sulle impostazioni di configurazione della riunione globale:</span><span class="sxs-lookup"><span data-stu-id="0f29f-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="0f29f-125">Get-CsMeetingConfiguration-Identity "Global" le impostazioni di configurazione delle riunioni possono essere configurate anche nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="0f29f-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="0f29f-126">Per questo motivo, è possibile utilizzare il comando seguente, che restituisce informazioni su tutte le impostazioni di configurazione delle riunioni:</span><span class="sxs-lookup"><span data-stu-id="0f29f-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="0f29f-127">Il cmdlet **Get-CsMeetingConfiguration** restituisce informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f29f-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="0f29f-128">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-128">Identity : Global</span></span>

<span data-ttu-id="0f29f-129">PstnCallersBypassLobby: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="0f29f-130">EnableAssignedConferenceType: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="0f29f-131">DesignateAsPresenter: società</span><span class="sxs-lookup"><span data-stu-id="0f29f-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="0f29f-132">AssignedConferenceTypeByDefault: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="0f29f-133">AdmitAnonymousUsersByDefault: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="0f29f-134">Anche in questo caso, l'elemento finale nell'elenco, **AdmitAnonymousUsersByDefault**, consente di abilitare o disabilitare la capacità degli utenti anonimi di partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="0f29f-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="0f29f-135">Quando si verificano le impostazioni di configurazione delle riunioni, potrebbe essere utile confrontare le impostazioni correnti con gli equivalenti predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0f29f-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="0f29f-136">È possibile visualizzare le impostazioni di configurazione delle riunioni predefinite eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0f29f-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0f29f-137">Il comando precedente consente di creare un'istanza solo in memoria delle impostazioni di configurazione della riunione globale, un'istanza che utilizza il valore predefinito per ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f29f-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="0f29f-138">Quando si esegue il comando, non vengono create impostazioni di configurazione delle riunioni effettive.</span><span class="sxs-lookup"><span data-stu-id="0f29f-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="0f29f-139">Tuttavia, tutti i valori della proprietà predefinita verranno visualizzati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="0f29f-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="0f29f-140">Controllare i server perimetrali e le relative impostazioni</span><span class="sxs-lookup"><span data-stu-id="0f29f-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="0f29f-141">È possibile recuperare le informazioni sui server perimetrali utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f29f-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="0f29f-142">Questo comando restituisce informazioni su tutti i server perimetrali configurati per l'utilizzo nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="0f29f-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="0f29f-143">Le informazioni restituite includono tutte le impostazioni di FQDN e di porta per ogni server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="0f29f-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="0f29f-144">Identità: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f29f-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="0f29f-145">Registrar: Registrar: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f29f-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="0f29f-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="0f29f-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="0f29f-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="0f29f-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="0f29f-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="0f29f-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="0f29f-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="0f29f-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="0f29f-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="0f29f-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="0f29f-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="0f29f-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="0f29f-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="0f29f-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="0f29f-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="0f29f-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="0f29f-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="0f29f-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="0f29f-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="0f29f-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="0f29f-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="0f29f-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="0f29f-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="0f29f-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="0f29f-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f29f-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0f29f-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f29f-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0f29f-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="0f29f-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="0f29f-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="0f29f-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="0f29f-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f29f-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0f29f-163">DependentServiceList: {Registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="0f29f-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="0f29f-164">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="0f29f-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="0f29f-165">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="0f29f-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="0f29f-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="0f29f-166">fabrikam.com}</span></span>

<span data-ttu-id="0f29f-167">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="0f29f-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="0f29f-168">SiteId: site: fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="0f29f-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="0f29f-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0f29f-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="0f29f-170">Versione: 5</span><span class="sxs-lookup"><span data-stu-id="0f29f-170">Version : 5</span></span>

<span data-ttu-id="0f29f-171">Ruolo: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="0f29f-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="0f29f-172">Controllare le impostazioni di Federazione</span><span class="sxs-lookup"><span data-stu-id="0f29f-172">Check federation settings</span></span>

<span data-ttu-id="0f29f-173">Verificare le impostazioni di federazione, ad esempio se sono configurate e, se la risposta è "Sì", il nome di dominio completo e la porta.</span><span class="sxs-lookup"><span data-stu-id="0f29f-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="0f29f-174">La Federazione è abilitata e disabilitata utilizzando la raccolta globale delle impostazioni di configurazione di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="0f29f-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="0f29f-175">Tra le altre cose, significa che la Federazione è configurata in base a tutto o niente: la Federazione è abilitata per l'intera organizzazione o la Federazione è disabilitata per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0f29f-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="0f29f-176">Le impostazioni di configurazione di Access Edge possono essere restituite tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f29f-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="0f29f-177">A tale scopo, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="0f29f-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="0f29f-178">In questo modo, il comando restituirà dati simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f29f-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="0f29f-179">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-179">Identity : Global</span></span>

<span data-ttu-id="0f29f-180">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="0f29f-181">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="0f29f-182">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="0f29f-183">BeClearingHouse: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-183">BeClearingHouse : False</span></span>

<span data-ttu-id="0f29f-184">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="0f29f-185">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="0f29f-186">KeepCrlsUpToDateForPeers: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="0f29f-187">MarkSourceVerifiableOnOutgoingMessages: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="0f29f-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="0f29f-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="0f29f-189">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="0f29f-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="0f29f-190">Se la proprietà **AllowFederatedUsers** è impostata su true, significa che la Federazione è abilitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0f29f-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="0f29f-191">(L'impostazione di **AllowFederatedUsers** su true significa anche che, in uno scenario di dominio diviso, gli utenti locali potranno comunicare senza problemi con gli utenti in-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="0f29f-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="0f29f-192">Per recuperare il nome di dominio completo e le impostazioni della porta per il server perimetrale, vedere l'attività precedente (server perimetrali e relative impostazioni).</span><span class="sxs-lookup"><span data-stu-id="0f29f-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="0f29f-193">L'abilitazione della Federazione nell'ambito globale implica solo che gli utenti possano comunicare con utenti federati.</span><span class="sxs-lookup"><span data-stu-id="0f29f-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="0f29f-194">Per determinare se i singoli utenti possono comunicare effettivamente con gli utenti federati, è necessario esaminare i criteri di accesso utente esterno assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="0f29f-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="0f29f-195">Le informazioni sull'accesso degli utenti esterni possono essere restituite tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f29f-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="0f29f-196">Ad esempio, questo comando restituisce le informazioni per il criterio di accesso utente esterno globale:</span><span class="sxs-lookup"><span data-stu-id="0f29f-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="0f29f-197">E questo comando restituisce informazioni su tutti i criteri di accesso degli utenti esterni:</span><span class="sxs-lookup"><span data-stu-id="0f29f-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="0f29f-198">Le informazioni restituite saranno simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f29f-198">The returned information will resemble this:</span></span>

<span data-ttu-id="0f29f-199">Identity: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-199">Identity : False</span></span>

<span data-ttu-id="0f29f-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f29f-200">Description :</span></span>

<span data-ttu-id="0f29f-201">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="0f29f-202">EnablePublicCloudAccess: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="0f29f-203">EnablePublicCloudAccessAudioVideoAccess: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="0f29f-204">EnableOutsideAccess: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="0f29f-205">Se **EnableFederationAccess** è impostato su true, gli utenti gestiti dal criterio specificato potranno comunicare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="0f29f-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="0f29f-206">Controllare le impostazioni di archiviazione</span><span class="sxs-lookup"><span data-stu-id="0f29f-206">Check archiving settings</span></span>

<span data-ttu-id="0f29f-207">Controllare le impostazioni di archiviazione per le comunicazioni interne e federate. Prima di verificare le impostazioni per l'archiviazione interna ed esterna, è necessario verificare che l'archiviazione sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="0f29f-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="0f29f-208">È possibile verificare le impostazioni di configurazione dell'archiviazione utilizzando Windows PowerShell e il cmdlet Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="0f29f-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="0f29f-209">Si noti che le impostazioni di archiviazione possono essere configurate anche nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="0f29f-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="0f29f-210">Per restituire informazioni su tutte le impostazioni di archiviazione, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="0f29f-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="0f29f-211">Il cmdlet Get-CsArchivingConfiguration restituisce dati simili al seguente:</span><span class="sxs-lookup"><span data-stu-id="0f29f-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="0f29f-212">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-212">Identity : Global</span></span>

<span data-ttu-id="0f29f-213">EnableArchiving: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-213">EnableArchiving : False</span></span>

<span data-ttu-id="0f29f-214">EnablePurging: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-214">EnablePurging : False</span></span>

<span data-ttu-id="0f29f-215">PurgeExportedArchivesOnly: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="0f29f-216">BlockOnArchiveFailure: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="0f29f-217">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="0f29f-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="0f29f-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="0f29f-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="0f29f-219">ArchiveDuplicateMessages: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="0f29f-220">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="0f29f-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="0f29f-221">Se la proprietà EnableArchiving è impostata su false, significa che non verranno archiviate sessioni di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="0f29f-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="0f29f-222">Se si desidera archiviare solo le sessioni di messaggistica istantanea, utilizzare un comando simile al seguente per abilitare l'archiviazione delle sessioni di messaggistica istantanea:</span><span class="sxs-lookup"><span data-stu-id="0f29f-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="0f29f-223">Per archiviare le sessioni di conferenza e le sessioni di messaggistica istantanea, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="0f29f-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="0f29f-224">Se si desidera confrontare le impostazioni di archiviazione correnti con quelle predefinite, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="0f29f-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0f29f-225">Questo comando consente di creare un'istanza solo in memoria delle impostazioni di configurazione di archiviazione globale.</span><span class="sxs-lookup"><span data-stu-id="0f29f-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="0f29f-226">Non si tratta di una vera e propria raccolta di impostazioni utilizzata da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f29f-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="0f29f-227">Tuttavia, vengono visualizzati i valori predefiniti per tutte le proprietà di configurazione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0f29f-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="0f29f-228">È inoltre possibile utilizzare questo comando per restituire il nome di dominio completo dei server di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="0f29f-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="0f29f-229">Dopo aver verificato che l'archiviazione sia abilitata, è possibile visualizzare i criteri di archiviazione per determinare se le sessioni di comunicazione interne ed esterne vengono archiviate.</span><span class="sxs-lookup"><span data-stu-id="0f29f-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="0f29f-230">Le informazioni sui criteri di archiviazione possono essere recuperate utilizzando il cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="0f29f-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="0f29f-231">Ad esempio, questo comando restituisce le informazioni sul criterio di archiviazione globale:</span><span class="sxs-lookup"><span data-stu-id="0f29f-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="0f29f-232">Poiché i criteri di archiviazione possono essere configurati anche nel sito e nell'ambito per utente, è possibile anche utilizzare questo comando, che restituisce informazioni su tutti i criteri di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="0f29f-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="0f29f-233">Le informazioni ricevute da Get-CsArchivingPolicy saranno simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f29f-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="0f29f-234">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-234">Identity : Global</span></span>

<span data-ttu-id="0f29f-235">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f29f-235">Description :</span></span>

<span data-ttu-id="0f29f-236">ArchiveInternal: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-236">ArchiveInternal : False</span></span>

<span data-ttu-id="0f29f-237">ArchiveExternal: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-237">ArchiveExternal : False</span></span>

<span data-ttu-id="0f29f-238">Si noti che, per impostazione predefinita, sia l'archiviazione interna sia quella esterna sono disattivate in un criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0f29f-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="0f29f-239">Controllare le impostazioni di registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="0f29f-239">Check CDR settings</span></span>

<span data-ttu-id="0f29f-240">Controllare le impostazioni del record dettagli chiamata (CDR) per la registrazione dei dettagli delle chiamate peer-to-peer, conferenze e vocali.</span><span class="sxs-lookup"><span data-stu-id="0f29f-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="0f29f-241">Per informazioni dettagliate sulle impostazioni di registrazione dettagli chiamata, è possibile utilizzare il cmdlet **Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0f29f-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="0f29f-242">Ad esempio, questo comando restituisce informazioni sulla raccolta globale delle impostazioni di configurazione di registrazione dettagli chiamata:</span><span class="sxs-lookup"><span data-stu-id="0f29f-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="0f29f-243">Poiché CDR può anche essere configurato nell'ambito del sito, è possibile che si desideri eseguire questo comando, che restituisce informazioni su tutte le impostazioni di configurazione di registrazione dettagli chiamata:</span><span class="sxs-lookup"><span data-stu-id="0f29f-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="0f29f-244">Il cmdlet Get-CsCdrConfiguration restituisce informazioni simili a queste per ogni raccolta di impostazioni di configurazione di registrazione dettagli chiamata:</span><span class="sxs-lookup"><span data-stu-id="0f29f-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="0f29f-245">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-245">Identity : Global</span></span>

<span data-ttu-id="0f29f-246">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-246">EnableCDR : True</span></span>

<span data-ttu-id="0f29f-247">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-247">EnablePurging : True</span></span>

<span data-ttu-id="0f29f-248">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="0f29f-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="0f29f-249">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="0f29f-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="0f29f-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="0f29f-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="0f29f-251">È possibile restituire informazioni simili per il monitoraggio QoE utilizzando il cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="0f29f-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="0f29f-252">Ad esempio, questo comando restituisce informazioni sulla raccolta globale di impostazioni di configurazione QoE:</span><span class="sxs-lookup"><span data-stu-id="0f29f-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="0f29f-253">Queste informazioni saranno simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f29f-253">That information will resemble this:</span></span>

<span data-ttu-id="0f29f-254">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-254">Identity : Global</span></span>

<span data-ttu-id="0f29f-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="0f29f-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="0f29f-256">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-256">EnablePurging : True</span></span>

<span data-ttu-id="0f29f-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="0f29f-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="0f29f-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="0f29f-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="0f29f-259">EnableExternalConsumer: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="0f29f-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="0f29f-260">ExternalConsumerName :</span></span>

<span data-ttu-id="0f29f-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="0f29f-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="0f29f-262">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-262">EnableQoE : True</span></span>

<span data-ttu-id="0f29f-263">Se si desidera confrontare le impostazioni di registrazione dettagli chiamata correnti con le impostazioni di registrazione dettagli chiamata predefinite, è possibile rivedere i valori predefiniti eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0f29f-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0f29f-264">Analogamente, i valori predefiniti per il monitoraggio QoE possono essere recuperati utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0f29f-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="0f29f-265">È anche possibile restituire il nome di dominio completo dei server di monitoraggio eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0f29f-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="0f29f-266">Controllare le impostazioni vocali</span><span class="sxs-lookup"><span data-stu-id="0f29f-266">Check voice settings</span></span>

<span data-ttu-id="0f29f-267">Le impostazioni vocali in genere importanti per gli amministratori sono contenute nei criteri vocali e nelle route vocali: i criteri vocali contengono le impostazioni che determinano le funzionalità esposte ai singoli utenti, ad esempio la possibilità di inoltrare o trasferire le chiamate, mentre le route vocali determinano come (e se) le chiamate vengono instradate attraverso la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="0f29f-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="0f29f-268">Le informazioni sui criteri vocali possono essere recuperate tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f29f-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="0f29f-269">Ad esempio, questo comando restituisce le informazioni sul criterio vocale globale:</span><span class="sxs-lookup"><span data-stu-id="0f29f-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="0f29f-270">Questo comando restituisce informazioni su tutti i criteri vocali configurati per l'utilizzo nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="0f29f-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="0f29f-271">Le informazioni restituite dal cmdlet Get-CsVoicePolicy sono analoghe a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="0f29f-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="0f29f-272">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-272">Identity : Global</span></span>

<span data-ttu-id="0f29f-273">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="0f29f-273">PstnUsages : {}</span></span>

<span data-ttu-id="0f29f-274">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f29f-274">Description :</span></span>

<span data-ttu-id="0f29f-275">AllowSimulRing: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-275">AllowSimulRing : True</span></span>

<span data-ttu-id="0f29f-276">AllowCallForwarding: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="0f29f-277">AllowPSTNReRouting: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="0f29f-278">Nome: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="0f29f-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="0f29f-279">EnableDelegation: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-279">EnableDelegation : True</span></span>

<span data-ttu-id="0f29f-280">EnableTeamCall: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-280">EnableTeamCall : True</span></span>

<span data-ttu-id="0f29f-281">EnableCallTransfer: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="0f29f-282">EnableCallPark: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-282">EnableCallPark : False</span></span>

<span data-ttu-id="0f29f-283">EnableMaliciousCallTracing: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="0f29f-284">EnableBWPolicyOverride: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="0f29f-285">PreventPSTNTollBypass: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="0f29f-286">È inoltre possibile creare query che restituiscono un sottoinsieme di criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="0f29f-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="0f29f-287">Ad esempio, questo comando restituisce tutti i criteri vocali che consentono l'inoltro di chiamata:</span><span class="sxs-lookup"><span data-stu-id="0f29f-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="0f29f-288">Questo comando consente di restituire tutti i criteri vocali che non consentono l'inoltro delle chiamate:</span><span class="sxs-lookup"><span data-stu-id="0f29f-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="0f29f-289">In Windows PowerShell, utilizzare il cmdlet Get-CsVoiceRouting per restituire le informazioni sulle route vocali:</span><span class="sxs-lookup"><span data-stu-id="0f29f-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="0f29f-290">Questo comando restituisce informazioni come questa per tutte le route vocali:</span><span class="sxs-lookup"><span data-stu-id="0f29f-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="0f29f-291">Identità: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="0f29f-291">Identity : LocalRoute</span></span>

<span data-ttu-id="0f29f-292">Priorità: 0</span><span class="sxs-lookup"><span data-stu-id="0f29f-292">Priority : 0</span></span>

<span data-ttu-id="0f29f-293">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f29f-293">Description :</span></span>

<span data-ttu-id="0f29f-294">NumberPattern: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="0f29f-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="0f29f-295">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="0f29f-295">PstnUsages : {}</span></span>

<span data-ttu-id="0f29f-296">PstnGatewayList {}</span><span class="sxs-lookup"><span data-stu-id="0f29f-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="0f29f-297">Nome: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="0f29f-297">Name : LocalRoute</span></span>

<span data-ttu-id="0f29f-298">SuppressCallerId</span><span class="sxs-lookup"><span data-stu-id="0f29f-298">SuppressCallerId :</span></span>

<span data-ttu-id="0f29f-299">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="0f29f-299">AlternateCallerId :</span></span>

<span data-ttu-id="0f29f-300">Lync Server consente di creare route vocali che non dispongono di un utilizzo PSTN e non specificano un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="0f29f-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="0f29f-301">Tuttavia, non è possibile instradare effettivamente le chiamate su una route vocale che non dispone di questi due valori di proprietà configurati.</span><span class="sxs-lookup"><span data-stu-id="0f29f-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="0f29f-302">Per questo motivo, potrebbe essere utile eseguire periodicamente questo comando, che restituisce l'identità di qualsiasi route vocale che non ha un utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="0f29f-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="0f29f-303">Analogamente, questo comando restituisce l'identità di qualsiasi route vocale che non è stata configurata per avere un gateway PSTN:</span><span class="sxs-lookup"><span data-stu-id="0f29f-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="0f29f-304">Verificare le impostazioni dell'operatore conferenza</span><span class="sxs-lookup"><span data-stu-id="0f29f-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="0f29f-305">Verificare le impostazioni dell'operatore di conferenza per le conferenze telefoniche con accesso esterno PSTN.</span><span class="sxs-lookup"><span data-stu-id="0f29f-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="0f29f-306">Le impostazioni dell'operatore conferenza possono essere recuperate solo utilizzando il cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0f29f-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="0f29f-307">Queste impostazioni non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f29f-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="0f29f-308">Per visualizzare le impostazioni dell'operatore conferenza, utilizzare un comando di Windows PowerShell simile al seguente, che restituisce la raccolta globale di impostazioni Operatore Conferenza:</span><span class="sxs-lookup"><span data-stu-id="0f29f-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="0f29f-309">Tenere presente che è possibile configurare le impostazioni dell'operatore conferenza anche nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="0f29f-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="0f29f-310">Per restituire informazioni su tutte le impostazioni dell'operatore conferenza, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="0f29f-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="0f29f-311">Il cmdlet Get-CsDialInConferencingConfiguration restituisce dati simili al seguente:</span><span class="sxs-lookup"><span data-stu-id="0f29f-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="0f29f-312">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="0f29f-312">Identity : Global</span></span>

<span data-ttu-id="0f29f-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="0f29f-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="0f29f-314">EnableNameRecording: true</span><span class="sxs-lookup"><span data-stu-id="0f29f-314">EnableNameRecording : True</span></span>

<span data-ttu-id="0f29f-315">EntryExitAnnouncementsEnabledByDefault: false</span><span class="sxs-lookup"><span data-stu-id="0f29f-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="0f29f-316">Se EntryExitAnnouncementsEnabledByDefault è impostato su false, significa che gli annunci per le conferenze sono disattivati.</span><span class="sxs-lookup"><span data-stu-id="0f29f-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="0f29f-317">Per abilitare gli annunci di entrata e uscita, eseguire un comando di Windows PowerShell analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="0f29f-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f29f-318">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f29f-318">See Also</span></span>


[<span data-ttu-id="0f29f-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="0f29f-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="0f29f-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f29f-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="0f29f-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="0f29f-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="0f29f-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f29f-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="0f29f-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0f29f-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="0f29f-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f29f-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="0f29f-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f29f-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="0f29f-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f29f-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="0f29f-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="0f29f-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="0f29f-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="0f29f-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="0f29f-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f29f-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

