---
title: 'Lync Server 2013: cmdlet del server della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35106634d9ad9dbc8c4a044aad42d50081cd1e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="22f26-102">Cmdlet del server della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22f26-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f26-103">_**Ultimo argomento modificato:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="22f26-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="22f26-104">I server della Rubrica sono intermediari tra servizi di dominio Active Directory e Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22f26-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="22f26-105">Il server della Rubrica garantisce che le informazioni utente archiviate in Lync Server 2013 siano sincronizzate con le informazioni utente archiviate in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22f26-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="22f26-106">A tale scopo, i file della Rubrica vengono sincronizzati periodicamente con le informazioni archiviate nel database utenti.</span><span class="sxs-lookup"><span data-stu-id="22f26-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="22f26-107">A sua incirca, Lync Server include una serie di cmdlet per la gestione dei server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="22f26-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="22f26-108">Address Book Server Cmdlets</span><span class="sxs-lookup"><span data-stu-id="22f26-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="22f26-109">Non è possibile configurare le impostazioni del server della Rubrica nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22f26-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="22f26-110">Windows PowerShell è lo strumento principale per la gestione di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="22f26-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="22f26-111">Viene riportato di seguito un elenco di cmdlet direttamente correlati alla gestione dei server della Rubrica:</span><span class="sxs-lookup"><span data-stu-id="22f26-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="22f26-112">**Server della Rubrica**</span><span class="sxs-lookup"><span data-stu-id="22f26-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="22f26-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="22f26-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="22f26-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="22f26-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="22f26-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="22f26-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="22f26-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="22f26-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="22f26-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22f26-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22f26-121">See Also</span></span>


[<span data-ttu-id="22f26-122">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="22f26-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

