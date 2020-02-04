---
title: "Lync Server 2013: configurazione di un nodo Watcher per l'uso dell'autenticazione delle credenziali"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d0fa67c4ef2688035471d2290ead78123f73239
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Configurazione di un nodo Watcher per l'uso dell'autenticazione delle credenziali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è necessario seguire una procedura leggermente diversa per configurare il nodo Watcher in modo da eseguire transazioni sintetiche. In particolare, non è consigliabile creare un pool di applicazioni attendibili e un'applicazione attendibile ed è necessario installare un certificato che consenta al nodo Watcher di inviare avvisi a un computer all'interno della rete perimetrale. Ciò significa che dovrai completare due attività separate:

  - Aggiornare l'appartenenza al gruppo di amministratori di sola lettura locale RTC del computer

  - Installare i file di configurazione del nodo Watcher

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Aggiornamento dell'appartenenza al gruppo di amministratori di sola lettura RTC Local

Se il nodo Watcher si trova all'esterno della rete perimetrale, è necessario aggiungere l'account del servizio di rete al gruppo amministratori locali di sola lettura RTC nel computer del nodo Watcher. A questo scopo, completare la procedura seguente nel nodo Watcher:

1.  Fare clic su **Start**, fare clic con il pulsante destro del mouse su **computer**e quindi scegliere **Gestisci**.

2.  In Server Manager espandere **configurazione**, espandere **utenti e gruppi locali**e quindi fare clic su **gruppi**.

3.  Nel riquadro gruppi fare doppio clic su **amministratori locali di sola lettura RTC**.

4.  Nella finestra di dialogo **Proprietà amministratori locali di sola lettura RTC** fare clic su **Aggiungi**.

5.  Nella finestra di dialogo **Seleziona utenti, computer, account di servizio o gruppi** fare clic su **percorsi**.

6.  Nella finestra di dialogo **posizioni** selezionare il nome del computer del nodo Watcher e quindi fare clic su **OK**.

7.  Nella casella **immettere i nomi degli oggetti da selezionare** digitare **servizio di rete**e quindi fare clic su **OK**.

8.  Nella finestra di dialogo **Proprietà amministratori locali di sola lettura RTC** fare clic su **OK**e quindi chiudere **Gestione server**.

Riavviare il computer del nodo Watcher.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Installazione dei file di configurazione del nodo Watcher

Dopo il riavvio del computer del nodo Watcher, il passaggio successivo consiste nell'eseguire il file WatcherNode. msi. Per eseguire questo file, aprire Lync Server 2013 Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, facendo clic su **Lync Server 2013**e quindi scegliendo **Lync Server Management Shell**. In Lync Server Management Shell digitare il comando seguente e quindi premere INVIO (assicurarsi e specificare il percorso effettivo della copia di WatcherNode. msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Come indicato in precedenza, Watchernode. msi può essere eseguito anche da una finestra di comando. Per aprire una finestra di comando, fare clic su <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>prompt dei comandi</STRONG>e quindi scegliere <STRONG>Esegui come amministratore</STRONG>. Quando viene visualizzata la finestra di comando, digitare lo stesso comando illustrato in precedenza.



</div>

La modalità di negoziazione viene usata ogni volta che il nodo Watcher non può essere configurato come pool di applicazioni attendibili. In questa modalità, gli amministratori dovranno gestire le password degli utenti di test nel nodo Watcher.

</div>

</div>

<span> </span>

</div>

</div>

</div>

