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
ms.openlocfilehash: d70b090f59c0a0f8510d778ef659def77cfd0747
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="79c29-102">Modifiche dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c29-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c29-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="79c29-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="79c29-104">Prima di distribuire e utilizzare Lync Server 2013, è necessario preparare i servizi di dominio Active Directory estendendo lo schema.</span><span class="sxs-lookup"><span data-stu-id="79c29-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="79c29-105">Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79c29-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="79c29-106">Lync Server 2013 richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti.</span><span class="sxs-lookup"><span data-stu-id="79c29-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="79c29-107">Inoltre, molte informazioni di configurazione per Lync Server 2013 sono archiviate nell'archivio di gestione centrale invece che in servizi di dominio Active Directory come nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="79c29-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="79c29-108">Le informazioni seguenti sono ancora memorizzate in servizi di dominio Active Directory in Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="79c29-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="79c29-109">**Estensioni dello schema**:</span><span class="sxs-lookup"><span data-stu-id="79c29-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="79c29-110">Estensioni degli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="79c29-110">User object extensions</span></span>
    
      - <span data-ttu-id="79c29-111">Estensioni per le classi di Office Communications Server 2007 e Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti supportate</span><span class="sxs-lookup"><span data-stu-id="79c29-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="79c29-112">**Dati** (memorizzati nello schema esteso di Lync Server e nelle classi dello schema esistenti):</span><span class="sxs-lookup"><span data-stu-id="79c29-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="79c29-113">URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="79c29-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="79c29-114">Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="79c29-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="79c29-115">Puntatore all'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="79c29-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="79c29-116">Account di autenticazione Kerberos (un oggetto computer facoltativo)</span><span class="sxs-lookup"><span data-stu-id="79c29-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="79c29-117">In questo argomento vengono descritte le modifiche allo schema di Active Directory richieste da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79c29-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="79c29-118">Non vengono descritte le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="79c29-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="79c29-119">Per un elenco delle classi e delle relative descrizioni, vedere [classi e descrizioni di schemi in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="79c29-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="79c29-120">Per un elenco degli attributi e delle relative descrizioni, vedere [attributi e descrizioni dello schema in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="79c29-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="79c29-121">Per un elenco di classi con gli attributi che possono contenere, vedere [schema Attributes by Class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="79c29-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="79c29-122">Il prefisso msRTCSIP identifica le classi e gli attributi specifici di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79c29-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="79c29-123">Nuovi attributi di Active Directory</span><span class="sxs-lookup"><span data-stu-id="79c29-123">New Active Directory Attributes</span></span>

<span data-ttu-id="79c29-124">Nella tabella seguente vengono descritti gli attributi di Active Directory aggiunti da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79c29-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="79c29-125">Attributi aggiunti da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c29-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c29-126">Attributo</span><span class="sxs-lookup"><span data-stu-id="79c29-126">Attribute</span></span></th>
<th><span data-ttu-id="79c29-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79c29-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c29-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="79c29-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="79c29-129">Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente.</span><span class="sxs-lookup"><span data-stu-id="79c29-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="79c29-130">I criteri di conservazione conservano gli elementi della cassetta postale per l'utente per tutta la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="79c29-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="79c29-131">Questo attributo è condiviso con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="79c29-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c29-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="79c29-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="79c29-133">Questo è l'ID del gruppo di routing SIP.</span><span class="sxs-lookup"><span data-stu-id="79c29-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="79c29-134">Gli utenti dello stesso gruppo registreranno lo stesso front end server.</span><span class="sxs-lookup"><span data-stu-id="79c29-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c29-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="79c29-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="79c29-136">Questo attributo viene utilizzato per archiviare il backend di SQL Server con mirroring utilizzato dal pool Front end.</span><span class="sxs-lookup"><span data-stu-id="79c29-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="79c29-137">Classi di Active Directory modificate</span><span class="sxs-lookup"><span data-stu-id="79c29-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="79c29-138">Nella tabella seguente vengono descritte le classi di Active Directory modificate da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79c29-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="79c29-139">Classi modificate da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c29-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c29-140">Classe</span><span class="sxs-lookup"><span data-stu-id="79c29-140">Class</span></span></th>
<th><span data-ttu-id="79c29-141">Modifica</span><span class="sxs-lookup"><span data-stu-id="79c29-141">Change</span></span></th>
<th><span data-ttu-id="79c29-142">Classe o attributo</span><span class="sxs-lookup"><span data-stu-id="79c29-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c29-143">Utente</span><span class="sxs-lookup"><span data-stu-id="79c29-143">User</span></span></p></td>
<td><p><span data-ttu-id="79c29-144">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="79c29-144">add: mayContain</span></span></p>
<p><span data-ttu-id="79c29-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="79c29-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="79c29-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="79c29-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="79c29-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="79c29-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c29-148">Contatto</span><span class="sxs-lookup"><span data-stu-id="79c29-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="79c29-149">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="79c29-149">add: mayContain</span></span></p>
<p><span data-ttu-id="79c29-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="79c29-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="79c29-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="79c29-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="79c29-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="79c29-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c29-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="79c29-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="79c29-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="79c29-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="79c29-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="79c29-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c29-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="79c29-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="79c29-157">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="79c29-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="79c29-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="79c29-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

