---
title: 'Lync Server 2013: amministrazione degli utenti in una distribuzione ibrida'
description: 'Lync Server 2013: amministrazione degli utenti in una distribuzione ibrida.'
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
ms.openlocfilehash: 7f1d7684a9f56eb013574a985ded0313378621c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552992"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-29_

È possibile gestire le impostazioni utente e i criteri per gli utenti migrati in Lync Online utilizzando le funzionalità di gestione utente disponibili nell'interfaccia di amministrazione di Microsoft 365. Per eseguire le attività di amministrazione, è necessario accedere utilizzando l'account amministratore tenant.

<div>

## <a name="moving-users-back-to-on-premises"></a>Spostamento degli utenti in locale

<div class="">


> [!IMPORTANT]  
> Questa sezione si applica solo agli utenti che sono stati creati e abilitati per Lync in locale e quindi spostati da una distribuzione locale a Lync Online. Se si desidera spostare gli utenti creati in Lync Online (e non mai abilitati per Lync in una distribuzione locale), vedere <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">spostamento di utenti da Lync Online a Lync in locale in Lync Server 2013</A>.



</div>

  - Eseguire i cmdlet seguenti per spostare un utente da Lync Online di nuovo in Lync locale:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL del pool in cui è in esecuzione il servizio di migrazione ospitata, nel formato seguente:

Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc. È possibile determinare l'URL del servizio di migrazione ospitata visualizzando l'URL del pannello di controllo di Lync Online per l'account dell'organizzazione Microsoft 365 o Office 365.

**Per determinare l'URL del servizio di migrazione ospitata per l'organizzazione di Microsoft 365 o Office 365**

1.  Accedere all'organizzazione come amministratore.

2.  Aprire l'interfaccia di **amministrazione di Lync**.

3.  Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**. Un URL di esempio è simile al seguente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Sostituire **WebDir** nell'URL con l' **amministratore**, ottenendo quanto segue:
    
    `https://admin0a.online.lync.com`

5.  Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe essere simile al seguente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

