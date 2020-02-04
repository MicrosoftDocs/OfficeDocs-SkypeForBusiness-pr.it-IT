---
title: 'Lync Server 2013: assegnare criteri a un telefono con area comune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e19e2fccabe4759f8cf4cf5eb55ade7e68e2b560
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="e407e-102">Assegnare criteri in Lync Server 2013 a un telefono con area comune</span><span class="sxs-lookup"><span data-stu-id="e407e-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e407e-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e407e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e407e-104">Dopo aver creato i criteri per i telefoni delle aree comuni (per informazioni dettagliate, vedere [creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), è possibile assegnare i criteri a un telefono con area comune tramite Windows PowerShell e il cmdlet **Grant-CS** appropriato.</span><span class="sxs-lookup"><span data-stu-id="e407e-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="e407e-105">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e407e-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e407e-106">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="e407e-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="e407e-107">Assegnazione di un criterio a un singolo telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="e407e-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="e407e-108">Con il comando seguente viene assegnato il criterio vocale per utente RedmondVoice al telefono per l'area comune con la sala d'identità Building 14.</span><span class="sxs-lookup"><span data-stu-id="e407e-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="e407e-109">Assegnazione di un criterio a più telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="e407e-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="e407e-110">In questo esempio, il criterio vocale per utente RedmondVoice viene assegnato a tutti i telefoni per l'area comune configurati per l'uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e407e-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="e407e-111">Per informazioni dettagliate, vedere gli argomenti della Guida relativi a [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="e407e-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e407e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e407e-112">See Also</span></span>


[<span data-ttu-id="e407e-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="e407e-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

