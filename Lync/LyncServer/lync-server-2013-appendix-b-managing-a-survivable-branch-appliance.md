---
title: 'Lync Server 2013: Appendice B: gestione di un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Appendice B: gestione di un Survivable Branch Appliance in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Questo argomento descrive le procedure per la gestione di un Survivable Branch Appliance. In particolare, come sostituire e rinominare un Survivable Branch Appliance e come cambiare il pool di front end di Lync Server 2013 a cui è associato il Survivable Branch Appliance.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Per sostituire un Survivable Branch Appliance

1.  Arrestare tutti i servizi di Lync Server 2013 nell'appliance Survivable Branch. Vedere la documentazione del fornitore Survivable Branch Appliance.

2.  Consigliato Rimuovere il Survivable Branch Appliance dal dominio.

3.  Eliminare l'oggetto computer Survivable Branch Appliance in servizi di dominio Active Directory, eseguendo la procedura seguente:
    
      - Accedere a un server membro come membro del gruppo amministratori aziendali.
    
      - Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **utenti e computer di Active Directory**.
    
      - Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.

4.  Aggiungere di nuovo l'oggetto computer Survivable Branch Appliance. Vedere [aggiungere un Survivable Branch Appliance in Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).

5.  Attendere che venga eseguita la replica di Active Directory.

6.  Aprire Lync Server Management Shell e digitare **Enable-CsTopology**.

7.  Connettere il nuovo dispositivo Survivable Branch Appliance alla rete e seguire la procedura descritta in [distribuire un Survivable Branch Appliance o un server con Lync server 2013-attività del sito centrale](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [distribuire un Survivable Branch Appliance o un server con Lync Server 2013-attività del sito filiale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Per rinominare un Survivable Branch Appliance

1.  Trasferire gli utenti nel sito centrale. Per informazioni dettagliate, vedere [trasferire utenti in un altro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrestare tutti i servizi di Lync Server 2013 nell'appliance Survivable Branch. Vedere la documentazione del fornitore Survivable Branch Appliance.

3.  Per rimuovere l'appliance Survivable Branch dalla topologia, seguire questa procedura:
    
      - Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Lync Server**e quindi su **Generatore di topologia di Lync Server**.
    
      - Nell'albero della console espandere **siti di succursale**, fare clic su Survivable Branch Appliance e quindi fare clic su **Elimina** nel riquadro azioni.

4.  Rimuovere il Survivable Branch Appliance dal dominio.

5.  Eliminare l'oggetto computer Survivable Branch Appliance in Active Directory, eseguendo la procedura seguente:
    
      - Accedere a un controller di dominio come membro del gruppo amministratori aziendali.
    
      - Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **utenti e computer di Active Directory**.
    
      - Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.

6.  Ripristinare le impostazioni predefinite della Survivable Branch Appliance. Vedere la documentazione del fornitore Survivable Branch Appliance.

7.  Seguire i passaggi descritti in [distribuzione di un Survivable Branch Appliance o server con Lync server 2013-attività del sito centrale](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [distribuire un Survivable Branch Appliance o un server con Lync Server 2013-attività del sito filiale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Consente di trasferire gli utenti nell'appliance Survivable Branch rinominato. Per informazioni dettagliate, vedere [trasferire utenti in un altro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Per modificare il pool Front End di Lync Server a cui è associato l'appliance Survivable Branch

1.  È necessario trasferire gli utenti dall'appliance Survivable Branch al pool Front End di Lync Server nel sito centrale. Per informazioni dettagliate, vedere [trasferire utenti in un altro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrestare tutti i servizi Lync Server nell'appliance Survivable Branch. Vedere la documentazione del fornitore Survivable Branch Appliance.

3.  Aggiornare il pool Front End di Lync Server a cui è associato il Survivable Branch Appliance, eseguendo le operazioni seguenti:
    
      - Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Lync Server**e quindi su **Generatore di topologia di Lync Server**.
    
      - Espandere **siti di succursale**.
    
      - Fare clic con il pulsante destro del mouse sull'oggetto Appliance Survivable Branch da modificare e quindi scegliere **modifica proprietà** .
    
      - In resilienza selezionare il nuovo pool di front end a cui deve essere associato il Survivable Branch Appliance e quindi fare clic su **Avanti**.
    
      - Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo dispositivo Survivable Branch Appliance, scegliere **topologia**e quindi fare clic su **pubblica**.

4.  Riavviare tutti i servizi Lync Server nell'appliance Survivable Branch.

5.  Testare l'appliance Survivable Branch. Per informazioni dettagliate, vedere [utenti privati in un Survivable Branch Appliance o server in Lync server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Consente di trasferire utenti dal pool Front-End di Lync Server nel sito centrale all'appliance Survivable Branch.

</div>

</div>

<span> </span>

</div>

</div>

</div>

