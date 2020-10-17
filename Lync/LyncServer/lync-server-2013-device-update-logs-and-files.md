---
title: 'Lync Server 2013: file e registri di aggiornamento dei dispositivi'
description: 'Lync Server 2013: file e registri di aggiornamento dei dispositivi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50db4935f62a4c037ab81a0d11e1eb993466fa80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565992"
---
# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="db6ed-103">Registri e file degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db6ed-103">Device Update logs and files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db6ed-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="db6ed-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="db6ed-105">I registri degli aggiornamenti dei dispositivi contengono informazioni importanti che è possibile utilizzare per la gestione e la risoluzione dei problemi relativi al servizio Web aggiornamento dispositivi.</span><span class="sxs-lookup"><span data-stu-id="db6ed-105">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="db6ed-106">È possibile modificare le operazioni registrate e rimuovere i registri e gli aggiornamenti dei dispositivi che non si desiderano o che non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="db6ed-106">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="db6ed-107">In questa sezione viene descritto come utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per modificare le impostazioni di registrazione, cancellare il log degli aggiornamenti del dispositivo o rimuovere i file di registro dal server.</span><span class="sxs-lookup"><span data-stu-id="db6ed-107">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db6ed-108">Per informazioni dettagliate sui file di log degli aggiornamenti dei dispositivi, vedere <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">log file types and locations</A> in the Lync Server 2010 TechNet Library.</span><span class="sxs-lookup"><span data-stu-id="db6ed-108">For details about device update log files, see <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="db6ed-109">Si noti che il servizio Web aggiornamento dispositivi, come tutti i componenti di Lync Phone Edition, è compatibile con Lync Server 2013 come accade con Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="db6ed-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="db6ed-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="db6ed-110">In This Section</span></span>

  - [<span data-ttu-id="db6ed-111">Modificare le impostazioni per i file di log degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db6ed-111">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="db6ed-112">Eliminare i file di registro degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db6ed-112">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="db6ed-113">Rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo in rimuovere i file di aggiornamento dei dispositivi non associati a un dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db6ed-113">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

