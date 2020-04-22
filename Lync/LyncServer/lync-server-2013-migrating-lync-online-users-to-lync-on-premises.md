---
title: 'Lync Server 2013: migrazione degli utenti di Lync Online a Lync in locale'
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
ms.openlocfilehash: e87b977dd70227d134e5feae8df2ea089e216df3
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migrazione degli utenti di Lync Online a Lync locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Questi passaggi sono necessari solo per la migrazione degli account utente originariamente abilitati per Lync in Lync Online, prima di distribuire Lync in locale. Per spostare gli utenti originariamente abilitati per Lync in locale, successivamente spostati in Lync Online, vedere <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</A>.<BR>Inoltre, tutti gli utenti spostati devono disporre di account in Active Directory locale.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrazione degli account utente originariamente abilitati in Lync Online a Lync in locale

1.  Prima di tutto, assicurarsi che l'organizzazione sia configurata per l'ambiente ibrido.
    
      - Installare lo strumento di sincronizzazione di Azure Active Directory. Per ulteriori informazioni, vedere <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Per consentire agli utenti di utilizzare Single Sign-on per Lync Online, installare Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.
    
      - Nella distribuzione locale, in Lync Server Management Shell, digitare i seguenti cmdlet per creare il provider di hosting per Lync Online:
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Verificare che nei server perimetrali locali sia presente la catena di certificati che consente la connessione a Lync Online, come illustrato nella tabella seguente. È possibile scaricare questa catena qui:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Certificato</th>
    <th>Archivio certificati</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>Autorità di certificazione radice attendibile</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (nuovo certificato CA)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine auth CA2 (nuovo CA2 di emissione)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    </tbody>
    </table>

3.  In Active Directory locale, abilitare gli account utente coinvolti per Lync in locale. È possibile eseguire questa operazione per un singolo utente digitando il cmdlet seguente:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    In alternativa, è possibile creare uno script che consenta di leggere i nomi utente da un file e di visualizzarli come input per il cmdlet Enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Eseguire DirSync per sincronizzare gli utenti di Lync Online con gli utenti locali di Lync aggiornati.

5.  Aggiornare alcuni record DNS per indirizzare tutto il traffico SIP a Lync locale:
    
      - Aggiornare **lyncdiscover.contoso.com** un record in modo che punti al nome di dominio completo del server proxy inverso locale.
    
      - Aggiornare il ***\_SIP *.\_ tls.contoso.com** SRV record da risolvere nell'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.
    
      - Aggiornare il ***\_sipfederationtls *.\_ tcp.contoso.com** SRV record da risolvere nell'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.
    
      - Se nell'organizzazione viene utilizzato Split DNS (a volte denominato "Split Brain DNS"), assicurarsi che gli utenti che desiderano risolvere i nomi tramite la zona DNS interna vengano indirizzati al pool Front end.

6.  Digitare il `Get-CsUser` cmdlet per controllare alcune proprietà degli utenti da spostare. Si desidera verificare che l'HostingProviderProxyFQDN sia impostato su `"sipfed.online.lync.com"` e che gli indirizzi SIP siano impostati correttamente.

7.  Spostare gli utenti di Lync online in Lync locale.
    
    Per spostare un singolo utente, digitare il comando seguente:
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    È possibile spostare più utenti utilizzando il cmdlet **Get-CsUSer** con il parametro – Filter per selezionare gli utenti che dispongono di una proprietà specifica. Ad esempio, è possibile selezionare tutti gli utenti di Lync Online filtrando per {provider di hosting-EQ "sipfed.online.lync.om"}. È quindi possibile eseguire il piping degli utenti restituiti al cmdlet **Move-CsUSer** , come illustrato di seguito.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL del pool in cui è in esecuzione il servizio di migrazione ospitata, nel formato seguente *:\<https://FQDN\>del pool/HostedMigration/hostedmigrationService.svc*.
    
    È possibile determinare l'URL del servizio di migrazione ospitata visualizzando l'URL del pannello di controllo di Lync Online per l'account dell'organizzazione di Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-organization"></a>Per determinare l'URL del servizio di migrazione ospitata per l'organizzazione di Office 365
    
    1.  Accedere all'organizzazione di Office 365 come amministratore.
    
    2.  Aprire l'interfaccia di **amministrazione di Lync**.
    
    3.  Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**. Un URL di esempio è simile al seguente:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Sostituire **WebDir** nell'URL con l' **amministratore**, ottenendo quanto segue:
        
        `https://admin0a.online.lync.com`
    
    5.  Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.
        
        L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe essere simile al seguente:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > La dimensione massima predefinita per i file di registro delle transazioni del database di rtcxds è 16 GB. Potrebbe non essere sufficiente se si sta spostando un numero elevato di utenti contemporaneamente, soprattutto se è stato abilitato il mirroring. Per aggirare questo è possibile aumentare le dimensioni del file o eseguire il backup dei file di registro regolarmente. Per ulteriori informazioni, vedere <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.

    
    </div>

8.  Questo passo è facoltativo. Se è necessario eseguire l'integrazione con Exchange 2013 online, è necessario utilizzare un provider di hosting aggiuntivo. Per informazioni dettagliate, vedere [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Gli utenti sono ora spostati. Per verificare che un utente disponga di valori corretti per gli attributi illustrati nella tabella seguente, digitare questo cmdlet:
    
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
    <th>Attributo di Active Directory</th>
    <th>Nome attributo</th>
    <th>Valore corretto per l'utente di Lync Online</th>
    <th>Valore corretto per gli utenti di Lync in-premises</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>Provider dihosting</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>Abilitato</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Ogni utente che è stato spostato dovrà disconnettersi da Lync, quindi eseguire nuovamente l'accesso. Quando eseguono l'accesso, devono verificare gli elenchi di contatti e aggiungere i contatti, se necessario.
    
    Tenere presente che le riunioni pianificate non vengono migrate da Lync Online a Lync in locale. Gli utenti dovranno ripianificare queste riunioni dopo essere state spostate.
    
    Dopo l'aggiornamento dei record DNS e tutti gli utenti in locale, l'attributo provider dihosting indirizza l'utente Lync a utilizzare i record SRV o a indirizzarli al provider online "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

