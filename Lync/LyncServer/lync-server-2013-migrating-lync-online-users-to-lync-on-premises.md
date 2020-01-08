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

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migrazione degli utenti di Lync Online a Lync locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Questi passaggi sono necessari solo per la migrazione degli account utente inizialmente abilitati per Lync in Lync Online, prima di distribuire Lync locale. Per spostare gli utenti originariamente abilitati per Lync locale, in seguito spostati in Lync Online, vedere <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</A>.<BR>Inoltre, tutti gli utenti spostati devono avere account nell'Active Directory locale.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrazione degli account utente inizialmente abilitati in Lync Online a Lync locale

1.  Prima di tutto, assicurati che l'organizzazione sia configurata per Hybrid.
    
      - Installare lo strumento di sincronizzazione di Azure Active Directory. Per altre informazioni, vedere <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Per consentire agli utenti di usare Single Sign-on per Lync Online, installare Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.
    
      - Nella distribuzione locale, in Lync Server Management Shell, digitare i cmdlet seguenti per creare il provider di hosting per Lync Online:
        
           ```
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Verificare che in un server perimetrale locale sia disponibile la catena di certificati che consente la connessione a Lync Online, come illustrato nella tabella seguente. È possibile scaricare questa catena qui:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>Radice CyberTrust Baltimore</p></td>
    <td><p>CA radice attendibile</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (nuovo certificato CA)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT (nuova emissione di CA2)</p></td>
    <td><p>CA intermedia</p></td>
    </tr>
    </tbody>
    </table>

3.  In Active Directory locale abilitare gli account utente interessati per Lync locale. Puoi eseguire questa operazione per un singolo utente digitando il cmdlet seguente:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    In alternativa, è possibile creare uno script che legga i nomi utente da un file e li fornisca come input per il cmdlet Enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Eseguire DirSync per sincronizzare gli utenti di Lync Online con gli utenti locali di Lync aggiornati.

5.  Aggiornare alcuni record DNS per indirizzare tutto il traffico SIP a Lync locale:
    
      - Aggiornare **lyncdiscover.contoso.com** un record in cui puntare il nome di dominio completo del server proxy inverso locale.
    
      - Aggiornare il ***\_SIP *.\_ tls.contoso.com** SRV record per risolvere l'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.
    
      - Aggiornare il ***\_sipfederationtls *.\_ tcp.contoso.com** SRV record per risolvere l'indirizzo IP pubblico o VIP del servizio Access Edge di Lync locale.
    
      - Se l'organizzazione usa il DNS diviso (a volte denominato "Split-Brain DNS"), verificare che gli utenti che risolvono i nomi tramite la zona DNS interna vengano indirizzati al pool Front-end.

6.  Digitare il `Get-CsUser` cmdlet per verificare alcune proprietà relative agli utenti che verranno spostati. Si vuole verificare che HostingProviderProxyFQDN sia impostato su `"sipfed.online.lync.com"` e che gli indirizzi SIP siano impostati correttamente.

7.  Trasferire gli utenti di Lync online in Lync locale.
    
    Per trasferire un singolo utente, digitare:
    
       ```
       $cred = Get-Credential
       ```
    
       ```
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Puoi trasferire più utenti usando il cmdlet **Get-CsUSer** con il parametro – Filter per selezionare gli utenti con una specifica proprietà. Ad esempio, è possibile selezionare tutti gli utenti di Lync Online filtrando per {provider di hosting-EQ "sipfed.online.lync.om"}. È quindi possibile eseguire il piping degli utenti restituiti al cmdlet **Move-CsUSer** , come illustrato di seguito.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL per il pool in cui è in uso il servizio di migrazione ospitata, con il formato seguente: *https://\<FQDN\>del pool di/HostedMigration/hostedmigrationService.svc*.
    
    Per determinare l'URL del servizio di migrazione ospitata, è possibile visualizzare l'URL del pannello di controllo di Lync Online dell'account del tenant di Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Per determinare l'URL del servizio di migrazione ospitata per il tenant di Office 365
    
    1.  Accedere al tenant di Office 365 come amministratore.
    
    2.  Aprire l'interfaccia di **amministrazione di Lync**.
    
    3.  Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**. Un URL di esempio ha un aspetto simile al seguente:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Sostituire **WebDir** nell'URL con l' **amministratore**, con il risultato seguente:
        
        `https://admin0a.online.lync.com`
    
    5.  Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.
        
        L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe avere un aspetto simile al seguente:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Le dimensioni massime predefinite per i file di log delle transazioni del database rtcxds sono di 16 GB. Questo potrebbe non essere abbastanza grande se si sta spostando un numero elevato di utenti contemporaneamente, in particolare se è abilitato il mirroring. Per aggirare questo problema, è possibile aumentare le dimensioni del file o eseguire il backup dei file di log regolarmente. Per altre informazioni, vedere <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.

    
    </div>

8.  Questo è un passaggio facoltativo. Se è necessario integrarsi con Exchange 2013 online, è necessario usare un altro provider di hosting. Per informazioni dettagliate, vedere [configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Ora gli utenti vengono spostati. Per verificare che un utente disponga di valori corretti per gli attributi illustrati nella tabella seguente, digitare questo cmdlet:
    
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
    <th>Attributo Active Directory</th>
    <th>Nome attributo</th>
    <th>Valore corretto per l'utente di Lync Online</th>
    <th>Valore corretto per gli utenti di Lync in-locale</th>
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
    <td><p>Abilitata</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Ogni utente che è stato spostato dovrà disconnettersi da Lync, quindi accedere di nuovo. Quando accedono, dovrebbero verificare gli elenchi di contatti e aggiungere i contatti, se necessario.
    
    Tieni presente che le riunioni pianificate non vengono migrate da Lync Online a Lync locale. Gli utenti dovranno ripianificare queste riunioni dopo lo spostamento.
    
    Dopo che i record DNS vengono aggiornati e tutti gli utenti vengono indirizzati in locale, l'attributo provider dihosting indirizza l'utente di Lync a usare i record SRV o a indirizzarli al provider online "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

