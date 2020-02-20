---
title: 'Lync Server 2013: ripristino di un archivio file'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 409d22b6a0c2d762e39603a1c8eda5ce11cb5433
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="c1837-102">Ripristino di un archivio file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1837-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1837-103">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="c1837-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="c1837-104">Gli archivi di file per Standard Edition in genere si trovano nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c1837-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="c1837-105">Gli archivi file per Enterprise Edition si trovano in genere in un file server o in un cluster.</span><span class="sxs-lookup"><span data-stu-id="c1837-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="c1837-106">Nella procedura seguente viene descritto come ripristinare un archivio file.</span><span class="sxs-lookup"><span data-stu-id="c1837-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="c1837-107">Per ripristinare un archivio file</span><span class="sxs-lookup"><span data-stu-id="c1837-107">To restore a File Store</span></span>

1.  <span data-ttu-id="c1837-108">Se un archivio file ha esito negativo, copiare l'archivio file\\ appropriato da $backup al percorso dell'archivio file nel server file server o Standard Edition e quindi condividere la cartella.</span><span class="sxs-lookup"><span data-stu-id="c1837-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1837-109">Il percorso e il nome del file dell'archivio file ripristinato devono essere identici a quelli dell'archivio file di cui è stato eseguito il backup, in modo che i componenti che utilizzano i file possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="c1837-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="c1837-110">Se necessario, impostare gli elenchi di controllo di accesso (ACL, Access Control List) per l'archivio file.</span><span class="sxs-lookup"><span data-stu-id="c1837-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="c1837-111">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c1837-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1837-112">È necessario eseguire questo passaggio solo se non è stato altrimenti eseguito Generatore di topologie durante il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="c1837-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

