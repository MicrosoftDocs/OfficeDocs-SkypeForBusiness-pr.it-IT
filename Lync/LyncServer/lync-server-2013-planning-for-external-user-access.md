---
title: "Lync Server 2013: pianificazione dell'accesso degli utenti esterni"
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
ms.openlocfilehash: 15b4a64c729268efcbdf2bb572c47122d4b41510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="b142d-102">Pianificazione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b142d-103">_**Ultimo argomento modificato:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="b142d-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="b142d-p101">Nella maggior parte delle organizzazioni le comunicazioni coinvolgono servizi e utenti non compresi nella rete interna. Tali servizi e utenti includono dipendenti temporaneamente o permanentemente fuori sede, dipendenti di organizzazioni clienti e partner, persone che utilizzano i servizi di messaggistica istantanea pubblica e potenziali clienti, partner e utenti anonimi che vengono invitati a riunioni e presentazioni. In questa documentazione queste persone vengono indicate come *utenti esterni*.</span><span class="sxs-lookup"><span data-stu-id="b142d-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="b142d-107">Con Microsoft Lync Server 2013, gli utenti dell'organizzazione possono utilizzare la messaggistica istantanea e la presenza per comunicare con gli utenti esterni e possono partecipare a conferenze audio/video (A/V) e Web Conferencing con i dipendenti esterni e altri tipi di utente esterno.</span><span class="sxs-lookup"><span data-stu-id="b142d-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="b142d-108">È inoltre possibile supportare l'accesso esterno da dispositivi mobili e tramite VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="b142d-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="b142d-109">Gli utenti esterni che non sono membri dell'organizzazione possono partecipare alle riunioni di Lync Server 2013, consentendo ai partecipanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="b142d-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="b142d-110">Per supportare le comunicazioni tra il firewall dell'organizzazione, è necessario distribuire Lync Server 2013 Edge Server nella rete perimetrale (nota anche come DMZ, area demilitarizzata e subnet schermata).</span><span class="sxs-lookup"><span data-stu-id="b142d-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="b142d-111">Il server perimetrale controlla il modo in cui gli utenti esterni al firewall possono connettersi alla distribuzione interna di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b142d-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="b142d-112">Controlla inoltre le comunicazioni con utenti esterni che hanno origine nel firewall.</span><span class="sxs-lookup"><span data-stu-id="b142d-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="b142d-113">A seconda di specifici requisiti, è possibile distribuire uno o più server perimetrali in una o più posizioni.</span><span class="sxs-lookup"><span data-stu-id="b142d-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="b142d-114">In questa sezione vengono descritti gli scenari per l'accesso degli utenti esterni in Lync Server 2013 e viene illustrato come pianificare la topologia di proxy inverso e Edge.</span><span class="sxs-lookup"><span data-stu-id="b142d-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b142d-115">Anche se è necessario un server perimetrale per il supporto di VoIP aziendale e accesso utente esterno, questa sezione si concentra sul supporto per messaggistica istantanea, presenza, A/V Conferencing, Federazione, Web Conferencing e Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="b142d-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="b142d-116">Per informazioni dettagliate sul supporto di VoIP aziendale, vedere <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b142d-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b142d-117">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="b142d-117">In This Section</span></span>

  - [<span data-ttu-id="b142d-118">Modifiche apportate in Lync Server 2013 che influiscono sulla pianificazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="b142d-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="b142d-119">Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="b142d-120">Panoramica dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="b142d-121">Informazioni su individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="b142d-122">Scelta di una topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="b142d-123">Raccolta dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="b142d-124">Determinare i requisiti DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="b142d-125">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="b142d-126">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="b142d-127">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b142d-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

