---
title: Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server
description: Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12916b12de1ef3a3f990c6bee54c312ba6c1992
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571132"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="f2c02-103">Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2c02-103">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2c02-104">_**Ultimo argomento modificato:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="f2c02-104">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="f2c02-105">Il processo di provisioning per la connettività Lync-Skype è stato modificato rispetto ai metodi di provisioning dei PIC precedenti.</span><span class="sxs-lookup"><span data-stu-id="f2c02-105">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="f2c02-106">Questo processo di provisioning può richiedere fino a 30 giorni per il completamento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-106">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="f2c02-107">Si consiglia di iniziare il processo prima di completare i passaggi rimanenti del documento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-107">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="f2c02-108">Dopo aver completato il processo di provisioning del Lync-Skype per l'account, l'account viene attivato e gli utenti idonei sono abilitati per la connettività per la messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="f2c02-108">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="f2c02-109">Per eseguire il provisioning della connettività Lync-Skype, sono necessarie le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="f2c02-109">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="f2c02-110">Numero del contratto Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2c02-110">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="f2c02-111">Nome di dominio completo (FQDN) del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="f2c02-111">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="f2c02-112">Domini SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="f2c02-112">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="f2c02-113">Qualsiasi FQDN del servizio Access Edge aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="f2c02-113">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="f2c02-114">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="f2c02-114">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f2c02-115">A partire da aprile 2019, si interromperà la raccolta e la conservazione delle informazioni di contatto per i clienti che sono stati provisionati per la Federazione Skype tramite il sito Web pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f2c02-115">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="f2c02-116">Questa modifica viene apportata per garantire che il sistema di provisioning di pic.lync.com sia conforme ai criteri di privacy di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2c02-116">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="f2c02-117">Una volta che questa modifica è attiva, non sarà più possibile fornire gli aggiornamenti della posta elettronica sulle modifiche di provisioning in sospeso.</span><span class="sxs-lookup"><span data-stu-id="f2c02-117">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="f2c02-118">Le modifiche del provisioning delle PIC vengono in genere completate entro 24-48 ore dopo l'immissione.</span><span class="sxs-lookup"><span data-stu-id="f2c02-118">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="f2c02-119">Se si verificano ancora problemi relativi alla Federazione di Skype 48 ore dopo l'invio di una richiesta di provisioning, contattare il supporto tecnico Microsoft per approfondire ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="f2c02-119">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2c02-120">Come parte di questa modifica, tutte le informazioni di contatto inserite in precedenza verranno eliminate dal sistema entro la fine di aprile 2019.</span><span class="sxs-lookup"><span data-stu-id="f2c02-120">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="f2c02-121">Per avviare il processo di provisioning per la connettività Lync-Skype:</span><span class="sxs-lookup"><span data-stu-id="f2c02-121">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="f2c02-122">Accedere al sito Web <strong>https://pic.lync.com</strong> utilizzando il Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="f2c02-122">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="f2c02-123">Selezionare il tipo di contratto Microsoft Licensing.</span><span class="sxs-lookup"><span data-stu-id="f2c02-123">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="f2c02-124">Selezionare la casella di controllo per verificare che i diritti di utilizzo del prodotto siano stati letti e accettati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2c02-124">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="f2c02-125">Nella pagina <strong>Avvia una richiesta di provisioning</strong> fare clic sul collegamento appropriato per avviare una richiesta di provisioning:</span><span class="sxs-lookup"><span data-stu-id="f2c02-125">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="f2c02-126">Nella pagina <strong>specifica informazioni di provisioning</strong> immettere il <strong>nome di dominio completo del servizio Access Edge</strong>.</span><span class="sxs-lookup"><span data-stu-id="f2c02-126">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="f2c02-127">Ad esempio, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="f2c02-127">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="f2c02-128">Dopo il 1 ° luglio 2017 Microsoft richiederà inoltre ai clienti che il record DNS di Federazione SRV è stato distribuito per la connettività di messaggistica istantanea pubblica per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="f2c02-128">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="f2c02-129">Immettere almeno uno o più nomi di dominio SIP e quindi fare clic su <strong>Aggiungi</strong>.</span><span class="sxs-lookup"><span data-stu-id="f2c02-129">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="f2c02-130">Per completare il processo di provisioning, sono necessari almeno un server perimetrale di accesso e un dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="f2c02-130">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="f2c02-131">Il dominio SIP e il server perimetrale di accesso devono essere attivi, funzionanti e raggiungibili sulla rete.</span><span class="sxs-lookup"><span data-stu-id="f2c02-131">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="f2c02-132">Nell'elenco dei <strong>provider di servizi di messaggistica istantanea pubblica</strong>, selezionare <strong>Skype</strong> e fare clic su <strong>Avanti</strong> per aggiungere le informazioni di contatto e inviare la richiesta di provisioning.</span><span class="sxs-lookup"><span data-stu-id="f2c02-132">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2c02-133">Dopo aver inoltrato la richiesta di provisioning, possono essere necessari fino a 30 giorni affinché l'account venga attivato e gli utenti siano abilitati per la connettività per la messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="f2c02-133">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="f2c02-134">Abilitazione della Federazione e della connettività per la messaggistica istantanea pubblica (PIC)</span><span class="sxs-lookup"><span data-stu-id="f2c02-134">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="f2c02-135">Dopo aver inoltrato la richiesta di provisioning, è possibile concentrarsi sull'ambiente Lync Server e sulle attività amministrative necessarie per configurare Lync-Skype la connettività.</span><span class="sxs-lookup"><span data-stu-id="f2c02-135">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="f2c02-136">In questa sezione si presuppone che l'amministratore di Lync Server abbia distribuito Lync Server e abbia configurato l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f2c02-136">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="f2c02-137">Per ulteriori informazioni sulla configurazione dell'accesso esterno per Lync Server, vedere la sezione relativa alla pianificazione dell'accesso degli utenti esterni in [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) e "Deploying External User Access" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) .</span><span class="sxs-lookup"><span data-stu-id="f2c02-137">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="f2c02-138">Per preparare l'ambiente Lync Server per la connettività Lync-Skype, è necessario che l'amministratore di Lync Server completi le tre attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2c02-138">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="f2c02-139">1\.</span><span class="sxs-lookup"><span data-stu-id="f2c02-139">1\.</span></span> <span data-ttu-id="f2c02-140">Configurazione della Federazione e del PIC</span><span class="sxs-lookup"><span data-stu-id="f2c02-140">Configure Federation and PIC</span></span>

