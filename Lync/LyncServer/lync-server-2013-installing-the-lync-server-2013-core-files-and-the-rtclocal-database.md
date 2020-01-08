---
title: Installazione dei file di base di Lync Server 2013 e del database RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="be358-102">Installazione dei file di base di Lync Server 2013 e del database RTCLocal</span><span class="sxs-lookup"><span data-stu-id="be358-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be358-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="be358-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="be358-104">Per installare i file principali di Lync Server 2013 in un computer, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="be358-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="be358-105">Il database RTCLocal viene installato automaticamente quando si installano i file di base.</span><span class="sxs-lookup"><span data-stu-id="be358-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="be358-106">Tieni presente che non è necessario installare SQL Server nei nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="be358-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="be358-107">In alternativa, SQL Server Express viene installato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="be358-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="be358-108">Per installare i file di base di Lync Server 2013 e il database di RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="be358-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="be358-109">Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="be358-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="be358-110">Nella finestra della console digitare il comando seguente e quindi premere INVIO, usando il percorso appropriato per i file di configurazione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="be358-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="be358-111">Per verificare che i componenti di base di Lync Server siano stati installati correttamente, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="be358-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="be358-112">In Lync Server 2013 Management Shell digitare il comando di Windows PowerShell seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="be358-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="be358-113">La prima volta che si esegue questo comando non vengono restituiti dati perché non sono ancora stati configurati i computer dei nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="be358-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="be358-114">Purché il comando venga eseguito senza restituire un errore, è possibile supporre che la configurazione del server Lync sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="be358-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="be358-115">Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando seguente per verificare l'installazione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="be358-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="be358-116">Verranno ricevute informazioni simili a quelle seguenti, a seconda del numero di criteri PIN (Personal Identification Number) configurati per l'uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="be358-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="be358-117">Se vengono visualizzate informazioni sui criteri PIN, significa che sono stati installati correttamente i componenti principali.</span><span class="sxs-lookup"><span data-stu-id="be358-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

