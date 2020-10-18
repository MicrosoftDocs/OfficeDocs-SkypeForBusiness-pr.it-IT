---
title: Installazione dei file principali di Lync Server 2013 e del database di RTCLocal
description: Installazione dei file di base di Lync Server 2013 e del database di RTCLocal.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68964f8b80f6377afd859d113783d61e33afbebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573862"
---
# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="56164-103">Installazione dei file principali di Lync Server 2013 e del database di RTCLocal</span><span class="sxs-lookup"><span data-stu-id="56164-103">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56164-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="56164-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="56164-105">Per installare i file di base di Lync Server 2013 in un computer, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="56164-105">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="56164-106">Il database RTCLocal viene installato automaticamente con i file principali.</span><span class="sxs-lookup"><span data-stu-id="56164-106">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="56164-107">Si noti che non è necessario installare SQL Server nei nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="56164-107">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="56164-108">Al contrario, SQL Server Express viene installato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="56164-108">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="56164-109">Per installare i file di base di Lync Server 2013 e il database di RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="56164-109">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="56164-110">Nel computer del nodo Watcher fare clic su **Start**, scegliere **Tutti i programmi**, **Accessori**, quindi fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="56164-110">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="56164-111">Nella finestra della console digitare il comando seguente e quindi premere INVIO, utilizzando il percorso appropriato per i file di installazione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="56164-111">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="56164-112">Per verificare che i componenti di base di Lync Server siano stati installati correttamente, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="56164-112">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="56164-113">In Lync Server 2013 Management Shell, digitare il comando di Windows PowerShell seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="56164-113">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="56164-114">Quando si esegue questo comando per la prima volta, non viene restituito alcun dato perché non è ancora stato configurato alcun computer del nodo Wwatcher.</span><span class="sxs-lookup"><span data-stu-id="56164-114">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="56164-115">Se il comando viene eseguito senza restituire un errore, è possibile presumere che il programma di installazione di Lync Server sia stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="56164-115">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="56164-116">Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando riportato di seguito per verificare l'installazione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="56164-116">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="56164-117">Verranno restituite informazioni, a seconda del numero di criteri PIN configurati per l'uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="56164-117">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="56164-118">Se vengono restituite informazioni sui criteri PIN, i componenti principali sono stati correttamente installati.</span><span class="sxs-lookup"><span data-stu-id="56164-118">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

