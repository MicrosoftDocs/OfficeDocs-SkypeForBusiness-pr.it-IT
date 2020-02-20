---
title: Sincronizzare la password di un account di autenticazione Kerberos con IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 255c1035809b69d5de1bb5e08fc770dc9a6b1c4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Sincronizzare la password di un account di autenticazione Kerberos con IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2010-11-08_

Per eseguire correttamente questa procedura, è necessario essere connessi come utenti membri del gruppo RTCUniversalServerAdmins.

In un sito, i server front end, i server Standard Edition e gli amministratori possono utilizzare un account di autenticazione Kerberos allo scopo di autenticare le richieste al servizio servizi Web. Questa procedura consente di individuare ogni server che esegue i servizi Web in un sito a cui è stato assegnato un account Kerberos e di aggiornare le impostazioni di configurazione di Internet Information Services (IIS) per l'utilizzo dell'account Kerberos. Per ulteriori informazioni, vedere [impostare la password di un account di autenticazione Kerberos in un server di Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Per impostare e configurare una password per l'account di autenticazione Kerberos

1.  Eseguire l'accesso a un computer di origine, ad esempio fe01.contoso.com, come membri del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Dalla riga di comando di Lync Server Management Shell, eseguire i due comandi seguenti:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Ad esempio:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > Il nome del computer di origine e del computer di destinazione deve essere un nome di dominio completo (FQDN) del server. Non è possibile utilizzare l'FQDN del pool, a meno che il nome del pool non corrisponda al nome del computer utilizzato come origine o destinazione.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

