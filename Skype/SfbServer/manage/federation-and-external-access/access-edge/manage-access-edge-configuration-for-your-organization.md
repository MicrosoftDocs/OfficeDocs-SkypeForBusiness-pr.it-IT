---
title: Gestire la configurazione Access Edge per l'organizzazione
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno al dominio o al provider, l'accesso remoto agli utenti e l'accesso degli utenti anonimi alle conferenze tramite gli Edge Server che verranno supportati per l'organizzazione.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818347"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="0e580-103">Gestire la configurazione Access Edge per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0e580-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="0e580-104">Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno al dominio o al provider, l'accesso remoto agli utenti e l'accesso degli utenti anonimi alle conferenze tramite gli Edge Server che verranno supportati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0e580-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="0e580-105">Queste opzioni includono i seguenti tipi di Access che possono essere configurati tramite la pagina di **configurazione di Access Edge** :</span><span class="sxs-lookup"><span data-stu-id="0e580-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="0e580-106">**Abilitazione della Federazione e della connettività**   per messaggistica istantanea pubblica abilitare questa operazione se si vuole supportare l'accesso degli utenti ai domini partner federati.</span><span class="sxs-lookup"><span data-stu-id="0e580-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="0e580-107">Questa impostazione si applica alla federazione SIP configurata per gli ambiti globali, del sito o degli utenti nella pagina dei **criteri di accesso esterno** .</span><span class="sxs-lookup"><span data-stu-id="0e580-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="0e580-108">Per applicare le impostazioni federative, è necessario configurare il supporto federativo in entrambe le pagine.</span><span class="sxs-lookup"><span data-stu-id="0e580-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="0e580-109">Esistono due opzioni che sono impostazioni facoltative per il modo in cui vengono individuati i partner federati e se l'archiviazione delle dichiarazioni di non conformità (notifica ai contatti federati con cui si comunica che la distribuzione ha l'archiviazione abilitata e che le comunicazioni i dettagli verranno archiviati) verranno inviati ai contatti:</span><span class="sxs-lookup"><span data-stu-id="0e580-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="0e580-110">**Abilitare l'individuazione**   di un dominio partner selezionando questa opzione è possibile individuare automaticamente i domini con cui si può usare la Federazione.</span><span class="sxs-lookup"><span data-stu-id="0e580-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="0e580-111">Skype for Business Server usa i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in entrata da partner federati individuati e limitando o bloccando il traffico basato sull'attendibilità livello, quantità di traffico e impostazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0e580-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="0e580-112">Se non si seleziona questa opzione, l'accesso degli utenti federati è abilitato solo per gli utenti nei domini inclusi nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="0e580-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="0e580-113">Indipendentemente dal fatto che questa opzione sia selezionata, è possibile specificare che i singoli domini vengano bloccati o consentiti, incluso il limitare l'accesso a server specifici che gestiscono il servizio Access Edge nel dominio federato.</span><span class="sxs-lookup"><span data-stu-id="0e580-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="0e580-114">Per informazioni dettagliate, vedere [configurare il supporto per i domini esterni consentiti](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="0e580-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="0e580-115">**Inviare una dichiarazione di non responsabilità per i partner**   federati selezionare questa opzione consente l'invio di un messaggio di dichiarazione di non responsabilità per i partner federati che consigliano di registrare i dettagli delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="0e580-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="0e580-116">Se si archiviano comunicazioni esterne con domini partner federati, è necessario abilitare la notifica di dichiarazione di non responsabilità per l'archiviazione per avvisare i partner che i messaggi e i dettagli delle comunicazioni vengono archiviati dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0e580-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="0e580-117">Per informazioni dettagliate sull'archiviazione, vedere [abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="0e580-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="0e580-118">**Abilitare l'accesso**   degli utenti remoti per abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, possano connettersi a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e580-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="0e580-119">Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0e580-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="0e580-120">**Consentire agli utenti anonimi di accedere alle conferenze**   abilitare questa opzione se si vuole che gli utenti interni invitino utenti anonimi esterni alle conferenze organizzate.</span><span class="sxs-lookup"><span data-stu-id="0e580-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="0e580-121">L'abilitazione di questa impostazione consente solo agli utenti anonimi di conferenze.</span><span class="sxs-lookup"><span data-stu-id="0e580-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="0e580-122">Oltre a consentire il supporto degli accessi esterni agli utenti, è anche possibile configurare i criteri per controllare l'uso dell'accesso degli utenti remoti nell'organizzazione prima che l'utente sia disponibile per qualsiasi tipo di accesso da utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="0e580-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="0e580-123">Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere [gestire i criteri di accesso esterno per l'organizzazione](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="0e580-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="0e580-124">**Visualizzazione delle informazioni di configurazione di Access Edge tramite i cmdlet di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0e580-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="0e580-125">Le informazioni sulla configurazione di Access Edge possono essere visualizzate usando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0e580-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="0e580-126">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e580-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="0e580-127">Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="0e580-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="0e580-128">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0e580-128">That will return information similar to this:</span></span>
    
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

