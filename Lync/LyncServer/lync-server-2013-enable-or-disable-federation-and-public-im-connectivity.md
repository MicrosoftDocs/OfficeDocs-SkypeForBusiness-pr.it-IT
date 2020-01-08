---
title: 'Lync Server 2013: Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="28290-102">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28290-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28290-103">_**Argomento Ultima modifica:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="28290-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="28290-104">Il supporto per la Federazione è necessario per consentire agli utenti che hanno un account con un cliente o un'organizzazione partner attendibile, inclusi i domini partner e gli utenti di utenti del provider di messaggistica istantanea pubblici supportati, di collaborare con gli utenti del proprio organizzazione.</span><span class="sxs-lookup"><span data-stu-id="28290-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="28290-105">Alla Federazione è anche richiesto di usare un provider di servizi di Exchange ospitati per consentire agli utenti di VoIP aziendale le cassette postali si trovano in un servizio di Exchange ospitato, ad esempio Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28290-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="28290-106">Dopo aver stabilito una relazione di trust con questi domini esterni, è possibile autorizzare gli utenti di tali domini ad accedere alla distribuzione e partecipare alle comunicazioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28290-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="28290-107">Questa relazione di trust viene chiamata Federazione e non è correlata o dipendente da una relazione di trust di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28290-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="28290-108">Per supportare l'accesso da parte di utenti di domini federati, è necessario abilitare la Federazione.</span><span class="sxs-lookup"><span data-stu-id="28290-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="28290-109">Se si Abilita la Federazione per l'organizzazione, è necessario specificare anche se implementare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28290-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="28290-110">**Abilitare l'individuazione**   dei domini partner se si abilita questa opzione, Lync Server usa i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso da partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="28290-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="28290-111">Se non si seleziona questa opzione, l'accesso degli utenti federati è abilitato solo per gli utenti nei domini inclusi nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="28290-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="28290-112">Indipendentemente dal fatto che questa opzione sia selezionata, è possibile specificare che i singoli domini vengano bloccati o consentiti, incluso il limitare l'accesso a server specifici che gestiscono il servizio Access Edge nel dominio federato.</span><span class="sxs-lookup"><span data-stu-id="28290-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="28290-113">Per informazioni dettagliate sul controllo dell'accesso da domini federati, vedere [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="28290-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="28290-114">**Inviare una dichiarazione di non responsabilità per l'archiviazione per**     i partner federati l'avviso di non responsabilità viene inviato ai partner federati che l'archiviazione nella distribuzione è a posto.</span><span class="sxs-lookup"><span data-stu-id="28290-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="28290-115">Se si supporta l'archiviazione di comunicazioni esterne con i domini partner federati, è necessario abilitare la notifica di dichiarazione di non responsabilità per l'archiviazione per avvisare i partner che i loro messaggi vengono archiviati.</span><span class="sxs-lookup"><span data-stu-id="28290-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="28290-116">Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso da parte di utenti di domini federati, è possibile disabilitare la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="28290-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="28290-117">Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione, ad esempio specificando le opzioni federative appropriate da supportare per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="28290-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28290-118">L'abilitazione della Federazione per l'organizzazione specifica solo che i server che utilizzano il servizio Access Edge supportano il routing a domini federati.</span><span class="sxs-lookup"><span data-stu-id="28290-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="28290-119">Gli utenti nei domini federati non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione fino a quando non vengono configurati almeno un criterio per supportare l'accesso degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="28290-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="28290-120">Gli utenti dei provider di servizi di messaggistica istantanea pubblica non possono partecipare a messaggi istantanei o conferenze nell'organizzazione finché non si configura almeno un criterio per supportare la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="28290-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="28290-121">Lync Server non può utilizzare un servizio Exchange ospitato per fornire risposte alle chiamate, Outlook Voice Access (inclusa la segreteria telefonica) o servizi di operatore automatico per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitata finché non si configura un criterio di segreteria telefonica ospitata che fornisce informazioni di routing.</span><span class="sxs-lookup"><span data-stu-id="28290-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="28290-122">Per informazioni dettagliate sulla configurazione dei criteri per la comunicazione con gli utenti di domini federati in altre organizzazioni, vedere <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">gestire i domini federati SIP per l'organizzazione in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="28290-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="28290-123">Inoltre, se si vuole supportare la comunicazione con gli utenti dei provider di servizi di messaggistica istantanea, è necessario configurare i criteri per supportarlo e configurare il supporto per i singoli provider di servizi che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="28290-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="28290-124">Per informazioni dettagliate, vedere <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">gestire i provider federati SIP per l'organizzazione in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="28290-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="28290-125">Per informazioni dettagliate sulla creazione di criteri per la segreteria telefonica ospitata, vedere gestire i criteri di segreteria <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="28290-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="28290-126">Per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="28290-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="28290-127">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="28290-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="28290-128">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28290-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28290-129">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28290-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="28290-130">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="28290-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="28290-131">Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="28290-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="28290-132">In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28290-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="28290-133">Per abilitare l'accesso degli utenti federati per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .</span><span class="sxs-lookup"><span data-stu-id="28290-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="28290-134">Per disabilitare l'accesso degli utenti federati per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .</span><span class="sxs-lookup"><span data-stu-id="28290-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="28290-135">Se è stata selezionata la casella **di controllo Abilita comunicazioni con gli utenti federati** , eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28290-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="28290-136">Se si vuole supportare l'individuazione automatica dei domini partner, selezionare la casella di controllo **Abilita individuazione dominio partner** .</span><span class="sxs-lookup"><span data-stu-id="28290-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="28290-137">Se l'organizzazione supporta l'archiviazione di comunicazioni esterne, selezionare la casella **di controllo Invia Disclaimer per l'archiviazione ai partner federati** .</span><span class="sxs-lookup"><span data-stu-id="28290-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="28290-138">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="28290-138">Click **Commit**.</span></span>

<span data-ttu-id="28290-139">Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Lync Server 2013, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="28290-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="28290-140">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="28290-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="28290-141">Per controllare l'accesso per specifici domini federati, vedere [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) nella documentazione relativa alle operazioni o alla documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="28290-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="28290-142">Abilitare o disabilitare la connettività per la messaggistica istantanea e la Federazione usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28290-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="28290-143">La connettività di messaggistica istantanea pubblica e della Federazione può essere gestita anche tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="28290-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="28290-144">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28290-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="28290-145">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="28290-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="28290-146">Per abilitare la connettività per la messaggistica istantanea pubblica e la Federazione</span><span class="sxs-lookup"><span data-stu-id="28290-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="28290-147">Per abilitare la connettività per la messaggistica istantanea pubblica e la Federazione, imposta il valore della proprietà **AllowFederatedUsers** su True ($true):</span><span class="sxs-lookup"><span data-stu-id="28290-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="28290-148">Per disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione</span><span class="sxs-lookup"><span data-stu-id="28290-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="28290-149">Per disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione, imposta il valore della proprietà **AllowFederatedUsers** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="28290-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

