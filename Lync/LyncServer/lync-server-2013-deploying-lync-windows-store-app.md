---
title: "Lync Server 2013: distribuzione dell'app Lync Windows Store"
description: "Lync Server 2013: distribuzione dell'app Lync Windows Store."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9260d656079fb694a14aadf5049ca36241830c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571712"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="b28c2-103">Distribuzione di Lync Windows Store app in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b28c2-103">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b28c2-104">_**Ultimo argomento modificato:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="b28c2-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="b28c2-105">Prima di rendere disponibile l'app Windows Store di Lync per gli utenti, verificare che la distribuzione soddisfi i [requisiti delle app di Windows Store per Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28c2-105">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="b28c2-106">Per informazioni dettagliate sulla configurazione di Lync Server 2013 per il supporto delle app di Windows Store di Lync, vedere l'articolo del Blog di NextHop "individuazione automatica di Lync Server e l'app Lync Windows Store" all'indirizzo [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) .</span><span class="sxs-lookup"><span data-stu-id="b28c2-106">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="b28c2-107">Dopo che l'ambiente server è stato configurato correttamente, è possibile indirizzare gli utenti a scaricare l'app Lync da Windows Store eseguendo una ricerca per "Lync".</span><span class="sxs-lookup"><span data-stu-id="b28c2-107">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="b28c2-108">Abilitazione dell'autenticazione a più fattori per l'app Windows Store di Lync</span><span class="sxs-lookup"><span data-stu-id="b28c2-108">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="b28c2-109">Aggiornamenti cumulativi per Lync Server 2013: giugno 2013 aggiunge il supporto per l'autenticazione a più fattori per i client delle app di Windows Store di Lync.</span><span class="sxs-lookup"><span data-stu-id="b28c2-109">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="b28c2-110">Oltre a nome utente e password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti esterni quando eseguono l'accesso alle riunioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="b28c2-110">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="b28c2-111">Per abilitare l'autenticazione a più fattori, è necessario distribuire il server federativo di Active Directory Federation Services (ADFS) e abilitare l'autenticazione passiva in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b28c2-111">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="b28c2-112">Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare alle riunioni di Lync sono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene il nome utente e la sfida per la password insieme ai metodi di autenticazione aggiuntivi che sono stati configurati.</span><span class="sxs-lookup"><span data-stu-id="b28c2-112">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b28c2-113">Di seguito sono riportate considerazioni importanti se si prevede di configurare ad FS per l'autenticazione a più fattori per l'app Windows Store di Lync:</span><span class="sxs-lookup"><span data-stu-id="b28c2-113">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b28c2-114">Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: il numero di giugno 2013 è necessario almeno.</span><span class="sxs-lookup"><span data-stu-id="b28c2-114">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="b28c2-115">I client desktop Lync 2013 non richiedono aggiornamenti cumulativi per Lync Server 2013: giugno 2013, pertanto potrebbe sembrare che l'autenticazione passiva funzioni perché i client di Lync 2013 sono in grado di eseguire l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b28c2-115">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="b28c2-116">Tuttavia, il processo di autenticazione per i client app di Windows Store di Lync non verrà completato e non verrà visualizzato alcun messaggio di errore o notifica.</span><span class="sxs-lookup"><span data-stu-id="b28c2-116">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="b28c2-117">Il server deve essere configurato in modo che l'autenticazione passiva sia l'unico tipo di autenticazione offerto.</span><span class="sxs-lookup"><span data-stu-id="b28c2-117">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="b28c2-118">Se si utilizzano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie sui bilanciamento del carico in modo che tutte le richieste provenienti dal client app Lync Windows Store siano gestite dallo stesso front end server.</span><span class="sxs-lookup"><span data-stu-id="b28c2-118">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="b28c2-119">Quando si stabilisce una relazione di trust relying party tra Lync Server e i server AD FS, assegnare una durata del token sufficiente a coprire la lunghezza massima delle riunioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="b28c2-119">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="b28c2-120">240 minuti in genere sono una durata sufficiente per i token.</span><span class="sxs-lookup"><span data-stu-id="b28c2-120">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="b28c2-121">**Per configurare l'autenticazione a più fattori**</span><span class="sxs-lookup"><span data-stu-id="b28c2-121">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="b28c2-122">Installare un ruolo del server federativo ADFS.</span><span class="sxs-lookup"><span data-stu-id="b28c2-122">Install an AD FS federation server role.</span></span> <span data-ttu-id="b28c2-123">Per informazioni dettagliate, vedere la guida alla distribuzione di Active Directory Federation Services 2,0 all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=267511> .</span><span class="sxs-lookup"><span data-stu-id="b28c2-123">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="b28c2-124">Creare certificati per ADFS.</span><span class="sxs-lookup"><span data-stu-id="b28c2-124">Create certificates for AD FS.</span></span> <span data-ttu-id="b28c2-125">Per ulteriori informazioni, vedere la sezione relativa ai certificati del server federativo del piano per la distribuzione di ADFS per l'utilizzo con l'argomento Single Sign-on all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="b28c2-125">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="b28c2-126">Dall'interfaccia della riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b28c2-126">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="b28c2-127">Stabilire una relazione eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b28c2-127">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="b28c2-128">Impostare le regole di relying party seguenti:</span><span class="sxs-lookup"><span data-stu-id="b28c2-128">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="b28c2-129">Problemi noti che possono impedire l'accesso</span><span class="sxs-lookup"><span data-stu-id="b28c2-129">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="b28c2-130">La data e l'ora non vengono impostate con precisione sul dispositivo che esegue Lync Windows Store app</span><span class="sxs-lookup"><span data-stu-id="b28c2-130">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="b28c2-131">L'impostazione relativa all'ora del dispositivo deve essere sincronizzata con l'impostazione relativa all'ora sul server.</span><span class="sxs-lookup"><span data-stu-id="b28c2-131">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="b28c2-132">Questo è particolarmente importante per i dispositivi come Microsoft Surface e altri dispositivi che eseguono Windows RT che non sono aggiunti a un dominio.</span><span class="sxs-lookup"><span data-stu-id="b28c2-132">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="b28c2-133">Per impostare automaticamente l'ora su questi dispositivi da un server di tempo, eseguire il comando seguente da un prompt dei comandi con privilegi elevati nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b28c2-133">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="b28c2-134">L'app Lync Windows Store non è in grado di accedere al server o ai servizi Lync</span><span class="sxs-lookup"><span data-stu-id="b28c2-134">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="b28c2-135">L'app Lync Windows Store potrebbe non essere in grado di accedere a Lync Server o ai servizi tramite schede di rete, ad esempio i modem USB 4G LTE, che non sono registrati con Windows 8 come dispositivi fisici.</span><span class="sxs-lookup"><span data-stu-id="b28c2-135">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="b28c2-136">L'app Lync Windows Store può avere questo problema anche quando le app e i browser desktop sono in grado di accedere ad altri server e siti Web.</span><span class="sxs-lookup"><span data-stu-id="b28c2-136">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="b28c2-137">L'app Lync Windows Store non è in grado di accedere con Lync Server 2010 e il server perimetrale di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b28c2-137">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="b28c2-138">Se la topologia è costituita da Lync Server 2010 con Office Communications Server 2007 R2 Edge Server, sarà necessario eseguire la versione aggiornata di generatore di topologie disponibile nell'aggiornamento cumulativo per Lync Server 2010: luglio 2013.</span><span class="sxs-lookup"><span data-stu-id="b28c2-138">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="b28c2-139">Le versioni precedenti del generatore di topologie non creano il mapping necessario a Office Communications Server 2007 Edge Server, quindi i client app di Lync Windows Store non sono in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b28c2-139">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="b28c2-140">Sono necessari i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b28c2-140">The following steps are required:</span></span>

