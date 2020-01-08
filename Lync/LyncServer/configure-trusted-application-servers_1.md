---
title: Configurare i server applicazioni attendibili
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b28002e8bb060e9ac966121a419d8475b4828258
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40979471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurare i server applicazioni attendibili

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

In un ambiente misto, se si crea un nuovo server delle applicazioni attendibile dopo l'Unione della topologia legacy di Office Communications Server con Lync Server 2013 e si definisce un nuovo server applicazioni attendibile tramite Generatore di topologie, è necessario impostare il pool di hop successivo come un Pool di Lync Server 2013. In un ambiente Unito sia il pool legacy di Office Communications Server che il pool di Lync Server 2013 vengono visualizzati nell'elenco a discesa. La selezione del pool legacy *non* è supportata.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Per selezionare Lync Server 2013 come hop successivo quando si crea un server applicazioni attendibile

1.  Aprire una topologia esistente in Generatore di topologie.

2.  Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili** e scegliere **nuovo pool di applicazioni attendibili**.

3.  Immettere il **nome di dominio completo del pool** di applicazioni attendibili e scegliere se si tratta di una distribuzione a server singolo o a più server.

4.  Fare clic su **Avanti**.

5.  Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool di front end di Lync Server 2013.
    
    ![Definire la nuova finestra di dialogo pool di applicazioni attendibili](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "")  

6.  Fare clic su **fine**.

7.  Selezionare il nodo superiore **Lync Server** e scegliere **pubblica**dal riquadro **azioni** .

8.  Verificare che il **pool di applicazioni attendibili** sia stato creato correttamente ed è associato al pool Front-end corretto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

