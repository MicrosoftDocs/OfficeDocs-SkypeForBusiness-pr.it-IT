---
title: 'Lync Server 2013: Definizione dei requisiti per le chiamate di emergenza'
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
ms.openlocfilehash: beb4b1e196a95d19a06c502cc9aeb989d6806b06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="ce2e8-102">Definizione dei requisiti per le chiamate di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce2e8-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="ce2e8-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="ce2e8-104">Prima di iniziare una distribuzione E9-1-1 di Microsoft Lync Server 2013, è necessario prima di tutto rispondere alle domande descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ce2e8-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="ce2e8-105">La pianificazione che devi eseguire dipende dal tipo di soluzione E9-1-1 che scegli di distribuire: un provider di servizi E9-1-1 trunk SIP o un gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="ce2e8-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="ce2e8-106">La tabella seguente identifica le sezioni della cartella di lavoro per la pianificazione che è necessario rivedere per ognuna di queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="ce2e8-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="ce2e8-107">Passaggi per la pianificazione per tipo di soluzione E9-1-1</span><span class="sxs-lookup"><span data-stu-id="ce2e8-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce2e8-108">Provider di servizi trunk SIP</span><span class="sxs-lookup"><span data-stu-id="ce2e8-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="ce2e8-109">Gateway ELIN</span><span class="sxs-lookup"><span data-stu-id="ce2e8-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce2e8-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce2e8-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce2e8-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Abilitazione degli utenti per E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Abilitazione degli utenti per E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce2e8-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gestione delle posizioni per i gateway ELIN in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce2e8-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce2e8-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Progettazione del trunk SIP per E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-121"><a href="lync-server-2013-including-the-security-desk.md">Incluso il servizio di sicurezza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce2e8-122"><a href="lync-server-2013-including-the-security-desk.md">Incluso il servizio di sicurezza in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-123"><a href="lync-server-2013-defining-the-location-policy.md">Definizione dei criteri di posizione per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce2e8-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Scelta di un provider di servizi E9-1-1 per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ce2e8-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce2e8-126"><a href="lync-server-2013-defining-the-location-policy.md">Definizione dei criteri di posizione per Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce2e8-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce2e8-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="ce2e8-128">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ce2e8-128">In This Section</span></span>

  - [<span data-ttu-id="ce2e8-129">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="ce2e8-130">Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="ce2e8-131">Abilitazione degli utenti per E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="ce2e8-132">Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="ce2e8-133">Gestione delle posizioni per i gateway ELIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="ce2e8-134">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="ce2e8-135">Progettazione del trunk SIP per E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="ce2e8-136">Incluso il servizio di sicurezza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="ce2e8-137">Scelta di un provider di servizi E9-1-1 per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="ce2e8-138">Definizione dei criteri di posizione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="ce2e8-139">Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce2e8-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

