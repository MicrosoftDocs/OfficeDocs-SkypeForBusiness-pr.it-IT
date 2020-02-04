---
title: Connettere il pool pilota ai server legacy di Edge Server
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
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server legacy di Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-29_

Dopo la distribuzione di Lync Server 2013, è necessario configurare una route federativo per il sito. Per usare la route federata usata da Lync Server 2010, è necessario configurare Lync Server 2013 per usare questa route.

Per consentire al sito di Lync Server 2013 di usare il Director e il server perimetrale della distribuzione di Lync Server 2010, usare generatore di topologie per associare il pool di Edge legacy.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di Edge legacy tramite Generatore di topologia

1.  Aprire **Generatore di topologie**.

2.  Selezionare il sito, che si trova direttamente sotto il nodo **Lync Server** .

3.  Nel menu **azioni** fare clic su **modifica proprietà**.

4.  Nel riquadro sinistro selezionare **Route federativo**.

5.  In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare il director di Lync Server 2010 o Lync Server 2010 Edge Server se non è elencato alcun amministratore.
    
    ![Modifica proprietà - Pagina Route di federazione](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifica proprietà - Pagina Route di federazione")  

6.  Fare clic su **OK** per chiudere la pagina **modifica proprietà** .

7.  In Generatore di topologia, nel nodo Lync Server 2013, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

8.  In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**.

9.  Nell'elenco selezionare il server perimetrale legacy.
    
    ![Finestra di dialogo Modifica proprietà - Selezione del server perimetrale legacy](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Selezione del server perimetrale legacy")  

10. Fare clic su **OK** per chiudere la pagina **modifica proprietà** .

11. In **Generatore di topologie**selezionare il nodo di primo livello, **Lync Server**.

12. Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.

13. Al termine della **pubblicazione guidata** , fare clic su **fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

