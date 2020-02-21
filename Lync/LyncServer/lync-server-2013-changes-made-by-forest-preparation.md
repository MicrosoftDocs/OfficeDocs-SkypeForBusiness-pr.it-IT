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
ms.openlocfilehash: 6954e8a4cd76e103516fd1f2323ef04d820dc056
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="fa255-102">Modifiche apportate dalla preparazione della foresta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa255-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa255-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="fa255-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="fa255-104">In questa sezione vengono descritti gli oggetti e le impostazioni globali e i gruppi amministrativi e di servizio universali creati durante il passaggio di preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="fa255-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="fa255-105">Oggetti e impostazioni globali di Active Directory</span><span class="sxs-lookup"><span data-stu-id="fa255-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="fa255-106">Se si archiviano le impostazioni globali nel contenitore di configurazione (come nel caso di tutte le nuove distribuzioni di Lync Server 2013), la preparazione della foresta utilizza il contenitore dei servizi esistente e aggiunge un\\oggetto **RTC Service** nell'oggetto Configuration Services.</span><span class="sxs-lookup"><span data-stu-id="fa255-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="fa255-107">Nell'oggetto RTC Service viene aggiunto per la preparazione della foresta un oggetto **Global Settings** di tipo msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="fa255-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="fa255-108">L'oggetto Global Settings contiene tutte le impostazioni che si applicano alla distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="fa255-109">Se si archiviano le impostazioni globali nel contenitore di sistema, la preparazione della foresta utilizza un contenitore Microsoft nel contenitore del sistema del dominio radice e un oggetto\\RTC Service nell'oggetto System Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa255-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="fa255-110">Durante la preparazione della foresta viene aggiunto inoltre un nuovo oggetto **msRTCSIP-Domain** per il dominio radice in cui viene eseguita la procedura.</span><span class="sxs-lookup"><span data-stu-id="fa255-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="fa255-111">Gruppi amministrativi e di servizio universali di Active Directory</span><span class="sxs-lookup"><span data-stu-id="fa255-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="fa255-p102">Durante la preparazione della foresta vengono creati gruppi universali basati sul dominio specificato e vengono aggiunte voci di controllo di accesso (ACE) per tali gruppi. Durante questo passaggio vengono creati i gruppi universali nei contenitori User del dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="fa255-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="fa255-p103">I gruppi universali consentono agli amministratori di accedere ai servizi e alle impostazioni globali e di gestirli. Per la preparazione della foresta vengono aggiunti i tipi di gruppi universali seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa255-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="fa255-116">**Gruppi amministrativi questi**   gruppi definiscono i ruoli di amministratore per una rete di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="fa255-117">**Gruppi di infrastruttura**   questi gruppi forniscono le autorizzazioni per accedere a aree specifiche dell'infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="fa255-118">Funzionano come componenti di gruppi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="fa255-118">They function as components of administrative groups.</span></span> <span data-ttu-id="fa255-119">Non modificare questi gruppi né aggiungervi direttamente gli utenti.</span><span class="sxs-lookup"><span data-stu-id="fa255-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="fa255-120">**Gruppi di servizi**   questi gruppi sono account di servizio necessari per accedere ai diversi servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="fa255-121">Nella tabella riportata di seguito vengono descritti i gruppi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="fa255-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="fa255-122">Gruppi amministrativi creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="fa255-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa255-123">Gruppo amministrativo</span><span class="sxs-lookup"><span data-stu-id="fa255-123">Administrative group</span></span></th>
<th><span data-ttu-id="fa255-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa255-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa255-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="fa255-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="fa255-126">Consente ai membri di gestire le impostazioni di server e pool, inclusi tutti gli utenti, le impostazioni globali e i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="fa255-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa255-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="fa255-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="fa255-128">Consente ai membri di gestire le impostazioni utente e di spostare gli utenti da un server o da un pool a un altro.</span><span class="sxs-lookup"><span data-stu-id="fa255-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa255-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="fa255-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="fa255-130">Consente ai membri di leggere le impostazioni di server, pool e utenti.</span><span class="sxs-lookup"><span data-stu-id="fa255-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa255-131">Nella tabella riportata di seguito vengono descritti i gruppi di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="fa255-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="fa255-132">Gruppi di infrastruttura creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="fa255-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa255-133">Gruppo di infrastruttura</span><span class="sxs-lookup"><span data-stu-id="fa255-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="fa255-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa255-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa255-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="fa255-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="fa255-136">Concede l'accesso in scrittura a oggetti setting globali per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa255-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="fa255-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="fa255-138">Concede l'accesso in sola lettura agli oggetti setting globali per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa255-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="fa255-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="fa255-140">Concede l'accesso in sola lettura alle impostazioni utente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa255-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="fa255-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="fa255-142">Concede l'accesso in sola lettura alle impostazioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="fa255-143">Questo gruppo non dispone dell'accesso alle impostazioni a livello di pool, ma solo a quelle specifiche di un singolo server.</span><span class="sxs-lookup"><span data-stu-id="fa255-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa255-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="fa255-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="fa255-145">Concede l'accesso in sola lettura alla configurazione di Lync Server e viene inserito nel gruppo Administrators locale di Survivable Branch Appliances durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fa255-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa255-146">Nella tabella riportata di seguito vengono descritti i gruppi di servizio.</span><span class="sxs-lookup"><span data-stu-id="fa255-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="fa255-147">Gruppi di servizio creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="fa255-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa255-148">Gruppo di servizio</span><span class="sxs-lookup"><span data-stu-id="fa255-148">Service group</span></span></th>
<th><span data-ttu-id="fa255-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa255-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa255-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="fa255-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="fa255-151">Include gli account di servizio utilizzati per l'esecuzione di front end server e server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fa255-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="fa255-152">Questo gruppo consente ai server di accedere in lettura/scrittura alle impostazioni globali di Lync Server e agli oggetti utente di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fa255-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa255-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="fa255-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="fa255-154">Include gli account di servizio utilizzati per l'esecuzione di A/V Conferencing Server, servizi Web, Mediation Server, server di archiviazione e Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa255-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="fa255-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="fa255-156">Include gli account di servizio utilizzati per eseguire i server perimetrali di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa255-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="fa255-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="fa255-158">Include i server che possono partecipare alla replica dell'archivio di gestione centrale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa255-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="fa255-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="fa255-160">Concede l'accesso in sola lettura alle impostazioni di Lync Server, ma consente la configurazione per l'installazione di una distribuzione Survivable Branch Server e Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="fa255-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa255-161">Durante la preparazione della foresta vengono quindi aggiunti i gruppi amministrativi e di servizio ai gruppi di infrastruttura appropriati, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fa255-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="fa255-162">RTCUniversalServerAdmins viene aggiunto a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="fa255-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="fa255-163">RTCUniversalUserAdmins viene aggiunto come membro di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="fa255-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="fa255-164">RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins vengono aggiunti come membri di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="fa255-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="fa255-165">Durante la preparazione della foresta vengono creati inoltre i gruppi di controllo dell'accesso basato sui ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa255-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="fa255-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-166">CSAdministrator</span></span>

  - <span data-ttu-id="fa255-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="fa255-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="fa255-168">CSHelpDesk</span></span>

  - <span data-ttu-id="fa255-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="fa255-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="fa255-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="fa255-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="fa255-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="fa255-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="fa255-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="fa255-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="fa255-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="fa255-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="fa255-176">CsResponseGroupManager</span></span>

