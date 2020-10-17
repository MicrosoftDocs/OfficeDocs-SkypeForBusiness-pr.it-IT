---
title: 'Lync Server 2013: rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo'
description: 'Lync Server 2013: rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8338f7274d1d27e2290d822324986238f4856fe4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553502"
---
# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="b3776-103">Rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3776-103">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3776-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b3776-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b3776-105">Ogni volta che sul sistema vengono caricati degli aggiornamenti dei dispositivi, viene creata una corrispondente regola di aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b3776-105">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="b3776-106">Per impostazione predefinita, queste nuove regole di aggiornamento dei dispositivi vengono assegnate allo stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="b3776-106">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="b3776-107">Questo significa che le regole possono essere scaricate e installate nei dispositivi di test, ma non nei dispositivi di produzione, che consentono di testare gli aggiornamenti prima di renderli disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b3776-107">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="b3776-108">In base ai test, è possibile accettare e distribuire o rifiutare ed eliminare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b3776-108">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="b3776-109">Quando si rifiuta un aggiornamento, l'aggiornamento del dispositivo è disassociato dalla regola di aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b3776-109">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="b3776-110">I file di aggiornamento dei dispositivi che non sono più associati a un dispositivo possono essere rimossi utilizzando Windows PowerShell e il cmdlet **Clear-CsDeviceUpdateFile** .</span><span class="sxs-lookup"><span data-stu-id="b3776-110">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="b3776-111">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3776-111">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3776-112">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="b3776-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="b3776-113">Ad esempio, il comando seguente rimuove tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com che non sono più associate a un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b3776-113">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="b3776-114">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .</span><span class="sxs-lookup"><span data-stu-id="b3776-114">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

