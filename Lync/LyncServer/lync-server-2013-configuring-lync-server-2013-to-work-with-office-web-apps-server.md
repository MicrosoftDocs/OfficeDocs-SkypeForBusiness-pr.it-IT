---
title: Configurazione di Lync Server 2013 per l'utilizzo con Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3516822064d0fd42b44edb7af73b321644c36c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Configurazione di Lync Server 2013 per l'utilizzo con Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-04-22_

Prima di poter configurare Lync Server 2013 per l'uso di Office Web Apps Server, è necessario che Office Web Apps Server venga distribuito e configurato. Vedere la **Guida ai documenti per la distribuzione di Office Web Apps Server e Office** Web Apps per informazioni dettagliate su come installare e configurare un singolo server di Office Web Apps o per informazioni su come installare e configurare una farm di Office Web Apps Server per una disponibilità elevata.

Dopo l'installazione di Office Web Apps Server e la Web farm correttamente configurata, è necessario configurare Lync Server per comunicare con il nuovo server. a questo scopo, Aggiungi l'URL di individuazione del server Office Web Apps alla topologia di Lync Server. Per aggiungere Office Web Apps Server alla topologia, eseguire la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nella finestra di dialogo **Generatore di topologia** selezionare **Scarica topologia da distribuzione esistente** e quindi fare clic su **OK**.

3.  Nella finestra di dialogo **Salva topologia come** Digitare un nome per il documento della topologia, ad esempio **PreWebAppsServerTopology**, nella casella **nome file** e quindi fare clic su **Salva**. Questa topologia può essere recuperata e ripubblicata in seguito se si verificano problemi con la nuova topologia.

4.  In Generatore di topologie espandere **Lync Server 2013**, espandere il nome del sito, espandere i **pool di front-end di Enterprise Edition**, fare clic con il pulsante destro del mouse sul nome di uno dei pool e quindi scegliere **modifica proprietà**.

5.  Nella scheda **generale** della finestra di dialogo **modifica proprietà** individuare il titolo **associato a Office Web Apps Server** e quindi fare clic su **nuovo** (o selezionare un server di Office Web Apps esistente nell'elenco a discesa).

6.  Nella finestra di dialogo **Definisci nuovo server Office Web Apps** Digitare il nome di dominio completo (FQDN) del computer Office Web Apps Server nella casella **FQDN server di Office Web Apps** . Quando si esegue questa operazione, l'URL di individuazione del server di Office Web Apps deve essere automaticamente immesso nella casella **URL individuazione server di Office Web Apps** .
    
    Se il server Office Web Apps è installato in locale e nella stessa area di rete di Lync Server 2013, l'opzione **Office Web Apps Server è distribuita in una rete esterna, ovvero perimetro/Internet,** non deve essere selezionata.
    
    Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**.

7.  Nella finestra di dialogo **Definisci nuovo server Office Web Apps** fare clic su **OK**e quindi su **OK** nella finestra di dialogo **modifica proprietà** . L'URL di individuazione di Office Web Apps verrà quindi elencato come una delle associazioni del pool.

Sarà necessario ripetere questa procedura per ogni pool che deve essere associato al server Office Web Apps.

Dopo aver aggiunto l'URL di individuazione alla topologia, è necessario pubblicare la topologia aggiornata. Per eseguire questa operazione in Generatore di topologie:

1.  Fare clic su **azione** e quindi su **Pubblica topologia**.

2.  Nella pagina **Pubblica topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.

3.  Nella pagina **completamento pubblicazione guidata** fare clic su **fine**.

4.  Chiudi generatore di topologie.

</div>

<span> </span>

</div>

</div>

</div>

