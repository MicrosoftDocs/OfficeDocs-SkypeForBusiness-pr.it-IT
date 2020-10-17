---
title: 'Lync Server 2013: creare un account di autenticazione Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e63b339f9a8d9705af47d9226adde88fe2d053
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507513"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Creare un account di autenticazione Kerberos in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-01-02_

Per eseguire correttamente questa procedura, è necessario essere connessi al server o al dominio almeno come membri del gruppo Domain Admins.

È possibile creare account di autenticazione Kerberos per ogni sito oppure creare un singolo account di autenticazione Kerberos e utilizzarlo per tutti i siti. È possibile utilizzare i cmdlet di Windows PowerShell per creare e gestire gli account, tra cui l'identificazione degli account assegnati a ogni sito. Il generatore di topologie e il pannello di controllo di Lync Server 2013 non visualizzano gli account di autenticazione Kerberos. Utilizzare la procedura seguente per creare uno o più account utente da utilizzare per l'autenticazione Kerberos.

<div>

## <a name="to-create-a-kerberos-account"></a>Per creare un account Kerberos

1.  Come membri del gruppo Domain Admins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire il comando seguente dalla riga di comando:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Ad esempio:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Verificare che l'oggetto Computer sia stato creato. A tale scopo aprire Utenti e computer di Active Directory, espandere il contenitore **Utenti** e quindi verificare che l'oggetto Computer per l'account utente sia presente nel contenitore.

</div>

</div>

<span> </span>

</div>

</div>

</div>

