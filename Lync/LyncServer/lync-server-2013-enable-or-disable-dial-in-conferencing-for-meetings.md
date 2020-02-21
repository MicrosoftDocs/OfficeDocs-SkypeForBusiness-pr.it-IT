---
title: 'Lync Server 2013: abilitare o disabilitare le conferenze telefoniche con accesso esterno per le riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b995ef14ad1b405b59eba8d54646989c9f63f43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a>Abilitare o disabilitare le conferenze telefoniche con accesso esterno per le riunioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

La procedura seguente descrive come consentire all'utente di partecipare a una riunione utilizzando l'accesso esterno.

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a>Per abilitare o disabilitare le conferenze telefoniche con accesso esterno

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.

4.  Nell'elenco dei criteri conferenza selezionare il criterio per il quale abilitare il servizio di conferenza con accesso esterno e quindi fare clic su **Modifica** e su **Mostra dettagli**.

5.  Per consentire agli utenti la partecipazione a una riunione mediante accesso esterno, selezionare la casella di controllo **Consenti conferenza telefonica con accesso esterno PSTN**. Per impostazione predefinita, gli utenti possono connettersi alle riunioni utilizzando la rete PSTN (Public Switched Telephone Network).

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

