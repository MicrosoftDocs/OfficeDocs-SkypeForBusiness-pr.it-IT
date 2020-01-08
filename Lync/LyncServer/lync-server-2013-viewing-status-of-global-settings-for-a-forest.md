---
title: 'Lync Server 2013: visualizzazione dello stato delle impostazioni globali per una foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="b9557-102">Visualizzare lo stato delle impostazioni globali per una foresta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9557-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9557-103">_**Argomento Ultima modifica:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b9557-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="b9557-104">Gli amministratori devono rivedere le impostazioni globali per una distribuzione di Lync Server 2013 mensili.</span><span class="sxs-lookup"><span data-stu-id="b9557-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="b9557-105">L'obiettivo consiste nel rivedere le impostazioni implementate in base a un set di configurazioni note, una configurazione di base per garantire che le impostazioni siano valide e per determinare se la documentazione prevista deve essere aggiornata.</span><span class="sxs-lookup"><span data-stu-id="b9557-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="b9557-106">Le modifiche apportate all'impostazione globale devono essere implementate tramite un processo di controllo delle modifiche che dovrebbe includere la documentazione delle nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b9557-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="b9557-107">Le impostazioni globali da rivedere sono descritte nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9557-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="b9557-108">Controllare le impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="b9557-108">Check general settings</span></span>

<span data-ttu-id="b9557-109">Verificare le impostazioni generali, inclusi i domini SIP (Session Initiation Protocol) supportati per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9557-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="b9557-110">Le informazioni sul dominio SIP possono essere restituite tramite Windows PowerShell e il cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="b9557-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="b9557-111">Per restituire queste informazioni, eseguire il `Get-CsSipDomain` comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9557-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="b9557-112">Get-CsSipDomain restituirà informazioni simili a quelle per tutti i domini SIP autorizzati:</span><span class="sxs-lookup"><span data-stu-id="b9557-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="b9557-113">Nome identità predefinito</span><span class="sxs-lookup"><span data-stu-id="b9557-113">Identity Name IsDefault</span></span>

<span data-ttu-id="b9557-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="b9557-114"></span></span>

<span data-ttu-id="b9557-115">fabrikam.com fabrikam.com vero</span><span class="sxs-lookup"><span data-stu-id="b9557-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="b9557-116">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="b9557-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="b9557-117">Se la proprietà IsDefault è impostata su true, il dominio corrispondente è il dominio SIP predefinito.</span><span class="sxs-lookup"><span data-stu-id="b9557-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="b9557-118">Puoi usare il cmdlet Set-CsSipDomain per cambiare il dominio SIP predefinito per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b9557-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="b9557-119">Tuttavia, non è possibile eliminare semplicemente il dominio SIP predefinito, perché questo non è possibile senza un dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b9557-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="b9557-120">Se si vuole eliminare il dominio fabrikam.com, come illustrato nell'esempio precedente, è necessario prima di tutto configurare na.fabrikam.com come dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b9557-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="b9557-121">Verificare le impostazioni della riunione</span><span class="sxs-lookup"><span data-stu-id="b9557-121">Check meeting settings</span></span>

<span data-ttu-id="b9557-122">Le impostazioni delle riunioni includono le definizioni dei criteri di riunione e il supporto per la partecipazione degli utenti anonimi alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b9557-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="b9557-123">Le impostazioni di configurazione della riunione possono essere recuperate tramite Windows PowerShell e il cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b9557-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="b9557-124">Ad esempio, questo comando restituisce informazioni sulle impostazioni di configurazione della riunione globale:</span><span class="sxs-lookup"><span data-stu-id="b9557-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="b9557-125">Get-CsMeetingConfiguration – Identity "Global" le impostazioni di configurazione delle riunioni possono essere configurate anche nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="b9557-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="b9557-126">Per questo motivo, potresti voler usare il comando seguente, che restituisce informazioni su tutte le impostazioni di configurazione della riunione:</span><span class="sxs-lookup"><span data-stu-id="b9557-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="b9557-127">Il cmdlet **Get-CsMeetingConfiguration** restituisce informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9557-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="b9557-128">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-128">Identity : Global</span></span>

