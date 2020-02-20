---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff045df8425b76a42edace4a6591f52566b8c9a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e8993-102">Test-CsAddressBookWebQuery per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8993-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8993-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e8993-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e8993-p101">Utenti autorizzati a eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet Test-CsAddressBookWebQuery: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di controllo di accesso basato sui ruoli (RBAC) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC creati personalmente), al prompt di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8993-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="e8993-p102">Analogamente alla transazione sintetica Test-CsAddressBookService, Test-CsAddressBookWebQuery invia una query al servizio Address Book Web Query per verificare che stia funzionando in modo corretto. Il cmdlet si connette al servizio di autenticazione Web Ticket e presenta le credenziali specificate in –UserCredential. Se l'autenticazione ha esito positivo, il cmdlet presenta quindi le informazioni –TargetSipAddress. Il cmdlet comunica l'esito positivo se è stato in grado di recuperare le informazioni sul contatto.</span><span class="sxs-lookup"><span data-stu-id="e8993-p102">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly. The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential. If authenticated, the cmdlet then present the –TargetSipAddress information. The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="e8993-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e8993-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="e8993-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8993-111">See Also</span></span>


[<span data-ttu-id="e8993-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="e8993-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

