---
title: 'Lync Server 2013: configurare i numeri di accesso per le conferenze telefoniche in ingresso'
description: 'Lync Server 2013: configurare i numeri di accesso per le conferenze telefoniche con chiamata in ingresso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0edb3492c243b36b69c4b48df8c22adc4ece7999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565081"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="a69cd-103">Configurare i numeri di accesso per le conferenze telefoniche con chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69cd-103">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a69cd-104">_**Ultimo argomento modificato:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="a69cd-104">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="a69cd-105">Quando si distribuiscono le conferenze telefoniche con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono comporre dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="a69cd-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="a69cd-106">Questi numeri di accesso esterno vengono visualizzati negli inviti alle riunioni e nella pagina Web delle impostazioni per le conferenze telefoniche con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a69cd-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="a69cd-107">Prima di poter creare numeri di accesso esterno, è necessario prima di tutto pianificare le aree di audioconferenza e quindi configurare i dial plan con le aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="a69cd-107">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="a69cd-108">Per informazioni dettagliate sulle aree geografiche, vedere Servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a69cd-108">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="a69cd-109">Per informazioni dettagliate sulla configurazione dei dial plan per le conferenze telefoniche con accesso esterno, vedere [configurare dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="a69cd-109">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a69cd-110">Non è possibile utilizzare un nuovo numero di accesso esterno finché non viene completata la replica di servizi di dominio Active Directory (AD &nbsp; DS) del numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="a69cd-110">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="a69cd-111">La replica può richiedere diverse ore per il completamento.</span><span class="sxs-lookup"><span data-stu-id="a69cd-111">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a69cd-112">Dopo aver creato i numeri di accesso esterno, è possibile modificare il nome visualizzato per gli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto.</span><span class="sxs-lookup"><span data-stu-id="a69cd-112">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="a69cd-113">Utilizzare il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a69cd-113">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="a69cd-114">Non è necessario modificare gli oggetti di Active Directory manualmente.</span><span class="sxs-lookup"><span data-stu-id="a69cd-114">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="a69cd-115">Per informazioni dettagliate sulla modifica di un numero di accesso, vedere la documentazione di Lync Server Management Shell per il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a69cd-115">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a69cd-116">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a69cd-116">In This Section</span></span>

[<span data-ttu-id="a69cd-117">Creare o modificare un numero di accesso per le conferenze telefoniche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69cd-117">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a69cd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a69cd-118">See Also</span></span>


[<span data-ttu-id="a69cd-119">Requisiti per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69cd-119">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="a69cd-120">Configurare i dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a69cd-120">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

