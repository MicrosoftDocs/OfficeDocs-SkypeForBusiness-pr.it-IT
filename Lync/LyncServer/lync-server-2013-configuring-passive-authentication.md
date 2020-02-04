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
ms.openlocfilehash: 0a2e52f957a8aba7e69e97b0ec2100ffbc5a190c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Configurazione dell'autenticazione passiva di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-11_

La sezione seguente descrive come configurare Lync Server 2013 con aggiornamenti cumulativi: luglio 2013 per supportare l'autenticazione passiva. Una volta abilitata, agli utenti di Lync abilitati per l'autenticazione a due fattori sarà richiesto di usare una smart card fisica o virtuale e un PIN valido per accedere con Lync 2013 con gli aggiornamenti cumulativi: client di luglio 2013.

<div class="">


> [!NOTE]  
> È consigliabile che i clienti consentano l'autenticazione passiva per il registrar e i servizi Web a livello di servizio. Se l'autenticazione passiva è abilitata per i servizi di registrazione e Web a livello globale, probabilmente si verificheranno errori di autenticazione a livello di organizzazione per gli utenti che non accedono con Lync 2013 con gli aggiornamenti cumulativi: client desktop client di luglio 2013.



</div>

<div>

## <a name="web-service-configuration"></a>Configurazione del servizio Web

I passaggi seguenti descrivono come creare una configurazione di servizio Web personalizzata per direttori, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva.

**Per creare una configurazione di un servizio Web personalizzato**

1.  Accedere a Lync Server 2013 con gli aggiornamenti cumulativi: luglio 2013 front end server con un account di amministratore di Lync.

2.  Avviare Lync Server 2013 Management Shell.

3.  Dalla riga di comando di Lync Server Management Shell creare una nuova configurazione del servizio Web per ogni Director, pool Enterprise e server Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > Il valore per l'FQDN di WsFedPassiveMetadataUri è il nome del servizio federativo del server ADFS 2,0. Il valore nome servizio federativo può essere trovato nella console di gestione di ADFS 2,0 facendo clic con il pulsante destro del mouse su <STRONG>servizio</STRONG> dal riquadro di spostamento e quindi selezionando <STRONG>modifica proprietà servizio federativo</STRONG>.

    
    </div>

4.  Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando seguente:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferibile per l'autenticazione webticket. Per tutti i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disabilitati in servizi Web Lync eseguendo il comando seguente:
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Verificare che tutti gli altri tipi di autenticazione siano stati correttamente disabilitati eseguendo il comando seguente:
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Configurazione proxy

Quando l'autenticazione dei certificati è disabilitata per i servizi Web Lync, il client Lync utilizzerà un tipo di autenticazione meno consigliato, ad esempio Kerberos o NTLM, per eseguire l'autenticazione nel servizio registrar. L'autenticazione del certificato è ancora necessaria per consentire al client Lync di recuperare un ticket, ma Kerberos e NTLM devono essere disabilitati per il servizio registrar.

I passaggi seguenti descrivono come creare una configurazione proxy personalizzata per i pool di Edge, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.

**Per creare una configurazione proxy personalizzata**

1.  Dalla riga di comando di Lync Server Management Shell creare una nuova configurazione proxy per ogni Lync Server 2013 con aggiornamenti cumulativi: luglio 2013 Edge pool, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva eseguendo il comandi seguenti:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Verificare che tutti gli altri tipi di autenticazione proxy siano stati correttamente disabilitati eseguendo il comando seguente:
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

