---
title: Aggiornare i record SRV DNS
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb3c5a3f74d3a85fbc5742514a92015df08d5c9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Aggiornare i record SRV DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-29_

Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.

In questo argomento viene descritto come aggiornare i record DNS (Domain Name System) dopo la migrazione a Lync Server 2013. Dopo che tutti gli utenti sono stati spostati in Lync Server 2013, ma prima che il pool o il Director di Office Communications Server 2007 R2 legacy venga rimosso, è necessario aggiornare i record SRV DNS nel DNS interno per ogni dominio SIP. Per questa procedura si presuppone che nel sistema DNS interno siano disponibili aree per i domini utente SIP.

**Per configurare un record DNS SRV**

1.  Nel server DNS fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.

2.  Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**, espandere il dominio SIP in cui è installato Lync Server 2013 e passare all'impostazione ** \_ TCP** .

3.  Nel riquadro destro fare clic con il pulsante destro del mouse su ** \_ sipinternaltls** e scegliere **proprietà**.

4.  In **host che offre questo servizio**aggiornare il nome di dominio completo host in modo che punti al pool di Lync Server 2013.

5.  Fare clic su **OK**.

**Per verificare che il nome di domino completo del pool Front End o del server Standard Edition possa essere risolto**

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

3.  Nella casella **Apri** digitare **cmd** e quindi fare clic su **OK**.

4.  Al prompt dei comandi digitare **nslookup** \<FQDN of the Front End pool\> o \<FQDN of the Standard Edition server\> , quindi premere INVIO.

5.  Verificare di ricevere una risposta che si risolve nell'indirizzo IP appropriato per il nome FQDN.

</div>

<span> </span>

</div>

</div>

</div>

