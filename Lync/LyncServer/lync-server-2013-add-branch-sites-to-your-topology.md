---
title: 'Lync Server 2013: Aggiungere siti di succursale alla topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Aggiungere siti di succursale alla topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

I siti di succursale rappresentano le filiali fisiche connesse agli uffici principali tramite un collegamento WAN. Per aggiungere un sito di succursale alla topologia di Lync, eseguire questa procedura nel sito centrale.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Per aggiungere siti di succursale alla topologia

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Lync Server**e quindi su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il sito centrale, fare clic con il pulsante destro del mouse su **siti di succursale**e quindi scegliere **nuovo sito filiale**.

3.  Nella finestra di dialogo **Definisci nuovo sito succursale** fare clic su **nome**e quindi digitare il nome del sito della filiale.

4.  Opzionale Fare clic su **Descrizione**e quindi digitare una descrizione significativa per il sito della filiale.

5.  Fare clic su **Avanti**.

6.  Opzionale Nella finestra di dialogo **Definisci nuovo sito della filiale** eseguire una delle operazioni seguenti:
    
      - Fare clic su **città**e quindi digitare il nome della città in cui si trova il sito della filiale.
    
      - Fare clic su **stato/area geografica**e quindi digitare il nome dello stato o dell'area geografica in cui si trova il sito della filiale.
    
      - Fare clic su **codice paese**e quindi digitare il codice di chiamata a due cifre per il paese/area geografica in cui si trova il sito della filiale.

7.  Fare clic su **Avanti**e quindi eseguire una delle operazioni seguenti:
    
      - Se si usa un Survivable Branch Appliance o un server in questo sito, verificare che la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata sia selezionata, fare clic su **fine**e quindi seguire le istruzioni della procedura guidata visualizzata. Per informazioni sugli elementi della procedura guidata, vedere [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Se non si usa un Survivable Branch Appliance o un server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata e quindi fare clic su **fine**.

8.  Ripetere i passaggi precedenti per ogni sito della filiale che si vuole aggiungere alla topologia.

**Passaggio successivo:**

Per gli elettrodomestici o i server Survivable Branch: [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Per la connettività PSTN non resiliente: [definire un gateway PSTN per un sito di succursale in Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