<span data-ttu-id="fa255-177">Per informazioni dettagliate sui ruoli RBAC e sulle attività consentite per ognuno di essi, vedere [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="fa255-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="fa255-178">Durante la preparazione della foresta vengono create voci di controllo di accesso private e pubbliche.</span><span class="sxs-lookup"><span data-stu-id="fa255-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="fa255-179">Crea voci ACE private nel contenitore delle impostazioni globali utilizzato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa255-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="fa255-180">Questo contenitore viene utilizzato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda della posizione in cui vengono archiviate le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="fa255-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="fa255-181">Le voci di controllo di accesso pubbliche create durante la preparazione della foresta sono elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="fa255-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="fa255-182">Voci di controllo di accesso pubbliche create durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="fa255-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa255-183">ACE</span><span class="sxs-lookup"><span data-stu-id="fa255-183">ACE</span></span></th>
<th><span data-ttu-id="fa255-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="fa255-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa255-185">Lettura del contenitore System del dominio radice (non ereditata)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="fa255-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="fa255-186">X</span><span class="sxs-lookup"><span data-stu-id="fa255-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa255-187">Lettura del contenitore DisplaySpecifiers della configurazione (non ereditata)</span><span class="sxs-lookup"><span data-stu-id="fa255-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="fa255-188">X</span><span class="sxs-lookup"><span data-stu-id="fa255-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fa255-189"><STRONG>\*</STRONG>Le voci ACE non ereditate non consentono di accedere agli oggetti figlio in questi contenitori.</span><span class="sxs-lookup"><span data-stu-id="fa255-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="fa255-190">Alle voci di controllo di accesso ereditate viene concesso l'accesso agli oggetti figlio presenti in tali contenitori.</span><span class="sxs-lookup"><span data-stu-id="fa255-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="fa255-191">Nel contesto dei nomi di configurazione all'interno del contenitore Configuration durante la preparazione della foresta vengono eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa255-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="fa255-192">Aggiunta di una voce **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** per la pagina della proprietà **RTC** negli attributi adminContextMenu e adminPropertyPages dell'identificatore di visualizzazione lingua per gli oggetti User, Contact e InetOrgPerson, ad esempio, CN=user-Display,CN=409,CN=DisplaySpecifiers.</span><span class="sxs-lookup"><span data-stu-id="fa255-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="fa255-193">Aggiunta di un oggetto **RTCPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che da applicare alle classi User e Contact.</span><span class="sxs-lookup"><span data-stu-id="fa255-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="fa255-194">Aggiunta di un oggetto **RTCUserSearchPropertySet** di tipo **controlAccessRight** in **Extended-Rights** da applicare alle classi User, Contact, OU e DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="fa255-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="fa255-195">Aggiunta di un oggetto **msRTCSIP-PrimaryUserAddress** nell'attributo **extraColumns** di ogni identificatore di visualizzazione unità organizzativa lingua (ad esempio CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia dei valori dell'attributo **extraColumns** della visualizzazione predefinita (ad esempio CN=default-Display, CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="fa255-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="fa255-196">Aggiunta degli attributi di filtro **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** nell'attributo **attributeDisplayNames** di ogni identificatore di visualizzazione lingua per gli oggetti User, Contact e InetOrgPerson (ad esempio per la lingua inglese: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="fa255-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

