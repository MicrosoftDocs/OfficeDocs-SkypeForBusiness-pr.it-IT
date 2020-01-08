---
title: 'Lync Server 2013: Assegnare un account di autenticazione Kerberos a un sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb755f7e7b814d4ca643bd04ddfc0241b4d96d60
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40974141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Assegnare un account di autenticazione Kerberos a un sito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-04-18_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.

Dopo aver creato l'account Kerberos, è necessario assegnarlo a un sito. Si tratta di un sito di Lync Server 2013 e non di un sito di Active Directory. È possibile creare più account di autenticazione Kerberos per ogni distribuzione, ma è possibile assegnare un solo account a un sito. Usare la procedura seguente per assegnare un account di autenticazione Kerberos creato in precedenza a un sito. Per informazioni dettagliate sulla creazione dell'account Kerberos, vedere [creare un account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Per assegnare un account di autenticazione Kerberos a un sito

1.  Come membro del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o in un computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

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
    > Devi specificare il parametro UserAccount usando il formato dominio\utente. Il formato User@Domain. Extension non è supportato per il riferimento agli oggetti computer creati per scopi di autenticazione Kerberos.

    
    </div>

4.  **Facoltativo**: è possibile che sia stato configurato un nome FQDN (Fully Qualified Domain Name) di override per i servizi Web, come per [modificare l'URL di Microsoft Services in Lync Server 2013](lync-server-2013-change-the-web-services-url.md). In questo caso, è necessario aggiungere un nome SPN anche per questo nome di dominio completo. Ad esempio, se il nome di dominio completo era WebServices. contoso. local, si eseguirebbe:
    
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

