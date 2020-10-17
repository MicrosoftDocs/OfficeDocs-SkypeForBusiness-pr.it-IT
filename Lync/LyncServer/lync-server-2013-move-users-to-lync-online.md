---
title: 'Lync Server 2013: spostare gli utenti in Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 189bf46da6c6bdaa6749f899d2a672967680cc45
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500573"
---
# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Spostare gli utenti in Lync online in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-29_

Prima di avviare la migrazione degli utenti a Lync Online, è necessario eseguire il backup dei dati degli utenti associati agli account da spostare. Non tutti i dati dell'utente vengono spostati con l'account utente. Per informazioni, vedere [backup and Restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Eseguire la migrazione delle impostazioni utente a Lync Online

Le impostazioni utente vengono spostate con l'account utente. Alcune impostazioni locali non vengono spostate con l'account utente.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Spostamento di utenti pilota in Lync Online

Prima di iniziare a spostare gli utenti in Lync Online, potrebbe essere necessario spostare alcuni utenti pilota per confermare che l'ambiente sia configurato correttamente. È quindi possibile verificare che le funzionalità e i servizi di Lync funzionino come previsto prima di tentare di spostare altri utenti.

Per spostare un utente locale nel tenant di Lync Online, eseguire i cmdlet seguenti in Lync Server Management Shell, utilizzando le credenziali di amministratore per l'organizzazione Microsoft 365 o Office 365. Sostituire "username@contoso.com" con le informazioni per l'utente che si desidera spostare.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL del pool in cui è in esecuzione il servizio di migrazione ospitata, nel formato seguente: https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.

È possibile determinare l'URL del servizio di migrazione ospitata visualizzando l'URL del pannello di controllo di Lync Online per l'account dell'organizzazione Microsoft 365 o Office 365.

**Per determinare l'URL del servizio di migrazione ospitata per l'organizzazione**

1.  Accedere all'organizzazione Microsoft 365 o Office 365 come amministratore.

2.  Aprire l'interfaccia di **amministrazione di Lync**.

3.  Con l'interfaccia di **amministrazione di Lync** visualizzata, selezionare e copiare l'URL nella barra degli indirizzi fino a **Lync.com**. Un URL di esempio è simile al seguente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Sostituire **WebDir** nell'URL con l' **amministratore**, ottenendo quanto segue:
    
    `https://admin0a.online.lync.com`

5.  Aggiungere la stringa seguente all'URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    L'URL risultante, che è il valore di **HostedMigrationOverrideUrl**, dovrebbe essere simile al seguente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Spostamento degli utenti in Lync Online

È possibile spostare più utenti utilizzando il cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) con il parametro – Filter per selezionare gli utenti che dispongono di una proprietà specifica assegnata agli account utente, ad esempio RegistrarPool. È quindi possibile eseguire il piping degli utenti restituiti al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , come illustrato nell'esempio seguente.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

È inoltre possibile utilizzare il parametro – OU per recuperare tutti gli utenti nell'unità organizzativa specificata, come illustrato nell'esempio seguente.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Verificare le impostazioni e le caratteristiche dell'utente di Lync Online

È possibile verificare che l'utente sia stato spostato con esito positivo nei modi seguenti:

  - Visualizzare lo stato dell'utente nel pannello di controllo di Lync Online. L'indicatore visivo per gli utenti locali e gli utenti online è diverso.

  - Eseguire il cmdlet seguente:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

