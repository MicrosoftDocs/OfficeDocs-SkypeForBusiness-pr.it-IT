---
title: 'Lync Server 2013: installare i componenti server di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f15afbb1602f369a063826c2196387dcff819b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Installare componenti server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-05_

Prima di eseguire la procedura seguente, verificare di aver eseguito l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmins in Active Directory.

La distribuzione guidata di Lync Server viene utilizzata per installare i componenti necessari per ogni ruolo di Lync Server e per attivare il server. In questo articolo vengono illustrati i passaggi per la distribuzione di un server Standard Edition o di un front end server nell'infrastruttura di Lync.

<div>

## <a name="to-install-lync-server-components"></a>Per installare i componenti di Lync Server

1.  Se la distribuzione guidata di Lync Server non è in esecuzione, avviarla nel server in cui si desidera installare Lync.

2.  Fare clic su **Installa o aggiorna il sistema Lync Server**.

3.  Nella distribuzione guidata, verificare che il **passaggio 1: installazione dell'archivio di configurazione locale** disponga di un segno di spunta verde, il che significa che questo server dispone di una copia locale dell'archivio installato correttamente. Se non è selezionata, è necessario installare l'archivio di configurazione locale sul server. Eseguire la procedura seguente per [installare l'archivio di configurazione locale in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e quindi tornare qui.

4.  Quando si è pronti per installare i componenti di Lync Server 2013 nel server, fare clic su **Esegui** accanto a **passaggio 2: installazione o rimozione componenti di Lync Server**.

5.  Nella pagina **Configura componenti di Lync Server** fare clic su **Avanti** per configurare i componenti come definito nella topologia pubblicata.

6.  Nella pagina **esecuzione comandi** in corso viene visualizzato un riepilogo dei comandi e delle informazioni di installazione come avviene il set up. Al termine, è possibile utilizzare l'elenco per selezionare un registro da visualizzare e quindi fare clic su **Visualizza registro**.

7.  Quando viene eseguito il programma di installazione dei componenti di Lync Server 2013 e i registri sono stati esaminati in base alle esigenze, fare clic su **fine** per completare questo passaggio nell'installazione.
    
    <div>
    

    > [!NOTE]  
    > Se viene richiesto di riavviare il server (operazione che potrebbe verificarsi se è necessario installare Windows Desktop Experience), farlo definitivamente. Quando si esegue il backup e l'esecuzione del computer, è necessario eseguire di nuovo questi passaggi, a partire dal passaggio tre elencato sopra (in pratica eseguire il passaggio 2 nella distribuzione guidata un'altra volta).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

