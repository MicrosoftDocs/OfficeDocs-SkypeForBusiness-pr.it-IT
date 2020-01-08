---
title: Rimuovere pool Front End o server Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a3b08d6e8b4f0b792063b19a47889de11283c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>Rimuovere pool Front End o server Standard Edition

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Questo argomento illustra il processo di rimozione di un pool Front-end o di un server front-end Standard Edition. Quando si rimuove un pool Front-End, si rimuove ogni server front-end che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un server front-end Standard Edition, è necessario rimuovere la definizione di SQL Store da generatore di topologie.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>Per rimuovere un pool di server front-end

1.  Aprire Generatore di topologie.

2.  Passare al nodo Lync Server 2010.

3.  Espandere pool di **front-end Enterprise Edition**, espandere il pool Front-End, fare clic con il pulsante destro del mouse sul pool Front-end che si desidera rimuovere e quindi scegliere **Elimina**.

4.  Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Per rimuovere un server front-end Standard Edition

1.  Aprire Generatore di topologie.

2.  Passare al nodo Lync Server 2010.

3.  Espandere i **server front-end Standard Edition**, fare clic con il pulsante destro del mouse sul server front-end che si desidera rimuovere e quindi scegliere **Elimina**.

4.  Espandere **Archivi SQL**, fare clic con il pulsante destro del mouse sul database di SQL Server associato al server front-end Standard Edition e quindi scegliere **Elimina**.
    
    <div>
    

    > [!IMPORTANT]  
    > È necessario rimuovere la definizione dei database di SQL Server collocati dal server front-end Standard Edition.

    
    </div>

5.  Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.

</div>

</div>

<span> </span>

</div>

</div>

</div>

