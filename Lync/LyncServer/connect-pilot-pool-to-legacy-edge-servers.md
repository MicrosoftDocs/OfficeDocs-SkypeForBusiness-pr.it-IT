---
title: Connettere il pool pilota ai server perimetrali legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02ceb7ecc6a80daf767ed6f675bdd4a92dcae9db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server perimetrali legacy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-29_

Dopo aver distribuito Lync Server 2013, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata da Lync Server 2010, è necessario che Lync Server 2013 sia configurato per l'utilizzo di questa route.

Per abilitare il sito Lync Server 2013 per l'utilizzo del server Director e Edge della distribuzione di Lync Server 2010, utilizzare Generatore di topologie per associare il pool perimetrale legacy.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di server perimetrali legacy tramite Generatore di topologie

1.  Aprire **Generatore di topologie**.

2.  Selezionare il sito, disponibile direttamente sotto il nodo **Lync Server**.

3.  Scegliere **Modifica proprietà** dal menu **Azioni**.

4.  Nel riquadro sinistro selezionare **Route di federazione**.

5.  In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare Lync Server 2010 Director o il server perimetrale di Lync Server 2010 se non è elencato alcun Director.
    
    ![Modifica proprietà, pagina Route di Federazione](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifica proprietà, pagina Route di Federazione")  

6.  Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **.

7.  In Generatore di topologie, nel nodo Lync Server 2013, passare al **Server Standard Edition** o **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

8.  In **Associazioni** selezionare la casella di controllo accanto ad **Associa pool di server perimetrali (per componenti multimediali)**.

9.  Selezionare il server perimetrale legacy nell'elenco.
    
    ![Finestra di dialogo Modifica proprietà, selezione del perimetro legacy](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Finestra di dialogo Modifica proprietà, selezione del perimetro legacy")  

10. Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **.

11. In  **Generatore di topologie ** selezionare il nodo di primo livello  **Lync Server**.

12. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.

13. Al termine della Pubblicazione guidata **** fare clic su  **Fine **.

</div>

</div>

<span> </span>

</div>

</div>

</div>

