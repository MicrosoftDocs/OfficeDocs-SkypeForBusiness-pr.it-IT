---
title: 'Lync Server 2013: distribuzione di Lync Web App'
description: 'Lync Server 2013: distribuzione di Lync Web App.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce6fef02781afbd5bc5f315ce24bfb3bdb16df1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560422"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="b0a7e-103">Distribuzione di Lync Web App in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0a7e-103">Deploying Lync Web App in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0a7e-104">_**Ultimo argomento modificato:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="b0a7e-104">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="b0a7e-105">Lync Web App è un client Web di Internet Information Services (IIS) che viene installato con Lync Server 2013 ed è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-105">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="b0a7e-106">Non è necessario eseguire ulteriori passaggi per abilitare Lync Web App nel server o distribuire il client Web agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-106">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="b0a7e-107">Ogni volta che un utente fa clic su un URL di riunione ma non è installato il client Lync 2013, all'utente viene presentata la possibilità di partecipare alla riunione utilizzando la versione più recente di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-107">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="b0a7e-108">Le funzionalità vocali, video e di condivisione in Lync Web App richiedono un controllo ActiveX Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-108">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="b0a7e-109">È possibile installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, ovvero la prima volta che si utilizza Lync Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="b0a7e-110">Nelle distribuzioni di Lync Server 2013 Edge Server, è necessario un proxy inverso HTTPS nella rete perimetrale per l'accesso client di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-110">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="b0a7e-111">È inoltre necessario pubblicare gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-111">You must also publish simple URLs.</span></span> <span data-ttu-id="b0a7e-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync server 2013</A> e <A href="lync-server-2013-planning-for-simple-urls.md">Planning for Simple URLs in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-112">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="b0a7e-113">Abilitazione dell'autenticazione a più fattori per Lync Web App</span><span class="sxs-lookup"><span data-stu-id="b0a7e-113">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="b0a7e-114">La versione Lync Server 2013 di Lync Web App supporta l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-114">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="b0a7e-115">Oltre a nome utente e password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti che si congiungono da reti esterne quando eseguono l'accesso alle riunioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-115">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="b0a7e-116">È possibile abilitare l'autenticazione a più fattori mediante la distribuzione del server federativo di Active Directory Federation Services (ADFS) e l'abilitazione dell'autenticazione passiva in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-116">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="b0a7e-117">Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare alle riunioni di Lync sono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene il nome utente e la sfida per la password insieme ai metodi di autenticazione aggiuntivi che sono stati configurati.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-117">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b0a7e-118">Se si intende configurare ADFS per l'autenticazione a più fattori, è importante considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b0a7e-118">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b0a7e-119">L'autenticazione di ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione sono entrambi presenti nella stessa organizzazione o sono entrambi provenienti da un'organizzazione federata ADFS.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-119">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="b0a7e-120">L'autenticazione ad ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non lo supporta.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-120">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="b0a7e-121">Se si utilizzano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie sui bilanciamento del carico in modo che tutte le richieste provenienti dal client Lync Web App siano gestite dallo stesso front end server.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-121">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="b0a7e-122">Quando si stabilisce una relazione di trust relying party tra Lync Server e i server AD FS, assegnare una durata del token sufficiente a coprire la lunghezza massima delle riunioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-122">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="b0a7e-123">240 minuti in genere sono una durata sufficiente per i token.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-123">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="b0a7e-124">Questa configurazione non è valida per i client mobili di Lync.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-124">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="b0a7e-125">**Per configurare l'autenticazione a più fattori**</span><span class="sxs-lookup"><span data-stu-id="b0a7e-125">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="b0a7e-126">Installare un ruolo del server federativo ADFS.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-126">Install an AD FS federation server role.</span></span> <span data-ttu-id="b0a7e-127">Per informazioni dettagliate, vedere la guida alla distribuzione di Active Directory Federation Services 2,0 all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="b0a7e-127">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="b0a7e-128">Creare certificati per ADFS.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-128">Create certificates for AD FS.</span></span> <span data-ttu-id="b0a7e-129">Per ulteriori informazioni, vedere la sezione relativa ai certificati del server federativo del piano per la distribuzione di ADFS per l'utilizzo con l'argomento Single Sign-on all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="b0a7e-129">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="b0a7e-130">Dall'interfaccia della riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0a7e-130">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="b0a7e-131">Stabilire una relazione eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b0a7e-131">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="b0a7e-132">Impostare le regole di relying party seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0a7e-132">Set the following relying party rules:</span></span>
    
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

## <a name="branchcache-configuration"></a><span data-ttu-id="b0a7e-133">Configurazione di BranchCache</span><span class="sxs-lookup"><span data-stu-id="b0a7e-133">BranchCache Configuration</span></span>

<span data-ttu-id="b0a7e-134">La funzionalità BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con i componenti Web di Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-134">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="b0a7e-135">Per evitare problemi per gli utenti di Lync Web App, verificare che BranchCache non sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-135">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="b0a7e-136">Per informazioni dettagliate sulla disabilitazione di BranchCache, vedere la guida alla distribuzione di BranchCache, disponibile in formato Word nell'area download Microsoft all'interno [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) e in formato HTML nella raccolta tecnica di Windows Server 2008 R2 all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) .</span><span class="sxs-lookup"><span data-stu-id="b0a7e-136">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="b0a7e-137">Verifica della distribuzione di Lync Web App</span><span class="sxs-lookup"><span data-stu-id="b0a7e-137">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="b0a7e-138">È possibile utilizzare il cmdlet Test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza tramite UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="b0a7e-138">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b0a7e-139">Per informazioni dettagliate su questo cmdlet, vedere [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-139">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="b0a7e-140">Risoluzione dei problemi relativi all'installazione del plug-in in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b0a7e-140">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="b0a7e-141">Se l'installazione del plug-in ha esito negativo su un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del registro di sistema DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-141">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="b0a7e-142">**Per modificare l'impostazione di sicurezza in Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="b0a7e-142">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="b0a7e-143">Aprire Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-143">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="b0a7e-144">Fare clic su **Strumenti**, su **Opzioni Internet** e quindi su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-144">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="b0a7e-145">Scorrere verso il basso fino alla sezione **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-145">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="b0a7e-146">Deselezionare **Non salvare pagine crittografate su disco** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-146">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b0a7e-147">Se si seleziona questa opzione, si verificherà un errore anche quando si tenta di scaricare un allegato da Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-147">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="b0a7e-148">Tornare a partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-148">Rejoin the meeting.</span></span> <span data-ttu-id="b0a7e-149">Il download del plug-in dovrebbe avere luogo senza errori.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-149">The plug-in should download without errors.</span></span>

<span data-ttu-id="b0a7e-150">**Per modificare l'impostazione DisableMSI del Registro di sistema**</span><span class="sxs-lookup"><span data-stu-id="b0a7e-150">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="b0a7e-151">Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-151">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="b0a7e-152">Per accedere all'editor del Registro di sistema, digitare **regedit**.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-152">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="b0a7e-153">Accedere a \_ criteri software del computer locale di HKEY \_ \\ \\ \\ Microsoft \\ Windows \\ Installer.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-153">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="b0a7e-154">Modificare o aggiungere la chiave del registro di sistema DisableMSI di tipo REG \_ DWORD e impostarla su 0.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-154">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="b0a7e-155">Tornare a partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="b0a7e-155">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0a7e-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0a7e-156">See Also</span></span>


[<span data-ttu-id="b0a7e-157">Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0a7e-157">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="b0a7e-158">Lync Web App piattaforme supportate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0a7e-158">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

