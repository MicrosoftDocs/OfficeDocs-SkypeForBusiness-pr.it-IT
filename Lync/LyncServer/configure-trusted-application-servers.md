---
title: Configurare i server applicazioni attendibili
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40981385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurare i server applicazioni attendibili

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-11_

In un ambiente misto, se si crea un nuovo server applicazioni attendibile, è necessario impostare il pool di hop successivo come pool di Lync Server 2013. In un ambiente misto sia il pool legacy Lync Server 2010 che il pool Lync Server 2013 vengono visualizzati nell'elenco a discesa. La selezione del pool legacy non è supportata.

**Selezionare Lync Server 2013 come hop successivo quando si crea un server applicazioni attendibile**

1.  Aprire Generatore di topologie.

2.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili** e scegliere **nuovo pool di applicazioni attendibili**.

3.  Immettere il **nome di dominio completo del pool** di applicazioni attendibili e selezionare se si tratta di un server singolo o multiplo.

4.  Fare clic su **Avanti**.

5.  Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool di front end di Lync Server 2013.

6.  Fare clic su **fine**.

7.  Selezionare il nodo superiore **Lync Server** e scegliere **pubblica**dal menu **azione** .
    
    Verificare che il **pool di applicazioni attendibili** sia stato creato correttamente ed è associato al pool Front-end corretto.

</div>

<span> </span>

</div>

</div>

</div>

