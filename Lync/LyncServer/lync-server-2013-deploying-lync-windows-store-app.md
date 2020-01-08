---
title: "Lync Server 2013: distribuzione dell'app Lync di Windows Store"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef2e96b1e58bb9a92b2dc9748624d38f605965f
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40984909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="f7078-102">Distribuzione dell'app Lync di Windows Store in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7078-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7078-103">_**Argomento Ultima modifica:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="f7078-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="f7078-104">Prima di rendere disponibile l'app Lync di Windows Store agli utenti, assicurati che la distribuzione soddisfi i [requisiti dell'app Lync di Windows Store per Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7078-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="f7078-105">Per informazioni dettagliate sulla configurazione di Lync Server 2013 per il supporto dell'app Lync di Windows Store, vedere l'articolo su Blog di NextHop "individuazione automatica Lync Server e l'app [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Lync Windows Store".</span><span class="sxs-lookup"><span data-stu-id="f7078-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="f7078-106">Dopo aver configurato correttamente l'ambiente server, è possibile indirizzare gli utenti a scaricare l'app Lync da Windows Store cercando "Lync".</span><span class="sxs-lookup"><span data-stu-id="f7078-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="f7078-107">Abilitare l'autenticazione a più fattori per l'app Lync di Windows Store</span><span class="sxs-lookup"><span data-stu-id="f7078-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="f7078-108">Aggiornamenti cumulativi per Lync Server 2013: giugno 2013 aggiunge il supporto per l'autenticazione a più fattori per i client delle app Lync di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="f7078-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="f7078-109">Oltre al nome utente e alla password, è possibile richiedere altri metodi di autenticazione, ad esempio smart card o pin, per autenticare gli utenti esterni quando accedono alle riunioni Lync.</span><span class="sxs-lookup"><span data-stu-id="f7078-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="f7078-110">Per abilitare l'autenticazione a più fattori, distribuire il server federativo di Active Directory Federation Service (ADFS) e abilitare l'autenticazione passiva in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f7078-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="f7078-111">Dopo aver configurato ADFS, gli utenti esterni che tentano di partecipare a riunioni Lync vengono presentati con una pagina Web di autenticazione a più fattori di ADFS che contiene la sfida di nome utente e password, oltre a eventuali altri metodi di autenticazione configurati .</span><span class="sxs-lookup"><span data-stu-id="f7078-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f7078-112">Di seguito sono riportate considerazioni importanti se si prevede di configurare ADFS per l'autenticazione a più fattori per l'app Lync di Windows Store:</span><span class="sxs-lookup"><span data-stu-id="f7078-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="f7078-113">Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013:2013 giugno è necessario almeno.</span><span class="sxs-lookup"><span data-stu-id="f7078-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="f7078-114">I client desktop di Lync 2013 non richiedono aggiornamenti cumulativi per Lync Server 2013: giugno 2013, quindi potrebbe sembrare che l'autenticazione passiva funzioni perché i client di Lync 2013 possono eseguire l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f7078-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="f7078-115">Tuttavia, il processo di autenticazione per i client delle app Lync di Windows Store non verrà completato e non verrà visualizzata alcuna notifica o messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="f7078-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="f7078-116">Il server deve essere configurato in modo che l'autenticazione passiva sia l'unico tipo di autenticazione disponibile.</span><span class="sxs-lookup"><span data-stu-id="f7078-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="f7078-117">Se si usano i dispositivi di bilanciamento del carico hardware, abilitare la persistenza dei cookie in bilanciamento del carico in modo che tutte le richieste del client dell'app Lync di Windows Store vengano gestite dallo stesso server front-end.</span><span class="sxs-lookup"><span data-stu-id="f7078-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="f7078-118">Quando si stabilisce un trust tra i server Lync e i server ADFS, assegnare una durata abbastanza lunga per la durata massima delle riunioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="f7078-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="f7078-119">In genere, una durata del token di 240 minuti è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="f7078-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f7078-120">**Per configurare l'autenticazione a più fattori**</span><span class="sxs-lookup"><span data-stu-id="f7078-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="f7078-121">Installare un ruolo del server federativo ADFS.</span><span class="sxs-lookup"><span data-stu-id="f7078-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="f7078-122">Per informazioni dettagliate, vedere la guida alla distribuzione di <http://go.microsoft.com/fwlink/p/?linkid=267511>Active Directory Federation Services 2,0.</span><span class="sxs-lookup"><span data-stu-id="f7078-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="f7078-123">Creare certificati per ADFS.</span><span class="sxs-lookup"><span data-stu-id="f7078-123">Create certificates for AD FS.</span></span> <span data-ttu-id="f7078-124">Per altre informazioni, vedere la sezione "certificati del server federativo" del piano per e distribuire ADFS per l'uso con l'argomento Single Sign-on [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span><span class="sxs-lookup"><span data-stu-id="f7078-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="f7078-125">Dall'interfaccia della riga di comando di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f7078-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="f7078-126">Creare una partnership eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f7078-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="f7078-127">Impostare le regole del componente seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7078-127">Set the following relying party rules:</span></span>
    
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

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="f7078-128">Problemi noti che possono impedire l'accesso</span><span class="sxs-lookup"><span data-stu-id="f7078-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="f7078-129">La data e l'ora non sono impostate in modo accurato nel dispositivo che esegue Lync Windows Store app</span><span class="sxs-lookup"><span data-stu-id="f7078-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="f7078-130">L'impostazione dell'ora nel dispositivo deve essere sincronizzata con l'impostazione dell'ora nel server.</span><span class="sxs-lookup"><span data-stu-id="f7078-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="f7078-131">Questo aspetto è particolarmente importante per i dispositivi come Microsoft Surface e altri dispositivi che usano Windows RT non collegati a un dominio.</span><span class="sxs-lookup"><span data-stu-id="f7078-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="f7078-132">Per impostare automaticamente l'ora di questi dispositivi da un server temporale, eseguire il comando seguente da un prompt dei comandi con privilegi elevati nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f7078-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="f7078-133">L'app Lync di Windows Store non può accedere al server o ai servizi Lync</span><span class="sxs-lookup"><span data-stu-id="f7078-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="f7078-134">L'app Lync di Windows Store potrebbe non essere in grado di accedere a Lync Server o ai servizi tramite schede di rete, ad esempio i modem USB 4G LTE, che non si registrano in Windows 8 come dispositivi fisici.</span><span class="sxs-lookup"><span data-stu-id="f7078-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="f7078-135">L'app Lync di Windows Store potrebbe avere questo problema anche quando le app e i browser desktop sono in grado di accedere ad altri server e siti Web.</span><span class="sxs-lookup"><span data-stu-id="f7078-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="f7078-136">L'app Lync di Windows Store non riesce ad accedere con Lync Server 2010 e Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="f7078-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="f7078-137">Se la topologia è costituita da Lync Server 2010 con Office Communications Server 2007 R2 Edge Server, sarà necessario eseguire la versione aggiornata di generatore di topologia disponibile nell'aggiornamento cumulativo per Lync Server 2010: luglio 2013.</span><span class="sxs-lookup"><span data-stu-id="f7078-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="f7078-138">Le versioni precedenti di generatore di topologie non creano il mapping obbligatorio a Office Communications Server 2007 Edge Server, quindi i client delle app Lync di Windows Store non riescono ad accedere.</span><span class="sxs-lookup"><span data-stu-id="f7078-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="f7078-139">I passaggi seguenti sono obbligatori:</span><span class="sxs-lookup"><span data-stu-id="f7078-139">The following steps are required:</span></span>

1.  <span data-ttu-id="f7078-140">Installare l'aggiornamento cumulativo per Lync Server 2010: luglio 2013 nei pool di Lync Server 2010 e nei direttori di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f7078-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="f7078-141">Aggiornare la configurazione di individuazione automatica di Lync per indicare che il punto di ingresso SIP esterno è l'indirizzo del server perimetrale eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7078-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="f7078-142">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f7078-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="f7078-143">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f7078-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="f7078-144">L'app Lync di Windows Store non può accedere a causa di un errore di convalida dei nomi di certificato</span><span class="sxs-lookup"><span data-stu-id="f7078-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="f7078-145">Un problema di accesso può verificarsi per gli utenti di Office 365 che non hanno eseguito l'ultima versione dell'app Lync di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="f7078-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="f7078-146">Questo problema si verifica in genere quando si usano più domini, ad esempio quando l'URI SIP è **usera@domainZ.com** , ma il server perimetrale è **SIP.domainX.com**.</span><span class="sxs-lookup"><span data-stu-id="f7078-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="f7078-147">Per risolvere il problema, gli utenti devono installare la versione più recente dell'app Lync di Windows Store, che richiede anche Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="f7078-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="f7078-148">Usare i registri delle app Lync di Windows Store per risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="f7078-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="f7078-149">È possibile usare i registri generati nel dispositivo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="f7078-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="f7078-150">I registri sono archiviati nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="f7078-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="f7078-151">% LocalAppData%\\Packages\\Microsoft.\_LyncMX\\8wekyb3d8bbwe\\LocalState Tracing</span><span class="sxs-lookup"><span data-stu-id="f7078-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="f7078-152">Prima di ottenere i log da un utente, verificare che la registrazione sia attivata e quindi chiedere all'utente di salvare i registri in modo che tutte le informazioni archiviate in memoria vengano salvate anche nei file del disco rigido.</span><span class="sxs-lookup"><span data-stu-id="f7078-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="f7078-153">**Per attivare la registrazione**</span><span class="sxs-lookup"><span data-stu-id="f7078-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="f7078-154">Aprire l'app Lync di Windows Store nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7078-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="f7078-155">Scorrere rapidamente dal lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="f7078-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="f7078-156">Se si usa un mouse, posizionare il puntatore sull'angolo in alto a destra dello schermo e quindi spostare il cursore del mouse sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="f7078-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="f7078-157">Selezionare **Impostazioni**, **Opzioni**e quindi imposta log di **diagnostica** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="f7078-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="f7078-158">Se i **registri diagnostici** erano spenti in precedenza, è necessario riavviare Lync.</span><span class="sxs-lookup"><span data-stu-id="f7078-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="f7078-159">Per riavviare Lync, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7078-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="f7078-160">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7078-160">Restart the device.</span></span>
    
      - <span data-ttu-id="f7078-161">Terminare l'attività di Lync e avviare di nuovo l'app.</span><span class="sxs-lookup"><span data-stu-id="f7078-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="f7078-162">Per terminare l'attività, aprire Gestione attività di Windows, selezionare **Lync**e quindi toccare **Termina attività**.</span><span class="sxs-lookup"><span data-stu-id="f7078-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="f7078-163">Se Lync non è elencato, toccare **altri dettagli** e cercare Lync in **processi in background**.</span><span class="sxs-lookup"><span data-stu-id="f7078-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="f7078-164">**Per salvare i registri**</span><span class="sxs-lookup"><span data-stu-id="f7078-164">**To save the logs**</span></span>

1.  <span data-ttu-id="f7078-165">Aprire l'app Lync di Windows Store nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7078-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="f7078-166">Provare a eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f7078-166">Try signing in.</span></span>

3.  <span data-ttu-id="f7078-167">Scorrere rapidamente dal lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="f7078-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="f7078-168">Se si usa un mouse, posizionare il puntatore sull'angolo in alto a destra dello schermo e quindi spostare il cursore del mouse sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="f7078-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="f7078-169">Selezionare **Impostazioni**, quindi selezionare **informazioni su**e quindi **Salva registri**.</span><span class="sxs-lookup"><span data-stu-id="f7078-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