<span data-ttu-id="b9557-129">PstnCallersBypassLobby: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="b9557-130">EnableAssignedConferenceType: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="b9557-131">DesignateAsPresenter: società</span><span class="sxs-lookup"><span data-stu-id="b9557-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="b9557-132">AssignedConferenceTypeByDefault: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="b9557-133">AdmitAnonymousUsersByDefault: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="b9557-134">Anche in questo caso, l'elemento finale nell'elenco, **AdmitAnonymousUsersByDefault**, Abilita o Disabilita la capacità degli utenti anonimi di partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b9557-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="b9557-135">Quando si verificano le impostazioni di configurazione della riunione, è possibile che sia utile confrontare le impostazioni correnti con quelle predefinite.</span><span class="sxs-lookup"><span data-stu-id="b9557-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="b9557-136">È possibile visualizzare le impostazioni di configurazione della riunione predefinite eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b9557-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b9557-137">Il comando precedente crea un'istanza solo in memoria delle impostazioni di configurazione della riunione globale, un'istanza che usa il valore predefinito per ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="b9557-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="b9557-138">Quando si esegue il comando non viene creata alcuna impostazione di configurazione della riunione effettiva.</span><span class="sxs-lookup"><span data-stu-id="b9557-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="b9557-139">Tuttavia, tutti i valori di proprietà predefiniti verranno visualizzati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="b9557-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="b9557-140">Controllare i server Edge e le relative impostazioni</span><span class="sxs-lookup"><span data-stu-id="b9557-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="b9557-141">Le informazioni su Edge Server possono essere recuperate tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9557-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="b9557-142">Questo comando restituisce informazioni su tutti i server perimetrali configurati per l'uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="b9557-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="b9557-143">Le informazioni restituite includono tutte le impostazioni di FQDN e di porta per ogni server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="b9557-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="b9557-144">Identità: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b9557-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="b9557-145">Cancelliere: cancelliere: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b9557-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="b9557-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="b9557-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="b9557-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="b9557-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="b9557-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="b9557-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="b9557-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="b9557-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="b9557-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="b9557-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="b9557-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="b9557-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="b9557-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="b9557-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="b9557-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="b9557-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="b9557-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="b9557-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="b9557-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="b9557-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="b9557-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="b9557-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="b9557-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="b9557-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="b9557-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b9557-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b9557-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b9557-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b9557-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="b9557-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="b9557-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="b9557-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="b9557-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b9557-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b9557-163">DependentServiceList: {Registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="b9557-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="b9557-164">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="b9557-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="b9557-165">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="b9557-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="b9557-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="b9557-166">fabrikam.com}</span></span>

<span data-ttu-id="b9557-167">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="b9557-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="b9557-168">SiteId: sito: fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="b9557-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="b9557-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b9557-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b9557-170">Versione: 5</span><span class="sxs-lookup"><span data-stu-id="b9557-170">Version : 5</span></span>

<span data-ttu-id="b9557-171">Ruolo: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="b9557-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="b9557-172">Controllare le impostazioni della Federazione</span><span class="sxs-lookup"><span data-stu-id="b9557-172">Check federation settings</span></span>

<span data-ttu-id="b9557-173">Verificare le impostazioni della Federazione, ad esempio se è configurata e, se la risposta è "Sì", il nome di dominio completo e la porta.</span><span class="sxs-lookup"><span data-stu-id="b9557-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="b9557-174">La Federazione viene abilitata e disabilitata tramite la raccolta globale delle impostazioni di configurazione di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="b9557-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="b9557-175">Tra le altre cose, significa che la Federazione è configurata in base a tutti o nulla: la Federazione è abilitata per l'intera organizzazione o la Federazione è disabilitata per l'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="b9557-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="b9557-176">Le impostazioni di configurazione di Access Edge possono essere restituite tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9557-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="b9557-177">A tale scopo, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="b9557-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="b9557-178">A sua volta, il comando restituirà dati simili a quelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9557-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="b9557-179">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-179">Identity : Global</span></span>

<span data-ttu-id="b9557-180">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="b9557-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="b9557-181">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="b9557-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="b9557-182">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="b9557-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="b9557-183">BeClearingHouse: false</span><span class="sxs-lookup"><span data-stu-id="b9557-183">BeClearingHouse : False</span></span>

