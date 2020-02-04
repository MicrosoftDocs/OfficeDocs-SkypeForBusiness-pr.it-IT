---
title: "Lync Server 2013: Gestire i criteri di accesso esterno per l'organizzazione"
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
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="c59aa-102">Gestire i criteri di accesso esterno per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59aa-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c59aa-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c59aa-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c59aa-104">Dopo aver distribuito uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno che verranno supportati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c59aa-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="c59aa-105">Per impostazione predefinita, non sono configurati criteri per supportare l'accesso degli utenti esterni, incluso l'accesso degli utenti remoti, l'accesso degli utenti federati, anche se è già stato abilitato il supporto per l'accesso degli utenti esterni per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c59aa-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="c59aa-106">Per controllare l'uso dell'accesso degli utenti esterni, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="c59aa-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="c59aa-107">Gli ambiti di criteri seguenti sono disponibili per la creazione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c59aa-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="c59aa-108">Per impostazione predefinita, il criterio globale viene creato, ma non può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="c59aa-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="c59aa-109">**Criteri globali il**   criterio globale viene creato quando si distribuisce un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="c59aa-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="c59aa-110">Per impostazione predefinita, nel criterio globale non sono abilitate le opzioni di accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="c59aa-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="c59aa-111">Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare il criterio globale per supportare uno o più tipi di opzioni di accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="c59aa-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="c59aa-112">Il criterio globale si applica a tutti gli utenti dell'organizzazione, ma i criteri del sito e i criteri degli utenti eseguono l'override del criterio globale.</span><span class="sxs-lookup"><span data-stu-id="c59aa-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="c59aa-113">Se elimini il criterio globale, non lo Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="c59aa-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="c59aa-114">Puoi invece reimpostarla sull'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c59aa-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="c59aa-115">**Criteri sito è**   possibile creare e configurare uno o più criteri del sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici.</span><span class="sxs-lookup"><span data-stu-id="c59aa-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="c59aa-116">La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono.</span><span class="sxs-lookup"><span data-stu-id="c59aa-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="c59aa-117">Ad esempio, se si Abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio per il sito che disabilita l'accesso degli utenti remoti per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="c59aa-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="c59aa-118">Per impostazione predefinita, un criterio del sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione dei criteri del sito.</span><span class="sxs-lookup"><span data-stu-id="c59aa-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="c59aa-119">**Criteri**   per gli utenti è possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="c59aa-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="c59aa-120">La configurazione nel criterio utente sostituisce il criterio globale e del sito, ma solo per gli utenti specifici a cui è assegnato il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="c59aa-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="c59aa-121">Ad esempio, se si Abilita l'accesso degli utenti remoti nei criteri globali e nei criteri del sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare i criteri utente a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="c59aa-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="c59aa-122">Se crei un criterio utente, devi applicarlo a uno o più utenti prima che abbia effetto.</span><span class="sxs-lookup"><span data-stu-id="c59aa-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c59aa-123">Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="c59aa-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c59aa-124">La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="c59aa-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c59aa-125">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c59aa-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="c59aa-126">Queste opzioni includono i tipi di accesso esterno seguenti:</span><span class="sxs-lookup"><span data-stu-id="c59aa-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="c59aa-127">**Abilitare le comunicazioni con gli utenti**   federati abilitare questa operazione se si vuole supportare l'accesso degli utenti ai domini partner federati.</span><span class="sxs-lookup"><span data-stu-id="c59aa-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="c59aa-128">Questa impostazione configura la possibilità per gli utenti di comunicare con altri domini federati SIP, nonché di provider ospitati come Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="c59aa-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="c59aa-129">Se si seleziona questa impostazione, è possibile selezionare l'opzione per consentire la comunicazione con domini federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="c59aa-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="c59aa-130">Come opzione, puoi selezionare **Abilita comunicazioni con partner federativi XMPP** se per la prima volta scegli **Abilita comunicazioni con gli utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="c59aa-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="c59aa-131">La Federazione XMPP è una federazione con organizzazioni che usano il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="c59aa-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c59aa-132">Se abiliti la Federazione XMPP, devi anche selezionare per distribuire la <STRONG>Federazione XMPP</STRONG> nella sezione Configurazione pool di bordi di generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="c59aa-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="c59aa-133">La configurazione della Federazione XMPP distribuisce un proxy XMPP nell'Edge Server e un gateway XMPP nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="c59aa-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="c59aa-134">**Abilitare le comunicazioni con gli utenti**   remoti abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, possano connettersi a Lync Server tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="c59aa-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="c59aa-135">**Abilitare le comunicazioni con gli utenti**   pubblici abilitare questa opzione se si vuole che gli utenti interni possano comunicare con i contatti del provider di messaggistica istantanea pubblici, ad esempio quelli forniti\!da Windows Live, Yahoo e America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="c59aa-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="c59aa-136">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="c59aa-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c59aa-137">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c59aa-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c59aa-138">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="c59aa-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="c59aa-139">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c59aa-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c59aa-140">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="c59aa-140">has been announced.</span></span> <span data-ttu-id="c59aa-141">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c59aa-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c59aa-142">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c59aa-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c59aa-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="c59aa-143">Messenger.</span></span> <span data-ttu-id="c59aa-144">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="c59aa-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c59aa-145">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="c59aa-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c59aa-146">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="c59aa-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c59aa-147">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="c59aa-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="c59aa-148">Oltre ad abilitare il supporto per l'accesso degli utenti esterni, devi anche configurare i criteri per controllare l'uso dell'accesso degli utenti esterni nell'organizzazione prima che qualsiasi tipo di accesso utente esterno sia disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c59aa-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="c59aa-149">Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c59aa-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c59aa-150">**Per visualizzare i criteri di accesso esterno usando i cmdlet di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c59aa-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="c59aa-151">Per visualizzare i criteri di accesso esterno, è possibile usare Lync Server Management Shell e il cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="c59aa-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="c59aa-152">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c59aa-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c59aa-153">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="c59aa-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="c59aa-154">Per visualizzare informazioni su tutti i criteri di accesso esterno, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="c59aa-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="c59aa-155">Questo comando restituisce informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="c59aa-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="c59aa-156">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c59aa-156">In This Section</span></span>

  - [<span data-ttu-id="c59aa-157">Configurare criteri per controllare l'accesso utente federato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59aa-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="c59aa-158">Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59aa-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="c59aa-159">Configurare criteri per controllare l'accesso degli utenti remoti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59aa-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="c59aa-160">Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59aa-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="c59aa-161">Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59aa-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="c59aa-162">Reimpostazione o eliminazione dei criteri di accesso esterno degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59aa-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

