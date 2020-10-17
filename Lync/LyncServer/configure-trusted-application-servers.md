---
title: Configurare i server applicazioni attendibili
description: Configurare i server applicazioni attendibili.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39f439ea3e5996e0a3464540069024b70c415e3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548822"
---
# <a name="configure-trusted-application-servers"></a>Configurare i server applicazioni attendibili

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-11_

In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool dell'hop successivo come pool di Lync Server 2013. In un ambiente misto, sia il pool di Lync Server 2010 legacy che il pool di Lync Server 2013 vengono visualizzati nell'elenco a discesa. La selezione del pool legacy non è supportata.

**Selezionare Lync Server 2013 come hop successivo durante la creazione di un server applicazioni attendibile**

1.  Apre lo strumento di generazione topologia

2.  Nel riquadro di sinistra fare clic con il pulsante destro del mouse su **Server applicazioni attendibili** e quindi scegliere **Nuovo pool di applicazioni attendibili**.

3.  Immettere il nome FQDN del pool di applicazioni attendibili in **FQDN pool** e specificare se sarà un pool a server singolo o a più server.

4.  Fare clic su **Avanti**.

5.  Nell'elenco nella pagina **selezionare l'hop successivo** selezionare il pool Front End di Lync Server 2013.

6.  Fare clic su **Fine**.

7.  Selezionare il nodo principale **Lync Server** e nel menu **Azioni** selezionare **Pubblica**.
    
    Verificare che il **Pool di applicazioni attendibili** sia stato creato correttamente e sia associato al pool Front End corretto.

</div>

<span> </span>

</div>

</div>

</div>

