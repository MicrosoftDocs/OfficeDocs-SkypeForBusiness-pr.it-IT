---
title: Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server
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
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="fbe2d-102">Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbe2d-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbe2d-103">_**Argomento Ultima modifica:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="fbe2d-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="fbe2d-104">Il processo di provisioning per la connettività Lync-Skype è stato modificato rispetto ai metodi di provisioning di PIC precedenti.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="fbe2d-105">Questo processo di provisioning può richiedere fino a 30 giorni per il completamento.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="fbe2d-106">Prima di completare i passaggi rimanenti di questo documento, è consigliabile iniziare prima questo processo.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="fbe2d-107">Dopo aver completato il processo di provisioning Lync-Skype per l'account, l'account viene attivato e gli utenti idonei sono abilitati per la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="fbe2d-108">Per eseguire il provisioning della connettività di Lync-Skype, sono necessarie le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbe2d-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="fbe2d-109">Numero di contratto Microsoft</span><span class="sxs-lookup"><span data-stu-id="fbe2d-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-110">Nome di dominio completo (FQDN) di Access Edge Services</span><span class="sxs-lookup"><span data-stu-id="fbe2d-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-111">Domini SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="fbe2d-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-112">Altri FQDN dei servizi di Access Edge aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="fbe2d-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-113">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="fbe2d-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fbe2d-114">A partire da aprile 2019, si fermerà la raccolta e la conservazione delle informazioni di contatto per i clienti che hanno effettuato il provisioning per la Federazione Skype tramite il sito Web pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="fbe2d-115">Questa modifica viene eseguita per garantire che il sistema di provisioning di pic.lync.com aderisca ai criteri di privacy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="fbe2d-116">Al termine della modifica, non sarà più possibile inviare aggiornamenti tramite posta elettronica in sospeso.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="fbe2d-117">Le modifiche al provisioning di PIC vengono in genere completate entro 24-48 ore dopo l'immissione.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="fbe2d-118">Se si verificano ancora problemi con la Federazione di Skype 48 ore dopo l'invio di una richiesta di provisioning, contattare il supporto tecnico Microsoft per approfondire ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbe2d-119">Come parte di questa modifica, tutte le informazioni di contatto inserite in precedenza verranno eliminate dal sistema entro la fine di aprile 2019.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="fbe2d-120">Per avviare il processo di provisioning per Lync-connettività Skype:</span><span class="sxs-lookup"><span data-stu-id="fbe2d-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="fbe2d-121">Accedi al sito Web <strong>https://pic.lync.com</strong>, usando il tuo Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-122">Selezionare il tipo di contratto Microsoft Licensing.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-123">Selezionare la casella di controllo per verificare di aver letto e accettato i diritti di utilizzo del prodotto per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-124">Nella pagina <strong>Avvia una richiesta di provisioning</strong> fare clic sul collegamento appropriato per avviare una richiesta di provisioning:</span><span class="sxs-lookup"><span data-stu-id="fbe2d-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="fbe2d-125">Nella pagina <strong>specifica informazioni di provisioning</strong> immettere l' <strong>FQDN del servizio Edge di Access</strong>.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="fbe2d-126">Ad esempio, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="fbe2d-127">Dopo il 1 ° luglio 2017 Microsoft richiederà inoltre ai clienti che il record SRV DNS federativo distribuito per la connettività di messaggistica istantanea pubblica continui a funzionare.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="fbe2d-128">Immettere almeno uno o più nomi di dominio SIP e quindi fare clic su <strong>Aggiungi</strong>.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="fbe2d-129">Per completare il processo di provisioning è necessario almeno un server Edge di Access e un dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="fbe2d-130">Il dominio SIP e l'Access Edge Server devono essere attivi, funzionanti e raggiungibili in rete.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="fbe2d-131">Nell'elenco dei <strong>provider di servizi di messaggistica istantanea pubblici</strong>selezionare <strong>Skype</strong> e fare clic su <strong>Avanti</strong> per aggiungere le informazioni di contatto e inviare la richiesta di provisioning.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fbe2d-132">Dopo l'invio della richiesta di provisioning, possono essere necessarie fino a 30 giorni per l'attivazione dell'account e consentire agli utenti di essere abilitati per la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="fbe2d-133">Abilitazione della Federazione e della connettività per messaggistica istantanea pubblica (PIC)</span><span class="sxs-lookup"><span data-stu-id="fbe2d-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="fbe2d-134">Dopo aver inviato la richiesta di provisioning, è possibile concentrarsi sull'ambiente Lync Server e sulle attività amministrative necessarie per configurare la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="fbe2d-135">In questa sezione Supponiamo che l'amministratore di Lync Server abbia distribuito Lync Server e abbia configurato l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="fbe2d-136">Per altre informazioni sulla configurazione dell'accesso esterno per Lync Server, vedere "pianificazione per l'accesso degli utenti [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) esterni" all'indirizzo e "distribuzione di [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)accessi esterni agli utenti".</span><span class="sxs-lookup"><span data-stu-id="fbe2d-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="fbe2d-137">Per preparare l'ambiente Lync Server per la connettività Lync-Skype, l'amministratore di Lync Server deve completare le tre attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbe2d-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="fbe2d-138">1 \.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-138">1\.</span></span> <span data-ttu-id="fbe2d-139">Configurare la Federazione e PIC</span><span class="sxs-lookup"><span data-stu-id="fbe2d-139">Configure Federation and PIC</span></span>

