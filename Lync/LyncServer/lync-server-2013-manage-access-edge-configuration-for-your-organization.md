---
title: "Lync Server 2013: gestire la configurazione di Access Edge per l'organizzazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a2c8758caf6b913dd7b8a98fb699f7da148a8f6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="8aa3f-102">Gestire la configurazione di Access Edge per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa3f-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aa3f-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8aa3f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8aa3f-104">Si tratta di una documentazione preliminare e soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="8aa3f-105">Gli argomenti vuoti sono inclusi come segnaposto.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="8aa3f-106">Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso di dominio esterno o di provider, accesso utente remoto e accesso degli utenti anonimi alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="8aa3f-107">Queste opzioni includono i tipi seguenti di accesso, che possono essere configurati nella pagina **Configurazione Access Edge**:</span><span class="sxs-lookup"><span data-stu-id="8aa3f-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="8aa3f-108">**Abilitare la Federazione e la connettività**   per la messaggistica istantanea pubblica abilitarla se si desidera supportare l'accesso degli utenti ai domini partner federati.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="8aa3f-109">Questa impostazione si applica sia alla federazione SIP che alla Federazione XMPP configurati per gli ambiti globali, dei siti o degli utenti nella pagina **criteri di accesso esterno** .</span><span class="sxs-lookup"><span data-stu-id="8aa3f-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="8aa3f-110">Per applicare le impostazioni di federazione, è necessario configurare il supporto federativo in entrambe le pagine.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="8aa3f-111">Esistono due opzioni che costituiscono impostazioni facoltative relative al modo in cui i partner federati vengono individuati e indicano se ai contatti verranno inviate le dichiarazioni di non responsabilità di archiviazione, ovvero notifiche che informano i contatti federati con cui si comunica che l’archiviazione è abilitata nella distribuzione e che i dettagli delle comunicazioni verranno archiviati.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="8aa3f-112">**Attiva individuazione**   dominio partner selezionando questa opzione, viene abilitata l'individuazione automatica dei domini che è possibile federare con.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="8aa3f-113">Lync Server 2013 utilizza i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso proveniente da partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità. quantità di traffico e impostazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="8aa3f-114">Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="8aa3f-115">Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="8aa3f-116">Per ulteriori informazioni, vedere [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="8aa3f-117">**Invia dichiarazione di non responsabilità per i partner**   federati selezionando questa opzione, viene abilitato l'invio di un messaggio di dichiarazione di non responsabilità per l'archiviazione ai partner federati che consigliano che vengano registrati i dettagli della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="8aa3f-118">Se si archiviano comunicazioni esterne con domini partner federati, è consigliabile abilitare la dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i dettagli relativi a messaggi e comunicazioni vengono archiviati dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="8aa3f-119">Per informazioni dettagliate sull'archiviazione, vedere [definizione dei requisiti per l'archiviazione in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="8aa3f-120">**Abilitare l'accesso**   degli utenti remoti abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio telecommuter e utenti che viaggiano, siano in grado di connettersi a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="8aa3f-121">Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="8aa3f-122">**Consenti agli utenti anonimi di accedere alle conferenze**   abilitare questa opzione se si desidera che gli utenti interni invitino gli utenti anonimi esterni alle conferenze organizzate.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="8aa3f-123">L'abilitazione di questa impostazione consente solo agli utenti anonimi per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="8aa3f-124">Per configurare l'esperienza di conferenza e le opzioni che definiscono come e cosa gli utenti possono fare con le conferenze e per l'inclusione di utenti anonimi, vedere informazioni dettagliate su [Create or modify Conferencing user experience for a site or users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing Policy Settings Reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8aa3f-125">Oltre ad abilitare il supporto per l'accesso utenti esterni, è necessario configurare anche criteri per controllare l'uso dell'accesso remoto utenti nell'organizzazione, prima che qualsiasi tipo di accesso utente esterno venga reso disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="8aa3f-126">Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestire i criteri di accesso esterno in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8aa3f-127">**Visualizzazione delle informazioni sulla configurazione di Access Edge tramite i cmdlet di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8aa3f-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="8aa3f-128">È possibile visualizzare le informazioni di configurazione di Access Edge utilizzando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8aa3f-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="8aa3f-129">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8aa3f-130">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="8aa3f-131">Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="8aa3f-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="8aa3f-132">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="8aa3f-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="8aa3f-133">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="8aa3f-133">In This Section</span></span>

  - [<span data-ttu-id="8aa3f-134">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa3f-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="8aa3f-135">Abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa3f-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="8aa3f-136">Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa3f-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="8aa3f-137">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa3f-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="8aa3f-138">Abilitazione o disabilitazione dell'accesso degli utenti anonimi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa3f-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="8aa3f-139">Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa3f-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

