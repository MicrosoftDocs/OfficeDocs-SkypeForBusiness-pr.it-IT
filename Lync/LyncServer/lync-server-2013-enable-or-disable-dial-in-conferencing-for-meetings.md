---
title: 'Lync Server 2013: abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno per le riunioni'
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
ms.openlocfilehash: 4600d5f978c553699029416951505c952f62bb62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="80458-102">Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno per le riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80458-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80458-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="80458-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="80458-104">La procedura seguente descrive come consentire all'utente di partecipare a una riunione con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="80458-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="80458-105">Per abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="80458-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="80458-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="80458-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="80458-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80458-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="80458-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="80458-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="80458-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="80458-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="80458-110">Nell'elenco dei criteri di conferenza selezionare i criteri per cui si desidera abilitare i servizi di conferenza telefonica con accesso esterno, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="80458-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="80458-111">Per consentire agli utenti di partecipare a una riunione effettuando la chiamata, selezionare la casella di controllo **Abilita conferenza telefonica con accesso esterno PSTN** .</span><span class="sxs-lookup"><span data-stu-id="80458-111">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="80458-112">Per impostazione predefinita, gli utenti possono eseguire la chiamata alle riunioni tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="80458-112">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="80458-113">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="80458-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

