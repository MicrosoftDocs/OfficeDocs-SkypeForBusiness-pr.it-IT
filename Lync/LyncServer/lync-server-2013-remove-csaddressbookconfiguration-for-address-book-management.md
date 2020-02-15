---
title: Remove-CsAddressBookConfiguration per la gestione della Rubrica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsAddressBookConfiguration for Address Book management
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48184258
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d87010bc17fb400edb861c8e6ea55a40ad50c7fd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="c9808-102">Remove-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9808-102">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9808-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c9808-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c9808-p101">Chi può eseguire questo cmdlet: per impostazione predefinita, sono autorizzati a eseguire localmente il cmdlet Remove-CsAddressBookConfiguration i membri dei gruppi seguenti: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di Controllo dell'accesso basato sui ruoli (RBAC) a cui tale cmdlet è stato assegnato, inclusi i ruoli RBAC personalizzati creati personalmente, al prompt di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c9808-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

<span data-ttu-id="c9808-106">Come indica il nome, Remove-CsAddressBookConfiguration rimuoverà la configurazione in base all'identità di sito definita.</span><span class="sxs-lookup"><span data-stu-id="c9808-106">As the name implies, Remove-CsAddressBookConfiguration will remove the configuration based on the defined Site Identity.</span></span>

<span data-ttu-id="c9808-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c9808-107">For example:</span></span>

    Remove-CsAddressBookConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="c9808-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9808-108">See Also</span></span>


<span data-ttu-id="c9808-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c9808-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

