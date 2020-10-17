---
title: 'Lync Server 2013: definizione dei requisiti per le chiamate di emergenza'
description: 'Lync Server 2013: definizione dei requisiti per le chiamate di emergenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3c9908dcb4008a1442af86971e42eb4096a98b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545402"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="2431c-103">Definizione dei requisiti per le chiamate di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-103">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2431c-104">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2431c-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2431c-105">Prima di iniziare una distribuzione di Microsoft Lync Server 2013 E9-1-1, è innanzitutto necessario essere in grado di rispondere alle domande descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2431c-105">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="2431c-106">Gli elementi da pianificare dipendono dal tipo di soluzione E9-1-1 che si sceglie di distribuire, ovvero un provider di servizi E9-1-1 trunk SIP o un gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="2431c-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="2431c-107">Nella tabella seguente sono indicate le sezioni di questa cartella di lavoro per la pianificazione che è consigliabile consultare per ogni tipo di soluzione.</span><span class="sxs-lookup"><span data-stu-id="2431c-107">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="2431c-108">Passaggi per la pianificazione in base al tipo di soluzione E9-1-1</span><span class="sxs-lookup"><span data-stu-id="2431c-108">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2431c-109">Provider di servizi trunk SIP</span><span class="sxs-lookup"><span data-stu-id="2431c-109">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="2431c-110">Gateway ELIN</span><span class="sxs-lookup"><span data-stu-id="2431c-110">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2431c-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2431c-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definizione degli elementi di rete utilizzati per determinare la posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definizione degli elementi di rete utilizzati per determinare la posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2431c-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Abilitazione degli utenti per il servizio E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Abilitazione degli utenti per il servizio E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2431c-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gestione delle posizioni per i gateway ELIN in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2431c-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2431c-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Progettazione del trunk SIP per il servizio E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-122"><a href="lync-server-2013-including-the-security-desk.md">Inclusione del desk di sicurezza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2431c-123"><a href="lync-server-2013-including-the-security-desk.md">Inclusione del desk di sicurezza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-123"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-124"><a href="lync-server-2013-defining-the-location-policy.md">Definizione dei criteri percorso per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-124"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2431c-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Scelta di un provider di servizi E9-1-1 per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2431c-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Assegnazione dell'ambito dei criteri percorso in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2431c-127"><a href="lync-server-2013-defining-the-location-policy.md">Definizione dei criteri percorso per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-127"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2431c-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Assegnazione dell'ambito dei criteri percorso in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2431c-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="2431c-129">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="2431c-129">In This Section</span></span>

  - [<span data-ttu-id="2431c-130">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-130">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="2431c-131">Definizione degli elementi di rete utilizzati per determinare la posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-131">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="2431c-132">Abilitazione degli utenti per il servizio E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-132">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="2431c-133">Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-133">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="2431c-134">Gestione delle posizioni per i gateway ELIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-134">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="2431c-135">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-135">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="2431c-136">Progettazione del trunk SIP per il servizio E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-136">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="2431c-137">Inclusione del desk di sicurezza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-137">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="2431c-138">Scelta di un provider di servizi E9-1-1 per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-138">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="2431c-139">Definizione dei criteri percorso per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-139">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="2431c-140">Assegnazione dell'ambito dei criteri percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2431c-140">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