<span data-ttu-id="b9557-184">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="b9557-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="b9557-185">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="b9557-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="b9557-186">KeepCrlsUpToDateForPeers: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="b9557-187">MarkSourceVerifiableOnOutgoingMessages: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="b9557-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="b9557-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="b9557-189">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="b9557-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="b9557-190">Se la proprietà **AllowFederatedUsers** è impostata su true, significa che la Federazione è abilitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b9557-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="b9557-191">L'impostazione di **AllowFederatedUsers** su true significa anche che in uno scenario di dominio diviso gli utenti locali saranno in grado di comunicare in modo uniforme con gli utenti in-the-cloud.</span><span class="sxs-lookup"><span data-stu-id="b9557-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="b9557-192">Per recuperare le impostazioni di FQDN e di porta per l'Edge Server, vedere l'attività precedente (Edge Server e le relative impostazioni).</span><span class="sxs-lookup"><span data-stu-id="b9557-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="b9557-193">L'abilitazione della Federazione nell'ambito globale indica che gli utenti possono comunicare potenzialmente con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="b9557-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="b9557-194">Per determinare se i singoli utenti possono effettivamente comunicare con gli utenti federati, è necessario esaminare i criteri di accesso degli utenti esterni assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="b9557-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="b9557-195">Le informazioni di accesso degli utenti esterni possono essere restituite tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9557-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="b9557-196">Ad esempio, questo comando restituisce le informazioni per il criterio di accesso utente esterno globale:</span><span class="sxs-lookup"><span data-stu-id="b9557-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="b9557-197">Questo comando restituisce le informazioni per tutti i criteri di accesso degli utenti esterni:</span><span class="sxs-lookup"><span data-stu-id="b9557-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="b9557-198">Le informazioni restituite saranno simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9557-198">The returned information will resemble this:</span></span>

<span data-ttu-id="b9557-199">Identità: false</span><span class="sxs-lookup"><span data-stu-id="b9557-199">Identity : False</span></span>

<span data-ttu-id="b9557-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9557-200">Description :</span></span>

<span data-ttu-id="b9557-201">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="b9557-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="b9557-202">EnablePublicCloudAccess: false</span><span class="sxs-lookup"><span data-stu-id="b9557-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="b9557-203">EnablePublicCloudAccessAudioVideoAccess: false</span><span class="sxs-lookup"><span data-stu-id="b9557-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="b9557-204">EnableOutsideAccess: false</span><span class="sxs-lookup"><span data-stu-id="b9557-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="b9557-205">Se **EnableFederationAccess** è impostato su true, gli utenti gestiti dal criterio specifico possono comunicare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="b9557-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="b9557-206">Controllare le impostazioni di archiviazione</span><span class="sxs-lookup"><span data-stu-id="b9557-206">Check archiving settings</span></span>

<span data-ttu-id="b9557-207">Controllare le impostazioni di archiviazione per le comunicazioni interne e federate. Prima di verificare le impostazioni per l'archiviazione interna ed esterna, è necessario verificare che l'archiviazione sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="b9557-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="b9557-208">È possibile verificare le impostazioni di configurazione dell'archiviazione tramite Windows PowerShell e il cmdlet Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="b9557-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="b9557-209">Tieni presente che le impostazioni di archiviazione possono essere configurate anche nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="b9557-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="b9557-210">Per restituire informazioni su tutte le impostazioni di archiviazione, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="b9557-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="b9557-211">Il cmdlet Get-CsArchivingConfiguration restituisce i dati in modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b9557-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="b9557-212">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-212">Identity : Global</span></span>

<span data-ttu-id="b9557-213">EnableArchiving: false</span><span class="sxs-lookup"><span data-stu-id="b9557-213">EnableArchiving : False</span></span>

<span data-ttu-id="b9557-214">EnablePurging: false</span><span class="sxs-lookup"><span data-stu-id="b9557-214">EnablePurging : False</span></span>

