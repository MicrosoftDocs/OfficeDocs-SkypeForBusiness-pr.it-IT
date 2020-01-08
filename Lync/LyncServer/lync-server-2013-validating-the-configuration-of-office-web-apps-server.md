---
title: 'Lync Server 2013: convalida della configurazione di Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="e0cd3-102">Convalida della configurazione di Office Web Apps Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0cd3-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0cd3-103">_**Argomento Ultima modifica:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="e0cd3-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="e0cd3-104">Dopo che Office Web Apps Server è stato aggiunto alla topologia e dopo la pubblicazione di tale topologia, dovrebbero essere visualizzati due nuovi eventi del log eventi nel log eventi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="e0cd3-105">Prima di tutto, è necessario aggiungere un evento MCU dati LS (ID evento 41034); Questo evento riporterà che il server Office Web Apps è stato individuato:</span><span class="sxs-lookup"><span data-stu-id="e0cd3-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="e0cd3-106">**Web Conferencing Server Office Web Apps Server viene individuato, il contenuto di PowerPoint è abilitato.**</span><span class="sxs-lookup"><span data-stu-id="e0cd3-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="e0cd3-107">Oltre a questo, dovrebbe essere visualizzato un altro evento di MCU dati LS (ID evento 41032) che riporta gli URL del server di Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-107">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="e0cd3-108">Ad esempio, dovresti vedere qualcosa di simile a questo:</span><span class="sxs-lookup"><span data-stu-id="e0cd3-108">For example, you should see something similar to this:</span></span>

<span data-ttu-id="e0cd3-109">**L'individuazione del server Web Conferencing Server Office Web Apps è riuscita.**</span><span class="sxs-lookup"><span data-stu-id="e0cd3-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="e0cd3-110">**Pagina del relatore interno del server Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="e0cd3-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="e0cd3-111">**Pagina partecipanti interni a Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="e0cd3-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="e0cd3-112">**Pagina del relatore esterno di Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="e0cd3-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="e0cd3-113">**Pagina partecipanti interni a Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="e0cd3-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="e0cd3-114">Se viene visualizzato un evento di MCU dati LS con l'ID evento di 41033, significa che l'individuazione di Office Web Apps Server non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="e0cd3-115">In questo caso, Microsoft Lync Server 2013 tenterà tutte le volte necessarie per individuare il server Office Web Apps appena configurato.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="e0cd3-116">Se il processo di individuazione non riesce più volte, è necessario rimuovere Office Web Apps Server dal documento della topologia, pubblicare la topologia aggiornata e quindi provare a aggiungere Office Web Apps Server alla topologia dopo la risoluzione dei problemi di connettività.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="e0cd3-117">Se il server Office Web Apps sembra configurato correttamente ed è stato riconosciuto dal processo di individuazione, è possibile verificare che Office Web Apps Server funzioni come previsto condividendo una presentazione di PowerPoint tra una coppia di client di Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="e0cd3-118">Se l'utente A può caricare e visualizzare la presentazione di PowerPoint e se l'utente B può quindi partecipare alla riunione e vedere la presentazione, il server Office Web Apps funziona.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="e0cd3-119">Anche se il server Office Web Apps sembra configurato correttamente, è possibile che venga visualizzato il messaggio di errore "alcune funzionalità di condivisione non sono disponibili a causa di problemi di connettività del server" quando si prova a condividere una presentazione di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="e0cd3-120">Se viene visualizzato il messaggio di errore, è necessario riavviare il server front-end (o i server) associato al nuovo server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="e0cd3-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

