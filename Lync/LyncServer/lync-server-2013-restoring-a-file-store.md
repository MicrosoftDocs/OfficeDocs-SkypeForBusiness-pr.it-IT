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

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Ripristino di un archivio di file in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-18_

Gli archivi di file per l'edizione standard si trovano in genere nel server Standard Edition. Gli archivi di file per Enterprise Edition si trovano in genere in un file server o un cluster. La procedura seguente descrive come ripristinare un archivio di file.

<div>

## <a name="to-restore-a-file-store"></a>Per ripristinare un archivio di file

1.  Se un archivio di file non riesce, copiare l'archivio di file\\ appropriato da $backup nella posizione dell'archivio file nel server file server o Standard Edition e quindi condividere la cartella.
    
    <div>
    

    > [!IMPORTANT]  
    > Il percorso e il nome file dell'archivio file ripristinato devono essere esattamente gli stessi dell'archivio di file di cui è stato eseguito il backup, in modo che i componenti che usano i file possano accedervi.

    
    </div>

2.  Se necessario, imposta gli elenchi di controllo di accesso (ACL) per l'archivio di file. Nella riga di comando digitare:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > È necessario eseguire questo passaggio solo se non è stato altrimenti eseguito Generatore di topologie durante il processo di ripristino.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

