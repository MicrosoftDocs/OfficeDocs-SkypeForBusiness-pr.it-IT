---
title: 'Lync Server 2013: classi e descrizioni dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="3b541-102">Classi e descrizioni dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b541-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b541-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3b541-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3b541-104">In questa sezione vengono descritte tutte le classi dello schema usate da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b541-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="3b541-105">Classi e descrizioni dello schema</span><span class="sxs-lookup"><span data-stu-id="3b541-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b541-106">Classe</span><span class="sxs-lookup"><span data-stu-id="3b541-106">Class</span></span></th>
<th><span data-ttu-id="3b541-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b541-107">Description</span></span></th>
<th><span data-ttu-id="3b541-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="3b541-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b541-109">Destinatario della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3b541-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="3b541-110">Destinatario della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b541-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="3b541-111">Questa classe ausiliaria viene condivisa con la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b541-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-112">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="3b541-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="3b541-113">Questa classe è un contenitore per più contatti dell'applicazione e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-114">Novità di Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-115">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="3b541-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="3b541-116">Questa classe contiene la voce per il punto di controllo del servizio per un'istanza di Unified Communications Application Services (UCAS).</span><span class="sxs-lookup"><span data-stu-id="3b541-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="3b541-117">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-118">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="3b541-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="3b541-119">Questa classe fornisce un'associazione da un pool specifico al relativo servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b541-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="3b541-120">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-121">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="3b541-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="3b541-122">Questa classe ausiliaria di msRTCSIP-ApplicationServer contiene gli attributi che rappresentano le impostazioni per le istanze del servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b541-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="3b541-123">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-124">msRTCSIP-Archive (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-125">Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni correlate all'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3b541-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="3b541-126">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-127">msRTCSIP-ArchivingServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-128">Questa classe rappresenta un singolo server di archiviazione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="3b541-128">This class represents a single instant messaging Archiving Server.</span></span> <span data-ttu-id="3b541-129">Un'istanza di questa classe viene creata quando un computer viene attivato come server di archiviazione di messaggistica istantanea, ad esempio un computer in cui è installato il servizio di archiviazione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="3b541-129">An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="3b541-130">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-131">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="3b541-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="3b541-132">Questa classe è un contenitore per più istanze di directory conferenza e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-133">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-134">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="3b541-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="3b541-135">Questa classe contiene gli attributi che rappresentano le impostazioni per una specifica directory conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b541-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="3b541-136">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-137">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="3b541-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="3b541-138">SCP (Generic Service Control Point) per specificare il computer come server che usa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b541-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="3b541-139">Nuovo in Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-140">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="3b541-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="3b541-141">Questa classe ausiliaria contiene le impostazioni per una banca di Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="3b541-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="3b541-142">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-143">msRTCSIP-Domain</span><span class="sxs-lookup"><span data-stu-id="3b541-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="3b541-144">Questa classe contiene gli attributi che definiscono i domini configurati del registrar SIP.</span><span class="sxs-lookup"><span data-stu-id="3b541-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-145">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="3b541-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="3b541-146">Questo contenitore di classi rappresenta un singolo servizio Edge di Access.</span><span class="sxs-lookup"><span data-stu-id="3b541-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="3b541-147">Poiché un servizio di Access Edge viene distribuito nella rete perimetrale e i clienti in genere non consentono l'accesso a servizi di dominio Active Directory dalla rete perimetrale, le istanze del servizio Access Edge non vengono unite alla rete Active Directory della Intranet.</span><span class="sxs-lookup"><span data-stu-id="3b541-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="3b541-148">Di conseguenza, i proxy di Access non vengono registrati automaticamente in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b541-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="3b541-149">L'amministratore deve configurare manualmente l'esistenza di ogni istanza di Access Edge Services in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b541-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-150">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="3b541-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="3b541-151">Questa classe ausiliaria per msRTCSIP-MCU contiene gli attributi che rappresentano le impostazioni per i server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b541-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="3b541-152">Novità di Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-153">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="3b541-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="3b541-154">Questa classe ausiliaria di msRTCSIP-MediationServer contiene gli attributi che rappresentano le impostazioni per i server di mediazione.</span><span class="sxs-lookup"><span data-stu-id="3b541-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="3b541-155">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-156">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="3b541-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="3b541-157">Questa classe ausiliaria di msRTCSIP-Server contiene gli attributi che rappresentano le impostazioni per i server SIP.</span><span class="sxs-lookup"><span data-stu-id="3b541-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-158">msRTCSIP-Federation</span><span class="sxs-lookup"><span data-stu-id="3b541-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="3b541-159">Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni correlate alla Federazione.</span><span class="sxs-lookup"><span data-stu-id="3b541-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-160">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="3b541-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="3b541-161">Questa classe contiene tutte le impostazioni che si applicano in una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b541-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-162">msRTCSIP-GlobalUserPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-163">Questa classe rappresenta un singolo criterio di riunione di Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="3b541-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="3b541-164">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-165">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="3b541-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="3b541-166">Oggetto impostazione topologia globale locale.</span><span class="sxs-lookup"><span data-stu-id="3b541-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="3b541-167">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-168">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="3b541-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="3b541-169">Contenitore per contenere gli oggetti di impostazione della topologia globale.</span><span class="sxs-lookup"><span data-stu-id="3b541-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="3b541-170">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-171">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="3b541-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="3b541-172">Questa classe è un contenitore che rappresenta un'istanza di una regola di normalizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="3b541-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-173">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="3b541-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="3b541-174">Questa classe viene creata dall'applicazione per i servizi di conferenza e contiene gli attributi usati per categorizzare i numeri di telefono per le conferenze per area geografica.</span><span class="sxs-lookup"><span data-stu-id="3b541-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="3b541-175">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-176">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="3b541-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="3b541-177">Questa classe è un contenitore per più istanze di mapping dei contatti di posizione e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-178">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-179">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="3b541-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="3b541-180">Questa classe è un contenitore che rappresenta un profilo di posizione specifico.</span><span class="sxs-lookup"><span data-stu-id="3b541-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-181">msRTCSIP-LocationProfiles (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-182">Questa classe è un contenitore per più profili di posizione e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-183">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-184">msRTCSIP-LocalNormalizations (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-185">Questa classe è un contenitore per più regole di normalizzazione locali e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-186">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-187">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="3b541-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="3b541-188">Questa classe rappresenta un singolo server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b541-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="3b541-189">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-190">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="3b541-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="3b541-191">Questa classe contiene più classi msRTCSIP-MCUFactory e non ha attributi.</span><span class="sxs-lookup"><span data-stu-id="3b541-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-192">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-193">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="3b541-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="3b541-194">Questa classe è un contenitore che rappresenta una factory di servizi di conferenza per un singolo tipo di supporto.</span><span class="sxs-lookup"><span data-stu-id="3b541-194">This class is a container representing a Conferencing Server Factory for a single medium type.</span></span> <span data-ttu-id="3b541-195">Viene creata un'istanza di questa classe quando viene attivato il primo server di conferenza per il tipo specifico e il fornitore.</span><span class="sxs-lookup"><span data-stu-id="3b541-195">An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="3b541-196">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-197">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="3b541-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="3b541-198">Questa classe fornisce un'associazione da un pool specifico alla propria factory di server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b541-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="3b541-199">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-200">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="3b541-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="3b541-201">Questa classe contiene la voce per il punto di controllo del servizio di un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="3b541-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="3b541-202">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-203">msRTCSIP-Meeting (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-204">Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni delle riunioni configurabili.</span><span class="sxs-lookup"><span data-stu-id="3b541-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="3b541-205">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-206">msRTCSIP-Mobility</span><span class="sxs-lookup"><span data-stu-id="3b541-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="3b541-207">Contenitore che archivia le impostazioni di mobilità globale.</span><span class="sxs-lookup"><span data-stu-id="3b541-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="3b541-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="3b541-209">Questa classe contiene gli attributi che rappresentano le impostazioni per un singolo server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="3b541-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="3b541-210">Nuovo in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3b541-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-211">msRTCSIP-PhoneRoute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-212">Questa classe è un contenitore che rappresenta un'istanza di una route con costi minimi a un gateway o un set di gateway.</span><span class="sxs-lookup"><span data-stu-id="3b541-212">This class is a container representing an instance of a least cost route to a gateway or set of gateways.</span></span> <span data-ttu-id="3b541-213">Queste informazioni vengono usate da tutti i pool o i server aziendali che usano Standard Edition per instradare le chiamate in uscita alla rete PSTN (Public Switched Telephone Network) in modo più conveniente.</span><span class="sxs-lookup"><span data-stu-id="3b541-213">This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="3b541-214">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-215">msRTCSIP-PhoneRoutes (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-216">Questa classe è un contenitore per più route di costo inferiore e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-217">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-218">msRTCSIP-Policy (obsolete)</span><span class="sxs-lookup"><span data-stu-id="3b541-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-219">Questa classe contiene più classi di criteri di Lync Server e non ha alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-220">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-221">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="3b541-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="3b541-222">Questa classe rappresenta un singolo pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b541-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-223">msRTCSIP-Pools</span><span class="sxs-lookup"><span data-stu-id="3b541-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="3b541-224">Questa classe contiene più pool di Lync Server e non ha alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-225">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="3b541-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="3b541-226">Questa classe rappresenta il punto di controllo pointservice del controllo del servizio di un pool.</span><span class="sxs-lookup"><span data-stu-id="3b541-226">This class represents the service control pointservice control point of a pool.</span></span> <span data-ttu-id="3b541-227">Gli utenti ospitati in un pool hanno il punto di attributo msRTCSIP-PrimaryHomeServer su un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="3b541-227">Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-228">msRTCSIP-Presence</span><span class="sxs-lookup"><span data-stu-id="3b541-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="3b541-229">Contenitore in cui sono archiviate le impostazioni di presenza globale.</span><span class="sxs-lookup"><span data-stu-id="3b541-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-230">msRTCSIP-Registrar</span><span class="sxs-lookup"><span data-stu-id="3b541-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="3b541-231">Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni utente gestite dai server di registrazione SIP.</span><span class="sxs-lookup"><span data-stu-id="3b541-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-232">msRTCSIP-RouteUsage (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-233">Questa classe è un contenitore che rappresenta un'istanza dell'utilizzo di una route telefonica.</span><span class="sxs-lookup"><span data-stu-id="3b541-233">This class is a container representing an instance of a phone route usage.</span></span> <span data-ttu-id="3b541-234">La classe di utilizzo di una route telefonica è costituita da un campo attributo e da un campo Description.</span><span class="sxs-lookup"><span data-stu-id="3b541-234">A phone route usage class consists of an attribute field and a description field.</span></span> <span data-ttu-id="3b541-235">Il campo attributo definisce un tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="3b541-235">The attribute field defines a usage type.</span></span> <span data-ttu-id="3b541-236">Il campo Description consente agli amministratori di descrivere l'utilizzo di questo attributo nell'itinerario telefonico.</span><span class="sxs-lookup"><span data-stu-id="3b541-236">The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="3b541-237">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-238">msRTCSIP-RouteUsages (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-239">Questa classe contiene più istanze della classe msRTCSIP-RouteUsage e non ha alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-240">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-241">msRTCSIP-search</span><span class="sxs-lookup"><span data-stu-id="3b541-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="3b541-242">Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che limitano e controllano l'ambito dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="3b541-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-243">msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="3b541-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="3b541-244">Questa classe rappresenta un singolo server in cui è in uso Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b541-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-245">msRTCSIP-Service</span><span class="sxs-lookup"><span data-stu-id="3b541-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="3b541-246">Questa classe contiene il contenitore di impostazioni globali e gli oggetti msRTCSIP-Domain.</span><span class="sxs-lookup"><span data-stu-id="3b541-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-247">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="3b541-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="3b541-248">Questa classe contiene gli attributi che rappresentano le impostazioni per un server di conferenza attendibile.</span><span class="sxs-lookup"><span data-stu-id="3b541-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="3b541-249">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-250">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="3b541-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="3b541-251">Questa classe contiene più istanze della classe msRTCSIP-TrustedMCU e non ha alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-252">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-253">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="3b541-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="3b541-254">Questa classe contiene più classi msRTCSIP-TrustedProxy e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-255">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-256">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="3b541-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="3b541-257">Questa classe è un contenitore che rappresenta un server che gestisce il server proxy.</span><span class="sxs-lookup"><span data-stu-id="3b541-257">This class is a container representing a server running Proxy Server.</span></span> <span data-ttu-id="3b541-258">Viene creata un'istanza di questa classe quando si attiva un nuovo server proxy in un computer collegato a servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b541-258">An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="3b541-259">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-260">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="3b541-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="3b541-261">Questa classe contiene gli attributi che rappresentano le impostazioni per un server attendibile.</span><span class="sxs-lookup"><span data-stu-id="3b541-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-262">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="3b541-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="3b541-263">Questa classe è un contenitore che rappresenta un servizio attendibile instradabile con un indirizzo GRUU (Globally User Agent URI).</span><span class="sxs-lookup"><span data-stu-id="3b541-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="3b541-264">Viene creata un'istanza di questa classe quando viene attivato un nuovo server considerato attendibile da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b541-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="3b541-265">Questo server attendibile deve essere associato a un dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b541-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="3b541-266">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-267">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="3b541-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="3b541-268">Questa classe è un contenitore per più server GRUU e non contiene alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-269">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-270">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="3b541-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="3b541-271">Questa classe contiene gli attributi che rappresentano le impostazioni per un componente Web attendibile.</span><span class="sxs-lookup"><span data-stu-id="3b541-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="3b541-272">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-273">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="3b541-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="3b541-274">Questa classe contiene più istanze della classe msRTCSIP-TrustedWebComponentServer e non ha alcun attributo.</span><span class="sxs-lookup"><span data-stu-id="3b541-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="3b541-275">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-276">msRTCSIP-UnifiedCommunications (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="3b541-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3b541-277">Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi correlati alle comunicazioni unificate.</span><span class="sxs-lookup"><span data-stu-id="3b541-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="3b541-278">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3b541-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-279">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="3b541-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="3b541-280">Questa classe contiene il punto di controllo del controllo del servizio pointservice per Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="3b541-280">This class holds the service control pointservice control point for Internet Information Server (IIS).</span></span> <span data-ttu-id="3b541-281">Identifica un server come server di componenti Web.</span><span class="sxs-lookup"><span data-stu-id="3b541-281">It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="3b541-282">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b541-283">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="3b541-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="3b541-284">Questa classe fornisce un'associazione da un pool specifico ai componenti Web che verranno usati dal pool.</span><span class="sxs-lookup"><span data-stu-id="3b541-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="3b541-285">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b541-286">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="3b541-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="3b541-287">Questa classe ausiliaria di msRTCSIP-WebComponents contiene gli attributi che rappresentano le impostazioni per i componenti Web.</span><span class="sxs-lookup"><span data-stu-id="3b541-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="3b541-288">Nuovo in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3b541-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

