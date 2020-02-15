---
title: Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2013 alla topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e57a7b062cd95012102ba30a527c99c2fba71d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2013 alla topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-07_

Microsoft Lync Server 2013 Survivable Branch Appliance (SBA) non può essere associato a un pool Front End di Microsoft Lync Server 2010 come registrar di backup. L'ASB deve essere associato a un pool Front End di Microsoft Lync Server 2013. In questa procedura si presuppone che Microsoft Lync Server 2013 SBA. Eseguire questa procedura nel sito centrale.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Per aggiungere siti di succursale con Microsoft Lync Server 2013 SBA alla propria topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nell'albero della console espandere il sito centrale, espandere **Siti di succursale** e quindi fare clic su **Nuovo sito di succursale**.

3.  Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare un nome per il nuovo sito di succursale.

4.  (Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.

5.  Fare clic su **Avanti**.

6.  (Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:
    
      - Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.
    
      - Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.
    
      - Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.

7.  Fare clic su **Avanti** e quindi eseguire una delle operazioni seguenti:
    
      - Se si utilizza un Survivable Branch Appliance o Survivable Branch Server in questo sito, accertarsi che la casella di controllo **Apri la procedura guidata nuovo Survivable Wizard al termine della procedura guidata** sia selezionata.
    
      - Se non si utilizza un Survivable Branch Appliance o Survivable Branch Server in questo sito, deselezionare la casella di controllo **aprire la procedura guidata nuovo Survivable Wizard quando la procedura guidata viene chiusa** .
    
      - Fare clic su **Fine** e quindi seguire le indicazioni fornite nella procedura guidata che verrà visualizzata. Per informazioni sugli elementi della procedura guidata, vedere [define a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Definire un Survivable Branch Appliance o un server di succursale in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definire un gateway PSTN per un sito di succursale in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

