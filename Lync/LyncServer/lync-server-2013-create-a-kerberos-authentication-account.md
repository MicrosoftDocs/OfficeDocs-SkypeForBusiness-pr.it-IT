---
title: 'Lync Server 2013: Creare un account di autenticazione Kerberos'
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
ms.openlocfilehash: 797e9216aed5d523e39dc4827d630e0cb1b857fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Creare un account di autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-01-02_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio in minima parte come membro del gruppo Domain Admins.

È possibile creare account di autenticazione Kerberos per ogni sito oppure creare un singolo account di autenticazione Kerberos e usarlo per tutti i siti. Puoi usare i cmdlet di Windows PowerShell per creare e gestire gli account, incluso l'identificazione degli account assegnati a ogni sito. Il generatore di topologia e il pannello di controllo di Lync Server 2013 non visualizzano gli account di autenticazione Kerberos. Usare la procedura seguente per creare uno o più account utente da usare per l'autenticazione Kerberos.

<div>

## <a name="to-create-a-kerberos-account"></a>Per creare un account Kerberos

1.  Come membro del gruppo Domain Admins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o in un computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando eseguire il comando seguente:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Ad esempio:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Verificare che l'oggetto computer sia stato creato aprendo utenti e computer di Active Directory, espandere il contenitore **utenti** e quindi verificare che l'oggetto computer per l'account utente si trovi nel contenitore.

</div>

</div>

<span> </span>

</div>

</div>

</div>

