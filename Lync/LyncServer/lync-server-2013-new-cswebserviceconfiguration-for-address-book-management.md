---
title: 'Lync Server 2013: New-CsWebServiceConfiguration per la gestione della Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccc4eafd9fd7db6173b14c17b44218c122ad01b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="1e58a-102">New-CsWebServiceConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e58a-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e58a-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1e58a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1e58a-p101">Chi può eseguire questo cmdlet: per impostazione predefinita, sono autorizzati a eseguire localmente il cmdlet New-CsWebServiceConfiguration i membri dei gruppi seguenti: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli di Controllo dell'accesso basato sui ruoli (RBAC) a cui tale cmdlet è stato assegnato, inclusi i ruoli RBAC personalizzati creati personalmente, al prompt di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1e58a-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="1e58a-p102">Il cmdlet New-CsWebServiceConfiguration definisce una nuova configurazione per i servizi Web nell'organizzazione. L'ambito per la configurazione dei servizi Web può essere solo a livello di sito o di servizio. Non è possibile creare una nuova configurazione di servizi Web a livello globale. Per la Rubrica è di particolare interesse l'attributo EnableGroupExansion. Se impostato su True, i servizi Web possono rispondere alle richieste di espansione dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="1e58a-p102">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization. The scope for the Web Services configuration can only be at the site or service level. It cannot create a new Web Services configuration at the global level. Specifically of interest to the Address Book is the EnableGroupExansion attribute. If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="1e58a-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1e58a-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="1e58a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e58a-112">See Also</span></span>


[<span data-ttu-id="1e58a-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="1e58a-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