<span data-ttu-id="b9557-215">PurgeExportedArchivesOnly: false</span><span class="sxs-lookup"><span data-stu-id="b9557-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="b9557-216">BlockOnArchiveFailure: false</span><span class="sxs-lookup"><span data-stu-id="b9557-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="b9557-217">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="b9557-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="b9557-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="b9557-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="b9557-219">ArchiveDuplicateMessages: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="b9557-220">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="b9557-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="b9557-221">Se la proprietà EnableArchiving è impostata su false, significa che non verranno archiviate sessioni di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="b9557-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="b9557-222">Se si vogliono archiviare solo le sessioni di messaggistica istantanea, usare un comando come il seguente per abilitare l'archiviazione delle sessioni di messaggistica istantanea:</span><span class="sxs-lookup"><span data-stu-id="b9557-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="b9557-223">Per archiviare sessioni di conferenza e sessioni di messaggistica istantanea, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="b9557-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="b9557-224">Se si vuole confrontare le impostazioni di archiviazione correnti con quelle predefinite, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="b9557-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b9557-225">Questo comando crea un'istanza solo in memoria delle impostazioni di configurazione dell'archiviazione globale.</span><span class="sxs-lookup"><span data-stu-id="b9557-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="b9557-226">Non si tratta di una raccolta reale di impostazioni usate da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9557-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="b9557-227">Tuttavia, Visualizza i valori predefiniti per tutte le proprietà di configurazione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b9557-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="b9557-228">Puoi anche usare questo comando per restituire il nome di dominio completo dei server di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="b9557-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="b9557-229">Dopo aver verificato che l'archiviazione sia abilitata, è possibile visualizzare i criteri di archiviazione per determinare se le sessioni di comunicazione interna ed esterna vengono archiviate.</span><span class="sxs-lookup"><span data-stu-id="b9557-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="b9557-230">Le informazioni sui criteri di archiviazione possono essere recuperate usando il cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="b9557-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="b9557-231">Ad esempio, questo comando restituisce informazioni sui criteri di archiviazione globale:</span><span class="sxs-lookup"><span data-stu-id="b9557-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="b9557-232">Poiché i criteri di archiviazione possono essere configurati anche nel sito e nell'ambito per utente, è anche possibile usare questo comando, che restituisce informazioni su tutti i criteri di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="b9557-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="b9557-233">Le informazioni ricevute da Get-CsArchivingPolicy saranno simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9557-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="b9557-234">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-234">Identity : Global</span></span>

<span data-ttu-id="b9557-235">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9557-235">Description :</span></span>

<span data-ttu-id="b9557-236">ArchiveInternal: false</span><span class="sxs-lookup"><span data-stu-id="b9557-236">ArchiveInternal : False</span></span>

<span data-ttu-id="b9557-237">ArchiveExternal: false</span><span class="sxs-lookup"><span data-stu-id="b9557-237">ArchiveExternal : False</span></span>

<span data-ttu-id="b9557-238">Tieni presente che, per impostazione predefinita, sia l'archiviazione interna che quella esterna sono disabilitate in un criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b9557-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="b9557-239">Controllare le impostazioni di CDR</span><span class="sxs-lookup"><span data-stu-id="b9557-239">Check CDR settings</span></span>

<span data-ttu-id="b9557-240">Controllare le impostazioni del record di dettaglio delle chiamate (CDR) per la registrazione dei dettagli tra peer-to-peer, conferenze e chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="b9557-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="b9557-241">Le informazioni dettagliate sulle impostazioni CDR possono essere restituite usando il cmdlet **Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b9557-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="b9557-242">Ad esempio, questo comando restituisce informazioni sulla raccolta globale delle impostazioni di configurazione CDR:</span><span class="sxs-lookup"><span data-stu-id="b9557-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="b9557-243">Poiché CDR può essere configurato anche nell'ambito del sito, è anche possibile eseguire questo comando, che restituisce informazioni su tutte le impostazioni di configurazione CDR:</span><span class="sxs-lookup"><span data-stu-id="b9557-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="b9557-244">Il cmdlet Get-CsCdrConfiguration restituisce informazioni simili a queste per ogni raccolta di impostazioni di configurazione CDR:</span><span class="sxs-lookup"><span data-stu-id="b9557-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="b9557-245">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-245">Identity : Global</span></span>

<span data-ttu-id="b9557-246">EnableCDR: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-246">EnableCDR : True</span></span>

<span data-ttu-id="b9557-247">EnablePurging: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-247">EnablePurging : True</span></span>

<span data-ttu-id="b9557-248">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="b9557-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="b9557-249">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="b9557-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="b9557-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="b9557-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="b9557-251">Le informazioni simili possono essere restituite per il monitoraggio QoE usando il cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b9557-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="b9557-252">Ad esempio, questo comando restituisce informazioni sulla raccolta globale di impostazioni di configurazione QoE:</span><span class="sxs-lookup"><span data-stu-id="b9557-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="b9557-253">Queste informazioni saranno simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9557-253">That information will resemble this:</span></span>

