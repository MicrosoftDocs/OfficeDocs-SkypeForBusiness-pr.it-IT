---
title: 'Lync Server 2013: attivazione della connettività Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e26e54d0704ed009af1ef528e60979b759eb69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528583"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="b8c9a-102">Abilitazione della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8c9a-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8c9a-103">_**Ultimo argomento modificato:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="b8c9a-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="b8c9a-104">Dopo aver inoltrato la richiesta di provisioning, è possibile concentrarsi sull'ambiente Lync Server e sulle attività amministrative necessarie per configurare Lync-Skype la connettività.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="b8c9a-105">In questa sezione si presuppone che l'amministratore di Lync Server abbia distribuito Lync Server e abbia configurato l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="b8c9a-106">Per ulteriori informazioni sulla configurazione dell'accesso esterno per Lync Server, vedere [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b8c9a-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="b8c9a-107">Per preparare l'ambiente Lync Server per la connettività Lync-Skype, è necessario che l'amministratore di Lync Server completi le tre attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8c9a-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="b8c9a-108">1\.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-108">1\.</span></span> <span data-ttu-id="b8c9a-109">Configurazione della Federazione e del PIC</span><span class="sxs-lookup"><span data-stu-id="b8c9a-109">Configure Federation and PIC</span></span>

<span data-ttu-id="b8c9a-110">La Federazione è necessaria per consentire agli utenti di Skype di comunicare con gli utenti di Lync nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="b8c9a-111">La connettività per la messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Lync di comunicare con gli utenti di Skype.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="b8c9a-112">La Federazione e il PIC sono configurati utilizzando il pannello di controllo di Lync Server, mostrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="b8c9a-113">![Visualizzazione PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Visualizzazione PIC")</span><span class="sxs-lookup"><span data-stu-id="b8c9a-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8c9a-114">La Federazione PIC non è più supportata da Live Communication Server 2005 SP1 o da Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="b8c9a-115">Le piattaforme supportate per la Federazione PIC sono Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="b8c9a-116">2\.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-116">2\.</span></span> <span data-ttu-id="b8c9a-117">Configurare almeno un criterio per il supporto dell'accesso utente federato</span><span class="sxs-lookup"><span data-stu-id="b8c9a-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="b8c9a-118">Se si utilizza il pannello di controllo di Lync Server, un amministratore deve configurare uno o più criteri di accesso utente esterno per controllare se gli utenti di Skype possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="b8c9a-119">![Criteri](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Criteri")</span><span class="sxs-lookup"><span data-stu-id="b8c9a-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="b8c9a-120">3\.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-120">3\.</span></span> <span data-ttu-id="b8c9a-121">Configurare l'impostazione di Skype PIC provider per Lync</span><span class="sxs-lookup"><span data-stu-id="b8c9a-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="b8c9a-122">Utilizzando Lync Server Management Shell, un amministratore deve configurare il criterio client di Lync per visualizzare Skype come un ulteriore provider PIC.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8c9a-123">Gli utenti dei provider di servizi di connettività di messaggistica istantanea pubblica non possono partecipare a conferenze di messaggistica istantanea o audio o video nell'organizzazione fino a quando non si configura anche almeno un criterio (passaggio 2, più indietro in questa procedura) per supportare la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="b8c9a-124">Per configurare la Federazione e il PIC, vedere "abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) .</span><span class="sxs-lookup"><span data-stu-id="b8c9a-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="b8c9a-125">Per configurare almeno un criterio per il supporto dell'accesso degli utenti federati, vedere la sezione relativa alla configurazione di criteri per il controllo dell'accesso degli utenti pubblici all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) .</span><span class="sxs-lookup"><span data-stu-id="b8c9a-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="b8c9a-126">**Per modificare un provider di Messenger o Skype PIC esistente e configurarlo per Skype**</span><span class="sxs-lookup"><span data-stu-id="b8c9a-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="b8c9a-127">Da un server front-end di Lync Server, aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="b8c9a-128">Eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8c9a-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8c9a-129">Se non si dispone già di un provider PIC nel proprio ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b8c9a-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8c9a-130">Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificare e instradarli a Skype (il formato di: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="b8c9a-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="b8c9a-131">Queste nuove impostazioni consentiranno la formattazione automatica della finestra di dialogo "Aggiungi contatto Skype" con il NameDecorationRoutingDomain (che dovrebbe essere impostato su msn.com) se non contiene i domini nel NameDecorationExcludedDomainList (attualmente in grado di supportare msn.com, live.com, hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="b8c9a-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="b8c9a-132">Da un client Lync, è ora possibile selezionare Skype come provider PIC e aggiungere un client Skype specificando il proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="b8c9a-133">Inoltre, un utente Skype che ha eseguito l'Unione e l'accesso con il proprio account Microsoft può inviare una richiesta di contatto agli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="b8c9a-134">Per ulteriori informazioni sugli account Microsoft, vedere [che cos'è un account Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="b8c9a-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="b8c9a-135">Per ulteriori informazioni sull'aggiunta di client a Lync, vedere [Using Lync-Skype Connectivity in Lync Server 2013 As an End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="b8c9a-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="b8c9a-136">![Aggiungere contatti Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Aggiungere contatti Skype")</span><span class="sxs-lookup"><span data-stu-id="b8c9a-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="b8c9a-137">Per informazioni dettagliate sulla modifica dei provider ospitati, vedere "creare o modificare provider federati SIP ospitati" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="b8c9a-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="b8c9a-138">Vengono completate le attività amministrative che devono essere eseguite sul server.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="b8c9a-139">Ora è possibile configurare la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="b8c9a-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

