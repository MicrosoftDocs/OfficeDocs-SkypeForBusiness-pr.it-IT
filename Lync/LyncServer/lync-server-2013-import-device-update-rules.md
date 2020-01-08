---
title: 'Lync Server 2013: importare le regole di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cef7e14806a1f4c7853d157d0c4ce304583b9720
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="03db2-102">Importare le regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03db2-102">Import Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03db2-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="03db2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="03db2-104">Le regole di aggiornamento dei dispositivi possono essere importate solo usando Windows PowerShell e il cmdlet **Import-CsDeviceUpdate** .</span><span class="sxs-lookup"><span data-stu-id="03db2-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="03db2-105">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03db2-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03db2-106">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="03db2-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="03db2-107">Per importare le regole di aggiornamento del dispositivo in un singolo server Web</span><span class="sxs-lookup"><span data-stu-id="03db2-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="03db2-108">Il comando seguente importa le regole di aggiornamento dei dispositivi per il server Web atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="03db2-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="03db2-109">Per importare le regole di aggiornamento dei dispositivi in tutti i server Web</span><span class="sxs-lookup"><span data-stu-id="03db2-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="03db2-110">In questo esempio le regole di aggiornamento dei dispositivi vengono importate in tutti i server Web distribuiti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03db2-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="03db2-111">Affinché il comando funzioni, la cartella \\ \\ATL-FS-001.litwareinc.com\\gli aggiornamenti devono essere condivisi e disponibili per tutti i server Web.</span><span class="sxs-lookup"><span data-stu-id="03db2-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="03db2-112">Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) .</span><span class="sxs-lookup"><span data-stu-id="03db2-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03db2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03db2-113">See Also</span></span>


[<span data-ttu-id="03db2-114">Visualizzare informazioni sulle regole di aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03db2-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="03db2-115">Approvare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03db2-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

