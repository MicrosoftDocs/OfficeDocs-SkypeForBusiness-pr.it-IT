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
ms.openlocfilehash: 37d23187c76a0e8711340f68e75a422a20ea7588
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532103"
---
# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="dc843-102">Abilitare o disabilitare le conferenze telefoniche con accesso esterno per le riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc843-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc843-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dc843-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dc843-104">La procedura seguente descrive come consentire all'utente di partecipare a una riunione utilizzando l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="dc843-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="dc843-105">Per abilitare o disabilitare le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="dc843-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="dc843-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="dc843-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc843-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc843-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc843-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dc843-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc843-109">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.</span><span class="sxs-lookup"><span data-stu-id="dc843-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="dc843-110">Nell'elenco dei criteri conferenza selezionare il criterio per il quale abilitare il servizio di conferenza con accesso esterno e quindi fare clic su **Modifica** e su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="dc843-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc843-p102">Per consentire agli utenti la partecipazione a una riunione mediante accesso esterno, selezionare la casella di controllo **Consenti conferenza telefonica con accesso esterno PSTN**. Per impostazione predefinita, gli utenti possono connettersi alle riunioni utilizzando la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="dc843-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="dc843-113">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dc843-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