<span data-ttu-id="fbe2d-140">La Federazione è necessaria per consentire agli utenti Skype di comunicare con gli utenti di Lync dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="fbe2d-141">La connettività di messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Lync di comunicare con gli utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="fbe2d-142">La Federazione e il PIC vengono configurati tramite il pannello di controllo di Lync Server, illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="fbe2d-143">La Federazione PIC non è più supportata da Live Communication Server 2005 SP1 o da Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="fbe2d-144">Le piattaforme supportate per la Federazione PIC includono Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="fbe2d-145">2 \.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-145">2\.</span></span> <span data-ttu-id="fbe2d-146">Configurare almeno un criterio per supportare l'accesso degli utenti federati</span><span class="sxs-lookup"><span data-stu-id="fbe2d-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="fbe2d-147">Usando il pannello di controllo di Lync Server, un amministratore deve configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti Skype possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="fbe2d-148">3 \.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-148">3\.</span></span> <span data-ttu-id="fbe2d-149">Configurare l'impostazione del provider di Skype PIC per Lync</span><span class="sxs-lookup"><span data-stu-id="fbe2d-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="fbe2d-150">Usando Lync Server Management Shell, un amministratore deve configurare i criteri client di Lync per visualizzare Skype come provider di PIC aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fbe2d-151">Gli utenti dei provider di servizi di messaggistica istantanea pubblica (PIC) non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione finché non si configura almeno un criterio (passaggio 2, in precedenza in questa procedura) per supportare la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="fbe2d-152">Per configurare la Federazione e il PIC, vedere "abilitare o disabilitare la Federazione e la connettività <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>per la messaggistica istantanea pubblica".</span><span class="sxs-lookup"><span data-stu-id="fbe2d-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="fbe2d-153">Per configurare almeno un criterio per il supporto dell'accesso degli utenti federati, vedere "configurare i criteri per controllare l'accesso <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>degli utenti pubblici".</span><span class="sxs-lookup"><span data-stu-id="fbe2d-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="fbe2d-154">Da un server front-end di Lync Server aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="fbe2d-155">Eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbe2d-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="fbe2d-156">Se non si dispone già di un provider PIC nell'ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="fbe2d-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="fbe2d-157">Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificarli e instradarli a Skype (il formato di: User (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="fbe2d-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="fbe2d-158">Queste nuove impostazioni consentiranno la formattazione automatica dell'invio dell'utente dell'indirizzo nella finestra di dialogo "Aggiungi contatto Skype" con NameDecorationRoutingDomain (che deve essere impostato su msn.com) se non contiene i domini nel NameDecorationExcludedDomainList ( Attualmente possiamo supportare msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="fbe2d-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="fbe2d-159">Da un client Lync è ora possibile selezionare Skype come provider PIC e aggiungere un client Skype specificando il proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="fbe2d-160">Inoltre, un utente Skype che si è Unito e ha effettuato l'accesso con il proprio account Microsoft può inviare una richiesta di contatto agli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="fbe2d-161">Per altre informazioni sugli account Microsoft, vedere [che cos'è un account Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="fbe2d-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="fbe2d-162">Per altre informazioni sull'aggiunta di client a Lync, vedere [uso della connettività Lync-Skype in Lync Server 2013 come utente finale](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="fbe2d-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="fbe2d-163">Per informazioni dettagliate sulla modifica di provider ospitati, vedere la pagina relativa alla creazione o modifica di [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)provider federati SIP ospitati.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="fbe2d-164">In questo articolo vengono completate le attività amministrative che devono essere eseguite nel server.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="fbe2d-165">È ora configurato per la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="fbe2d-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="fbe2d-166">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbe2d-166">Additional Resources</span></span>

[<span data-ttu-id="fbe2d-167">Uso della connettività Lync-Skype in Lync Server 2013 come utente finale</span><span class="sxs-lookup"><span data-stu-id="fbe2d-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="fbe2d-168">Guida al provisioning della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbe2d-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

