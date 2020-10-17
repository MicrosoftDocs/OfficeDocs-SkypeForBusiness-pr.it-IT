---
title: 'Lync Server 2013: migrazione degli utenti di Lync Online a Lync in locale'
description: 'Lync Server 2013: migrazione degli utenti di Lync Online a Lync in locale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 620bc07def8e3c1f6b761c6398b452b4dbcd3b04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561002"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="ad53f-103">Migrazione degli utenti di Lync Online a Lync locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad53f-103">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad53f-104">_**Ultimo argomento modificato:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="ad53f-104">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="ad53f-105">Questi passaggi sono necessari solo per la migrazione degli account utente originariamente abilitati per Lync in Lync Online, prima di distribuire Lync in locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-105">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="ad53f-106">Per spostare gli utenti originariamente abilitati per Lync in locale, successivamente spostati in Lync Online, vedere <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ad53f-106">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="ad53f-107">Inoltre, tutti gli utenti spostati devono disporre di account in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-107">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="ad53f-108">Migrazione degli account utente originariamente abilitati in Lync Online a Lync in locale</span><span class="sxs-lookup"><span data-stu-id="ad53f-108">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="ad53f-109">Prima di tutto, assicurarsi che l'organizzazione sia configurata per l'ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="ad53f-109">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="ad53f-110">Installare lo strumento di sincronizzazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ad53f-110">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="ad53f-111">Per ulteriori informazioni, vedere <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="ad53f-111">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="ad53f-112">Per consentire agli utenti di utilizzare Single Sign-on per Lync Online, installare Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> .</span><span class="sxs-lookup"><span data-stu-id="ad53f-112">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="ad53f-113">Nella distribuzione locale, in Lync Server Management Shell, digitare i seguenti cmdlet per creare il provider di hosting per Lync Online:</span><span class="sxs-lookup"><span data-stu-id="ad53f-113">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="ad53f-114">Verificare che nei server perimetrali locali sia presente la catena di certificati che consente la connessione a Lync Online, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ad53f-114">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="ad53f-115">È possibile scaricare questa catena qui: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="ad53f-115">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ad53f-116">Certificato</span><span class="sxs-lookup"><span data-stu-id="ad53f-116">Certificate</span></span></th>
    <th><span data-ttu-id="ad53f-117">Archivio certificati</span><span class="sxs-lookup"><span data-stu-id="ad53f-117">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ad53f-118">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="ad53f-118">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-119">Autorità di certificazione radice attendibile</span><span class="sxs-lookup"><span data-stu-id="ad53f-119">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ad53f-120">Microsoft Internet Authority (nuovo certificato CA)</span><span class="sxs-lookup"><span data-stu-id="ad53f-120">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-121">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="ad53f-121">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ad53f-122">MSIT Machine auth CA2 (nuovo CA2 di emissione)</span><span class="sxs-lookup"><span data-stu-id="ad53f-122">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-123">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="ad53f-123">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="ad53f-124">In Active Directory locale, abilitare gli account utente coinvolti per Lync in locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-124">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="ad53f-125">È possibile eseguire questa operazione per un singolo utente digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="ad53f-125">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="ad53f-126">In alternativa, è possibile creare uno script che legga i nomi utente da un file e li fornisca come input per il cmdlet Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="ad53f-126">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="ad53f-127">Eseguire DirSync per sincronizzare gli utenti di Lync Online con gli utenti locali di Lync aggiornati.</span><span class="sxs-lookup"><span data-stu-id="ad53f-127">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="ad53f-128">Aggiornare alcuni record DNS per indirizzare tutto il traffico SIP a Lync locale:</span><span class="sxs-lookup"><span data-stu-id="ad53f-128">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="ad53f-129">Aggiornare **lyncdiscover.contoso.com** un record in modo che punti al nome di dominio completo del server proxy inverso locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-129">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="ad53f-130">Aggiornare il \*\*\* \_ SIP *. \_ tls.contoso.com*\* SRV record da risolvere nell'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-130">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="ad53f-131">Aggiornare il \*\*\* \_ sipfederationtls *. \_ tcp.contoso.com*\* SRV record da risolvere nell'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-131">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="ad53f-132">Se nell'organizzazione viene utilizzato Split DNS (a volte denominato "Split Brain DNS"), assicurarsi che gli utenti che desiderano risolvere i nomi tramite la zona DNS interna vengano indirizzati al pool Front end.</span><span class="sxs-lookup"><span data-stu-id="ad53f-132">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="ad53f-133">Digitare il `Get-CsUser` cmdlet per controllare alcune proprietà degli utenti da spostare.</span><span class="sxs-lookup"><span data-stu-id="ad53f-133">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="ad53f-134">Si desidera verificare che l'HostingProviderProxyFQDN sia impostato su `"sipfed.online.lync.com"` e che gli indirizzi SIP siano impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ad53f-134">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="ad53f-135">Spostare gli utenti di Lync online in Lync locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-135">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="ad53f-136">Per spostare un singolo utente, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ad53f-136">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="ad53f-137">È possibile spostare più utenti utilizzando il cmdlet **Get-CsUSer** con il parametro – Filter per selezionare gli utenti che dispongono di una proprietà specifica.</span><span class="sxs-lookup"><span data-stu-id="ad53f-137">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="ad53f-138">Ad esempio, è possibile selezionare tutti gli utenti di Lync Online filtrando per {provider di hosting-EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="ad53f-138">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="ad53f-139">È quindi possibile eseguire il piping degli utenti restituiti al cmdlet **Move-CsUSer** , come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ad53f-139">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="ad53f-140">Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL del pool in cui è in esecuzione il servizio di migrazione ospitata, nel formato seguente: *https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*.</span><span class="sxs-lookup"><span data-stu-id="ad53f-140">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="ad53f-141">È possibile determinare l'URL del servizio di migrazione ospitata visualizzando l'URL del pannello di controllo di Lync Online per l'account dell'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ad53f-141">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="ad53f-142">Per determinare l'URL del servizio di migrazione Hosted per il ORGANIZATON</span><span class="sxs-lookup"><span data-stu-id="ad53f-142">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="ad53f-143">Accedere all'organizzazione Microsoft 365 o Office 365 come amministratore.</span><span class="sxs-lookup"><span data-stu-id="ad53f-143">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="ad53f-144">Aprire l'interfaccia di **amministrazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="ad53f-144">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="ad53f-145">Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="ad53f-145">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="ad53f-146">Un URL di esempio è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ad53f-146">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="ad53f-147">Sostituire **WebDir** nell'URL con l' **amministratore**, ottenendo quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ad53f-147">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="ad53f-148">Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="ad53f-148">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="ad53f-149">L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ad53f-149">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="ad53f-150">La dimensione massima predefinita per i file di registro delle transazioni del database di rtcxds è 16 GB.</span><span class="sxs-lookup"><span data-stu-id="ad53f-150">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="ad53f-151">Potrebbe non essere sufficiente se si sta spostando un numero elevato di utenti contemporaneamente, soprattutto se è stato abilitato il mirroring.</span><span class="sxs-lookup"><span data-stu-id="ad53f-151">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="ad53f-152">Per aggirare questo è possibile aumentare le dimensioni del file o eseguire il backup dei file di registro regolarmente.</span><span class="sxs-lookup"><span data-stu-id="ad53f-152">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="ad53f-153">Per ulteriori informazioni, vedere <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> .</span><span class="sxs-lookup"><span data-stu-id="ad53f-153">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="ad53f-154">Questo passo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad53f-154">This is an optional step.</span></span> <span data-ttu-id="ad53f-155">Se è necessario eseguire l'integrazione con Exchange 2013 online, è necessario utilizzare un provider di hosting aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="ad53f-155">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="ad53f-156">Per informazioni dettagliate, vedere [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="ad53f-156">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="ad53f-157">Gli utenti sono ora spostati.</span><span class="sxs-lookup"><span data-stu-id="ad53f-157">The users are now moved.</span></span> <span data-ttu-id="ad53f-158">Per verificare che un utente disponga di valori corretti per gli attributi illustrati nella tabella seguente, digitare questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ad53f-158">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ad53f-159">Attributo di Active Directory</span><span class="sxs-lookup"><span data-stu-id="ad53f-159">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="ad53f-160">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="ad53f-160">Attribute name</span></span></th>
    <th><span data-ttu-id="ad53f-161">Valore corretto per l'utente di Lync Online</span><span class="sxs-lookup"><span data-stu-id="ad53f-161">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="ad53f-162">Valore corretto per gli utenti di Lync in-premises</span><span class="sxs-lookup"><span data-stu-id="ad53f-162">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ad53f-163">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="ad53f-163">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-164">Provider dihosting</span><span class="sxs-lookup"><span data-stu-id="ad53f-164">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-165">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ad53f-165">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-166">SRV</span><span class="sxs-lookup"><span data-stu-id="ad53f-166">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ad53f-167">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="ad53f-167">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-168">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="ad53f-168">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad53f-169">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-170">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad53f-170">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ad53f-171">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="ad53f-171">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-172">Abilitato</span><span class="sxs-lookup"><span data-stu-id="ad53f-172">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-173">True</span><span class="sxs-lookup"><span data-stu-id="ad53f-173">True</span></span></p></td>
    <td><p><span data-ttu-id="ad53f-174">True</span><span class="sxs-lookup"><span data-stu-id="ad53f-174">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="ad53f-175">Ogni utente che è stato spostato dovrà disconnettersi da Lync, quindi eseguire nuovamente l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ad53f-175">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="ad53f-176">Quando eseguono l'accesso, devono verificare gli elenchi di contatti e aggiungere i contatti, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ad53f-176">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="ad53f-177">Tenere presente che le riunioni pianificate non vengono migrate da Lync Online a Lync in locale.</span><span class="sxs-lookup"><span data-stu-id="ad53f-177">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="ad53f-178">Gli utenti dovranno ripianificare queste riunioni dopo essere state spostate.</span><span class="sxs-lookup"><span data-stu-id="ad53f-178">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="ad53f-179">Dopo l'aggiornamento dei record DNS e tutti gli utenti in locale, l'attributo provider dihosting indirizza l'utente Lync a utilizzare i record SRV o a indirizzarli al provider online "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="ad53f-179">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

