---
title: 'Lync Server 2013: ripristino di un archivio file'
description: 'Lync Server 2013: ripristino di un archivio file.'
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
ms.openlocfilehash: 201c4b20f224fa3a25e931689e564410c60143e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543832"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a>Ripristino di un archivio file in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-18_

Gli archivi di file per Standard Edition in genere si trovano nel server Standard Edition. Gli archivi file per Enterprise Edition si trovano in genere in un file server o in un cluster. Nella procedura seguente viene descritto come ripristinare un archivio file.

<div>

## <a name="to-restore-a-file-store"></a>Per ripristinare un archivio file

1.  Se un archivio file ha esito negativo, copiare l'archivio file appropriato da $Backup \\ al percorso dell'archivio file nel server file server o Standard Edition e quindi condividere la cartella.
    
    <div>
    

    > [!IMPORTANT]  
    > Il percorso e il nome del file dell'archivio file ripristinato devono essere identici a quelli dell'archivio file di cui è stato eseguito il backup, in modo che i componenti che utilizzano i file possano accedervi.

    
    </div>

2.  Se necessario, impostare gli elenchi di controllo di accesso (ACL, Access Control List) per l'archivio file. Nella riga di comando digitare il comando seguente:
    
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

