---
title: 'Lync Server 2013: supporto di riunioni di grandi dimensioni'
description: 'Lync Server 2013: supporto di riunioni di grandi dimensioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e116f4668c37fd26eea5cec322a8c6483385e7d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554782"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="12e0e-103">Supporto di riunioni di grandi dimensioni con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e0e-103">Supporting large meetings using Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e0e-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="12e0e-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="12e0e-105">Le riunioni di grandi dimensioni non seguono il modello di test descritto nella sezione precedente, poiché hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="12e0e-105">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="12e0e-106">La riunione è una presentazione uno a molti.</span><span class="sxs-lookup"><span data-stu-id="12e0e-106">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="12e0e-107">Pochi utenti hanno il ruolo di relatori o il relatore è uno solo e gli altri utenti sono solo partecipanti.</span><span class="sxs-lookup"><span data-stu-id="12e0e-107">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="12e0e-108">La principale attività di collaborazione dati è la condivisione di presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="12e0e-108">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="12e0e-109">L'audio è indispensabile e possono essere usate anche le funzionalità video.</span><span class="sxs-lookup"><span data-stu-id="12e0e-109">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="12e0e-110">Una persona dedicata, di solito l'organizzatore della riunione o un assistente dell'organizzatore, imposta la riunione con buon anticipo.</span><span class="sxs-lookup"><span data-stu-id="12e0e-110">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="12e0e-111">Uno staff dedicato (non i relatori) si occupa di aspetti della riunione quali la connessione alla riunione online, la verifica del funzionamento di audio, video e condivisione delle diapositive, la gestione della sala di attesa e dei ruoli utente, la disattivazione e la riattivazione dell'audio dei partecipanti, la raccolta delle domande e la gestione delle registrazione, come più opportuno.</span><span class="sxs-lookup"><span data-stu-id="12e0e-111">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="12e0e-112">Per supportare riunioni di grandi dimensioni con un massimo di 1000 utenti, è necessario affrontare i problemi relativi al modello dell'hardware condiviso e al modello senza prenotazione.</span><span class="sxs-lookup"><span data-stu-id="12e0e-112">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="12e0e-113">Per disporre di risorse di memoria e CPU sufficienti per riunioni fino a 1000 utenti, i front end server host non devono ospitare altri carichi di lavoro per la messaggistica istantanea e la presenza o VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="12e0e-113">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="12e0e-114">Inoltre, non devono ospitare altre riunioni, non importa quanto grandi.</span><span class="sxs-lookup"><span data-stu-id="12e0e-114">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="12e0e-115">Questo significa che l'hosting di riunioni fino a 1000 utenti richiede la configurazione di un pool di Lync Server separato dedicato all'hosting di riunioni di grandi dimensioni fino a 1000 utenti.</span><span class="sxs-lookup"><span data-stu-id="12e0e-115">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="12e0e-116">Un pool di Lync Server dedicato all'hosting di riunioni di grandi dimensioni deve ospitare una sola riunione fino a 1000 utenti contemporaneamente, in modo che i tempi di riunione debbano essere prenotati in anticipo tramite un processo di pianificazione fuori banda per garantire un supporto dedicato dai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="12e0e-116">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="12e0e-117">Per supportare più riunioni di grandi dimensioni contemporaneamente, si consiglia di configurare più pool dedicati.</span><span class="sxs-lookup"><span data-stu-id="12e0e-117">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="12e0e-p103">Si consiglia inoltre di dedicare una persona all'esecuzione e al monitoraggio della parte online delle riunioni di grandi dimensioni. Questa persona può essere l'organizzatore, un delegato dell'organizzatore o del relatore o un membro del team di supporto alle riunioni di grandi dimensioni, a seconda delle preferenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="12e0e-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="12e0e-120">Nelle sezioni seguenti viene descritto come implementare un pool dedicato per riunioni di grandi dimensioni, incluse le procedure consigliate per l'utilizzo di Lync Server 2013 per il supporto di scenari di riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="12e0e-120">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12e0e-121">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="12e0e-121">In This Section</span></span>

  - [<span data-ttu-id="12e0e-122">Configurazione del supporto per le riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e0e-122">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="12e0e-123">Gestione di riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e0e-123">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

