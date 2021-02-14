---
title: Distribuire client scaricabili Web in Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: "Riepilogo: distribuire Skype for Business Web App e l'app Riunioni Skype usata con Skype for Business."
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805926"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="33883-103">Distribuire client scaricabili Web in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="33883-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="33883-104">**Riepilogo:** Distribuire l'app Web Skype for Business 2015 e l'app Riunioni Skype usata con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="33883-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="33883-105">Skype for Business Web App è un client Web Internet Information Services (IIS) installato nel server che esegue Skype for Business Server e per impostazione predefinita viene distribuito su richiesta per soddisfare gli utenti che non hanno già il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="33883-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="33883-106">Questi utenti della riunione si connettono più spesso che dall'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="33883-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="33883-107">Ogni volta che un utente fa clic sull'URL di una riunione ma non ha il client Skype for Business installato, all'utente viene presentata l'opzione per partecipare alla riunione utilizzando la versione più recente di Skype for Business Web App, Skype Meetings App o Skype for Business per Mac.</span><span class="sxs-lookup"><span data-stu-id="33883-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="33883-108">Le funzionalità vocali, video e condivisione in Skype for Business Web App richiedono un controllo microsoft ActiveX utilizzato come plug-in dal browser dell'utente.</span><span class="sxs-lookup"><span data-stu-id="33883-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="33883-109">Puoi installare il controllo ActiveX in anticipo o consentire agli utenti di installarlo quando richiesto, cosa che avviene la prima volta che usano Skype for Business Web App o la prima volta che accedono a una funzionalità che richiede il controllo ActiveX.</span><span class="sxs-lookup"><span data-stu-id="33883-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="33883-110">Nelle distribuzioni di server perimetrali di Skype for Business Server, è necessario un proxy inverso HTTPS nella rete perimetrale per l'accesso client di Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="33883-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="33883-111">È inoltre necessario pubblicare gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="33883-111">You must also publish simple URLs.</span></span> <span data-ttu-id="33883-112">Per informazioni dettagliate, [vedere Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and DNS requirements for simple [URLs in Skype for Business Server.](../../plan-your-deployment/network-requirements/simple-urls.md)</span><span class="sxs-lookup"><span data-stu-id="33883-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="33883-113">Abilitare l'autenticazione a più fattori per Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="33883-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="33883-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="33883-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="33883-115">Skype for Business Web App, Skype Meetings App e Skype for Business per Mac supportano l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="33883-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="33883-116">Oltre al nome utente e alla password, è possibile richiedere metodi di autenticazione aggiuntivi, ad esempio smart card o PIN, per autenticare gli utenti che a loro volta aseguono le riunioni di Skype for Business da reti esterne.</span><span class="sxs-lookup"><span data-stu-id="33883-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="33883-117">È possibile abilitare l'autenticazione a più fattori distribuendo il server federativo Active Directory Federation Service (AD FS) e abilitando l'autenticazione passiva in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="33883-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="33883-118">Dopo aver configurato AD FS, gli utenti esterni che tentano di partecipare alle riunioni di Skype for Business vengono presentati con una pagina Web di autenticazione a più fattori di AD FS che contiene la richiesta di verifica del nome utente e della password insieme a eventuali altri metodi di autenticazione configurati.</span><span class="sxs-lookup"><span data-stu-id="33883-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33883-119">Se si intende configurare ADFS per l'autenticazione a più fattori, è importante considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="33883-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="33883-120">L'autenticazione ADFS a più fattori funziona se il partecipante e l'organizzatore della riunione sono entrambi nella stessa organizzazione o sono entrambi di un'organizzazione federata AD FS.</span><span class="sxs-lookup"><span data-stu-id="33883-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="33883-121">L'autenticazione ADFS a più fattori non funziona per gli utenti federati di Lync perché l'infrastruttura Web di Lync Server attualmente non la supporta.</span><span class="sxs-lookup"><span data-stu-id="33883-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="33883-122">Se si utilizzano servizi di bilanciamento del carico hardware, abilitare la persistenza dei cookie nei servizi di bilanciamento del carico in modo che tutte le richieste provenienti dai client dell'app Skype for Business Web App o Meetings siano gestite dallo stesso Front End Server.</span><span class="sxs-lookup"><span data-stu-id="33883-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="33883-123">Quando si stabilisce un trust relying party tra Skype for Business Server e i server AD FS, assegnare una durata token sufficientemente lunga da estendersi alla durata massima delle riunioni skype for business.</span><span class="sxs-lookup"><span data-stu-id="33883-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="33883-124">240 minuti in genere sono una durata sufficiente per i token.</span><span class="sxs-lookup"><span data-stu-id="33883-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="33883-125">Questa configurazione non si applica ai client mobili Lync.</span><span class="sxs-lookup"><span data-stu-id="33883-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="33883-126">Configurare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="33883-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="33883-127">Installare un ruolo del server federativo ADFS.</span><span class="sxs-lookup"><span data-stu-id="33883-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="33883-128">Per informazioni dettagliate, vedere la Guida alla distribuzione di [Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="33883-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="33883-129">Creare certificati per AD FS.</span><span class="sxs-lookup"><span data-stu-id="33883-129">Create certificates for AD FS.</span></span> <span data-ttu-id="33883-130">Per ulteriori informazioni, vedere [la sezione "Certificati server](https://go.microsoft.com/fwlink/p/?LinkId=285376) federativi" dell'argomento Pianificare e distribuire AD FS per l'utilizzo con Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="33883-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="33883-131">Dall'Windows PowerShell della riga di comando, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="33883-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="33883-132">Stabilire una relazione eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="33883-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="33883-133">Impostare le regole di relying party seguenti:</span><span class="sxs-lookup"><span data-stu-id="33883-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="33883-134">Disabilitare BranchCache</span><span class="sxs-lookup"><span data-stu-id="33883-134">Disable BranchCache</span></span>
<span data-ttu-id="33883-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="33883-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="33883-136">La funzionalità BranchCache in Windows 7 e Windows Server 2008 R2 può interferire con i componenti Web di Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="33883-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="33883-137">Per evitare problemi per gli utenti di Skype for Business Web App, assicurati che BranchCache non sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="33883-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="33883-138">Per informazioni dettagliate sulla disabilitazione di BranchCache, vedi la Guida [alla distribuzione di BranchCache.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="33883-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="33883-139">Verifica della distribuzione di Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="33883-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="33883-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="33883-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="33883-141">È possibile utilizzare il cmdlet Test-CsUcwaConference per verificare che una coppia di utenti di test possa partecipare a una conferenza tramite UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="33883-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="33883-142">Per informazioni dettagliate su questo cmdlet, vedere [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) nella documentazione di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="33883-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="33883-143">Risoluzione dei problemi relativi all'installazione dei plug-in in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="33883-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="33883-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="33883-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="33883-145">Se l'installazione del plug-in non riesce in un computer che esegue Windows Server 2008 R2, potrebbe essere necessario modificare l'impostazione di sicurezza di Internet Explorer o l'impostazione della chiave del Registro di sistema DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="33883-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="33883-146">Modificare l'impostazione di sicurezza in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="33883-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="33883-147">Aprire Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="33883-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="33883-148">Fare clic su **Strumenti**, su **Opzioni Internet** e quindi su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="33883-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="33883-149">Scorrere verso il basso fino alla sezione **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="33883-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="33883-150">Deselezionare **Non salvare pagine crittografate su disco** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="33883-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33883-151">Se selezionata, questa impostazione causerà un errore anche quando si tenta di scaricare un allegato da Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="33883-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="33883-152">Tornare a partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="33883-152">Rejoin the meeting.</span></span> <span data-ttu-id="33883-153">Il download del plug-in dovrebbe avere luogo senza errori.</span><span class="sxs-lookup"><span data-stu-id="33883-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="33883-154">Modificare l'impostazione disableMSI del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="33883-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="33883-155">Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="33883-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="33883-156">Per accedere all'editor del Registro di sistema, digitare **regedit**.</span><span class="sxs-lookup"><span data-stu-id="33883-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="33883-157">Passare a HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="33883-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="33883-158">Modificare o aggiungere la chiave DisableMSI di tipo REG_DWORD del Registro di sistema e impostarla su 0.</span><span class="sxs-lookup"><span data-stu-id="33883-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="33883-159">Tornare a partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="33883-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="33883-160">Abilitare l'app Riunioni Skype per sostituire Skype for Business Web App (facoltativo, solo Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="33883-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="33883-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="33883-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="33883-162">Questa procedura è facoltativa e si applica a Skype for Business Server 2015 CU5 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="33883-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="33883-163">In caso contrario, gli utenti esterni continueranno a partecipare alle riunioni con Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="33883-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="33883-164">Abilitare la partecipazione semplificata alle riunioni e l'app Riunioni Skype</span><span class="sxs-lookup"><span data-stu-id="33883-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="33883-165">Quando abiliti l'accesso alla rete per la distribuzione di contenuti (CDN), gli utenti avranno la possibilità di connettersi alla rete CDN online e ottenere Skype Meetings App (in Windows) e Skype for Business per Mac (su Mac) e useranno l'esperienza semplificata di partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="33883-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="33883-166">Consentire l'invio ai server Microsoft della telemetria della registrazione sul lato client dalla pagina Web di partecipazione alle riunioni o dall'app Riunioni Skype (il comando è impostato su false per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="33883-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="33883-167">Le informazioni inviate a Microsoft sono conformi alle procedure di raccolta dei dati [di Skype for Business.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)</span><span class="sxs-lookup"><span data-stu-id="33883-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="33883-168">Impostare il timeout prima del fall back sull'esperienza Skype for Business Web App ospitata localmente se la rete CDN non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="33883-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="33883-169">Il valore predefinito è 6 secondi.</span><span class="sxs-lookup"><span data-stu-id="33883-169">The default value is 6 seconds.</span></span> <span data-ttu-id="33883-170">Se questo valore è impostato su 0, non vi sarà alcun timeout.</span><span class="sxs-lookup"><span data-stu-id="33883-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="33883-171">Con MeetingUxUseCdn nell'aggiornamento cumulativo 5 di Skype for Business Server 2015, il valore predefinito è impostato su False.</span><span class="sxs-lookup"><span data-stu-id="33883-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="33883-172">Ciò causa un problema per cui il client Skype for Business per Mac non è in grado di partecipare alle riunioni dei partner non federati come guest, anche se l'amministratore di Skype for Business ha impostato MeetingUxUseCdn su True.</span><span class="sxs-lookup"><span data-stu-id="33883-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="33883-173">Per il funzionamento, Skype for Business Server 2015 deve disporre dell'aggiornamento cumulativo 7, 6.0.9319.534 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="33883-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="33883-174">Vedere [Abilitare l'app Riunioni Skype per sostituire Skype for Business Web App in Skype for Business Server 2015.](https://support.microsoft.com/kb/4132312)</span><span class="sxs-lookup"><span data-stu-id="33883-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="33883-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33883-175">See also</span></span>
<span data-ttu-id="33883-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="33883-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="33883-177">Pianificare i client riunioni (app Web e app Riunioni)</span><span class="sxs-lookup"><span data-stu-id="33883-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="33883-178">Configurare la pagina di partecipazione alle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="33883-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="33883-179">Informativa sulla privacy di Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="33883-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="33883-180">Condizioni di licenza e documentazione</span><span class="sxs-lookup"><span data-stu-id="33883-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
