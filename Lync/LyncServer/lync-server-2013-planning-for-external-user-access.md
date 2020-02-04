---
title: "Lync Server 2013: Pianificazione dell'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17d38abe775a915fc3357610ad2b741eb0e77628
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d9d18-102">Pianificazione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9d18-103">_**Argomento Ultima modifica:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="d9d18-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="d9d18-104">Le comunicazioni nella maggior parte delle organizzazioni coinvolgono i servizi e gli utenti che non si trovano all'interno della rete interna.</span><span class="sxs-lookup"><span data-stu-id="d9d18-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="d9d18-105">Questi servizi e utenti includono i dipendenti temporaneamente o definitivamente fuori sede, i dipendenti delle organizzazioni di clienti o partner, le persone che usano servizi di messaggistica istantanea pubblica e i potenziali clienti, partner e utenti anonimi che si invitano alle riunioni e alle presentazioni.</span><span class="sxs-lookup"><span data-stu-id="d9d18-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="d9d18-106">In questa documentazione, queste persone sono chiamate collettivamente *utenti esterni*.</span><span class="sxs-lookup"><span data-stu-id="d9d18-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="d9d18-107">Con Microsoft Lync Server 2013, gli utenti dell'organizzazione possono usare la messaggistica istantanea e la presenza per comunicare con gli utenti esterni e possono partecipare a conferenze audio/video (A/V) e conferenze Web con i dipendenti esterni e altri tipi di utente esterno.</span><span class="sxs-lookup"><span data-stu-id="d9d18-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="d9d18-108">Puoi anche supportare l'accesso esterno da dispositivi mobili e da VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d9d18-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="d9d18-109">Gli utenti esterni che non sono membri dell'organizzazione possono partecipare alle riunioni di Lync Server 2013, consentendo i partecipanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="d9d18-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="d9d18-110">Per supportare le comunicazioni attraverso il firewall dell'organizzazione, distribuire Lync Server 2013 Edge Server nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata).</span><span class="sxs-lookup"><span data-stu-id="d9d18-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="d9d18-111">Il server perimetrale controlla il modo in cui gli utenti esterni al firewall possono connettersi alla distribuzione interna di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9d18-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="d9d18-112">Controlla inoltre le comunicazioni con utenti esterni che hanno origine all'interno del firewall.</span><span class="sxs-lookup"><span data-stu-id="d9d18-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="d9d18-113">A seconda dei requisiti, è possibile distribuire uno o più Edge Server in una o più posizioni.</span><span class="sxs-lookup"><span data-stu-id="d9d18-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="d9d18-114">Questa sezione descrive scenari per l'accesso degli utenti esterni in Lync Server 2013 e spiega come pianificare la topologia del proxy inverso e del bordo.</span><span class="sxs-lookup"><span data-stu-id="d9d18-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9d18-115">Anche se è necessario un server perimetrale per supportare l'accesso a VoIP aziendale e utenti esterni, questa sezione si incentra sul supporto di messaggistica istantanea, presenza, servizi di conferenza A/V, Federazione, Web Conferencing e Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="d9d18-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="d9d18-116">Per informazioni dettagliate sul supporto per VoIP aziendale, vedere <A href="lync-server-2013-planning-for-enterprise-voice.md">pianificazione di VoIP aziendale in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d9d18-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d9d18-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d9d18-117">In This Section</span></span>

  - [<span data-ttu-id="d9d18-118">Modifiche introdotte in Lync Server 2013 che incidono sulla pianificazione dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="d9d18-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="d9d18-119">Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="d9d18-120">Panoramica dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="d9d18-121">Informazioni sull'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="d9d18-122">Scelta di una topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="d9d18-123">Raccolta dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="d9d18-124">Determinare i requisiti di DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="d9d18-125">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="d9d18-126">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="d9d18-127">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d18-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

