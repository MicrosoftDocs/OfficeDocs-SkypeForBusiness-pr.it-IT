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
ms.openlocfilehash: 88c2cbeb3ff4b9f75a0bce77543e8094ba8a7a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508833"
---
# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="2bce4-102">New-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bce4-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bce4-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2bce4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2bce4-p101">Utenti autorizzati a eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet New-CsAddressBookConfiguration: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di controllo di accesso basato sui ruoli a cui è assegnato questo cmdlet (inclusi eventuali ruoli del controllo di accesso basato sui ruoli creati personalmente), al prompt di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2bce4-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="2bce4-p102">Il cmdlet New-CsAddressBookConfiguration crea una nuova configurazione per la gestione del comportamento della Rubrica. Il cmdlet, in particolare, è in grado di definire se la Rubrica può creare i file di download del client, come e se utilizzare regole di normalizzazione, per quanto tempo conservare i file delta e delta compatti, nonché di definire la dimensione del file delta prima di incorporare una nuova creazione di file completa, l'ora di creazione della Rubrica del file completo e l'intervallo di sincronizzazione delle informazioni nel database degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2bce4-p102">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book. Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="2bce4-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2bce4-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="2bce4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bce4-109">See Also</span></span>


[<span data-ttu-id="2bce4-110">New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="2bce4-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