<span data-ttu-id="b9557-254">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-254">Identity : Global</span></span>

<span data-ttu-id="b9557-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="b9557-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="b9557-256">EnablePurging: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-256">EnablePurging : True</span></span>

<span data-ttu-id="b9557-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="b9557-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="b9557-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="b9557-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="b9557-259">EnableExternalConsumer: false</span><span class="sxs-lookup"><span data-stu-id="b9557-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="b9557-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="b9557-260">ExternalConsumerName :</span></span>

<span data-ttu-id="b9557-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="b9557-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="b9557-262">EnableQoE: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-262">EnableQoE : True</span></span>

<span data-ttu-id="b9557-263">Se si vogliono confrontare le impostazioni di CDR correnti con quelle predefinite, è possibile rivedere i valori predefiniti eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="b9557-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b9557-264">Allo stesso modo, i valori predefiniti per il monitoraggio QoE possono essere recuperati usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="b9557-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b9557-265">È anche possibile restituire il nome di dominio completo dei server di monitoraggio eseguendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="b9557-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="b9557-266">Controllare le impostazioni vocali</span><span class="sxs-lookup"><span data-stu-id="b9557-266">Check voice settings</span></span>

<span data-ttu-id="b9557-267">Le impostazioni vocali in genere importanti per gli amministratori sono contenute nei criteri vocali e nelle route vocali: i criteri vocali contengono le impostazioni che determinano le funzionalità esposte ai singoli utenti, ad esempio la possibilità di inoltrare o trasferire le chiamate, mentre le route vocali determinano la modalità di routing delle chiamate (e se) attraverso la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="b9557-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="b9557-268">Le informazioni sui criteri vocali possono essere recuperate tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9557-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="b9557-269">Ad esempio, questo comando restituisce informazioni sul criterio vocale globale:</span><span class="sxs-lookup"><span data-stu-id="b9557-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="b9557-270">Questo comando restituisce informazioni su tutti i criteri vocali configurati per l'uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="b9557-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="b9557-271">Le informazioni restituite dal cmdlet Get-CsVoicePolicy sono simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9557-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="b9557-272">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-272">Identity : Global</span></span>

<span data-ttu-id="b9557-273">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="b9557-273">PstnUsages : {}</span></span>

<span data-ttu-id="b9557-274">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9557-274">Description :</span></span>

<span data-ttu-id="b9557-275">AllowSimulRing: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-275">AllowSimulRing : True</span></span>

<span data-ttu-id="b9557-276">AllowCallForwarding: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="b9557-277">AllowPSTNReRouting: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="b9557-278">Nome: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="b9557-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="b9557-279">EnableDelegation: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-279">EnableDelegation : True</span></span>

<span data-ttu-id="b9557-280">EnableTeamCall: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-280">EnableTeamCall : True</span></span>

<span data-ttu-id="b9557-281">EnableCallTransfer: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="b9557-282">EnableCallPark: false</span><span class="sxs-lookup"><span data-stu-id="b9557-282">EnableCallPark : False</span></span>

<span data-ttu-id="b9557-283">EnableMaliciousCallTracing: false</span><span class="sxs-lookup"><span data-stu-id="b9557-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="b9557-284">EnableBWPolicyOverride: false</span><span class="sxs-lookup"><span data-stu-id="b9557-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="b9557-285">PreventPSTNTollBypass: false</span><span class="sxs-lookup"><span data-stu-id="b9557-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="b9557-286">È anche possibile creare query che restituiscono un sottoinsieme dei criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="b9557-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="b9557-287">Ad esempio, questo comando restituisce tutti i criteri vocali che consentono l'inoltro di chiamata:</span><span class="sxs-lookup"><span data-stu-id="b9557-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="b9557-288">Questo comando restituisce tutti i criteri vocali che non consentono l'inoltro di chiamata:</span><span class="sxs-lookup"><span data-stu-id="b9557-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="b9557-289">In Windows PowerShell, usare il cmdlet Get-CsVoiceRouting per restituire informazioni sulle route vocali:</span><span class="sxs-lookup"><span data-stu-id="b9557-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="b9557-290">Questo comando restituisce informazioni come questa per tutte le route vocali:</span><span class="sxs-lookup"><span data-stu-id="b9557-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="b9557-291">Identità: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="b9557-291">Identity : LocalRoute</span></span>

