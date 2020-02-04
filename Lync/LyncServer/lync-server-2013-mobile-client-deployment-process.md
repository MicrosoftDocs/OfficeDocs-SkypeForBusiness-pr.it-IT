---
title: 'Lync Server 2013: processo di distribuzione client per dispositivi mobili'
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
ms.openlocfilehash: e6beaeac91dae0ff5fbf755c4ccb33cae288df75
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="36795-102">Processo di distribuzione client per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36795-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36795-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="36795-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="36795-104">Dopo aver completato una distribuzione di Microsoft Lync Server 2013, gli utenti possono installare l'app Lync 2013 dal Marketplace mobile che sono abituati a usare per il dispositivo specifico.</span><span class="sxs-lookup"><span data-stu-id="36795-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="36795-105">Processo di distribuzione di Lync mobile</span><span class="sxs-lookup"><span data-stu-id="36795-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36795-106">Fase</span><span class="sxs-lookup"><span data-stu-id="36795-106">Phase</span></span></th>
<th><span data-ttu-id="36795-107">Passaggi</span><span class="sxs-lookup"><span data-stu-id="36795-107">Steps</span></span></th>
<th><span data-ttu-id="36795-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="36795-108">Permissions</span></span></th>
<th><span data-ttu-id="36795-109">Documentazione</span><span class="sxs-lookup"><span data-stu-id="36795-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36795-110">Eseguire attività di pre-installazione.</span><span class="sxs-lookup"><span data-stu-id="36795-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="36795-111">Verificare la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36795-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="36795-112">Verificare i requisiti dei certificati.</span><span class="sxs-lookup"><span data-stu-id="36795-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="36795-113">Amministratore</span><span class="sxs-lookup"><span data-stu-id="36795-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="36795-114"><a href="lync-server-2013-planning-for-mobility.md">Pianificazione della mobilità in Lync server 2013</a> nella documentazione relativa alla pianificazione del server.</span><span class="sxs-lookup"><span data-stu-id="36795-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="36795-115"><a href="lync-server-2013-deploying-mobility.md">Distribuzione della mobilità in Lync server 2013</a> nella documentazione di distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="36795-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="36795-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisiti per l'infrastruttura dei certificati per Lync server 2013</a> nella documentazione relativa alla pianificazione del server.</span><span class="sxs-lookup"><span data-stu-id="36795-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36795-117">Installare l'applicazione Lync in un dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="36795-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="36795-118">Installare prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="36795-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="36795-119">Installare dal Marketplace specifico per il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="36795-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="36795-120">Amministratore</span><span class="sxs-lookup"><span data-stu-id="36795-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="36795-121">Istruzioni per l'installazione specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">distribuzione di client mobili in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36795-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36795-122">Configurare il client.</span><span class="sxs-lookup"><span data-stu-id="36795-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="36795-123">Configurare le impostazioni di accesso e le informazioni sul server.</span><span class="sxs-lookup"><span data-stu-id="36795-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="36795-124">Amministratore</span><span class="sxs-lookup"><span data-stu-id="36795-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="36795-125"><a href="lync-server-2013-deploying-mobile-clients.md">Distribuzione di client mobili in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="36795-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36795-126">Testare scenari per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="36795-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="36795-127">Testare la messaggistica istantanea (IM) e la presenza.</span><span class="sxs-lookup"><span data-stu-id="36795-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="36795-128">Verificare i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="36795-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="36795-129">Cercare un contatto nella directory aziendale.</span><span class="sxs-lookup"><span data-stu-id="36795-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="36795-130">Verificare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="36795-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="36795-131">Amministratore</span><span class="sxs-lookup"><span data-stu-id="36795-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="36795-132">Istruzioni di verifica specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">distribuzione di client mobili in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36795-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36795-133">Installare l'applicazione Lync sui telefoni cellulari.</span><span class="sxs-lookup"><span data-stu-id="36795-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="36795-134">Installare prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="36795-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="36795-135">Installare dal Marketplace specifico per il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="36795-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="36795-136">Utente</span><span class="sxs-lookup"><span data-stu-id="36795-136">User</span></span></p></td>
<td><p><span data-ttu-id="36795-137">Istruzioni per l'installazione specifiche per il dispositivo mobile in <a href="lync-server-2013-deploying-mobile-clients.md">distribuzione di client mobili in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36795-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

