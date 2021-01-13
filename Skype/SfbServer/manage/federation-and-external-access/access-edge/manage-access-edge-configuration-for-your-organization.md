---
title: Gestire la configurazione Access Edge per l'organizzazione
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso di dominio esterno o di provider, accesso utente remoto e accesso degli utenti anonimi alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817336"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="1d64b-103">Gestire la configurazione Access Edge per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1d64b-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="1d64b-104">Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso di dominio esterno o di provider, accesso utente remoto e accesso degli utenti anonimi alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d64b-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="1d64b-105">Queste opzioni includono i tipi seguenti di accesso, che possono essere configurati nella pagina **Configurazione Access Edge**:</span><span class="sxs-lookup"><span data-stu-id="1d64b-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="1d64b-106">**Abilitare la Federazione e la connettività per la messaggistica istantanea pubblica**   Abilitare questa operazione se si desidera supportare l'accesso degli utenti ai domini partner federati.</span><span class="sxs-lookup"><span data-stu-id="1d64b-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="1d64b-107">Questa impostazione si applica alla federazione SIP configurata per gli ambiti globali, del sito o degli utenti nella pagina **criteri di accesso esterno** .</span><span class="sxs-lookup"><span data-stu-id="1d64b-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="1d64b-108">Per applicare le impostazioni di federazione, è necessario configurare il supporto federativo in entrambe le pagine.</span><span class="sxs-lookup"><span data-stu-id="1d64b-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="1d64b-109">Esistono due opzioni che sono impostazioni facoltative per la modalità di scoperta dei partner federati e se le dichiarazioni di non responsabilità per l'archiviazione (notifica ai contatti federati che comunicano con il fatto che la distribuzione ha l'archiviazione abilitata e che verranno archiviati i dettagli della comunicazione) verranno inviate ai contatti:</span><span class="sxs-lookup"><span data-stu-id="1d64b-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="1d64b-110">**Abilitare l'individuazione del dominio del partner**   Selezionando questa opzione, viene abilitata l'individuazione automatica dei domini che è possibile federare con.</span><span class="sxs-lookup"><span data-stu-id="1d64b-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="1d64b-111">Skype for Business Server utilizza i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso proveniente da partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="1d64b-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="1d64b-112">Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="1d64b-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="1d64b-113">Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato.</span><span class="sxs-lookup"><span data-stu-id="1d64b-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="1d64b-114">Per ulteriori informazioni, vedere [configurare il supporto per i domini esterni consentiti](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="1d64b-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="1d64b-115">**Inviare la dichiarazione di non responsabilità per l'archiviazione ai partner federati**   Selezionando questa opzione, viene abilitato l'invio di un messaggio di dichiarazione di non responsabilità per l'archiviazione ai partner federati che consigliano che vengano registrati i dettagli della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="1d64b-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="1d64b-116">Se si archiviano comunicazioni esterne con domini partner federati, è consigliabile abilitare la dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i dettagli relativi a messaggi e comunicazioni vengono archiviati dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1d64b-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="1d64b-117">Per informazioni dettagliate sull'archiviazione, vedere [Abilitazione o disabilitazione dell'invio di una dichiarazione di non responsabilità per l'archiviazione a un partner federato](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="1d64b-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="1d64b-118">**Abilitare l'accesso degli utenti remoti**   Abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, siano in grado di connettersi a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1d64b-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="1d64b-119">Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1d64b-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="1d64b-120">**Abilitazione degli utenti anonimi all'accesso alle conferenze**   Abilitare questa opzione se si desidera che gli utenti interni invitino gli utenti anonimi esterni alle conferenze organizzate.</span><span class="sxs-lookup"><span data-stu-id="1d64b-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="1d64b-121">L'abilitazione di questa impostazione consente solo agli utenti anonimi per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="1d64b-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="1d64b-122">Oltre ad abilitare il supporto per l'accesso utenti esterni, è necessario configurare anche criteri per controllare l'uso dell'accesso remoto utenti nell'organizzazione, prima che qualsiasi tipo di accesso utente esterno venga reso disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1d64b-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="1d64b-123">Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere [gestire i criteri di accesso esterno per l'organizzazione](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="1d64b-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="1d64b-124">**Visualizzazione delle informazioni sulla configurazione di Access Edge tramite i cmdlet di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1d64b-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="1d64b-125">È possibile visualizzare le informazioni di configurazione di Access Edge utilizzando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1d64b-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="1d64b-126">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d64b-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="1d64b-127">Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1d64b-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="1d64b-128">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d64b-128">That will return information similar to this:</span></span>
    
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

