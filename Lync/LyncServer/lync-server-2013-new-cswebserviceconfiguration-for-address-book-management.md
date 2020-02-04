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
ms.openlocfilehash: 434c9a7c4ded9516cd930bbaa9bba72873b15a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8b041-102">New-CsWebServiceConfiguration per la gestione della Rubrica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b041-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b041-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8b041-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8b041-104">Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet New-CsWebServiceConfiguration: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8b041-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="8b041-105">Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo (RBAC) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8b041-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="8b041-106">Il cmdlet New-CsWebServiceConfiguration definisce una nuova configurazione per i servizi Web nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b041-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="8b041-107">L'ambito per la configurazione dei servizi Web può essere a livello di sito o di servizio.</span><span class="sxs-lookup"><span data-stu-id="8b041-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="8b041-108">Non è possibile creare una nuova configurazione dei servizi Web a livello globale.</span><span class="sxs-lookup"><span data-stu-id="8b041-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="8b041-109">In particolare di interesse per la Rubrica è l'attributo EnableGroupExansion.</span><span class="sxs-lookup"><span data-stu-id="8b041-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="8b041-110">Se impostato su true, i servizi Web possono rispondere alle richieste di espansione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="8b041-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="8b041-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8b041-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="8b041-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b041-112">See Also</span></span>


[<span data-ttu-id="8b041-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b041-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

