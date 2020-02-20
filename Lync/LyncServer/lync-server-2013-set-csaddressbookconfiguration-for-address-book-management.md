---
title: 'Lync Server 2013: Set-CsAddressBookConfiguration per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5660a82aae2938ea7d1127943f0115d2b4def51b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="b1c4a-102">Set-CsAddressBookConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1c4a-102">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1c4a-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b1c4a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b1c4a-p101">Chi può eseguire questo cmdlet: per impostazione predefinita, sono autorizzati a eseguire localmente il cmdlet Set-CsAddressBookConfiguration i membri dei gruppi seguenti: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di Controllo dell'accesso basato sui ruoli (RBAC) a cui tale cmdlet è stato assegnato, inclusi i ruoli RBAC personalizzati creati personalmente, al prompt di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b1c4a-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="b1c4a-106">Set-CsAddressBookConfiguration è simile al cmdlet New-CsAddressBookConfiguration, con la differenza che viene utilizzato per modificare una configurazione esistente.</span><span class="sxs-lookup"><span data-stu-id="b1c4a-106">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="b1c4a-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b1c4a-107">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="b1c4a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1c4a-108">See Also</span></span>


[<span data-ttu-id="b1c4a-109">Set-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1c4a-109">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

