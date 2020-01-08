---
title: 'Lync Server 2013: Testare il server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Testare il server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

A questo punto, è configurato un pool di Director o Director, ma le voci SRV di Domain Name System (DNS) devono ancora puntare i client per accedere tramite un pool o un server Standard Edition. Prima di modificare il record DNS in modo che i client di Lync 2013 accedano automaticamente tramite il Director, testare un client manualmente puntando il puntatore del mouse sul Director.

<div>

## <a name="to-test-the-deployment"></a>Per testare la distribuzione

1.  Accedere al computer in cui è installato il pannello di controllo di Lync Server con un account di dominio che fa parte del gruppo **CsAdministrator** .

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nel riquadro di spostamento fare clic su **topologia**e nella colonna **stato** verificare che sia presente un server verde con una freccia, ovvero l'icona del server con l'icona del server ![freccia verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "con freccia verde"), per il pool di Director o Director.

4.  Connettere due computer client con il client Lync Server 2013 installato e accedere con un account utente diverso abilitato per Lync Server 2013 a ogni computer.

5.  In uno dei computer client fare clic sul menu **Opzioni** , selezionare il gruppo impostazioni **personali** , fare clic su **Avanzate**, su **configurazione manuale**e quindi impostare il **nome del server interno o l'indirizzo IP** per il nome di dominio completo (FQDN) del nuovo pool di Director o Director.

6.  Accedere a entrambi i client e verificare che il client che esegue l'accesso tramite il Director sia in grado di accedere correttamente, vedere lo stato presenza dell'altro utente e che possano scambiare messaggi istantanei.

</div>

</div>

<span> </span>

</div>

</div>

</div>

