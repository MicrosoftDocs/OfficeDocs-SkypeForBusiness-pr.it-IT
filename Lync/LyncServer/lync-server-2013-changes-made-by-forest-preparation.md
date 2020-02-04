---
title: 'Lync Server 2013: modifiche apportate dalla preparazione della foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4df16ffb24c4eb4e010e2b57f6af62d3518c05b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="80e52-102">Modifiche apportate dalla preparazione della foresta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80e52-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80e52-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="80e52-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="80e52-104">Questa sezione descrive le impostazioni globali e gli oggetti e i gruppi di servizi e di amministrazione universali creati dal passaggio di preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="80e52-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="80e52-105">Impostazioni globali e oggetti di Active Directory</span><span class="sxs-lookup"><span data-stu-id="80e52-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="80e52-106">Se si archiviano le impostazioni globali nel contenitore di configurazione, come nel caso di tutte le nuove distribuzioni di Lync Server 2013, la preparazione della foresta usa il contenitore di servizi esistente e aggiunge un oggetto\\ **servizio RTC** nell'oggetto Configuration Services.</span><span class="sxs-lookup"><span data-stu-id="80e52-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="80e52-107">Sotto l'oggetto servizio RTC, la preparazione della foresta aggiunge un oggetto **Impostazioni globali** di tipo msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="80e52-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="80e52-108">L'oggetto impostazioni globali contiene tutte le impostazioni applicabili alla distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="80e52-109">Se si archiviano le impostazioni globali nel contenitore di sistema, la preparazione della foresta usa un contenitore Microsoft nel contenitore di sistema del dominio radice e un oggetto\\servizio RTC nell'oggetto Microsoft System.</span><span class="sxs-lookup"><span data-stu-id="80e52-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="80e52-110">La preparazione della foresta aggiunge anche un nuovo oggetto **msRTCSIP-Domain** per il dominio radice in cui viene eseguita la procedura.</span><span class="sxs-lookup"><span data-stu-id="80e52-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="80e52-111">Gruppi di amministrazione e servizio universale di Active Directory</span><span class="sxs-lookup"><span data-stu-id="80e52-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="80e52-112">La preparazione della foresta crea gruppi universali in base al dominio specificato e aggiunge voci di controllo di accesso (ACE) per questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="80e52-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="80e52-113">Questo passaggio crea i gruppi universali nei contenitori utente del dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="80e52-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="80e52-114">I gruppi universali consentono agli amministratori di accedere e gestire le impostazioni e i servizi globali.</span><span class="sxs-lookup"><span data-stu-id="80e52-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="80e52-115">La preparazione della foresta aggiunge i tipi di gruppi universali seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e52-115">Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="80e52-116">**Gruppi amministrativi questi**   gruppi definiscono i ruoli di amministratore per una rete Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="80e52-117">**Gruppi di infrastrutture**   questi gruppi conferiscono l'autorizzazione per accedere ad aree specifiche dell'infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="80e52-118">Funzionano come componenti di gruppi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="80e52-118">They function as components of administrative groups.</span></span> <span data-ttu-id="80e52-119">Non è consigliabile modificare questi gruppi né aggiungere utenti direttamente.</span><span class="sxs-lookup"><span data-stu-id="80e52-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="80e52-120">**Gruppi di servizi**   questi gruppi sono account di servizio necessari per accedere a vari servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="80e52-121">La tabella seguente descrive i gruppi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="80e52-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="80e52-122">Gruppi amministrativi creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="80e52-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80e52-123">Gruppo amministrativo</span><span class="sxs-lookup"><span data-stu-id="80e52-123">Administrative group</span></span></th>
<th><span data-ttu-id="80e52-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80e52-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80e52-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="80e52-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="80e52-126">Consente ai membri di gestire le impostazioni del server e del pool, inclusi tutti i ruoli del server, le impostazioni globali e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="80e52-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e52-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="80e52-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="80e52-128">Consente ai membri di gestire le impostazioni utente e di trasferire gli utenti da un server o da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="80e52-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80e52-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="80e52-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="80e52-130">Consente ai membri di leggere le impostazioni del server, del pool e dell'utente.</span><span class="sxs-lookup"><span data-stu-id="80e52-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="80e52-131">La tabella seguente descrive i gruppi di infrastrutture.</span><span class="sxs-lookup"><span data-stu-id="80e52-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="80e52-132">Gruppi di infrastrutture creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="80e52-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80e52-133">Gruppo infrastruttura</span><span class="sxs-lookup"><span data-stu-id="80e52-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="80e52-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80e52-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80e52-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="80e52-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="80e52-136">Concede l'accesso in scrittura agli oggetti setting globali per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e52-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="80e52-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="80e52-138">Concede l'accesso in sola lettura agli oggetti setting globali per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80e52-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="80e52-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="80e52-140">Concede l'accesso in sola lettura alle impostazioni utente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e52-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="80e52-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="80e52-142">Concede l'accesso in sola lettura alle impostazioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="80e52-143">Questo gruppo non ha accesso alle impostazioni del livello del pool, solo alle impostazioni specifiche di un singolo server.</span><span class="sxs-lookup"><span data-stu-id="80e52-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80e52-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="80e52-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="80e52-145">Concede l'accesso in sola lettura alla configurazione di Lync Server e viene inserito nel gruppo amministratori locali degli appliance Survivable Branch durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="80e52-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="80e52-146">La tabella seguente descrive i gruppi di servizi.</span><span class="sxs-lookup"><span data-stu-id="80e52-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="80e52-147">Gruppi di servizi creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="80e52-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80e52-148">Gruppo di servizi</span><span class="sxs-lookup"><span data-stu-id="80e52-148">Service group</span></span></th>
<th><span data-ttu-id="80e52-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80e52-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80e52-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="80e52-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="80e52-151">Include gli account di servizio usati per eseguire front end server e server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="80e52-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="80e52-152">Questo gruppo consente ai server di accedere in lettura/scrittura alle impostazioni globali di Lync Server e agli oggetti utente di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80e52-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e52-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="80e52-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="80e52-154">Include gli account di servizio usati per eseguire servizi di conferenza A/V, Web Services, Mediation Server, server di archiviazione e server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="80e52-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80e52-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="80e52-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="80e52-156">Include gli account di servizio usati per eseguire Lync Server Edge Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e52-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="80e52-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="80e52-158">Include server che possono partecipare alla replica di Lync Server Central Management store.</span><span class="sxs-lookup"><span data-stu-id="80e52-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80e52-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="80e52-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="80e52-160">Concede l'accesso in sola lettura alle impostazioni di Lync Server, ma consente la configurazione per l'installazione di una distribuzione Survivable Branch Server e Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="80e52-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="80e52-161">La preparazione della foresta aggiunge quindi gruppi di servizi e di amministrazione ai gruppi di infrastruttura appropriati, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="80e52-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="80e52-162">RTCUniversalServerAdmins viene aggiunto a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="80e52-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="80e52-163">RTCUniversalUserAdmins viene aggiunto come membro di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="80e52-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="80e52-164">RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins vengono aggiunti come membri di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="80e52-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="80e52-165">La preparazione della foresta crea inoltre i seguenti gruppi di controllo di accesso basati sui ruoli (RBAC):</span><span class="sxs-lookup"><span data-stu-id="80e52-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="80e52-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-166">CSAdministrator</span></span>

  - <span data-ttu-id="80e52-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="80e52-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="80e52-168">CSHelpDesk</span></span>

  - <span data-ttu-id="80e52-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="80e52-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="80e52-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="80e52-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="80e52-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="80e52-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="80e52-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="80e52-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="80e52-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="80e52-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="80e52-176">CsResponseGroupManager</span></span>

