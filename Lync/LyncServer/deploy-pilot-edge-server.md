---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba616f6a5ce86e0f94c3b52afd60aaba34b7635
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Distribuire Edge Server pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Lync Server 2013. I processi di distribuzione e configurazione per Lync Server 2013 sono molto simili a Lync Server 2010. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, in cui viene descritto il processo di distribuzione e vengono fornite anche informazioni di configurazione per l'accesso degli utenti esterni.

Man mano che si va avanti nella procedura guidata **Definisci pool di server perimetrali**, esaminare le impostazioni di configurazione chiave illustrate nei passaggi seguenti. Si noti che sono visualizzate solo alcune pagine della procedura guidata **Definisci pool di server perimetrali**.

**Definire un pool di server perimetrali**

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Passare al nodo Lync Server 2013. Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e scegliere **Nuovo pool di server perimetrali**.
    
    ![Finestra di dialogo definire il nuovo pool di server perimetrali](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Finestra di dialogo definire il nuovo pool di server perimetrali")

3.  Un pool di server perimetrali può essere un **Pool di più computer** o un **Pool computer singolo**.
    
    ![Finestra di dialogo definire l'FQDN del pool di server perimetrali](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Finestra di dialogo definire l'FQDN del pool di server perimetrali")

4.  Nella pagina **Selezionare funzionalità** non abilitare la federazione o la federazione XMPP. La Federazione e la Federazione XMPP sono entrambe instradate al server perimetrale di Lync Server 2010 legacy. Queste funzionalità verranno configurate in una fase successiva della migrazione.
    
    ![Finestra di dialogo Seleziona funzionalità.](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Finestra di dialogo Seleziona funzionalità.")

5.  Successivamente, continuare a completare le pagine seguenti della procedura guidata: **FQDN esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.

6.  Nella pagina **definire l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2010.
    
    ![Finestra di dialogo definire l'hop successivo](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Finestra di dialogo definire l'hop successivo")

7.  Nella pagina **associa gruppi front-end o pool di Mediation** non associare un pool a questo pool di server perimetrali in questo momento. Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale di Lync Server 2010 legacy. Questa impostazione verrà configurata in una fase successiva della migrazione.
    
    ![Finestra di dialogo Associa pool Front End](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Finestra di dialogo Associa pool Front End")

8.  Fare clic su **Fine** e quindi su **Pubblica** per pubblicare la topologia.

9.  Seguire la procedura descritta in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo server perimetrale, configurare i certificati e avviare i servizi.

È molto importante seguire le linee guida illustrate negli argomenti relativi alla [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione. In questa sezione vengono fornite solo indicazioni sulle impostazioni di configurazione durante la fase di installazione di questi ruoli server.

È ora necessario disporre di un server perimetrale di Lync Server 2010 legacy distribuito in parallelo con una distribuzione di Lync Server 2013 Edge Server. Prima di passare alla fase successiva, verificare che entrambe le distribuzioni funzionino correttamente, che i servizi siano stati avviati e che sia possibile amministrare ogni distribuzione.

</div>

<span> </span>

</div>

</div>

</div>

