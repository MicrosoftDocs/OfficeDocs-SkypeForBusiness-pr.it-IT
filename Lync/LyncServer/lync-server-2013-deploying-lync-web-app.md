---
title: 'Lync Server 2013: distribuzione di Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c355be1c1709cede9c032d59790d6beefb337ff6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40981843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="c8d93-102">Distribuzione di Lync Web App in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8d93-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8d93-103">_**Argomento Ultima modifica:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="c8d93-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="c8d93-104">Lync Web App è un client Web Internet Information Services (IIS) che viene installato con Lync Server 2013 ed è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c8d93-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="c8d93-105">Non sono necessarie altre procedure per abilitare Lync Web App sul server o distribuire il client Web agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c8d93-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="c8d93-106">Ogni volta che un utente fa clic su un URL di riunione ma non è installato il client Lync 2013, l'utente viene presentato con l'opzione di partecipare alla riunione usando la versione più recente di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c8d93-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="c8d93-107">Le funzionalità vocali, video e di condivisione in Lync Web App richiedono un controllo ActiveX Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8d93-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="c8d93-108">È possibile installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, ovvero la prima volta che usano Lync Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.</span><span class="sxs-lookup"><span data-stu-id="c8d93-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="c8d93-109">Nelle distribuzioni di Lync Server 2013 Edge Server è necessario un proxy inverso HTTPS nella rete perimetrale per l'accesso client Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c8d93-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="c8d93-110">Devi anche pubblicare URL semplici.</span><span class="sxs-lookup"><span data-stu-id="c8d93-110">You must also publish simple URLs.</span></span> <span data-ttu-id="c8d93-111">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configurazione di server proxy inversa per Lync server 2013</A> e <A href="lync-server-2013-planning-for-simple-urls.md">pianificazione di URL semplici in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c8d93-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="c8d93-112">Attivazione dell'autenticazione a più fattori per Lync Web App</span><span class="sxs-lookup"><span data-stu-id="c8d93-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="c8d93-113">La versione Lync Server 2013 di Lync Web App supporta l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="c8d93-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="c8d93-114">Oltre al nome utente e alla password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti che partecipano da reti esterne quando accedono a riunioni Lync.</span><span class="sxs-lookup"><span data-stu-id="c8d93-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="c8d93-115">È possibile abilitare l'autenticazione a più fattori distribuendo il server federativo di Active Directory Federation Service (ADFS) e abilitando l'autenticazione passiva in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d93-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="c8d93-116">Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare a riunioni Lync vengono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene la sfida di nome utente e password, oltre a eventuali altri metodi di autenticazione configurati .</span><span class="sxs-lookup"><span data-stu-id="c8d93-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="c8d93-117">Di seguito sono riportate considerazioni importanti se si prevede di configurare ADFS per l'autenticazione a più fattori:</span><span class="sxs-lookup"><span data-stu-id="c8d93-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c8d93-118">L'autenticazione ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione si trovano nella stessa organizzazione o sono entrambi provenienti da un'organizzazione federata ADFS.</span><span class="sxs-lookup"><span data-stu-id="c8d93-118">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="c8d93-119">L'autenticazione ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non lo supporta.</span><span class="sxs-lookup"><span data-stu-id="c8d93-119">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="c8d93-120">Se si usano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie in bilanciamento del carico in modo che tutte le richieste del client Lync Web App vengano gestite dallo stesso server front-end.</span><span class="sxs-lookup"><span data-stu-id="c8d93-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="c8d93-121">Quando si stabilisce un trust tra i server Lync e i server ADFS, assegnare una durata abbastanza lunga per la durata massima delle riunioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="c8d93-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="c8d93-122">In genere, una durata del token di 240 minuti è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="c8d93-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="c8d93-123">Questa configurazione non si applica ai client di Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="c8d93-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c8d93-124">**Per configurare l'autenticazione a più fattori**</span><span class="sxs-lookup"><span data-stu-id="c8d93-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="c8d93-125">Installare un ruolo del server federativo ADFS.</span><span class="sxs-lookup"><span data-stu-id="c8d93-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="c8d93-126">Per informazioni dettagliate, vedere la guida alla distribuzione di Active Directory Federation Services 2,0 all'indirizzo<http://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="c8d93-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="c8d93-127">Creare certificati per ADFS.</span><span class="sxs-lookup"><span data-stu-id="c8d93-127">Create certificates for AD FS.</span></span> <span data-ttu-id="c8d93-128">Per altre informazioni, vedere la sezione "certificati del server federativo" del piano per e distribuire ADFS per l'uso con l'argomento Single Sign-on [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span><span class="sxs-lookup"><span data-stu-id="c8d93-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="c8d93-129">Dall'interfaccia della riga di comando di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c8d93-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="c8d93-130">Creare una partnership eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c8d93-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="c8d93-131">Impostare le regole del componente seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8d93-131">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="c8d93-132">Configurazione di BranchCache</span><span class="sxs-lookup"><span data-stu-id="c8d93-132">BranchCache Configuration</span></span>

