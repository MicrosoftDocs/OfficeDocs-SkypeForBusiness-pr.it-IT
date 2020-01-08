---
title: "Lync Server 2013: Installare l'archivio di configurazione locale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 135dedc38bbc24dd69dfd44b74c70db8e3397252
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Installare l'archivio di configurazione locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-27_

Prima di eseguire questa procedura, verificare di aver effettuato l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmin.

Per poter eseguire qualsiasi operazione con la distribuzione guidata di Lync Server, è necessario che l'archivio di configurazione locale sia presente in un server. L'archivio di configurazione locale è una copia di sola lettura di Central Management store, che viene creata dopo l'installazione locale di SQL Server Express. L'archivio di gestione centralizzato viene aggiunto al database di SQL Server esistente installato nel server Standard Edition o nel database basato su SQL Server Express.

<div>


> [!IMPORTANT]  
> Se non è ancora stata eseguita la configurazione di Lync Server 2013 su questo server, verrà richiesto di eseguire un'unità e un percorso in cui installare Lync Server 2013. In questo modo è possibile eseguire l'installazione in un'unità diversa dall'unità di sistema, se l'organizzazione lo richiede o se si hanno problemi di spazio. È possibile modificare semplicemente il percorso di installazione per i file di Lync Server nella finestra di dialogo Imposta in una nuova unità disponibile. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, verranno distribuiti anche il resto dei file di Lync Server 2013.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Per installare l'archivio di configurazione locale

1.  Dal supporto di installazione passare \\a Setup\\amd64\\Setup. exe e quindi fare clic su **OK**.

2.  Se viene chiesto di installare Microsoft Visual C++ 2012 ridistribuibile, fare clic su **Sì**.

3.  Nella pagina **percorso di installazione di Lync Server 2013** fare clic su **OK**.

4.  Nella pagina **contratto di licenza con l'utente finale** verificare le condizioni di licenza, è necessario selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK** per poter continuare.

5.  Nella pagina distribuzione guidata fare clic su **Installa o aggiorna Lync Server System**.

6.  Nella pagina **Lync Server 2013** , accanto a **Step1: install Local Configuration Store**, fare clic su **Esegui**.

7.  Nella pagina **Installa configurazione locale Store** verificare che sia selezionata l'opzione **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.

8.  Dopo aver completato l'installazione di configurazione del server locale, fare clic su **fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

