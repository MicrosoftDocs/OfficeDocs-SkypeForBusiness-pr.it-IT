---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c477c9c899847b1dec28fe70a9b749761dc43689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="10c02-102">Test-CsAddressBookWebQuery per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10c02-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10c02-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="10c02-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="10c02-104">Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire il cmdlet Test-CsAddressBookWebQuery: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="10c02-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="10c02-105">Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo (RBAC) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="10c02-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="10c02-106">In modo analogo alla transazione sintetica Test-CsAddressBookService, Test-CsAddressBookWebQuery esegue una query sulla query Web Rubrica per verificare che funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="10c02-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="10c02-107">Il cmdlet si connette all'autenticazione del ticket web e presenta le credenziali specificate in-UserCredential.</span><span class="sxs-lookup"><span data-stu-id="10c02-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="10c02-108">Se autenticato, il cmdlet presenta le informazioni-TargetSipAddress.</span><span class="sxs-lookup"><span data-stu-id="10c02-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="10c02-109">Il cmdlet deve segnalare il successo se è stato in grado di recuperare le informazioni sul contatto.</span><span class="sxs-lookup"><span data-stu-id="10c02-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="10c02-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="10c02-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="10c02-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10c02-111">See Also</span></span>


[<span data-ttu-id="10c02-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="10c02-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

