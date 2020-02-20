---
title: Installazione dei file principali di Lync Server 2013 e del database di RTCLocal
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
ms.openlocfilehash: 17b3b1925607a80f143c57e6185c7a709b19ee0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="1daaf-102">Installazione dei file principali di Lync Server 2013 e del database di RTCLocal</span><span class="sxs-lookup"><span data-stu-id="1daaf-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1daaf-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1daaf-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1daaf-104">Per installare i file di base di Lync Server 2013 in un computer, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="1daaf-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="1daaf-105">Il database RTCLocal viene installato automaticamente con i file principali.</span><span class="sxs-lookup"><span data-stu-id="1daaf-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="1daaf-106">Si noti che non è necessario installare SQL Server nei nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="1daaf-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="1daaf-107">Al contrario, SQL Server Express viene installato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1daaf-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="1daaf-108">Per installare i file di base di Lync Server 2013 e il database di RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="1daaf-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="1daaf-109">Nel computer del nodo Watcher fare clic su **Start**, scegliere **Tutti i programmi**, **Accessori**, quindi fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="1daaf-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="1daaf-110">Nella finestra della console digitare il comando seguente e quindi premere INVIO, utilizzando il percorso appropriato per i file di installazione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1daaf-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="1daaf-111">Per verificare che i componenti di base di Lync Server siano stati installati correttamente, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1daaf-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="1daaf-112">In Lync Server 2013 Management Shell, digitare il comando di Windows PowerShell seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1daaf-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="1daaf-113">Quando si esegue questo comando per la prima volta, non viene restituito alcun dato perché non è ancora stato configurato alcun computer del nodo Wwatcher.</span><span class="sxs-lookup"><span data-stu-id="1daaf-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="1daaf-114">Se il comando viene eseguito senza restituire un errore, è possibile presumere che il programma di installazione di Lync Server sia stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1daaf-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="1daaf-115">Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando riportato di seguito per verificare l'installazione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1daaf-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="1daaf-116">Verranno restituite informazioni, a seconda del numero di criteri PIN configurati per l'uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="1daaf-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="1daaf-117">Se vengono restituite informazioni sui criteri PIN, i componenti principali sono stati correttamente installati.</span><span class="sxs-lookup"><span data-stu-id="1daaf-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

