---
title: "Lync Server 2013: configurazione dell'autenticazione passiva"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 780b539aeaf6a6bc6956fc5f8b6185092675632b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532493"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a>Configurazione dell'autenticazione passiva di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-11_

Nella sezione seguente viene descritto come configurare Lync Server 2013 con aggiornamenti cumulativi: luglio 2013 per supportare l'autenticazione passiva. Una volta abilitata, gli utenti di Lync abilitati per l'autenticazione a due fattori saranno tenuti a utilizzare una smart card fisica o virtuale e un PIN valido per accedere utilizzando Lync 2013 con aggiornamenti cumulativi: client di luglio 2013.

<div class="">


> [!NOTE]  
> È consigliabile che i clienti consentano l'autenticazione passiva per i servizi di registrazione e Web a livello di servizio. Se l'autenticazione passiva è abilitata per i servizi Web e di registrazione a livello globale, è probabile che si verifichino errori di autenticazione a livello dell'organizzazione per gli utenti che non accedono con Lync 2013 con gli aggiornamenti cumulativi: client desktop client di luglio 2013.



</div>

<div>

## <a name="web-service-configuration"></a>Configurazione del servizio Web

Nella procedura seguente viene descritto come creare una configurazione del servizio Web personalizzata per i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.

**Per creare una configurazione del servizio Web personalizzato**

1.  Accedere al Lync Server 2013 con gli aggiornamenti cumulativi: luglio 2013 front end server utilizzando un account di amministratore di Lync.

2.  Avviare Lync Server 2013 Management Shell.

3.  Dalla riga di comando di Lync Server Management Shell creare una nuova configurazione del servizio Web per ogni Director, pool Enterprise e server Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando riportato di seguito:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > Il valore dell'FQDN di WsFedPassiveMetadataUri è il nome del servizio federativo del server AD FS 2,0. Il valore nome servizio federativo può essere trovato nella console di gestione AD FS 2,0 facendo clic con il pulsante destro del mouse su <STRONG>servizio</STRONG> dal riquadro di spostamento e quindi selezionando <STRONG>modifica proprietà servizio federativo</STRONG>.

    
    </div>

4.  Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando riportato di seguito:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferibile per l'autenticazione webticket. Per tutti i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disattivati nei servizi Web Lync eseguendo il comando seguente:
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Verificare che tutti gli altri tipi di autenticazione siano stati disabilitati eseguendo il comando riportato di seguito:
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Configurazione del proxy

Quando l'autenticazione dei certificati è disabilitata per i servizi Web di Lync, il client Lync utilizzerà un tipo di autenticazione meno preferito, ad esempio Kerberos o NTLM, per eseguire l'autenticazione nel servizio di registrazione. L'autenticazione dei certificati è ancora necessaria per consentire al client Lync di recuperare un ticket, tuttavia Kerberos e NTLM devono essere disattivati per il servizio di registrazione.

Nella procedura seguente viene descritto come creare una configurazione proxy personalizzata per i pool di server perimetrali, i pool Enterprise e gli Standard Edition che verranno abilitati per l'autenticazione passiva.

**Per creare una configurazione proxy personalizzata**

1.  Dalla riga di comando di Lync Server Management Shell creare una nuova configurazione proxy per ogni Lync Server 2013 con aggiornamenti cumulativi: luglio 2013 Edge pool, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva tramite l'esecuzione dei seguenti comandi:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Verificare che tutti gli altri tipi di autenticazione proxy siano stati disabilitati eseguendo il comando riportato di seguito:
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

