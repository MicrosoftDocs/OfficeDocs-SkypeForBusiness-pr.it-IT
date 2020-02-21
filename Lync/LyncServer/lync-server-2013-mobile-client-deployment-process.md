---
title: 'Lync Server 2013: processo di distribuzione del client per dispositivi mobili'
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
ms.openlocfilehash: 14acbf4a8be4d453fc1a0c5dc4da303136433e0c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="4345b-102">Processo di distribuzione del client per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4345b-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4345b-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="4345b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="4345b-104">Dopo aver completato la distribuzione di Microsoft Lync Server 2013, gli utenti possono installare l'app Lync 2013 dal Marketplace mobile che sono abituati a utilizzare per il dispositivo specifico.</span><span class="sxs-lookup"><span data-stu-id="4345b-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="4345b-105">Processo di distribuzione di Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="4345b-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4345b-106">Fase</span><span class="sxs-lookup"><span data-stu-id="4345b-106">Phase</span></span></th>
<th><span data-ttu-id="4345b-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="4345b-107">Steps</span></span></th>
<th><span data-ttu-id="4345b-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4345b-108">Permissions</span></span></th>
<th><span data-ttu-id="4345b-109">Documentazione</span><span class="sxs-lookup"><span data-stu-id="4345b-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4345b-110">Eseguire le attività precedenti all'installazione.</span><span class="sxs-lookup"><span data-stu-id="4345b-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4345b-111">Verificare la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4345b-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="4345b-112">Verificare i requisiti per i certificati.</span><span class="sxs-lookup"><span data-stu-id="4345b-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4345b-113">Amministratore</span><span class="sxs-lookup"><span data-stu-id="4345b-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="4345b-114"><a href="lync-server-2013-planning-for-mobility.md">Pianificazione della mobilità in Lync server 2013</a> nella documentazione relativa alla pianificazione del server.</span><span class="sxs-lookup"><span data-stu-id="4345b-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="4345b-115"><a href="lync-server-2013-deploying-mobility.md">Distribuzione di dispositivi mobili in Lync server 2013</a> nella documentazione relativa alla distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="4345b-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="4345b-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisiti dell'infrastruttura dei certificati per Lync server 2013</a> nella documentazione relativa alla pianificazione del server.</span><span class="sxs-lookup"><span data-stu-id="4345b-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4345b-117">Installare l'applicazione Lync in un dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="4345b-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4345b-118">Installare i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="4345b-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="4345b-119">Eseguire l'installazione dal marketplace specifico per il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="4345b-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4345b-120">Amministratore</span><span class="sxs-lookup"><span data-stu-id="4345b-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="4345b-121">Istruzioni di installazione specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile Clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4345b-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4345b-122">Configurare il client.</span><span class="sxs-lookup"><span data-stu-id="4345b-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4345b-123">Configurare le impostazioni di accesso e le informazioni sul server.</span><span class="sxs-lookup"><span data-stu-id="4345b-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4345b-124">Amministratore</span><span class="sxs-lookup"><span data-stu-id="4345b-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="4345b-125"><a href="lync-server-2013-deploying-mobile-clients.md">Distribuzione di client mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4345b-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4345b-126">Testare gli scenari mobili.</span><span class="sxs-lookup"><span data-stu-id="4345b-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4345b-127">Testare la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="4345b-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="4345b-128">Verificare le funzionalità di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="4345b-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="4345b-129">Cercare un contatto nella directory aziendale.</span><span class="sxs-lookup"><span data-stu-id="4345b-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="4345b-130">Verificare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="4345b-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4345b-131">Amministratore</span><span class="sxs-lookup"><span data-stu-id="4345b-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="4345b-132">Istruzioni di verifica specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile Clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4345b-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4345b-133">Installare l'applicazione Lync nei cellulari.</span><span class="sxs-lookup"><span data-stu-id="4345b-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4345b-134">Installare i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="4345b-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="4345b-135">Eseguire l'installazione dal marketplace specifico per il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="4345b-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4345b-136">Utente</span><span class="sxs-lookup"><span data-stu-id="4345b-136">User</span></span></p></td>
<td><p><span data-ttu-id="4345b-137">Istruzioni di installazione specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile Clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4345b-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

