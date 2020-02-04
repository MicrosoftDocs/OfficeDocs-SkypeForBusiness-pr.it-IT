---
title: 'Lync Server 2013: Aggiornamento-CsAddressBook per la gestione della Rubrica'
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
ms.openlocfilehash: f03fe225b2eae508870220e278d7bfc3373dad22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="211fc-102">Update-CsAddressBook per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211fc-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="211fc-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="211fc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="211fc-104">Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet Update-CsAddressBook: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="211fc-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="211fc-105">Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo (RBAC) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="211fc-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="211fc-106">Il cmdlet Update-CsAddressBook sostituisce il comando **ABServer. exe – syncNow** da Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="211fc-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="211fc-107">Lo scopo del cmdlet è quello di avviare immediatamente una sincronizzazione anziché aspettare l'ora pianificata.</span><span class="sxs-lookup"><span data-stu-id="211fc-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="211fc-108">Il primo comando di esempio aggiorna tutte le rubriche dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="211fc-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="211fc-109">Il secondo aggiorna solo la rubrica associata al server definito.</span><span class="sxs-lookup"><span data-stu-id="211fc-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="211fc-110">In Lync Server 2013 Lync Server User Replicator rileverà le modifiche da Active Directory e aggiornerà il database degli utenti di Lync Server in base a un intervallo configurato.</span><span class="sxs-lookup"><span data-stu-id="211fc-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="211fc-111">Lync Server User Replicator propagherà rapidamente le modifiche al database di RTCab senza che l'amministratore debba eseguire Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="211fc-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="211fc-112">Gli amministratori dovranno eseguire solo Update-CSAddressBook se è abilitato il download di file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="211fc-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="211fc-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="211fc-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="211fc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="211fc-114">See Also</span></span>


[<span data-ttu-id="211fc-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="211fc-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

