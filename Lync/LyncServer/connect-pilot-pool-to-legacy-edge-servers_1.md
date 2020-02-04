---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09858b03c787af034790c94bcbf12ca6ea7ceecf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server legacy di Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Dopo la distribuzione di Lync Server 2013, una route federativa per il sito non è configurata. Per usare la route federata usata da Office Communications Server 2007 R2, è necessario configurare Lync Server 2013 per l'uso della route.

Per consentire al sito di Lync Server 2013 di usare il Director e il server perimetrale di BackCompatSite, usare generatore di topologie per associare il pool di Edge legacy.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di Edge legacy tramite Generatore di topologia

1.  Aprire la topologia del pool di piloti in Generatore di topologia.

2.  Selezionare il sito di Lync Server 2013.

3.  Nel menu **azione** fare clic su **modifica proprietà**.

4.  In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare Office Communications Server 2007 R2 Director o Office Communications Server 2007 R2 Edge Server se non è elencato alcun amministratore.
    
    ![Finestra di dialogo Modifica proprietà - Pagina Route di federazione](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Pagina Route di federazione")  

5.  Fare clic su **OK** per chiudere la pagina **modifica proprietà** .

6.  In Generatore di topologia, nel nodo Lync Server 2013, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

7.  In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**.

8.  Nell'elenco selezionare l'interfaccia Edge Server per BackCompatSite.
    
    ![Finestra di dialogo Modifica proprietà - Pagina Generale](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Pagina Generale")  

9.  Fare clic su **OK** per chiudere la pagina **modifica proprietà** .

10. In **Generatore di topologie**selezionare il nodo di primo livello, **Lync Server**.

11. Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.

12. Al termine della **pubblicazione guidata** , fare clic su **fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