<span data-ttu-id="80e52-177">Per informazioni dettagliate sui ruoli RBAC e sulle attività consentite per ognuna, vedere [pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="80e52-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="80e52-178">La preparazione della foresta crea sia gli assi privati che quelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="80e52-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="80e52-179">Crea Ace private nel contenitore di impostazioni globali usato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80e52-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="80e52-180">Questo contenitore viene usato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda di dove si archiviano le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="80e52-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="80e52-181">Le voci ACE pubbliche create dalla preparazione della foresta sono elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="80e52-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="80e52-182">Ace pubbliche create dalla preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="80e52-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80e52-183">ACE</span><span class="sxs-lookup"><span data-stu-id="80e52-183">ACE</span></span></th>
<th><span data-ttu-id="80e52-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="80e52-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80e52-185">Read Root Domain System container (non ereditato)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="80e52-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="80e52-186">X</span><span class="sxs-lookup"><span data-stu-id="80e52-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e52-187">Contenitore di DisplaySpecifiers della configurazione di lettura (non ereditato)</span><span class="sxs-lookup"><span data-stu-id="80e52-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="80e52-188">X</span><span class="sxs-lookup"><span data-stu-id="80e52-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="80e52-189"><STRONG>\*</STRONG>Le voci ACE non ereditate non consentono l'accesso agli oggetti figlio in questi contenitori.</span><span class="sxs-lookup"><span data-stu-id="80e52-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="80e52-190">Le voci ACE ereditate concedono l'accesso agli oggetti figlio in questi contenitori.</span><span class="sxs-lookup"><span data-stu-id="80e52-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="80e52-191">Nel contenitore di configurazione, in contesto dei nomi di configurazione, la preparazione della foresta esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e52-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="80e52-192">Aggiunge una voce **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** per la pagina delle **proprietà RTC** in attributi adminContextMenu e adminPropertyPages dello specificatore di visualizzazione della lingua per utenti, contatti e INETORGPERSON, ad esempio CN = user-Display, CN = 409, CN = DisplaySpecifiers.</span><span class="sxs-lookup"><span data-stu-id="80e52-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="80e52-193">Aggiunge un oggetto **RTCPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che si applica alle classi User e Contact.</span><span class="sxs-lookup"><span data-stu-id="80e52-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="80e52-194">Aggiunge un oggetto **RTCUserSearchPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che si applica alle classi User, Contact, ou e DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="80e52-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="80e52-195">Aggiunge **msRTCSIP-PrimaryUserAddress** nell'attributo **Columns** di ogni specificatore di visualizzazione dell'unità organizzativa (ad esempio, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) e copia i valori dell'attributo **Columns** della visualizzazione predefinita, ad esempio CN = default-display, CN = 409, CN = DisplaySpecifiers.</span><span class="sxs-lookup"><span data-stu-id="80e52-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="80e52-196">Aggiunge gli attributi di filtro msRTCSIP **-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**e **msRTCSIP-UserEnabled** nell'attributo **nell'attributeDisplayNames** di ogni identificatore di visualizzazione della lingua per gli utenti, i contatti e gli oggetti InetOrgPerson, ad esempio in inglese: CN = user-Display, CN = 409, CN = DisplaySpecifiers.</span><span class="sxs-lookup"><span data-stu-id="80e52-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

