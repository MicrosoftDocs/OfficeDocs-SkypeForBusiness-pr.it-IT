---
title: 'Lync Server 2013: creare o modificare un oggetto contatto per i dispositivi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bd3cfa6099d45cbad2d15ed164652756f50f5e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="e0aa6-102">Creare o modificare un oggetto contatto per i dispositivi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0aa6-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0aa6-103">_**Ultimo argomento modificato:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="e0aa6-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="e0aa6-104">Per creare un oggetto sala conferenze, creare innanzitutto un account utente di Active Directory per rappresentare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e0aa6-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="e0aa6-105">Utilizzare quindi il cmdlet **Enable-CsMeetingRoom** per consentire a tale account di funzionare come dispositivo per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e0aa6-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="e0aa6-106">Se è necessario modificare le proprietà di un dispositivo per i servizi di conferenza esistente, utilizzare il cmdlet **set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="e0aa6-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="e0aa6-107">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0aa6-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0aa6-108">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="e0aa6-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="e0aa6-109">Creazione di un dispositivo per conferenze</span><span class="sxs-lookup"><span data-stu-id="e0aa6-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="e0aa6-110">Dopo aver creato l'account utente di Active Directory che rappresenta il nuovo dispositivo per conferenze, abilitarlo utilizzando il cmdlet **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="e0aa6-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="e0aa6-111">Assicurarsi di includere a) l'identità del dispositivo per i servizi di conferenza, b) il pool di registrazione in cui verrà ospitata l'account della sala e c) l'indirizzo SIP da assegnare a quell'account.</span><span class="sxs-lookup"><span data-stu-id="e0aa6-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="e0aa6-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e0aa6-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="e0aa6-113">Modifica di un dispositivo per conferenze</span><span class="sxs-lookup"><span data-stu-id="e0aa6-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="e0aa6-114">Per modificare i valori delle proprietà di un dispositivo per i servizi di conferenza esistente, utilizzare il cmdlet **set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="e0aa6-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="e0aa6-115">Ad esempio, il seguente comando Aggiorna il numero di telefono (LineUri) associato a un dispositivo per conferenze:</span><span class="sxs-lookup"><span data-stu-id="e0aa6-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="e0aa6-116">Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e il cmdlet [set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="e0aa6-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

