---
title: 'Lync Server 2013: convalidare la configurazione del server Office Web Apps'
description: 'Lync Server 2013: convalidare la configurazione del server Office Web Apps.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80c3160dd9a76c129fbb0289929a868b897beb2c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547152"
---
# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="32e8f-103">Convalidare la configurazione del server Office Web Apps in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32e8f-103">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32e8f-104">_**Ultimo argomento modificato:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="32e8f-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="32e8f-105">Dopo che il server Office Web Apps è stato aggiunto alla topologia e dopo la pubblicazione della topologia, dovrebbero essere visualizzati due nuovi eventi del registro eventi nel registro eventi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32e8f-105">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="32e8f-106">Per prima cosa, è necessario aggiungere un evento MCU dati LS (ID evento 41034). Questo evento riporterà che il server Office Web Apps è stato individuato:</span><span class="sxs-lookup"><span data-stu-id="32e8f-106">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="32e8f-107">**Server Web Conferencing Server Office Web Apps è stato rilevato, il contenuto di PowerPoint è abilitato.**</span><span class="sxs-lookup"><span data-stu-id="32e8f-107">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="32e8f-p102">Inoltre, dovrebbe essere visualizzato un altro evento LS Data MCU (ID evento 41032) che restituisce gli URL di Office Web Apps Server. Ad esempio, dovrebbe essere visualizzato un evento simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="32e8f-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="32e8f-110">**Individuazione del server Web Conferencing Server Office Web Apps ha avuto esito positivo.**</span><span class="sxs-lookup"><span data-stu-id="32e8f-110">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="32e8f-111">**Pagina del relatore interno del server Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="32e8f-111">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="32e8f-112">**Pagina partecipante interno al server Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="32e8f-112">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="32e8f-113">**Pagina del relatore esterno del server Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="32e8f-113">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="32e8f-114">**Pagina partecipante interno al server Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="32e8f-114">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="32e8f-115">Se viene visualizzato un evento LS Data MCU con ID evento 41033, l'individuazione di Office Web Apps Server ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="32e8f-115">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="32e8f-116">In questo caso, Microsoft Lync Server 2013 tenterà tutte le volte necessarie per individuare il server Office Web Apps appena configurato.</span><span class="sxs-lookup"><span data-stu-id="32e8f-116">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="32e8f-117">Se è impossibile eseguire il processo di individuazione, è necessario rimuovere Office Web Apps Server dal documento relativo alla topologia, pubblicare la topologia aggiornata e quindi tentare di aggiungere di nuovo Office Web Apps Server alla topologia dopo avere risolto i problemi di connettività.</span><span class="sxs-lookup"><span data-stu-id="32e8f-117">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="32e8f-118">Se il server Office Web Apps sembra configurato correttamente ed è stato riconosciuto dal processo di individuazione, è possibile verificare che il server Office Web Apps funzioni come previsto condividendo una presentazione di PowerPoint tra una coppia di client Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="32e8f-118">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="32e8f-119">Se l'utente A può caricare e visualizzare la presentazione di PowerPoint e l'utente B può partecipare alla riunione e visualizzare la presentazione, Office Web Apps Server funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="32e8f-119">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="32e8f-p105">Anche se Office Web Apps Server sembra configurato correttamente, si potrebbe ricevere il messaggio di errore "Alcune funzionalità di condivisione non sono disponibili a causa di problemi di connettività del server" quando si tenta di condividere una presentazione di PowerPoint. Se si riceve questo messaggio di errore, riavviare i Front End Server associati al nuovo Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="32e8f-p105">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation. If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

