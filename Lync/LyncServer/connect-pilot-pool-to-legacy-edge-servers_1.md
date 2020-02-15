---
title: Connettere il pool pilota ai server perimetrali legacy
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
ms.openlocfilehash: 7f39f3444c0d660a1ed73da566df6b5b348171f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connettere il pool pilota ai server perimetrali legacy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Dopo la distribuzione di Lync Server 2013, non è configurata una route di federazione per il sito. Per utilizzare la route federata utilizzata da Office Communications Server 2007 R2, è necessario che Lync Server 2013 sia configurato per l'utilizzo di questa route.

Per abilitare il sito di Lync Server 2013 per l'utilizzo del server Director e Edge di BackCompatSite, utilizzare Generatore di topologie per associare il pool perimetrale legacy.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Per associare il pool di server perimetrali legacy tramite Generatore di topologie

1.  Aprire la topologia del pool pilota in Generatore tipologie

2.  Selezionare il sito Lync Server 2013.

3.  Scegliere  **Modifica proprietà ** dal menu  **Azioni **.

4.  In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare il Director di Office Communications Server 2007 R2 o il server perimetrale di Office Communications Server 2007 R2 se non è elencato alcun Director.
    
    ![Finestra di dialogo Modifica proprietà, pagina Route di Federazione](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina Route di Federazione")  

5.  Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **.

6.  In Generatore di topologie, nel nodo Lync Server 2013, passare al **Server Standard Edition** o **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

7.  In  **Associazioni ** selezionare la casella di controllo accanto ad  **Associa pool di server perimetrali (per componenti multimediali) **.

8.  Nell'elenco, selezionare l'interfaccia del server perimetrale per BackCompatSite.
    
    ![Finestra di dialogo Modifica proprietà, pagina generale](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina generale")  

9.  Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **.

10. In  **Generatore di topologie ** selezionare il nodo di primo livello  **Lync Server**.

11. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.

12. Al termine della Pubblicazione guidata **** fare clic su  **Fine **.

</div>

</div>

<span> </span>

</div>

</div>

</div>

