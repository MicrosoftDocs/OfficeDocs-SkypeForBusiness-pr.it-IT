---
title: "Lync Server 2013: impostare una password dell'account di autenticazione Kerberos in un server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20229f7bbc600b6a54bf28b13b9d5c14e8cbeb28
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510043"
---
# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Impostare la password di un account di autenticazione Kerberos in un server di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-01-16_

Per eseguire correttamente questa procedura è necessario accedere come utente membro del gruppo RTCUniversalServerAdmins.

È necessario impostare una password sull'account Kerberos per ogni sito che dispone di Front End Server, server Standard Edition e Director. È possibile impostare la password eseguendo il cmdlet **Set-CsKerberosAccountPassword**di   Windows PowerShell in un server del sito, ad esempio un front end server. Per ogni sito, è necessario eseguire il cmdlet **Set-CsKerberosAccountPassword**   . Il cmdlet configura Internet Information Services (IIS) per il servizio servizi Web e quindi imposta la password per l'account del computer in servizi di dominio Active Directory. Un metodo alternativo, basato sul parametro utilizzato con il cmdlet, consente di configurare IIS in un unico server utilizzando un altro server configurato come origine per la password dell'account Kerberos.

Quando si usa il cmdlet **Set-CsKerberosAccountPassword** per impostare una password, Kerberos imposta la password su una stringa generata in modo casuale. Questo cmdlet consente di contattare tutte le istanze di IIS in tutti i siti centrali di Lync Server 2013 a cui è assegnato questo account.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Per impostare una password per un account di autenticazione Kerberos

1.  Accedere a qualsiasi computer del dominio in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Nella riga di comando eseguire i due comandi seguenti:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Ad esempio:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > È necessario specificare il parametro UserAccount nel formato Dominio\Utente. Il formato Utente@Dominio.estensione non è supportato per fare riferimento a oggetti computer creati ai fini dell'autenticazione Kerberos.

    
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

