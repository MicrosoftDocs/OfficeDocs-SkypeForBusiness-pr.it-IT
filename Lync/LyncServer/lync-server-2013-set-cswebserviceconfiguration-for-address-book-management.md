---
title: 'Lync Server 2013: Set-CsWebServiceConfiguration per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52c10e3a0a405b7f437573325470f48d38ecd931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="0b8dd-102">Set-CsWebServiceConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b8dd-102">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b8dd-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0b8dd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0b8dd-p101">Chi può eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire il cmdlet Set-CsWebServiceConfiguration in locale: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di controllo di accesso basati sui ruoli a cui è stato assegnato questo cmdlet, inclusi tutti gli eventuali ruoli di controllo di accesso basati sui ruoli creati personalmente, eseguire il comando seguente al prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0b8dd-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

<span data-ttu-id="0b8dd-106">Il cmdlet Set-CsWebServiceConfiguration consente all'amministratore di ridefinire un attributo esistente nella configurazione dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="0b8dd-106">The Set-CsWebServiceConfiguration cmdlet allows the administrator to redefine an existing attribute in the configuration of the Web Services.</span></span>

<span data-ttu-id="0b8dd-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b8dd-107">For example:</span></span>

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a><span data-ttu-id="0b8dd-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b8dd-108">See Also</span></span>


[<span data-ttu-id="0b8dd-109">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="0b8dd-109">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

