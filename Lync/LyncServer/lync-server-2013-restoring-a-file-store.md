---
title: 'Lync Server 2013: ripristino di un archivio di file'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc9f1bae4e1a9a84815e576267a15155bec227da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="72ac4-102">Ripristino di un archivio di file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72ac4-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72ac4-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="72ac4-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="72ac4-104">Gli archivi di file per l'edizione standard si trovano in genere nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="72ac4-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="72ac4-105">Gli archivi di file per Enterprise Edition si trovano in genere in un file server o un cluster.</span><span class="sxs-lookup"><span data-stu-id="72ac4-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="72ac4-106">La procedura seguente descrive come ripristinare un archivio di file.</span><span class="sxs-lookup"><span data-stu-id="72ac4-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="72ac4-107">Per ripristinare un archivio di file</span><span class="sxs-lookup"><span data-stu-id="72ac4-107">To restore a File Store</span></span>

1.  <span data-ttu-id="72ac4-108">Se un archivio di file non riesce, copiare l'archivio di file\\ appropriato da $backup nella posizione dell'archivio file nel server file server o Standard Edition e quindi condividere la cartella.</span><span class="sxs-lookup"><span data-stu-id="72ac4-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72ac4-109">Il percorso e il nome file dell'archivio file ripristinato devono essere esattamente gli stessi dell'archivio di file di cui è stato eseguito il backup, in modo che i componenti che usano i file possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="72ac4-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="72ac4-110">Se necessario, imposta gli elenchi di controllo di accesso (ACL) per l'archivio di file.</span><span class="sxs-lookup"><span data-stu-id="72ac4-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="72ac4-111">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="72ac4-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72ac4-112">È necessario eseguire questo passaggio solo se non è stato altrimenti eseguito Generatore di topologie durante il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="72ac4-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