<span data-ttu-id="f2c02-141">La Federazione è necessaria per consentire agli utenti di Skype di comunicare con gli utenti di Lync nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2c02-141">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="f2c02-142">La connettività per la messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Lync di comunicare con gli utenti di Skype.</span><span class="sxs-lookup"><span data-stu-id="f2c02-142">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="f2c02-143">La Federazione e il PIC sono configurati utilizzando il pannello di controllo di Lync Server, mostrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f2c02-143">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f2c02-144">La Federazione PIC non è più supportata da Live Communication Server 2005 SP1 o da Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f2c02-144">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="f2c02-145">Le piattaforme supportate per la Federazione PIC sono Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f2c02-145">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="f2c02-146">2\.</span><span class="sxs-lookup"><span data-stu-id="f2c02-146">2\.</span></span> <span data-ttu-id="f2c02-147">Configurare almeno un criterio per il supporto dell'accesso utente federato</span><span class="sxs-lookup"><span data-stu-id="f2c02-147">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="f2c02-148">Se si utilizza il pannello di controllo di Lync Server, un amministratore deve configurare uno o più criteri di accesso utente esterno per controllare se gli utenti di Skype possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2c02-148">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="f2c02-149">3\.</span><span class="sxs-lookup"><span data-stu-id="f2c02-149">3\.</span></span> <span data-ttu-id="f2c02-150">Configurare l'impostazione di Skype PIC provider per Lync</span><span class="sxs-lookup"><span data-stu-id="f2c02-150">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="f2c02-151">Utilizzando Lync Server Management Shell, un amministratore deve configurare il criterio client di Lync per visualizzare Skype come un ulteriore provider PIC.</span><span class="sxs-lookup"><span data-stu-id="f2c02-151">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f2c02-152">Gli utenti dei provider di servizi di connettività di messaggistica istantanea pubblica non possono partecipare a conferenze o messaggistica istantanea nell'organizzazione fino a quando non si configura anche almeno un criterio (passaggio 2, più indietro in questa procedura) per supportare la connettività per la messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="f2c02-152">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="f2c02-153">Per configurare la Federazione e il PIC, vedere "abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica" all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> .</span><span class="sxs-lookup"><span data-stu-id="f2c02-153">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="f2c02-154">Per configurare almeno un criterio per il supporto dell'accesso degli utenti federati, vedere la sezione relativa alla configurazione di criteri per il controllo dell'accesso degli utenti pubblici all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> .</span><span class="sxs-lookup"><span data-stu-id="f2c02-154">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="f2c02-155">Da un server front-end di Lync Server, aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f2c02-155">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f2c02-156">Eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2c02-156">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="f2c02-157">Se non si dispone già di un provider PIC nel proprio ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f2c02-157">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="f2c02-158">Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificare e instradarli a Skype (il formato di: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="f2c02-158">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="f2c02-159">Queste nuove impostazioni consentiranno la formattazione automatica della finestra di dialogo "Aggiungi contatto Skype" con il NameDecorationRoutingDomain (che dovrebbe essere impostato su msn.com) se non contiene i domini nel NameDecorationExcludedDomainList (attualmente in grado di supportare msn.com, live.com, hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="f2c02-159">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="f2c02-160">Da un client Lync, è ora possibile selezionare Skype come provider PIC e aggiungere un client Skype specificando il proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2c02-160">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="f2c02-161">Inoltre, un utente Skype che ha eseguito l'Unione e l'accesso con il proprio account Microsoft può inviare una richiesta di contatto agli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="f2c02-161">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="f2c02-162">Per ulteriori informazioni sugli account Microsoft, vedere [che cos'è un account Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="f2c02-162">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="f2c02-163">Per ulteriori informazioni sull'aggiunta di client a Lync, vedere [Using Lync-Skype Connectivity in Lync Server 2013 As an End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="f2c02-163">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="f2c02-164">Per informazioni dettagliate sulla modifica dei provider ospitati, vedere "creare o modificare provider federati SIP ospitati" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="f2c02-164">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="f2c02-165">Vengono completate le attività amministrative che devono essere eseguite sul server.</span><span class="sxs-lookup"><span data-stu-id="f2c02-165">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="f2c02-166">Ora è possibile configurare la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="f2c02-166">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="f2c02-167">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f2c02-167">Additional Resources</span></span>

[<span data-ttu-id="f2c02-168">Utilizzo della connettività Lync-Skype in Lync Server 2013 come utente finale</span><span class="sxs-lookup"><span data-stu-id="f2c02-168">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="f2c02-169">Guida al provisioning per la connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2c02-169">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

