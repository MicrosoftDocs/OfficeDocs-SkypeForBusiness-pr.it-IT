---
title: 'Lync Server 2013: eliminare un oggetto contatto telefonico di area comune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98702f392020586b546d2db89fe6355923b47f67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="a562b-102">Eliminare un oggetto contatto telefonico di area comune in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a562b-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a562b-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a562b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a562b-104">È possibile che si desideri eliminare l'oggetto contatto associato a un telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="a562b-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="a562b-105">Ad esempio, se si rimuove il telefono da una sala per i dipendenti, non è necessario che un oggetto contatto sia associato a tale telefono.</span><span class="sxs-lookup"><span data-stu-id="a562b-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="a562b-106">Il cmdlet **Remove-CsCommonAreaPhone** consente di eliminare gli account telefonici delle aree comuni.</span><span class="sxs-lookup"><span data-stu-id="a562b-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="a562b-107">Quando si esegue questo cmdlet, il telefono viene eliminato dall'elenco dei telefoni delle aree comuni restituiti da **Get-CsCommonAreaPhone**.</span><span class="sxs-lookup"><span data-stu-id="a562b-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="a562b-108">Inoltre, l'oggetto contatto associato a tale telefono viene eliminato da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a562b-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="a562b-109">Utilizzare **Remove-CsCommonAreaPhone** per rimuovere un telefono di area comune o tutti i telefoni delle aree comuni che dispongono di un elemento comune, ad esempio un nome visualizzato o un paese e un prefisso.</span><span class="sxs-lookup"><span data-stu-id="a562b-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="a562b-110">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a562b-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a562b-111">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="a562b-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="a562b-112">Rimozione di un telefono di area comune specificato</span><span class="sxs-lookup"><span data-stu-id="a562b-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="a562b-113">Il comando seguente rimuove il telefono di area comune con l'indirizzo SIP sip:mainlobby@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="a562b-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="a562b-114">Rimozione dei telefoni delle aree comuni in base al nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="a562b-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="a562b-115">Questo comando consente di rimuovere tutti i telefoni delle aree comuni in cui il nome visualizzato include il valore stringa "Building 14":</span><span class="sxs-lookup"><span data-stu-id="a562b-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="a562b-116">Rimozione dei telefoni delle aree comuni in base ai rispettivi codici di paese e area</span><span class="sxs-lookup"><span data-stu-id="a562b-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="a562b-117">Questo comando consente di rimuovere tutti i telefoni delle aree comuni per gli Stati Uniti (codice paese 1) e il prefisso di area 425:</span><span class="sxs-lookup"><span data-stu-id="a562b-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="a562b-118">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="a562b-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a562b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a562b-119">See Also</span></span>


[<span data-ttu-id="a562b-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="a562b-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

