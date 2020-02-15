---
title: "Lync Server 2013: installazione dell'archivio di configurazione locale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00b4ffc463412064b578938516c4ea33b0dbb663
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Installare l'archivio di configurazione locale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-27_

Prima di eseguire la procedura seguente, verificare di aver eseguito l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmin.

Per poter eseguire qualsiasi operazione con la distribuzione guidata di Lync Server, è necessario che l'archivio di configurazione locale esista su un server. L'archivio di configurazione locale è una copia di sola lettura dell'archivio di gestione centrale, che viene creato dopo l'installazione locale di SQL Server Express. L'archivio di gestione centrale viene aggiunto al database di SQL Server esistente installato nel server Standard Edition o nel database basato su SQL Server Express.

<div>


> [!IMPORTANT]  
> Se non è stato eseguito il programma di installazione di Lync Server 2013 su questo server, verrà richiesto di eseguire un'unità e un percorso in cui installare Lync Server 2013. In questo modo è possibile eseguire l'installazione in un'unità diversa dall'unità di sistema, se l'organizzazione lo richiede o se si dispone di problemi di spazio. È possibile modificare il percorso di installazione dei file di Lync Server nella finestra di dialogo Imposta su una nuova unità disponibile. Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, verranno distribuiti anche gli altri file di Lync Server 2013.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Per installare l'archivio di configurazione locale

1.  Dal supporto di installazione, passare a \\installazione\\amd64\\Setup. exe e quindi fare clic su **OK**.

2.  Se viene richiesto di installare Microsoft Visual C++ 2012 Redistributable, fare clic su **Sì**.

3.  Nella pagina **percorso di installazione di Lync Server 2013** fare clic su **OK**.

4.  Nella pagina **contratto di licenza con l'utente finale** , esaminare le condizioni di licenza, è necessario selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK** per continuare.

5.  Nella pagina Distribuzione guidata fare clic su **Installa o aggiorna il sistema Lync Server**.

6.  Nella pagina **Lync Server 2013** , accanto a **passaggio 1: installazione dell'archivio di configurazione locale**, fare clic su **Esegui**.

7.  Nella pagina **installazione dell'archivio di configurazione locale** verificare che l'opzione **Recupera direttamente dall'archivio di gestione centrale** sia selezionata e quindi fare clic su **Avanti**.

8.  Al termine dell'installazione di configurazione del server locale, fare clic su **fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

