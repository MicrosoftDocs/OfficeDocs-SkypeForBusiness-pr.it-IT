---
title: 'Lync Server 2013: supportare riunioni di grandi dimensioni'
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
ms.openlocfilehash: 6d2c36d99bc5af62771aabb643df1223db3a291c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="6e02e-102">Supporto di riunioni di grandi dimensioni tramite Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e02e-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e02e-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6e02e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6e02e-104">Le riunioni di grandi dimensioni non seguono il modello di test descritto nella sezione precedente perché presentano le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e02e-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="6e02e-105">Il formato della riunione è una presentazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="6e02e-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="6e02e-106">Uno o più utenti sono relatori e tutti gli altri membri partecipano solo come partecipanti.</span><span class="sxs-lookup"><span data-stu-id="6e02e-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="6e02e-107">La condivisione delle presentazioni di PowerPoint è l'attività di collaborazione dati principale.</span><span class="sxs-lookup"><span data-stu-id="6e02e-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="6e02e-108">L'audio è obbligatorio e può essere usato anche il video.</span><span class="sxs-lookup"><span data-stu-id="6e02e-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="6e02e-109">Una persona dedicata, in genere l'organizzatore della riunione o un assistente dell'organizzatore configura bene la riunione in anticipo.</span><span class="sxs-lookup"><span data-stu-id="6e02e-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="6e02e-110">Il personale dedicato (non i relatori) esegue la riunione, inclusa la connessione a una riunione online, verificando che l'audio, il video e la condivisione delle diapositive funzionino, gestiscono i ruoli di lobby e utenti, riattivano e riattivano i partecipanti, le domande e la gestione delle registrazioni, come appropriato.</span><span class="sxs-lookup"><span data-stu-id="6e02e-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="6e02e-111">Il supporto di riunioni di grandi dimensioni fino a 1000 utenti richiede la risoluzione dei problemi relativi al modello hardware condiviso e al modello senza prenotazione.</span><span class="sxs-lookup"><span data-stu-id="6e02e-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="6e02e-112">Per avere sufficienti risorse di memoria e CPU per riunioni fino a 1000 utenti, i server front-end ospitanti non devono ospitare altri carichi di lavoro istantanei e di presenza o di Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6e02e-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="6e02e-113">Non deve inoltre ospitare altre riunioni, indipendentemente dalle dimensioni delle altre riunioni.</span><span class="sxs-lookup"><span data-stu-id="6e02e-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="6e02e-114">Ciò significa che le riunioni di hosting di un massimo di 1000 utenti richiedono la configurazione di un pool di Lync Server separato dedicato all'hosting di riunioni di grandi dimensioni fino a 1000 utenti.</span><span class="sxs-lookup"><span data-stu-id="6e02e-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="6e02e-115">Un pool di Lync Server dedicato all'hosting di riunioni di grandi dimensioni dovrebbe ospitare una sola riunione di un massimo di 1000 utenti contemporaneamente, in modo che gli orari delle riunioni debbano essere prenotati in anticipo tramite un processo di pianificazione fuori banda per garantire il supporto dedicato del servizio front end ERS.</span><span class="sxs-lookup"><span data-stu-id="6e02e-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="6e02e-116">Per supportare più di una riunione di grandi dimensioni contemporaneamente, è consigliabile configurare più pool di riunioni di grandi dimensioni dedicati.</span><span class="sxs-lookup"><span data-stu-id="6e02e-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="6e02e-117">È consigliabile che una persona dedicata esegua e controlli la parte online di una riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6e02e-117">We recommend that a dedicated person run and monitor the online portion of a large meeting.</span></span> <span data-ttu-id="6e02e-118">Questa persona può essere l'organizzatore, il delegato dell'organizzatore o del relatore oppure un membro del team di supporto di grandi riunioni dedicato, a seconda delle preferenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6e02e-118">This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="6e02e-119">Nelle sezioni seguenti viene descritto come implementare un pool dedicato per riunioni di grandi dimensioni, incluse le procedure consigliate per l'uso di Lync Server 2013 per supportare scenari di grandi riunioni.</span><span class="sxs-lookup"><span data-stu-id="6e02e-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e02e-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6e02e-120">In This Section</span></span>

  - [<span data-ttu-id="6e02e-121">Configurazione del supporto per riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e02e-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="6e02e-122">Gestione di riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e02e-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

