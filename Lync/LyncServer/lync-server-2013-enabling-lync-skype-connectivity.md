---
title: 'Lync Server 2013: Abilitazione della connettività Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d2a71c07e742a3ab5597d4bd2aff77157d675
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="78a54-102">Abilitazione della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78a54-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78a54-103">_**Argomento Ultima modifica:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="78a54-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="78a54-104">Dopo aver inviato la richiesta di provisioning, è possibile concentrarsi sull'ambiente Lync Server e sulle attività amministrative necessarie per configurare la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="78a54-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="78a54-105">In questa sezione Supponiamo che l'amministratore di Lync Server abbia distribuito Lync Server e abbia configurato l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="78a54-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="78a54-106">Per altre informazioni sulla configurazione dell'accesso esterno per Lync Server, vedere [pianificazione per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="78a54-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="78a54-107">Per preparare l'ambiente Lync Server per la connettività Lync-Skype, l'amministratore di Lync Server deve completare le tre attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="78a54-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="78a54-108">1 \.</span><span class="sxs-lookup"><span data-stu-id="78a54-108">1\.</span></span> <span data-ttu-id="78a54-109">Configurare la Federazione e PIC</span><span class="sxs-lookup"><span data-stu-id="78a54-109">Configure Federation and PIC</span></span>

<span data-ttu-id="78a54-110">La Federazione è necessaria per consentire agli utenti Skype di comunicare con gli utenti di Lync dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78a54-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="78a54-111">La connettività di messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Lync di comunicare con gli utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="78a54-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="78a54-112">La Federazione e il PIC vengono configurati tramite il pannello di controllo di Lync Server, illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="78a54-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="78a54-113">![Visualizzazione]di PIC con(images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "pic")</span><span class="sxs-lookup"><span data-stu-id="78a54-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78a54-114">La Federazione PIC non è più supportata da Live Communication Server 2005 SP1 o da Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="78a54-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="78a54-115">Le piattaforme supportate per la Federazione PIC includono Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="78a54-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="78a54-116">2 \.</span><span class="sxs-lookup"><span data-stu-id="78a54-116">2\.</span></span> <span data-ttu-id="78a54-117">Configurare almeno un criterio per supportare l'accesso degli utenti federati</span><span class="sxs-lookup"><span data-stu-id="78a54-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="78a54-118">Usando il pannello di controllo di Lync Server, un amministratore deve configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti Skype possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78a54-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="78a54-119">![](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Criteri") per i criteri</span><span class="sxs-lookup"><span data-stu-id="78a54-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="78a54-120">3 \.</span><span class="sxs-lookup"><span data-stu-id="78a54-120">3\.</span></span> <span data-ttu-id="78a54-121">Configurare l'impostazione del provider di Skype PIC per Lync</span><span class="sxs-lookup"><span data-stu-id="78a54-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="78a54-122">Usando Lync Server Management Shell, un amministratore deve configurare i criteri client di Lync per visualizzare Skype come provider di PIC aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="78a54-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78a54-123">Gli utenti dei provider di servizi di messaggistica istantanea pubblica (PIC) non possono partecipare a conferenze istantanee o audio o video nell'organizzazione finché non si configura anche almeno un criterio (passaggio 2, in precedenza in questa procedura) per supportare la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="78a54-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="78a54-124">Per configurare la Federazione e il PIC, vedere "abilitare o disabilitare la Federazione e la connettività [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)per la messaggistica istantanea pubblica".</span><span class="sxs-lookup"><span data-stu-id="78a54-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="78a54-125">Per configurare almeno un criterio per il supporto dell'accesso degli utenti federati, vedere "configurare i criteri per controllare l'accesso [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)degli utenti pubblici".</span><span class="sxs-lookup"><span data-stu-id="78a54-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="78a54-126">**Per modificare un provider di Messenger o Skype PIC esistente e configurarlo per Skype**</span><span class="sxs-lookup"><span data-stu-id="78a54-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="78a54-127">Da un server front-end di Lync Server aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78a54-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="78a54-128">Eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="78a54-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78a54-129">Se non si dispone già di un provider PIC nell'ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="78a54-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78a54-130">Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificarli e instradarli a Skype (il formato di: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="78a54-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="78a54-131">Queste nuove impostazioni consentiranno la formattazione automatica dell'invio dell'utente dell'indirizzo nella finestra di dialogo "Aggiungi contatto Skype" con NameDecorationRoutingDomain (che deve essere impostato su msn.com) se non contiene i domini nel NameDecorationExcludedDomainList ( Attualmente possiamo supportare msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="78a54-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="78a54-132">Da un client Lync è ora possibile selezionare Skype come provider PIC e aggiungere un client Skype specificando il proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78a54-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="78a54-133">Inoltre, un utente Skype che si è Unito e ha effettuato l'accesso con il proprio account Microsoft può inviare una richiesta di contatto agli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="78a54-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="78a54-134">Per altre informazioni sugli account Microsoft, vedere [che cos'è un account Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="78a54-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="78a54-135">Per altre informazioni sull'aggiunta di client a Lync, vedere [uso della connettività Lync-Skype in Lync Server 2013 come utente finale](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="78a54-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="78a54-136">![Aggiungere]contatto Skype(images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype contact")</span><span class="sxs-lookup"><span data-stu-id="78a54-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="78a54-137">Per informazioni dettagliate sulla modifica di provider ospitati, vedere la pagina relativa alla creazione o modifica di [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)provider federati SIP ospitati.</span><span class="sxs-lookup"><span data-stu-id="78a54-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="78a54-138">In questo articolo vengono completate le attività amministrative che devono essere eseguite nel server.</span><span class="sxs-lookup"><span data-stu-id="78a54-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="78a54-139">È ora configurato per la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="78a54-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

