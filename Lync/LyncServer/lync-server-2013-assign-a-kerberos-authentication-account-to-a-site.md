---
title: 'Lync Server 2013: assegnare un account di autenticazione Kerberos a un sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf69e71dd66337551557bddd3bfb7700257a7f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Assegnare un account di autenticazione Kerberos a un sito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-04-18_

Per eseguire correttamente questa procedura, è necessario essere connessi come utenti membri del gruppo RTCUniversalServerAdmins.

Dopo aver creato un account Kerberos, è necessario assegnarlo a un sito. Si tratta di un sito di Lync Server 2013, non di un sito di Active Directory. È possibile creare più account di autenticazione Kerberos per distribuzione, ma è possibile assegnare un solo account a un sito. Utilizzare la procedura seguente per assegnare a un sito un account di autenticazione Kerberos creato precedentemente. Per informazioni dettagliate sulla creazione dell'account Kerberos, vedere [creare un account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Per assegnare un account di autenticazione Kerberos a un sito

1.  Come membri del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Nella riga di comando eseguire i due comandi seguenti:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    Ad esempio:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > È necessario specificare il parametro UserAccount utilizzando il formato Dominio\Utente. Il formato Utente@Dominio.estensione non è supportato per fare riferimento agli oggetti computer creati per l'autenticazione Kerberos.

    
    </div>

4.  **Facoltativo**: è possibile che sia stata configurata una sostituzione FQDN (nome di dominio completo) per i servizi Web, in base alla [modifica dell'URL dei Services in Lync Server 2013](lync-server-2013-change-the-web-services-url.md). In tal caso, sarà necessario aggiungere anche un nome SPN per il nome di dominio completo. Ad esempio, se il nome di dominio completo è WebServices. contoso. local, è necessario eseguire le operazioni seguenti:
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

