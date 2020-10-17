---
title: 'Lync Server 2013: processo di distribuzione del client per dispositivi mobili'
description: 'Lync Server 2013: processo di distribuzione del client per dispositivi mobili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563482"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="37b33-103">Processo di distribuzione del client per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37b33-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37b33-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="37b33-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="37b33-105">Dopo aver completato la distribuzione di Microsoft Lync Server 2013, gli utenti possono installare l'app Lync 2013 dal Marketplace mobile che sono abituati a utilizzare per il dispositivo specifico.</span><span class="sxs-lookup"><span data-stu-id="37b33-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="37b33-106">Processo di distribuzione di Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="37b33-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37b33-107">Fase</span><span class="sxs-lookup"><span data-stu-id="37b33-107">Phase</span></span></th>
<th><span data-ttu-id="37b33-108">Passaggi</span><span class="sxs-lookup"><span data-stu-id="37b33-108">Steps</span></span></th>
<th><span data-ttu-id="37b33-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="37b33-109">Permissions</span></span></th>
<th><span data-ttu-id="37b33-110">Documentazione</span><span class="sxs-lookup"><span data-stu-id="37b33-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37b33-111">Eseguire le attività precedenti all'installazione.</span><span class="sxs-lookup"><span data-stu-id="37b33-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="37b33-112">Verificare la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37b33-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="37b33-113">Verificare i requisiti per i certificati.</span><span class="sxs-lookup"><span data-stu-id="37b33-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="37b33-114">Amministratore</span><span class="sxs-lookup"><span data-stu-id="37b33-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="37b33-115"><a href="lync-server-2013-planning-for-mobility.md">Pianificazione della mobilità in Lync server 2013</a> nella documentazione relativa alla pianificazione del server.</span><span class="sxs-lookup"><span data-stu-id="37b33-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="37b33-116"><a href="lync-server-2013-deploying-mobility.md">Distribuzione di dispositivi mobili in Lync server 2013</a> nella documentazione relativa alla distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="37b33-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="37b33-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisiti dell'infrastruttura dei certificati per Lync server 2013</a> nella documentazione relativa alla pianificazione del server.</span><span class="sxs-lookup"><span data-stu-id="37b33-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37b33-118">Installare l'applicazione Lync in un dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="37b33-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="37b33-119">Installare i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="37b33-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="37b33-120">Eseguire l'installazione dal marketplace specifico per il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="37b33-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="37b33-121">Amministratore</span><span class="sxs-lookup"><span data-stu-id="37b33-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="37b33-122">Istruzioni di installazione specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile Clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="37b33-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37b33-123">Configurare il client.</span><span class="sxs-lookup"><span data-stu-id="37b33-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="37b33-124">Configurare le impostazioni di accesso e le informazioni sul server.</span><span class="sxs-lookup"><span data-stu-id="37b33-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="37b33-125">Amministratore</span><span class="sxs-lookup"><span data-stu-id="37b33-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="37b33-126"><a href="lync-server-2013-deploying-mobile-clients.md">Distribuzione di client mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37b33-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37b33-127">Testare gli scenari mobili.</span><span class="sxs-lookup"><span data-stu-id="37b33-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="37b33-128">Testare la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="37b33-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="37b33-129">Verificare le funzionalità di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="37b33-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="37b33-130">Cercare un contatto nella directory aziendale.</span><span class="sxs-lookup"><span data-stu-id="37b33-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="37b33-131">Verificare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="37b33-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="37b33-132">Amministratore</span><span class="sxs-lookup"><span data-stu-id="37b33-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="37b33-133">Istruzioni di verifica specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile Clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="37b33-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37b33-134">Installare l'applicazione Lync nei cellulari.</span><span class="sxs-lookup"><span data-stu-id="37b33-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="37b33-135">Installare i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="37b33-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="37b33-136">Eseguire l'installazione dal marketplace specifico per il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="37b33-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="37b33-137">Utente</span><span class="sxs-lookup"><span data-stu-id="37b33-137">User</span></span></p></td>
<td><p><span data-ttu-id="37b33-138">Istruzioni di installazione specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile Clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="37b33-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