1.  <span data-ttu-id="b28c2-141">Installare l'aggiornamento cumulativo per Lync Server 2010: luglio 2013 nei pool Lync Server 2010 e nei direttori di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b28c2-141">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="b28c2-142">Aggiornare la configurazione di individuazione automatica di Lync per indicare che il punto di ingresso SIP esterno è l'indirizzo del server perimetrale eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b28c2-142">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="b28c2-143">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b28c2-143">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="b28c2-144">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b28c2-144">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="b28c2-145">L'app Lync Windows Store non è in grado di accedere a causa di un errore di convalida del nome del certificato</span><span class="sxs-lookup"><span data-stu-id="b28c2-145">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="b28c2-146">È possibile che si verifichi un problema di accesso per gli utenti di Microsoft 365 o Office 365 che non eseguono la versione più recente dell'app Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="b28c2-146">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="b28c2-147">Questo problema si verifica in genere quando si utilizzano più domini (ad esempio, quando l'URI SIP è **usera@domainZ.com** ma il server perimetrale è **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="b28c2-147">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="b28c2-148">Per risolvere il problema, è necessario che gli utenti installino la versione più recente dell'app Lync Windows Store, che richiede anche Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="b28c2-148">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="b28c2-149">Utilizzare i registri delle app di Windows Store di Lync per risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="b28c2-149">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="b28c2-150">È possibile utilizzare i registri generati nel dispositivo per risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="b28c2-150">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="b28c2-151">I registri sono archiviati nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="b28c2-151">The logs are stored in the following folder:</span></span>

