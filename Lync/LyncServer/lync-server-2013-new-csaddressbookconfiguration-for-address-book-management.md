---
title: 'Lync Server 2013: New-CsAddressBookConfiguration per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69c1ea9c68dfacb68ada70d4f7643b2777f062f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>New-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet New-CsAddressBookConfiguration: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo (RBAC) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

Il cmdlet New-CsAddressBookConfiguration crea una nuova configurazione per gestire il comportamento della Rubrica. Specifico di questo cmdlet è la possibilità di definire se il servizio Rubrica crea i file di download del client, come e se si usano le regole di normalizzazione, quanto tempo è necessario per mantenere i file Delta e Compact Delta, le dimensioni dei file delta prima di incorporare una nuova creazione di file completo, cosa ora del giorno viene creata la rubrica completa del file e l'interno dovrebbe essere per la sincronizzazione delle informazioni nel database degli utenti.

Ad esempio:

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a>Vedere anche


[New-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

