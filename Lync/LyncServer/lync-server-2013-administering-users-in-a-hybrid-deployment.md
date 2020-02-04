---
title: 'Lync Server 2013: amministrazione degli utenti in una distribuzione ibrida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e416901fd5a98ffa3974c29e469eef2b6f4cb783
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-29_

È possibile gestire le impostazioni utente e i criteri per gli utenti migrati a Lync Online usando le caratteristiche di gestione utente disponibili nel portale di Microsoft Office 365 online. Per eseguire attività di amministrazione, è necessario accedere con l'account di amministratore del tenant.

<div>

## <a name="moving-users-back-to-on-premises"></a>Spostamento degli utenti di nuovo in locale

<div class="">


> [!IMPORTANT]  
> Questa sezione si applica solo agli utenti creati e abilitati per Lync locale e quindi spostati da una distribuzione locale a Lync Online. Se si vogliono spostare gli utenti creati in Lync Online (e non sempre abilitati per Lync in una distribuzione locale), vedere <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">spostamento di utenti da Lync Online a Lync locale in Lync Server 2013</A>.



</div>

  - Eseguire i cmdlet seguenti per trasferire di nuovo un utente da Lync Online a Lync locale:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL per il pool in cui è in uso il servizio di migrazione ospitata, con il formato seguente:

Https://\<FQDN\>del pool/HostedMigration/hostedmigrationService.svc. Per determinare l'URL del servizio di migrazione ospitata, è possibile visualizzare l'URL del pannello di controllo di Lync Online dell'account del tenant di Office 365.

**Per determinare l'URL del servizio di migrazione ospitata per il tenant di Office 365**

1.  Accedere al tenant di Office 365 come amministratore.

2.  Aprire l'interfaccia di **amministrazione di Lync**.

3.  Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**. Un URL di esempio ha un aspetto simile al seguente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Sostituire **WebDir** nell'URL con l' **amministratore**, con il risultato seguente:
    
    `https://admin0a.online.lync.com`

5.  Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe avere un aspetto simile al seguente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

