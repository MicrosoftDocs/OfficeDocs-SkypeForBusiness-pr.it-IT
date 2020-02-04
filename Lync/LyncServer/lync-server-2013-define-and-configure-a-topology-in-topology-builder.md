---
title: 'Lync Server 2013: Definire e configurare una topologia in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Definire e configurare una topologia in Generatore di topologie per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

L'uso di generatore di topologia per definire una nuova topologia o per modificare una topologia esistente non richiede l'appartenenza a un amministratore locale o a un gruppo di domini privilegiati. Generatore di topologia guida i passaggi necessari per definire la topologia per un pool di front end Enterprise Edition o una versione standard in base ai requisiti di configurazione.

È necessario usare generatore di topologia per completare e pubblicare la topologia prima di poter installare Lync Server 2013 nei server. La procedura seguente include i passaggi necessari per definire una nuova topologia.

<div>

## <a name="to-define-a-topology"></a>Per definire una topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  In Generatore di topologie selezionare **nuova topologia**. Viene richiesto di richiedere un percorso e un nome di file per il salvataggio della topologia. Assegna al file della topologia un nome significativo e accetta l'estensione predefinita di. tbxml. Fare clic su **OK**.

3.  Passare al percorso in cui si vuole salvare il nuovo file XML della topologia, immettere un nome per il file e quindi fare clic su **Salva**.

4.  Nella pagina **Definisci il dominio principale** immettere il nome del dominio SIP principale per l'organizzazione e quindi fare clic su **Avanti**.

5.  Nella pagina **specifica altri domini supportati** immettere i nomi di altri domini, se presenti, e quindi fare clic su **Avanti**.

6.  Nella pagina **Definisci il primo sito** immettere un nome e una descrizione per il primo sito e quindi fare clic su **Avanti**.

7.  Nella pagina **specifica i dettagli del sito** immettere le informazioni sulla posizione per il sito e quindi fare clic su **Avanti**.

8.  Nella **nuova topologia la pagina è stata definita correttamente** , verificare che la casella di controllo **Apri la nuova creazione guidata front-end al termine della procedura** guidata sia selezionata e quindi fare clic su **fine**.

Dopo aver definito e salvato la topologia, usare la nuova procedura guidata front-end per definire un pool Front-end o un server Standard Edition per il sito. Per informazioni dettagliate, vedere [definire e configurare un pool Front-end o un server Standard Edition in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