<span data-ttu-id="b9557-292">Priorità: 0</span><span class="sxs-lookup"><span data-stu-id="b9557-292">Priority : 0</span></span>

<span data-ttu-id="b9557-293">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9557-293">Description :</span></span>

<span data-ttu-id="b9557-294">NumberPattern: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="b9557-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="b9557-295">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="b9557-295">PstnUsages : {}</span></span>

<span data-ttu-id="b9557-296">PstnGatewayList{}</span><span class="sxs-lookup"><span data-stu-id="b9557-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="b9557-297">Nome: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="b9557-297">Name : LocalRoute</span></span>

<span data-ttu-id="b9557-298">SuppressCallerId</span><span class="sxs-lookup"><span data-stu-id="b9557-298">SuppressCallerId :</span></span>

<span data-ttu-id="b9557-299">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="b9557-299">AlternateCallerId :</span></span>

<span data-ttu-id="b9557-300">Lync Server consente di creare route vocali che non hanno un uso PSTN e non specificano un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b9557-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="b9557-301">Tuttavia, non puoi effettivamente instradare le chiamate su una route vocale che non ha questi due valori di proprietà configurati.</span><span class="sxs-lookup"><span data-stu-id="b9557-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="b9557-302">Per questo motivo, potresti trovare utile eseguire periodicamente questo comando, che restituisce l'identità di qualsiasi route vocale che non ha un uso PSTN:</span><span class="sxs-lookup"><span data-stu-id="b9557-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="b9557-303">Analogamente, questo comando restituisce l'identità di una route vocale non configurata per avere un gateway PSTN:</span><span class="sxs-lookup"><span data-stu-id="b9557-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="b9557-304">Controllare le impostazioni dell'operatore di conferenza</span><span class="sxs-lookup"><span data-stu-id="b9557-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="b9557-305">Controllare le impostazioni dell'operatore di conferenza per i servizi di conferenza telefonica con accesso esterno PSTN.</span><span class="sxs-lookup"><span data-stu-id="b9557-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="b9557-306">Le impostazioni dell'operatore di conferenza possono essere recuperate solo usando il cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b9557-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="b9557-307">Queste impostazioni non sono disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9557-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="b9557-308">Per visualizzare le impostazioni di un operatore del servizio di conferenza, usare un comando di Windows PowerShell simile al seguente, che restituisce la raccolta globale delle impostazioni di operatore conferenza:</span><span class="sxs-lookup"><span data-stu-id="b9557-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="b9557-309">Tieni presente che le impostazioni dell'operatore di conferenza possono essere configurate anche nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="b9557-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="b9557-310">Per restituire informazioni su tutte le impostazioni dell'operatore di conferenza, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="b9557-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="b9557-311">Il cmdlet Get-CsDialInConferencingConfiguration restituisce i dati in modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b9557-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="b9557-312">Identità: globale</span><span class="sxs-lookup"><span data-stu-id="b9557-312">Identity : Global</span></span>

<span data-ttu-id="b9557-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="b9557-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="b9557-314">EnableNameRecording: vero</span><span class="sxs-lookup"><span data-stu-id="b9557-314">EnableNameRecording : True</span></span>

<span data-ttu-id="b9557-315">EntryExitAnnouncementsEnabledByDefault: false</span><span class="sxs-lookup"><span data-stu-id="b9557-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="b9557-316">Se EntryExitAnnouncementsEnabledByDefault è impostato su false, significa che gli annunci di conferenza sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="b9557-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="b9557-317">Per abilitare gli annunci di entrata e di uscita, eseguire un comando di Windows PowerShell simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b9557-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9557-318">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9557-318">See Also</span></span>


[<span data-ttu-id="b9557-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="b9557-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="b9557-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9557-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="b9557-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b9557-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="b9557-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9557-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="b9557-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="b9557-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="b9557-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9557-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="b9557-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9557-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="b9557-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9557-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="b9557-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="b9557-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="b9557-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="b9557-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="b9557-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9557-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

