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
ms.openlocfilehash: 86e71f87c20064e542aa6a8db1d9b38048c5f736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Sincronizzare la password di un account di autenticazione Kerberos con IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2010-11-08_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.

In un sito i server front-end, i server Standard Edition e gli amministratori possono usare un account di autenticazione Kerberos per l'autenticazione delle richieste al servizio servizi Web. Questa procedura consente di individuare ogni server che utilizza servizi Web in un sito a cui è stato assegnato un account Kerberos e di aggiornare le impostazioni di configurazione di Internet Information Services (IIS) per l'uso dell'account Kerberos. Per informazioni dettagliate, vedere [impostare la password di un account di autenticazione Kerberos in un server in Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Per impostare e configurare una password per l'account di autenticazione Kerberos

1.  Accedere a un computer di origine, ad esempio fe01.contoso.com, come membro del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando di Lync Server Management Shell eseguire i due comandi seguenti:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Ad esempio:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > Il nome del computer di origine e del computer di destinazione deve essere un nome di dominio completo (FQDN) del server. Non è possibile usare l'FQDN del pool a meno che il nome del pool non sia uguale al nome del computer in uso come computer di origine o di destinazione.

    
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