<span data-ttu-id="b28c2-152">% LocalAppData% \\ packages \\ Microsoft. \_ LyncMX \\ 8wekyb3d8bbwe \\ traccia LocalState</span><span class="sxs-lookup"><span data-stu-id="b28c2-152">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="b28c2-153">Prima di ottenere i log da un utente, verificare che la registrazione sia attivata e quindi chiedere all'utente di salvare i registri in modo che tutte le informazioni archiviate in memoria vengano salvate anche nei file nel disco rigido.</span><span class="sxs-lookup"><span data-stu-id="b28c2-153">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="b28c2-154">**Per abilitare la registrazione**</span><span class="sxs-lookup"><span data-stu-id="b28c2-154">**To turn on logging**</span></span>

1.  <span data-ttu-id="b28c2-155">Aprire l'app Lync Windows Store nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b28c2-155">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="b28c2-156">Scorrere rapidamente dal lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="b28c2-156">Swipe from the right side of the screen.</span></span> <span data-ttu-id="b28c2-157">Se si utilizza un mouse, puntare l'angolo in alto a destra dello schermo e quindi spostare il puntatore del mouse verso il basso sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="b28c2-157">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="b28c2-158">Selezionare **Impostazioni**, fare clic su **Opzioni**e quindi impostare i **registri diagnostici** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="b28c2-158">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="b28c2-159">Se i **log diagnostici** erano spenti in precedenza, è necessario riavviare Lync.</span><span class="sxs-lookup"><span data-stu-id="b28c2-159">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="b28c2-160">Per riavviare Lync, effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b28c2-160">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="b28c2-161">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b28c2-161">Restart the device.</span></span>
    
      - <span data-ttu-id="b28c2-162">Terminare l'attività Lync e avviare di nuovo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b28c2-162">End the Lync task and launch the app again.</span></span> <span data-ttu-id="b28c2-163">Per terminare l'attività, aprire Gestione attività di Windows, selezionare **Lync**e quindi toccare **Termina attività**.</span><span class="sxs-lookup"><span data-stu-id="b28c2-163">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="b28c2-164">Se Lync non è elencato, toccare **altre informazioni** e cercare Lync in **processi in background**.</span><span class="sxs-lookup"><span data-stu-id="b28c2-164">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="b28c2-165">**Per salvare i registri**</span><span class="sxs-lookup"><span data-stu-id="b28c2-165">**To save the logs**</span></span>

1.  <span data-ttu-id="b28c2-166">Aprire l'app Lync Windows Store nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b28c2-166">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="b28c2-167">Provare a eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b28c2-167">Try signing in.</span></span>

3.  <span data-ttu-id="b28c2-168">Scorrere rapidamente dal lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="b28c2-168">Swipe from the right side of the screen.</span></span> <span data-ttu-id="b28c2-169">Se si utilizza un mouse, puntare l'angolo in alto a destra dello schermo e quindi spostare il puntatore del mouse verso il basso sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="b28c2-169">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="b28c2-170">Selezionare **Impostazioni**, quindi fare clic **su**, quindi selezionare **Salva registri**.</span><span class="sxs-lookup"><span data-stu-id="b28c2-170">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

