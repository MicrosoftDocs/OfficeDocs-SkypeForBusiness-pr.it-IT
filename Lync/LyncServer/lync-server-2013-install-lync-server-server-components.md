---
title: 'Lync Server 2013: Installazione dei componenti server di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895047715bfa632970adbabb20311d8c68182499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Installazione dei componenti server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-05_

Prima di eseguire questa procedura, verificare di aver effettuato l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmins in Active Directory.

La distribuzione guidata di Lync Server viene usata per installare i componenti necessari per ogni ruolo di Lync Server e per attivare il server. In questo articolo vengono illustrati i passaggi della distribuzione di un server Standard Edition o di un server front-end nell'infrastruttura Lync.

<div>

## <a name="to-install-lync-server-components"></a>Per installare i componenti di Lync Server

1.  Se la distribuzione guidata di Lync Server non è in corso, avviarla nel server in cui si vuole installare Lync.

2.  Fare clic su **Installa o aggiorna Lync Server System**.

3.  Nella distribuzione guidata verificare che il **passaggio 1: install Local Configuration Store** contenga un segno di spunta verde, il che significa che il server ha una copia locale dello Store installata correttamente. Se non è selezionata, è necessario installare l'archivio di configurazione locale nel server. Seguire i passaggi descritti in [installare l'archivio di configurazione locale in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e quindi tornare qui.

4.  Quando si è pronti per installare i componenti di Lync Server 2013 nel server, fare clic su **Esegui** accanto al **passaggio 2: configurare o rimuovere i componenti di Lync Server**.

5.  Nella pagina **configurare i componenti di Lync Server** fare clic su **Avanti** per configurare i componenti come definiti nella topologia pubblicata.

6.  Nella pagina **comandi in esecuzione** viene visualizzato un riepilogo dei comandi e delle informazioni di installazione Man mano che viene eseguita la configurazione. Al termine, è possibile usare l'elenco per selezionare un log da visualizzare e quindi fare clic su **Visualizza log**.

7.  Quando è stata eseguita la configurazione dei componenti di Lync Server 2013 e i registri sono stati esaminati in base alle esigenze, fare clic su **fine** per completare questo passaggio nell'installazione.
    
    <div>
    

    > [!NOTE]  
    > Se viene richiesto di riavviare il server (che potrebbe verificarsi se l'esperienza desktop di Windows dovesse essere installata), eseguire definitivamente questa operazione. Quando il computer viene eseguito il backup e l'esecuzione, è necessario eseguire di nuovo questi passaggi, a partire dal passaggio tre elencato sopra (in pratica eseguire il passaggio 2 nella distribuzione guidata).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

