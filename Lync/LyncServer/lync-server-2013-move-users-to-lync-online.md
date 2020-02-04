---
title: 'Lync Server 2013: trasferire utenti in Lync Online'
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
ms.openlocfilehash: da56c7230f35d2f900f51b53beef98c64d1e750a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Trasferire utenti a Lync online in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-29_

Prima di iniziare la migrazione degli utenti a Lync Online, è consigliabile eseguire il backup dei dati degli utenti associati agli account da spostare. Non tutti i dati degli utenti vengono spostati con l'account utente. Per informazioni, vedere [requisiti di backup e ripristino in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Eseguire la migrazione delle impostazioni utente in Lync Online

Le impostazioni utente vengono spostate con l'account utente. Alcune impostazioni locali non vengono spostate con l'account utente.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Spostamento degli utenti pilota in Lync Online

Prima di iniziare a trasferire utenti in Lync Online, è consigliabile trasferire alcuni utenti pilota per verificare che l'ambiente sia configurato correttamente. Puoi quindi verificare che le caratteristiche e i servizi di Lync funzionino come previsto prima di tentare di trasferire altri utenti.

Per trasferire un utente locale nel tenant di Lync Online, eseguire i cmdlet seguenti in Lync Server Management Shell usando le credenziali di amministratore per il tenant di Microsoft Office 365. Sostituire "username@contoso.com" con le informazioni per l'utente che si desidera trasferire.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Il formato dell'URL specificato per il parametro **HostedMigrationOverrideUrl** deve essere l'URL per il pool in cui è in uso il servizio di migrazione ospitata, con il formato\<seguente:\>https://FQDN del pool/HostedMigration/hostedmigrationService.svc.

Per determinare l'URL del servizio di migrazione ospitata, è possibile visualizzare l'URL del pannello di controllo di Lync Online dell'account del tenant di Office 365.

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

<div>

## <a name="moving-users-to-lync-online"></a>Spostamento degli utenti in Lync Online

Puoi trasferire più utenti usando il cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) con il parametro – Filter per selezionare gli utenti con una specifica proprietà assegnata agli account utente, ad esempio RegistrarPool. È quindi possibile eseguire il piping degli utenti restituiti al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , come illustrato nell'esempio seguente.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Puoi anche usare il parametro – OU per recuperare tutti gli utenti nell'UO specificata, come illustrato nell'esempio seguente.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Verificare le impostazioni e le caratteristiche degli utenti di Lync Online

È possibile verificare che l'utente sia stato spostato correttamente nei modi seguenti:

  - Visualizzare lo stato dell'utente nel pannello di controllo di Lync Online. L'indicatore visivo per gli utenti locali e gli utenti online è diverso.

  - Eseguire il cmdlet seguente:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

