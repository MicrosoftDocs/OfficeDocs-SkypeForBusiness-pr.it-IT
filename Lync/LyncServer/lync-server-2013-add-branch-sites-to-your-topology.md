---
title: 'Lync Server 2013: aggiungere siti di succursale alla topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d4e024ed5cdb29bb8a8a4170b89399f955254bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Aggiungere siti di succursale alla topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

I siti di succursale rappresentano le succursali fisiche connesse alle sedi principali tramite un collegamento WAN. Per aggiungere un sito di succursale alla topologia di Lync, eseguire questa procedura nel sito centrale.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Per aggiungere siti di succursale alla topologia

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.

2.  Nell'albero della console espandere il sito centrale, fare clic con il pulsante destro del mouse su **Siti di succursale** e quindi scegliere **Nuovo sito di succursale**.

3.  Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.

4.  (Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.

5.  Fare clic su **Avanti**.

6.  (Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:
    
      - Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.
    
      - Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.
    
      - Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.

7.  Fare clic su **Avanti** e quindi eseguire una delle operazioni seguenti:
    
      - Se si utilizza un Survivable Branch Appliance o server in questo sito, accertarsi che la casella di controllo **Apri la procedura guidata nuovo Survivable Wizard al termine della procedura guidata** sia selezionata, fare clic su **fine**e quindi seguire le istruzioni nella procedura guidata che verrà aperta. Per informazioni sugli elementi della procedura guidata, vedere [define a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.

8.  Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.

**Passaggio successivo:**

Per i server o gli appliance Survivable Branch: [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Per la connettività PSTN non resiliente: [definire un gateway PSTN per un sito di succursale in Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

