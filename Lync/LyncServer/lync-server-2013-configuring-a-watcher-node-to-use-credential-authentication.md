---
title: "Lync Server 2013: configurazione di un nodo Watcher per l'utilizzo dell'autenticazione delle credenziali"
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
ms.openlocfilehash: 4e05ac48896b50b4b83e4211a5036f6a6d513d43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517692"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Configurazione di un nodo Watcher per l'utilizzo dell'autenticazione delle credenziali in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

Se il computer che funge da nodo Watcher si trova all'esterno della rete perimetrale, per configurarlo per l'esecuzione di transazioni sintetiche è necessario seguire una procedura leggermente diversa. Nello specifico, non andranno creati un pool di applicazioni attendibili e un'applicazione attendibile e sarà necessario installare un certificato che consenta al nodo Watcher di inviare avvisi a un computer che si trova all'interno della rete perimetrale. Questo vuol dire che bisognerà completare due attività separate:

  - Aggiornare l'appartenenza al gruppo RTC Local Read-Only Administrators del computer

  - Installare i file di configurazione del nodo Watcher

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Aggiornamento dell'appartenenza al gruppo RTC Local Read-Only Administrators

Se il nodo Watcher si trova all'esterno della rete perimetrale, è necessario aggiungere l'account Servizio di rete al gruppo RTC Local Read-only Administrators nel computer che funge da nodo Watcher. A questo scopo, completare la procedura seguente nel nodo Watcher:

1.  Fare clic sul pulsante **Start**, fare clic su **Computer** con il pulsante destro del mouse e quindi scegliere **Gestione**.

2.  In Server Manager espandere **Configurazione**, espandere **Utenti e gruppi locali** e quindi fare clic su **Gruppi**.

3.  Nel riquadro Gruppi fare doppio clic su **RTC Local Read-only Administrators**.

4.  Nella finestra delle proprietà del gruppo **RTC Local Read-only Administrators** fare clic su **Aggiungi**.

5.  Nella finestra di dialogo **Selezione utenti, computer, account di servizio o gruppi** fare clic su **Percorsi**.

6.  Nella finestra di dialogo **Percorsi** selezionare il nome del computer che funge da nodo Watcher e quindi fare clic su **OK**.

7.  Nella casella **Immettere i nomi degli oggetti da selezionare** digitare **Servizio di rete** e quindi fare clic su **OK**.

8.  Nella finestra delle proprietà del gruppo **RTC Local Read-only Administrators Properties** fare clic su **OK** e quindi chiudere **Server Manager**.

Riavviare il computer che funge da nodo Watcher.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Installazione dei file di configurazione del nodo Watcher

Dopo il riavvio del computer che funge da nodo Watcher, l'operazione successiva consiste nell'installare il file Watchernode.msi. Per eseguire questo file, aprire Lync Server 2013 Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, **Lync Server 2013**e quindi **Lync Server Management Shell**. In Lync Server Management Shell, digitare il comando seguente e quindi premere INVIO (accertarsi di specificare il percorso effettivo della copia di Watchernode.msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Come già osservato, Watchernode.msi può essere eseguito anche da una finestra di comando. Per aprire una finestra di comando fare clic su <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>Prompt dei comandi</STRONG>, quindi scegliere <STRONG>Esegui come amministratore</STRONG>. All'apertura della finestra di comando, digitare lo stesso comando come descritto in precedenza.



</div>

La modalità Negotiate viene usata ogni volta che non è possibile configurare il nodo Watcher come pool di applicazioni attendibili. In questa modalità, gli amministratori dovranno gestire le password utente di prova nel nodo Watcher.

</div>

</div>

<span> </span>

</div>

</div>

</div>

