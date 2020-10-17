---
title: 'Lync Server 2013: Update-CsAddressBook per la gestione della Rubrica'
description: 'Lync Server 2013: Update-CsAddressBook per la gestione della Rubrica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adc7f94e2f31f64f6517b8cdf9bbcb0649f6c8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546242"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook per la gestione della Rubrica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Chi può eseguire questo cmdlet: per impostazione predefinita, sono autorizzati a eseguire localmente il cmdlet Update-CsAddressBook i membri dei gruppi seguenti: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di Controllo dell'accesso basato sui ruoli (RBAC) a cui tale cmdlet è stato assegnato, inclusi i ruoli RBAC personalizzati creati personalmente, al prompt di Windows PowerShell eseguire il comando seguente:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Il cmdlet Update-CsAddressBook sostituisce il comando **abserver.exe –syncNow** di Office Communications Server. Lo scopo del cmdlet è quello di avviare immediatamente una sincronizzazione anziché attendere l'intervallo di tempo pianificato. Il primo comando di esempio aggiorna tutte le rubriche dell'organizzazione. Il secondo aggiorna solo la rubrica associata al server definito.

<div>


> [!NOTE]  
> In Lync Server 2013, Lync Server User Replicator rileverà le modifiche da Active Directory e aggiornerà il database degli utenti di Lync Server in base a un intervallo configurato. Lync Server User Replicator propagherà rapidamente le modifiche apportate al database di RTCab senza che l'amministratore debba eseguire Update-CSAddressBook. Gli amministratori devono solo eseguire Update-CSAddressBook se il download dei file della Rubrica è abilitato.



</div>

Ad esempio:

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>Vedere anche


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