<span data-ttu-id="c8d93-133">La caratteristica BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con i componenti Web di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c8d93-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="c8d93-134">Per evitare problemi per gli utenti di Lync Web App, verificare che BranchCache non sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="c8d93-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="c8d93-135">Per informazioni dettagliate sulla disabilitazione di BranchCache, vedere la guida alla distribuzione di BranchCache, disponibile in formato Word nell'area download Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) in e in formato HTML nella raccolta tecnica di Windows Server 2008 R2 [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span><span class="sxs-lookup"><span data-stu-id="c8d93-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="c8d93-136">Verifica della distribuzione di Lync Web App</span><span class="sxs-lookup"><span data-stu-id="c8d93-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="c8d93-137">Puoi usare il cmdlet test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza usando l'API Web Unified Communications (UCWA).</span><span class="sxs-lookup"><span data-stu-id="c8d93-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="c8d93-138">Per informazioni dettagliate su questo cmdlet, vedere [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8d93-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="c8d93-139">Risoluzione dei problemi di installazione del plug-in in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c8d93-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="c8d93-140">Se l'installazione del plug-in non riesce in un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del registro di sistema DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="c8d93-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="c8d93-141">**Per modificare l'impostazione di sicurezza in Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="c8d93-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="c8d93-142">Aprire Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c8d93-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="c8d93-143">Fare clic su **strumenti**, su **Opzioni Internet**e quindi su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="c8d93-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="c8d93-144">Scorrere verso il basso fino alla sezione **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="c8d93-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="c8d93-145">Deselezionare non **salvare pagine crittografate su disco**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8d93-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="c8d93-146">Se selezionata, questa impostazione causa anche un errore quando si prova a scaricare un allegato da Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c8d93-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="c8d93-147">Partecipare di più alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c8d93-147">Rejoin the meeting.</span></span> <span data-ttu-id="c8d93-148">Il plug-in dovrebbe essere scaricato senza errori.</span><span class="sxs-lookup"><span data-stu-id="c8d93-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="c8d93-149">**Per modificare l'impostazione del registro di sistema DisableMSI**</span><span class="sxs-lookup"><span data-stu-id="c8d93-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="c8d93-150">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c8d93-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="c8d93-151">Per accedere all'editor del registro di sistema, digitare **Regedit**.</span><span class="sxs-lookup"><span data-stu-id="c8d93-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="c8d93-152">Passare alla pagina\_relativa\_ai\\criteri\\\\del software\\locale\\HKEY Microsoft Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="c8d93-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="c8d93-153">Modificare o aggiungere la chiave del registro di sistema DisableMSI\_di tipo reg DWORD e impostarla su 0.</span><span class="sxs-lookup"><span data-stu-id="c8d93-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="c8d93-154">Partecipare di più alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c8d93-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8d93-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8d93-155">See Also</span></span>


[<span data-ttu-id="c8d93-156">Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8d93-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="c8d93-157">Piattaforme supportate di Lync Web App per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8d93-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

