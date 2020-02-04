---
title: "Lync Server 2013: installare i file dell'agente di Operation Manager"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Installazione dei file dell'agente di Operation Manager in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

Per installare i file dell'agente di Operations Manager nel computer, eseguire la procedura seguente.

1.  Nel supporto di configurazione di System Center fare doppio clic su **SetupOM. exe**.

2.  Nella configurazione di System Center Operation Manager fare clic su **Installa agente Operations Manager**.

3.  In configurazione guidata di System Center, nella pagina **Introduzione alla configurazione guidata di System Center Operations Manager** fare clic su **Avanti**.

4.  Nella pagina **cartella di destinazione** selezionare la cartella in cui verranno installati i file dell'agente di Operations Manager e quindi fare clic su **Avanti**.

5.  Nella pagina **Configurazione gruppo di gestione** selezionare **specifica informazioni gruppo di gestione**e quindi fare clic su **Avanti**.

6.  Nella pagina **Configurazione gruppo di gestione** Digitare il nome del gruppo gestione Operations Manager nella casella **nome gruppo di gestione** e quindi digitare il nome host del server Operations Manager, ad esempio ATL-SCOM-001, nella casella **server di gestione** . Se è stato modificato il numero di porta usato da Operations Manager, digitare il nuovo numero di porta nella casella porta del server di gestione. In caso contrario, lascia la porta al valore predefinito di 5723 e fai clic su **Avanti**.

7.  Nella pagina **account azione agente** selezionare **sistema locale**e quindi fare clic su **Avanti**.

8.  Nella pagina **Microsoft Update** selezionare **non si vuole usare Microsoft Update**e quindi fare clic su **Avanti**.

9.  Nella pagina **pronto per l'installazione** fare clic su **Installa**.

10. Nella pagina **completamento della configurazione guidata di System Center Operations Manager** fare clic su **fine**.

11. Fare clic su **Esci**.

Se si usa System Center 2007 R2, è possibile verificare che l'agente sia stato creato facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, scegliendo **System Center Operations Manager 2007 R2**e quindi facendo clic su **Operations Manager Shell**. In Operations Manager Shell digitare il comando di Windows PowerShell seguente e quindi premere INVIO:

    Get-Agent 

Un elenco di tutti gli agenti di Operations Manager verrà visualizzato sullo schermo.

Se si usa System Center 2012, eseguire questo comando dalla shell Operations 2012 Manager:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

