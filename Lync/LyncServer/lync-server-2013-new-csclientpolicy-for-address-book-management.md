---
title: 'Lync Server 2013: New-CsClientPolicy per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf1f7ebe085fc11d23381db9d1c474c79403d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ab633-102">New-CsClientPolicy per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab633-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab633-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ab633-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ab633-104">Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire il cmdlet New-CsClientPolicy: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab633-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="ab633-105">Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo (RBAC) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ab633-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="ab633-106">Il cmdlet New-CsClientPolicy definisce un numero elevato di impostazioni per il provisioning dei client per le funzionalità disponibili in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab633-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="ab633-107">Per il servizio Rubrica, il parametro AddressBookAvailability è di interesse.</span><span class="sxs-lookup"><span data-stu-id="ab633-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="ab633-108">Questo parametro, che ha un impatto diretto sulle opzioni disponibili per i client, ha tre possibili opzioni:</span><span class="sxs-lookup"><span data-stu-id="ab633-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="ab633-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="ab633-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="ab633-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="ab633-110">WebSearchOnly</span></span>

  - <span data-ttu-id="ab633-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="ab633-111">FileDownloadOnly</span></span>

<span data-ttu-id="ab633-112">Quando definito, determina il modo in cui la Rubrica viene accessibile dai client.</span><span class="sxs-lookup"><span data-stu-id="ab633-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="ab633-113">Se si definisce questo parametro, è necessario definire una delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="ab633-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="ab633-114">Se non si modifica questa impostazione, il valore predefinito di WebSearchAndFileDownload rimane attivo.</span><span class="sxs-lookup"><span data-stu-id="ab633-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="ab633-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ab633-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="ab633-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab633-116">See Also</span></span>


[<span data-ttu-id="ab633-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="ab633-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

