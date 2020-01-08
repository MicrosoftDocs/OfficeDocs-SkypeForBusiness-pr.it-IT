---
title: 'Lync Server 2013: Impostare la password di un account di autenticazione Kerberos in un server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc4eefe4c1ef804b1deb06d056bfbd61ade35eb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Impostare la password di un account di autenticazione Kerberos in un server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-01-16_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.

È necessario configurare una password nell'account Kerberos per ogni sito che dispone di server front-end, server Standard Edition e direttori. È possibile configurare la password eseguendo il cmdlet **Set-CsKerberosAccountPassword** di Windows PowerShell in un server del sito, ad esempio un server front-end. Per ogni sito, è necessario eseguire il cmdlet **Set-CsKerberosAccountPassword** . Il cmdlet configura Internet Information Services (IIS) per il servizio servizi Web e quindi imposta la password nell'account del computer in servizi di dominio Active Directory. Un metodo alternativo, in base al parametro usato con il cmdlet, configura IIS su un server durante l'uso di un altro server configurato come origine della password dell'account Kerberos.

Quando si usa il cmdlet **Set-CsKerberosAccountPassword** per impostare una password, Kerberos imposta la password su una stringa generata in modo casuale. Questo cmdlet Contatta tutte le istanze di IIS in tutti i siti centrali di Lync Server 2013 a cui è assegnato l'account.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Per impostare una password per un account di autenticazione Kerberos

1.  Accedere a qualsiasi computer di dominio con Lync Server Management Shell installato come membro del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando eseguire i due comandi seguenti:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Ad esempio:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Devi specificare il parametro UserAccount usando il formato dominio\utente. Il formato User@Domain. Extension non è supportato per fare riferimento agli oggetti computer creati per scopi di autenticazione Kerberos.

    
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

