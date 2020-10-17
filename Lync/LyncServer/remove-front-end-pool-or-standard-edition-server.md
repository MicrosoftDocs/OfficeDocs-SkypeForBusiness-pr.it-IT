---
title: Rimuovere pool Front End o server Standard Edition
description: Rimuovere il pool Front end o il server Standard Edition.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c878d56b073558f4f4b50f31b6742fd581c80241
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570242"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Rimuovere pool Front End o server Standard Edition

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

In questo argomento vengono illustrate le procedure per la rimozione di un pool Front end o di un front end server Standard Edition. Quando si rimuove un pool Front End, è necessario rimuovere ogni front end server che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un front end server Standard Edition, è necessario rimuovere la definizione dell'archivio SQL da generatore di topologie.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>Per rimuovere un pool di Font End Server

1.  Apre lo strumento di generazione topologia

2.  Passare al nodo Lync Server 2010.

3.  Espandere Pool **Enterprise Edition front end**, espandere il pool Front End, fare clic con il pulsante destro del mouse sul pool Front end che si desidera rimuovere e quindi scegliere **Elimina**.

4.  Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Per rimuovere un server Standard Edition Front End Server

1.  Apre lo strumento di generazione topologia

2.  Passare al nodo Lync Server 2010.

3.  Espandere **Standard Edition Front End Server**, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.

4.  Espandere **Archivi SQL**, fare clic con il pulsante destro del mouse sul database di SQL Server associato al front end server Standard Edition e quindi scegliere **Elimina**.
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario rimuovere la definizione dei database di SQL Server collocati dal front end server Standard Edition.

    
    </div>

5.  Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

</div>

<span> </span>

</div>

</div>

</div>

