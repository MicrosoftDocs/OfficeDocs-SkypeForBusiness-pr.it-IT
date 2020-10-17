---
title: 'Lync Server 2013: Appendice B: gestione di un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a766ae86d4c74d874f1db747c137f54cf568d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523223"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Appendice B: gestione di un Survivable Branch Appliance in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

In questo argomento vengono descritte le procedure per la gestione di un Survivable Branch Appliance. In particolare, come sostituire e rinominare un Survivable Branch Appliance e come modificare il pool Lync Server 2013 front end a cui è associato il Survivable Branch Appliance.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Per sostituire un Survivable Branch Appliance

1.  Arrestare tutti i servizi di Lync Server 2013 nel Survivable Branch Appliance. A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.

2.  Consigliato Rimuovere il Survivable Branch Appliance dal dominio.

3.  Eliminare l'oggetto computer Survivable Branch Appliance in servizi di dominio Active Directory attenendosi alla procedura seguente:
    
      - Eseguire l'accesso a un server membro come membro del gruppo Enterprise Admins.
    
      - Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.
    
      - Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.

4.  Aggiungere di nuovo l'oggetto computer Survivable Branch Appliance. Per ulteriori informazioni, vedere [aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).

5.  Attendere che venga eseguita la replica di Active Directory.

6.  Aprire Lync Server Management Shell e digitare **Enable-CsTopology**.

7.  Connettere il nuovo Survivable Branch Appliance alla rete e seguire i passaggi illustrati in [Deploying a Survivable Branch Appliance or Server with Lync server 2013-Central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Per rinominare un Survivable Branch Appliance

1.  Spostare gli utenti nel sito centrale. Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrestare tutti i servizi di Lync Server 2013 nel Survivable Branch Appliance. A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.

3.  Rimuovere il Survivable Branch Appliance dalla topologia, attenendosi alla procedura seguente:
    
      - Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.
    
      - Nell'albero della console espandere **siti di succursale**, fare clic sul Survivable Branch Appliance, quindi fare clic su **Elimina** nel riquadro azioni.

4.  Rimuovere il Survivable Branch Appliance dal dominio.

5.  Eliminare l'oggetto computer Survivable Branch Appliance in Active Directory, attenendosi alla procedura seguente:
    
      - Eseguire l'accesso a un controller di dominio come membro del gruppo Enterprise Admins.
    
      - Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.
    
      - Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.

6.  Ripristinare il Survivable Branch Appliance in Factory Defaults. A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.

7.  Seguire la procedura illustrata in [Deploying a Survivable Branch Appliance or Server with Lync server 2013-Central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Spostare gli utenti nel Survivable Branch Appliance rinominato. Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Per cambiare il pool Front End di Lync Server a cui è associato il Survivable Branch Appliance

1.  Spostare gli utenti dal Survivable Branch Appliance al pool Front End di Lync Server nel sito centrale. Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrestare tutti i servizi di Lync Server nel Survivable Branch Appliance. (Vedere la documentazione del fornitore di Survivable Branch Appliance).

3.  Aggiornare il pool Front End di Lync Server a cui è associato il Survivable Branch Appliance, attenendosi alla procedura seguente:
    
      - Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.
    
      - Espandere **Siti di succursale**.
    
      - Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance da modificare e quindi scegliere **modifica proprietà** .
    
      - In resilienza selezionare il nuovo pool Front end a cui deve essere associato il Survivable Branch Appliance, quindi fare clic su **Avanti**.
    
      - Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo Survivable Branch Appliance, scegliere **topologia**e quindi fare clic su **pubblica**.

4.  Riavviare tutti i servizi di Lync Server nel Survivable Branch Appliance.

5.  Testare il Survivable Branch Appliance. Per informazioni dettagliate, vedere [Home Users on a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Spostare gli utenti dal pool Front End di Lync Server nel sito centrale a Survivable Branch Appliance.

</div>

</div>

<span> </span>

</div>

</div>

</div>

