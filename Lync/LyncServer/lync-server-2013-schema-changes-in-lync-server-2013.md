---
title: 'Lync Server 2013: modifiche allo schema in Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b48cb0d83c12d1db8ec3fc43901d7e28d4288fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="d868d-102">Modifiche dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d868d-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d868d-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d868d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d868d-104">Prima di distribuire e utilizzare Lync Server 2013, è necessario preparare i servizi di dominio Active Directory estendendo lo schema.</span><span class="sxs-lookup"><span data-stu-id="d868d-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="d868d-105">Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d868d-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="d868d-106">Lync Server 2013 richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti.</span><span class="sxs-lookup"><span data-stu-id="d868d-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="d868d-107">Inoltre, molte informazioni di configurazione per Lync Server 2013 sono archiviate nell'archivio di gestione centrale invece che in servizi di dominio Active Directory come nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d868d-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="d868d-108">Le informazioni seguenti sono ancora memorizzate in servizi di dominio Active Directory in Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="d868d-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="d868d-109">**Estensioni dello schema**:</span><span class="sxs-lookup"><span data-stu-id="d868d-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="d868d-110">Estensioni degli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="d868d-110">User object extensions</span></span>
    
      - <span data-ttu-id="d868d-111">Estensioni per le classi di Office Communications Server 2007 e Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti supportate</span><span class="sxs-lookup"><span data-stu-id="d868d-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="d868d-112">**Dati** (memorizzati nello schema esteso di Lync Server e nelle classi dello schema esistenti):</span><span class="sxs-lookup"><span data-stu-id="d868d-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="d868d-113">URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="d868d-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="d868d-114">Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="d868d-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="d868d-115">Puntatore all'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="d868d-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="d868d-116">Account di autenticazione Kerberos (un oggetto computer facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d868d-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="d868d-117">In questo argomento vengono descritte le modifiche allo schema di Active Directory richieste da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d868d-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="d868d-118">Non vengono descritte le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="d868d-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="d868d-119">Per un elenco delle classi e delle relative descrizioni, vedere [classi e descrizioni di schemi in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="d868d-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="d868d-120">Per un elenco degli attributi e delle relative descrizioni, vedere [attributi e descrizioni dello schema in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="d868d-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="d868d-121">Per un elenco di classi con gli attributi che possono contenere, vedere [schema Attributes by Class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="d868d-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="d868d-122">Il prefisso msRTCSIP identifica le classi e gli attributi specifici di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d868d-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="d868d-123">Nuovi attributi di Active Directory</span><span class="sxs-lookup"><span data-stu-id="d868d-123">New Active Directory Attributes</span></span>

<span data-ttu-id="d868d-124">Nella tabella seguente vengono descritti gli attributi di Active Directory aggiunti da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d868d-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="d868d-125">Attributi aggiunti da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d868d-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d868d-126">Attributo</span><span class="sxs-lookup"><span data-stu-id="d868d-126">Attribute</span></span></th>
<th><span data-ttu-id="d868d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d868d-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d868d-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d868d-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="d868d-129">Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente.</span><span class="sxs-lookup"><span data-stu-id="d868d-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="d868d-130">I criteri di conservazione conservano gli elementi della cassetta postale per l'utente per tutta la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="d868d-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="d868d-131">Questo attributo è condiviso con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d868d-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d868d-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d868d-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="d868d-133">Questo è l'ID del gruppo di routing SIP.</span><span class="sxs-lookup"><span data-stu-id="d868d-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="d868d-134">Gli utenti dello stesso gruppo registreranno lo stesso front end server.</span><span class="sxs-lookup"><span data-stu-id="d868d-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d868d-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d868d-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="d868d-136">Questo attributo viene utilizzato per archiviare il backend di SQL Server con mirroring utilizzato dal pool Front end.</span><span class="sxs-lookup"><span data-stu-id="d868d-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="d868d-137">Classi di Active Directory modificate</span><span class="sxs-lookup"><span data-stu-id="d868d-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="d868d-138">Nella tabella seguente vengono descritte le classi di Active Directory modificate da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d868d-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="d868d-139">Classi modificate da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d868d-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d868d-140">Classe</span><span class="sxs-lookup"><span data-stu-id="d868d-140">Class</span></span></th>
<th><span data-ttu-id="d868d-141">Modifica</span><span class="sxs-lookup"><span data-stu-id="d868d-141">Change</span></span></th>
<th><span data-ttu-id="d868d-142">Classe o attributo</span><span class="sxs-lookup"><span data-stu-id="d868d-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d868d-143">Utente</span><span class="sxs-lookup"><span data-stu-id="d868d-143">User</span></span></p></td>
<td><p><span data-ttu-id="d868d-144">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d868d-144">add: mayContain</span></span></p>
<p><span data-ttu-id="d868d-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d868d-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d868d-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d868d-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="d868d-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d868d-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d868d-148">Contatto</span><span class="sxs-lookup"><span data-stu-id="d868d-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="d868d-149">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d868d-149">add: mayContain</span></span></p>
<p><span data-ttu-id="d868d-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d868d-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d868d-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d868d-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="d868d-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d868d-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d868d-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="d868d-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="d868d-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d868d-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d868d-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d868d-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d868d-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="d868d-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="d868d-157">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d868d-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d868d-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d868d-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

