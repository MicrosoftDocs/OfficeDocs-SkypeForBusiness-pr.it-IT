---
title: 'Lync Server 2013: utilizzo di Call me at con un telefono abilitato per Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 157ce646e606f6327e6d7a5fd1957da1480797e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="da76d-102">Utilizzo di Call me at con un telefono abilitato per Lync e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da76d-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da76d-103">_**Ultimo argomento modificato:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="da76d-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="da76d-104">La funzionalità Call me at in Lync consente agli utenti di partecipare alla parte audio di una conferenza utilizzando un telefono cellulare, "linea terrestre" o un altro dispositivo connesso alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="da76d-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="da76d-105">Quando si tenta di partecipare a una riunione utilizzando Lync, in genere viene visualizzata la finestra di dialogo **join meeting audio** :</span><span class="sxs-lookup"><span data-stu-id="da76d-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="da76d-106">![Utilizzo di Lync per partecipare a una schermata di audioconferenza della finestra riunione](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Utilizzo di Lync per partecipare a una schermata di audioconferenza della finestra riunione")</span><span class="sxs-lookup"><span data-stu-id="da76d-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="da76d-107">Se si seleziona **chiamami**, è possibile scegliere un numero di telefono dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="da76d-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="da76d-108">Lync Server 2013 invierà una chiamata al numero selezionato ed è quindi possibile utilizzare il telefono per partecipare alla parte audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="da76d-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="da76d-109">L'elenco a discesa è popolato dai numeri di telefono (per telefono cellulare, telefono di casa o altro telefono) immesso nella scheda **telefoni** della finestra di dialogo **Opzioni di Lync** :</span><span class="sxs-lookup"><span data-stu-id="da76d-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="da76d-110">![Configurazione delle opzioni per i telefoni Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Configurazione delle opzioni per i telefoni Lync")</span><span class="sxs-lookup"><span data-stu-id="da76d-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="da76d-111">Se non sono stati immessi numeri di telefono nella scheda **telefoni** , non saranno disponibili numeri nella casella a discesa.</span><span class="sxs-lookup"><span data-stu-id="da76d-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="da76d-112">Tuttavia, è sempre possibile fare clic su **nuovo numero** e fare in modo che Lync Server chiami il numero di telefono desiderato:</span><span class="sxs-lookup"><span data-stu-id="da76d-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="da76d-113">![Schermata di chiamata di Lync join meeting audio Window](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Schermata di chiamata di Lync join meeting audio Window")</span><span class="sxs-lookup"><span data-stu-id="da76d-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="da76d-114">La funzione Call me at è estremamente adatta a condizione che venga utilizzata come previsto: se Lync Server chiama un numero di telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="da76d-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="da76d-115">Tuttavia, è possibile eseguire un'esperienza meno che ottimale se si chiede a Lync Server di chiamarla in un endpoint abilitato per Lync, ad esempio un telefono in una sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="da76d-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="da76d-116">Di seguito è riportato il problema che potrebbe essere eseguito, oltre a due modi per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="da76d-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="da76d-117">Per iniziare, ecco cosa succede quando si fornisce la funzionalità chiamami alla caratteristica con il numero di telefono di un telefono abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="da76d-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="da76d-118">Si supponga che Ken remario tenti di partecipare a una riunione facendo in modo che Lync Server lo chiami a 1-206-555-1219, un numero di telefono abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da76d-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="da76d-119">Ken verrà inizialmente connesso alla riunione, ma dopo qualche secondo Lync visualizzerà la chiamata del messaggio **non è stata completata o è terminata**e Ken sembra essere stato eliminato dalla riunione:</span><span class="sxs-lookup"><span data-stu-id="da76d-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="da76d-120">![Schermata di Lync Call Conferencing Window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Schermata di Lync Call Conferencing Window")</span><span class="sxs-lookup"><span data-stu-id="da76d-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="da76d-121">Si noti, tuttavia, che vi è una discrepanza all'interno della finestra di conversazione di Lync.</span><span class="sxs-lookup"><span data-stu-id="da76d-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="da76d-122">Ken è l'unico nome elencato sotto l'intestazione **partecipanti** .</span><span class="sxs-lookup"><span data-stu-id="da76d-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="da76d-123">Tuttavia, se si guarda la barra del titolo della finestra, si noterà che la conferenza contiene un totale di 4 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="da76d-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="da76d-124">Analogamente, se si cerca nella finestra di conversazione di qualsiasi altro partecipante alla conferenza, non verrà visualizzato nessun elenco di informazioni:</span><span class="sxs-lookup"><span data-stu-id="da76d-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="da76d-125">![Schermata della finestra elenco partecipanti di Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Schermata della finestra elenco partecipanti di Lync")</span><span class="sxs-lookup"><span data-stu-id="da76d-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="da76d-126">Eppure, allo stesso tempo, Ken è in grado di partecipare alla parte audio della chiamata utilizzando il suo telefono abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="da76d-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="da76d-127">La funzione Call me at ha effettivamente avuto esito positivo, ma l'utilizzo dell'utente è inferiore a quello ottimale.</span><span class="sxs-lookup"><span data-stu-id="da76d-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="da76d-128">Esistono almeno due modi per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="da76d-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="da76d-129">Se si è già entrati a far parte di una conferenza in questo modo, come ha fatto Ken, è in genere possibile risolvere il problema coinvolgendo una modalità diversa.</span><span class="sxs-lookup"><span data-stu-id="da76d-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="da76d-130">Ad esempio, se si invia un messaggio istantaneo, la finestra di conversazione mostrerà tutti i partecipanti alla conferenza, tra cui:</span><span class="sxs-lookup"><span data-stu-id="da76d-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="da76d-131">![Schermata della conversazione di Lync e dell'elenco dei partecipanti](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Schermata della conversazione di Lync e dell'elenco dei partecipanti")</span><span class="sxs-lookup"><span data-stu-id="da76d-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="da76d-132">A questo punto, è necessario essere in grado di partecipare alla riunione nel modo previsto.</span><span class="sxs-lookup"><span data-stu-id="da76d-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="da76d-133">In alternativa, è possibile evitare il problema del tutto cambiando la modalità di partecipazione alla riunione.</span><span class="sxs-lookup"><span data-stu-id="da76d-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="da76d-134">Se è necessario che Lync Server chiami un telefono abilitato per Lync Server, iniziare a partecipare alla riunione senza una connessione audio.</span><span class="sxs-lookup"><span data-stu-id="da76d-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="da76d-135">A tale scopo, selezionare non aggiungere l'audio quando viene visualizzata la finestra di dialogo join meeting audio:</span><span class="sxs-lookup"><span data-stu-id="da76d-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="da76d-136">![Schermata di Lync Don ' t join the meeting audio Window](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Schermata di Lync Don ' t join the meeting audio Window")</span><span class="sxs-lookup"><span data-stu-id="da76d-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="da76d-137">Dopo aver correttamente connesso alla riunione, è ora possibile "invitare" il telefono abilitato per Lync Server anche per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="da76d-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="da76d-138">A tale scopo, posizionare il puntatore del mouse sull'icona persone e quindi fare clic su **invita altre persone**:</span><span class="sxs-lookup"><span data-stu-id="da76d-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="da76d-139">![Lync invitare altri partecipanti screenshot finestra](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invitare altri partecipanti screenshot finestra")</span><span class="sxs-lookup"><span data-stu-id="da76d-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="da76d-140">Verrà visualizzata la finestra di dialogo **Invia una chat** .</span><span class="sxs-lookup"><span data-stu-id="da76d-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="da76d-141">Ignorare il titolo della finestra di dialogo (non si sta effettivamente inviando un messaggio istantaneo) e digitare il numero di telefono del telefono abilitato per Lync:</span><span class="sxs-lookup"><span data-stu-id="da76d-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="da76d-142">![Schermata Invia una finestra di dialogo di messaggistica istantanea](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Schermata Invia una finestra di dialogo di messaggistica istantanea")</span><span class="sxs-lookup"><span data-stu-id="da76d-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="da76d-143">Dopo aver fatto clic su **OK**, Lync Server chiamerà il numero immesso nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="da76d-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="da76d-144">Quando si effettua la connessione, si avranno funzionalità audio complete tramite il telefono abilitato per Lync e si sarà in grado di visualizzare e interagire con l'elenco completo delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="da76d-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

