---
title: 'Lync Server 2013: testare il Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad5c885e032800e4233aaa58c5238c066a87a1df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Testare il Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

In questa fase, è configurato un server Director o un pool di Director, ma le voci SRV DNS (Domain Name System) sono ancora in grado di eseguire l'accesso dei client tramite un pool o uno Standard Edition. Prima di modificare il record DNS per fare in modo che i client di Lync 2013 accedano automaticamente tramite il server Director, testare un client facendole riferimento manualmente al server Director.

<div>

## <a name="to-test-the-deployment"></a>Per testare la distribuzione

1.  Accedere al computer in cui è installato il pannello di controllo di Lync Server con un account di dominio che fa parte del gruppo **CsAdministrator** .

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nel riquadro di spostamento fare clic su **topologia**e nella colonna **stato** verificare che sia presente un server verde con una freccia, ovvero un' ![icona del server con freccia verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icona del server con freccia verde"), per il Director o il pool di Director.

4.  Connettere due computer client in cui è installato il client Lync Server 2013 e accedere con un account utente diverso abilitato per Lync Server 2013 su ogni computer.

5.  In uno dei computer client fare clic sul menu **Opzioni** , selezionare il gruppo di impostazioni **personali** , fare clic su **Avanzate**, fare clic su **configurazione manuale**e quindi impostare il **nome o l'indirizzo IP del server interno** sul nome di dominio completo (FQDN) del nuovo Director o del pool di server Director.

6.  Accedere a entrambi i client e verificare che il client che accede utilizzando il Director sia in grado di eseguire l'accesso, vedere lo stato di presenza dell'altro utente e che possano scambiare messaggi istantanei.

</div>

</div>

<span> </span>

</div>

</div>

</div>

