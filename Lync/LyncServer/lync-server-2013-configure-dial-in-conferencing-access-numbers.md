---
title: 'Lync Server 2013: Configurare i numeri di accesso per le conferenze telefoniche con accesso esterno'
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
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="4b928-102">Configurare i numeri di accesso per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b928-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b928-103">_**Argomento Ultima modifica:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="4b928-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="4b928-104">Quando si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono effettuare la chiamata dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="4b928-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="4b928-105">I numeri di accesso per le connessioni in ingresso vengono visualizzati negli inviti alle riunioni e nella pagina Web delle impostazioni di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="4b928-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="4b928-106">Prima di poter creare numeri di accesso per la chiamata in ingresso, è necessario pianificare le aree dei servizi di conferenza telefonica con accesso esterno e quindi configurare i dial plan con le aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="4b928-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="4b928-107">Per informazioni dettagliate sulle aree geografiche, vedere Requisiti per i servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4b928-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="4b928-108">Per informazioni dettagliate sulla configurazione dei dial plan per i servizi di conferenza telefonica con accesso esterno, vedere Configurare i dial plan per i servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="4b928-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b928-109">Non è possibile usare un nuovo numero di accesso esterno finché non viene completata la replica di&nbsp;Active Directory Domain Services (ad DS).</span><span class="sxs-lookup"><span data-stu-id="4b928-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="4b928-110">La replica può richiedere diverse ore per il completamento.</span><span class="sxs-lookup"><span data-stu-id="4b928-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4b928-111">Dopo aver creato i numeri di accesso esterno, è possibile modificare il nome visualizzato per gli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto.</span><span class="sxs-lookup"><span data-stu-id="4b928-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="4b928-112">Usa il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="4b928-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="4b928-113">Non è consigliabile modificare manualmente gli oggetti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b928-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="4b928-114">Per informazioni dettagliate sulla modifica di un numero di accesso, vedere la documentazione di Lync Server Management Shell per il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4b928-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4b928-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4b928-115">In This Section</span></span>

[<span data-ttu-id="4b928-116">Creare o modificare un numero di accesso per una conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b928-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b928-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b928-117">See Also</span></span>


[<span data-ttu-id="4b928-118">Requisiti per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b928-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="4b928-119">Configurare dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b928-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

