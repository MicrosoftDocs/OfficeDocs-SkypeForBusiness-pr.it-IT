---
title: Aggiungere un sito di succursale Survivable Branch Appliance di Lync Server 2013 alla topologia
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
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Aggiungere un sito di succursale Survivable Branch Appliance di Lync Server 2013 alla topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-07_

Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) non può essere associato a un pool di front end di Microsoft Lync Server 2010 come registrar di backup. L'SBA deve essere associato a un pool Front-End di Microsoft Lync Server 2013. Questi passaggi presuppongono un SBA di Microsoft Lync Server 2013. Eseguire questa procedura nel sito centrale.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Per aggiungere siti di succursale con Microsoft Lync Server 2013 SBA alla propria topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il sito centrale, espandere **siti di succursale**e quindi fare clic su **nuovo sito filiale**.

3.  Nella finestra di dialogo **Definisci nuovo sito succursale** fare clic su **nome**e quindi digitare un nome per il nuovo sito della filiale.

4.  Opzionale Fare clic su **Descrizione**e quindi digitare una descrizione significativa per il sito della filiale.

5.  Fare clic su **Avanti**.

6.  Opzionale Nella finestra di dialogo **Definisci nuovo sito della filiale** eseguire una delle operazioni seguenti:
    
      - Fare clic su **città**e quindi digitare il nome della città in cui si trova il sito della filiale.
    
      - Fare clic su **stato/area geografica**e quindi digitare il nome dello stato o dell'area geografica in cui si trova il sito della filiale.
    
      - Fare clic su **codice paese**e quindi digitare il codice di chiamata a due cifre per il paese/area geografica in cui si trova il sito della filiale.

7.  Fare clic su **Avanti**e quindi eseguire una delle operazioni seguenti:
    
      - Se si usa un Survivable Branch Appliance o Survivable Branch Server in questo sito, verificare che la casella di controllo **Apri la nuova procedura guidata per la procedura** guidata sia selezionata.
    
      - Se non si usa un Survivable Branch Appliance o Survivable Branch Server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata.
    
      - Fare clic su **fine**e quindi seguire le istruzioni visualizzate nella procedura guidata. Per informazioni sugli elementi della procedura guidata, vedere [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Ripetere i passaggi precedenti per ogni sito della filiale che si vuole aggiungere alla topologia.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Definire un Survivable Branch Appliance o un Survivable Branch Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definire un gateway PSTN per un sito di succursale in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

