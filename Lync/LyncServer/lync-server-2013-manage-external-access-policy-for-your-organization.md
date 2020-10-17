---
title: "Lync Server 2013: gestione dei criteri di accesso esterno per l'organizzazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46242343d6da54a6ac1123663734645fd4f64a5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525003"
---
# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="80bd1-102">Gestire i criteri di accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bd1-102">Manage external access policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80bd1-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="80bd1-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="80bd1-104">Dopo avere distribuito uno o più server Edge Server, è necessario abilitare i tipi di accesso esterno da supportare per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80bd1-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="80bd1-p101">Per impostazione predefinita, non vi sono criteri configurati per supportare l'accesso utente esterno, inclusi l'accesso utente remoto e federato, anche se il supporto dell'accesso utente esterno è già stato abilitato per l'organizzazione. Per controllare l'uso dell'accesso utente esterno, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Per la creazione e la configurazione sono disponibili gli ambiti di criteri seguenti. Per impostazione predefinita, i criteri globali possono essere creati ma non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="80bd1-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="80bd1-109">**Criteri globali**   I criteri globali vengono creati quando si distribuiscono i server Edge Server.</span><span class="sxs-lookup"><span data-stu-id="80bd1-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="80bd1-110">Per impostazione predefinita, nei criteri globali non vengono abilitate opzioni di accesso per gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="80bd1-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="80bd1-111">Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare i criteri globali in modo da supportare uno o più tipi di opzioni di accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="80bd1-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="80bd1-112">I criteri globali si applicano a tutti gli utenti dell'organizzazione, ma i criteri sito e i criteri utente sostituiscono i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="80bd1-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="80bd1-113">Se si eliminano i criteri globali, questi non vengono rimossi,</span><span class="sxs-lookup"><span data-stu-id="80bd1-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="80bd1-114">ma ne vengono ripristinate le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="80bd1-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="80bd1-115">**Criteri sito**   È possibile creare e configurare uno o più criteri sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici.</span><span class="sxs-lookup"><span data-stu-id="80bd1-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="80bd1-116">La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito.</span><span class="sxs-lookup"><span data-stu-id="80bd1-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="80bd1-117">Se ad esempio si abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio sito che disabilita l'accesso degli utenti remoti per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="80bd1-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="80bd1-118">Per impostazione predefinita, un criterio sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione del criterio sito.</span><span class="sxs-lookup"><span data-stu-id="80bd1-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="80bd1-119">**Criteri utente**   È possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="80bd1-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="80bd1-120">La configurazione nel criterio utente ha la priorità sui criteri globale e sito, ma solo per gli utenti specifici a cui viene assegnato il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="80bd1-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="80bd1-121">Se ad esempio si abilita l'accesso degli utenti remoti nei criteri globale e sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare tale criterio utente a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="80bd1-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="80bd1-122">Se si crea un criterio utente, è necessario applicarlo a uno o più utenti per renderlo effettivo.</span><span class="sxs-lookup"><span data-stu-id="80bd1-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80bd1-p105">Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="80bd1-p105">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level. Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="80bd1-126">Queste opzioni includono i tipi di accesso esterno seguenti:</span><span class="sxs-lookup"><span data-stu-id="80bd1-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="80bd1-127">**Abilita comunicazioni con utenti federati**   Abilitare questa opzione se si desidera supportare l'accesso utente ai domini dei partner federati.</span><span class="sxs-lookup"><span data-stu-id="80bd1-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="80bd1-128">Questa impostazione consente di configurare la possibilità per gli utenti di comunicare con altri domini federati SIP, nonché di provider ospitati come Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80bd1-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="80bd1-129">Se si seleziona questa opzione, è possibile selezionare l'opzione che consente la comunicazione con i domini federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="80bd1-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="80bd1-p107">Dopo aver selezionato **Abilita comunicazioni con utenti federati** è possibile selezionare, se si vuole, **Abilita le comunicazioni con gli utenti federati XMPP**. La federazione XMPP è una federazione con organizzazioni che usano il protocollo XMPP (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="80bd1-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80bd1-132">Se si Abilita la Federazione XMPP, è necessario selezionare anche per distribuire la <STRONG>Federazione XMPP</STRONG> nella sezione Configurazione pool di server perimetrali del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="80bd1-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="80bd1-133">La configurazione per la Federazione XMPP distribuisce un proxy XMPP nel server perimetrale e un gateway XMPP nel front end server.</span><span class="sxs-lookup"><span data-stu-id="80bd1-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="80bd1-134">**Abilitare le comunicazioni con gli utenti**     remoti Abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, siano in grado di connettersi a Lync Server tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="80bd1-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="80bd1-135">**Abilitare le comunicazioni con gli utenti pubblici**     Abilitare questa opzione se si desidera che gli utenti interni siano in grado di comunicare con i contatti dei provider di messaggistica istantanea pubblici, ad esempio quelli forniti da Windows Live, Yahoo \! e America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="80bd1-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="80bd1-136">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="80bd1-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="80bd1-137">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="80bd1-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="80bd1-138">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="80bd1-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="80bd1-139">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="80bd1-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="80bd1-140">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="80bd1-140">has been announced.</span></span> <span data-ttu-id="80bd1-141">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="80bd1-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="80bd1-142">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="80bd1-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="80bd1-143">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="80bd1-143">Messenger.</span></span> <span data-ttu-id="80bd1-144">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="80bd1-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="80bd1-145">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="80bd1-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="80bd1-146">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="80bd1-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="80bd1-147">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="80bd1-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="80bd1-148">Oltre ad abilitare il supporto dell'accesso a utenti esterni, è inoltre necessario configurare i criteri per controllare l'uso dell'accesso agli utenti esterni nell'organizzazione prima che sia disponibile qualsiasi tipo di accesso esterno per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="80bd1-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="80bd1-149">Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="80bd1-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="80bd1-150">**Per visualizzare i criteri di accesso esterno usando i cmdlet di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="80bd1-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="80bd1-151">È possibile visualizzare i criteri di accesso esterno utilizzando Lync Server Management Shell e il cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="80bd1-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="80bd1-152">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80bd1-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="80bd1-153">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="80bd1-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="80bd1-154">Per visualizzare informazioni su tutti i criteri di accesso esterno, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="80bd1-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="80bd1-155">Il comando restituisce informazioni simili a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="80bd1-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="80bd1-156">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="80bd1-156">In This Section</span></span>

  - [<span data-ttu-id="80bd1-157">Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bd1-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="80bd1-158">Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bd1-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="80bd1-159">Configurazione di criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bd1-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="80bd1-160">Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bd1-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="80bd1-161">Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bd1-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="80bd1-162">Reimpostazione o eliminazione di criteri di accesso utente esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80bd1-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

