---
title: 'Lync Server 2013: migrazione degli utenti di Lync Online a Lync locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33888069b00eaf8a4d743f1e6ed3937d7a442bc
ms.sourcegitcommit: 5895afd0d5752a6ea1ace68d613f86c68eae8bdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "40984871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="c494b-102">Migrazione degli utenti di Lync Online a Lync locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c494b-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c494b-103">_**Argomento Ultima modifica:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="c494b-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="c494b-104">Questi passaggi sono necessari solo per la migrazione degli account utente inizialmente abilitati per Lync in Lync Online, prima di distribuire Lync locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="c494b-105">Per spostare gli utenti originariamente abilitati per Lync locale, in seguito spostati in Lync Online, vedere <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c494b-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="c494b-106">Inoltre, tutti gli utenti spostati devono avere account nell'Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="c494b-107">Migrazione degli account utente inizialmente abilitati in Lync Online a Lync locale</span><span class="sxs-lookup"><span data-stu-id="c494b-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="c494b-108">Prima di tutto, assicurati che l'organizzazione sia configurata per Hybrid.</span><span class="sxs-lookup"><span data-stu-id="c494b-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="c494b-109">Installare lo strumento di sincronizzazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c494b-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="c494b-110">Per altre informazioni, vedere <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="c494b-110">For more information, see <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="c494b-111">Per consentire agli utenti di usare Single Sign-on per Lync Online, installare Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span><span class="sxs-lookup"><span data-stu-id="c494b-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="c494b-112">Nella distribuzione locale, in Lync Server Management Shell, digitare i cmdlet seguenti per creare il provider di hosting per Lync Online:</span><span class="sxs-lookup"><span data-stu-id="c494b-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="c494b-113">Verificare che in un server perimetrale locale sia disponibile la catena di certificati che consente la connessione a Lync Online, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c494b-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="c494b-114">È possibile scaricare questa catena qui:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="c494b-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c494b-115">Certificato</span><span class="sxs-lookup"><span data-stu-id="c494b-115">Certificate</span></span></th>
    <th><span data-ttu-id="c494b-116">Archivio certificati</span><span class="sxs-lookup"><span data-stu-id="c494b-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c494b-117">Radice CyberTrust Baltimore</span><span class="sxs-lookup"><span data-stu-id="c494b-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="c494b-118">CA radice attendibile</span><span class="sxs-lookup"><span data-stu-id="c494b-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c494b-119">Microsoft Internet Authority (nuovo certificato CA)</span><span class="sxs-lookup"><span data-stu-id="c494b-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="c494b-120">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="c494b-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c494b-121">MSIT (nuova emissione di CA2)</span><span class="sxs-lookup"><span data-stu-id="c494b-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="c494b-122">CA intermedia</span><span class="sxs-lookup"><span data-stu-id="c494b-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="c494b-123">In Active Directory locale abilitare gli account utente interessati per Lync locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="c494b-124">Puoi eseguire questa operazione per un singolo utente digitando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c494b-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="c494b-125">In alternativa, è possibile creare uno script che legga i nomi utente da un file e li fornisca come input per il cmdlet Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="c494b-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="c494b-126">Eseguire DirSync per sincronizzare gli utenti di Lync Online con gli utenti locali di Lync aggiornati.</span><span class="sxs-lookup"><span data-stu-id="c494b-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="c494b-127">Aggiornare alcuni record DNS per indirizzare tutto il traffico SIP a Lync locale:</span><span class="sxs-lookup"><span data-stu-id="c494b-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="c494b-128">Aggiornare **lyncdiscover.contoso.com** un record in cui puntare il nome di dominio completo del server proxy inverso locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="c494b-129">Aggiornare il \*\**\_SIP *.\_ tls.contoso.com** SRV record per risolvere l'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="c494b-130">Aggiornare il \*\**\_sipfederationtls *.\_ tcp.contoso.com** SRV record per risolvere l'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="c494b-131">Se l'organizzazione usa il DNS diviso (a volte denominato "Split-Brain DNS"), verificare che gli utenti che risolvono i nomi tramite la zona DNS interna vengano indirizzati al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="c494b-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="c494b-132">Digitare il `Get-CsUser` cmdlet per verificare alcune proprietà relative agli utenti che verranno spostati.</span><span class="sxs-lookup"><span data-stu-id="c494b-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="c494b-133">Si vuole verificare che HostingProviderProxyFQDN sia impostato su `"sipfed.online.lync.com"` e che gli indirizzi SIP siano impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="c494b-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="c494b-134">Trasferire gli utenti di Lync online in Lync locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="c494b-135">Per trasferire un singolo utente, digitare:</span><span class="sxs-lookup"><span data-stu-id="c494b-135">To move a single user, type this:</span></span>
    
       ```
       $cred = Get-Credential
       ```
    
       ```
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="c494b-136">Puoi trasferire più utenti usando il cmdlet **Get-CsUSer** con il parametro – Filter per selezionare gli utenti con una specifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="c494b-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="c494b-137">Ad esempio, è possibile selezionare tutti gli utenti di Lync Online filtrando per {provider di hosting-EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="c494b-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="c494b-138">È quindi possibile eseguire il piping degli utenti restituiti al cmdlet **Move-CsUSer** , come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c494b-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="c494b-139">Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL per il pool in cui è in uso il servizio di migrazione ospitata, con il formato seguente: *https://\<FQDN\>del pool di/HostedMigration/hostedmigrationService.svc*.</span><span class="sxs-lookup"><span data-stu-id="c494b-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="c494b-140">Per determinare l'URL del servizio di migrazione ospitata, è possibile visualizzare l'URL del pannello di controllo di Lync Online dell'account del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c494b-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="c494b-141">Per determinare l'URL del servizio di migrazione ospitata per il tenant di Office 365</span><span class="sxs-lookup"><span data-stu-id="c494b-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="c494b-142">Accedere al tenant di Office 365 come amministratore.</span><span class="sxs-lookup"><span data-stu-id="c494b-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="c494b-143">Aprire l'interfaccia di **amministrazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="c494b-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="c494b-144">Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="c494b-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="c494b-145">Un URL di esempio ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c494b-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="c494b-146">Sostituire **WebDir** nell'URL con l' **amministratore**, con il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="c494b-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="c494b-147">Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="c494b-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="c494b-148">L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c494b-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="c494b-149">Le dimensioni massime predefinite per i file di log delle transazioni del database rtcxds sono di 16 GB.</span><span class="sxs-lookup"><span data-stu-id="c494b-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="c494b-150">Questo potrebbe non essere abbastanza grande se si sta spostando un numero elevato di utenti contemporaneamente, in particolare se è abilitato il mirroring.</span><span class="sxs-lookup"><span data-stu-id="c494b-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="c494b-151">Per aggirare questo problema, è possibile aumentare le dimensioni del file o eseguire il backup dei file di log regolarmente.</span><span class="sxs-lookup"><span data-stu-id="c494b-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="c494b-152">Per altre informazioni, vedere <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span><span class="sxs-lookup"><span data-stu-id="c494b-152">For more information, see <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="c494b-153">Questo è un passaggio facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c494b-153">This is an optional step.</span></span> <span data-ttu-id="c494b-154">Se è necessario integrarsi con Exchange 2013 online, è necessario usare un altro provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="c494b-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="c494b-155">Per informazioni dettagliate, vedere [configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="c494b-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="c494b-156">Ora gli utenti vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="c494b-156">The users are now moved.</span></span> <span data-ttu-id="c494b-157">Per verificare che un utente disponga di valori corretti per gli attributi illustrati nella tabella seguente, digitare questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c494b-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="c494b-158">Attributo Active Directory</span><span class="sxs-lookup"><span data-stu-id="c494b-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="c494b-159">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="c494b-159">Attribute name</span></span></th>
    <th><span data-ttu-id="c494b-160">Valore corretto per l'utente di Lync Online</span><span class="sxs-lookup"><span data-stu-id="c494b-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="c494b-161">Valore corretto per gli utenti di Lync in-locale</span><span class="sxs-lookup"><span data-stu-id="c494b-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c494b-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="c494b-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="c494b-163">Provider dihosting</span><span class="sxs-lookup"><span data-stu-id="c494b-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="c494b-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c494b-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="c494b-165">SRV</span><span class="sxs-lookup"><span data-stu-id="c494b-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c494b-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="c494b-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="c494b-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="c494b-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="c494b-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c494b-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="c494b-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c494b-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c494b-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="c494b-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="c494b-171">Abilitata</span><span class="sxs-lookup"><span data-stu-id="c494b-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="c494b-172">True</span><span class="sxs-lookup"><span data-stu-id="c494b-172">True</span></span></p></td>
    <td><p><span data-ttu-id="c494b-173">True</span><span class="sxs-lookup"><span data-stu-id="c494b-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="c494b-174">Ogni utente che è stato spostato dovrà disconnettersi da Lync, quindi accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="c494b-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="c494b-175">Quando accedono, dovrebbero verificare gli elenchi di contatti e aggiungere i contatti, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c494b-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="c494b-176">Tieni presente che le riunioni pianificate non vengono migrate da Lync Online a Lync locale.</span><span class="sxs-lookup"><span data-stu-id="c494b-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="c494b-177">Gli utenti dovranno ripianificare queste riunioni dopo lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="c494b-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="c494b-178">Dopo che i record DNS vengono aggiornati e tutti gli utenti vengono indirizzati in locale, l'attributo provider dihosting indirizza l'utente di Lync a usare i record SRV o a indirizzarli al provider online "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="c494b-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

