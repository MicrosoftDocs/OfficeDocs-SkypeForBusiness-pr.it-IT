---
title: 'Lync Server 2013: attributi e descrizioni dello schema'
description: 'Lync Server 2013: attributi e descrizioni dello schema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557192"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="a99d2-103">Attributi e descrizioni dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a99d2-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a99d2-104">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a99d2-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a99d2-105">In questa sezione vengono descritti tutti gli attributi dello schema utilizzati da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a99d2-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="a99d2-106">Per le classi associate agli attributi, vedere [schema Attributes by Class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="a99d2-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="a99d2-107">Per un elenco di classi e attributi nuovi in Lync Server 2013, vedere [modifiche dello schema in Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="a99d2-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="a99d2-108">Gli attributi che sono coppie collegate sono specificati come collegamenti inoltrati o collegamenti indietro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-108">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="a99d2-109">Un attributo che fa riferimento a un altro oggetto è un collegamento in avanti. l'attributo dell'altro oggetto che fa riferimento al primo oggetto è un collegamento a ritroso.</span><span class="sxs-lookup"><span data-stu-id="a99d2-109">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="a99d2-110">I collegamenti inoltrati sono aggiornabili, mentre i collegamenti indietro sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a99d2-110">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="a99d2-111">Alcuni attributi hanno un valore di maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="a99d2-111">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="a99d2-112">Per questi attributi, ogni impostazione è rappresentata da un bit e il valore decimale visualizzato rappresenta la posizione del bit.</span><span class="sxs-lookup"><span data-stu-id="a99d2-112">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="a99d2-113">Le posizioni dei bit iniziano con il bit 0.</span><span class="sxs-lookup"><span data-stu-id="a99d2-113">Bit positions start with bit 0.</span></span> <span data-ttu-id="a99d2-114">Ad esempio, 1 (binario) è il bit 0 set e 10000 (binario) è bit 4 set.</span><span class="sxs-lookup"><span data-stu-id="a99d2-114">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="a99d2-115">Ogni bit rappresenta una proprietà.</span><span class="sxs-lookup"><span data-stu-id="a99d2-115">Each bit represents a property.</span></span> <span data-ttu-id="a99d2-116">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="a99d2-116">The following are some examples:</span></span>

  - <span data-ttu-id="a99d2-117">10000 (binario) ha un valore decimale pari a 16, ovvero il bit 4 è impostato.</span><span class="sxs-lookup"><span data-stu-id="a99d2-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="a99d2-118">100 milioni (binario) ha un valore decimale pari a 256 (ovvero il bit 8 è impostato).</span><span class="sxs-lookup"><span data-stu-id="a99d2-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="a99d2-119">1100 (binario) ha un valore decimale pari a 12 (ovvero i bit 2 e 3 sono impostati, le proprietà rappresentate da entrambi i bit sono abilitate).</span><span class="sxs-lookup"><span data-stu-id="a99d2-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="a99d2-120">1111000001 (binario) ha un valore decimale di 961 (ovvero i bit 0, 6, 7, 8 e 9 sono impostati, le proprietà per ognuno di questi bit sono abilitate).</span><span class="sxs-lookup"><span data-stu-id="a99d2-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="a99d2-121">Attributi dello schema per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a99d2-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a99d2-122">Attributo</span><span class="sxs-lookup"><span data-stu-id="a99d2-122">Attribute</span></span></th>
<th><span data-ttu-id="a99d2-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a99d2-123">Description</span></span></th>
<th><span data-ttu-id="a99d2-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="a99d2-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="a99d2-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="a99d2-126">Un attributo esistente nei servizi di dominio Active Directory che ora è associato alle classi <strong>msRTCSIP-Pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="a99d2-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="a99d2-127">Questo attributo consente di specificare il nome di dominio completo (FQDN) di un pool o di un Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="a99d2-128">Un valore valido per ogni segmento è di 63 caratteri; un valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-129">Nuovo in Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-130">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-131">Questo attributo contiene la rappresentazione di stringa del nome distinto (DN) dell'oggetto in un'altra foresta corrispondente a questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="a99d2-131">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="a99d2-132">Questo attributo viene utilizzato per l'espansione del gruppo di distribuzione e la frequenza automatica.</span><span class="sxs-lookup"><span data-stu-id="a99d2-132">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="a99d2-133">Questo attributo è definito nello schema predefinito di Active Directory per Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-133">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="a99d2-134">Per evitare di richiedere un aggiornamento di AD DS a Windows Server 2003 R2, la preparazione dello schema di Active Directory estende lo schema di Windows Server 2003 con questa definizione di attributo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-135">Nuovo in Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="a99d2-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="a99d2-137">Questo attributo multivalore contiene le impostazioni della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="a99d2-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="a99d2-138">Questo attributo è condiviso con la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a99d2-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="a99d2-139">Nuovo in Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a99d2-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="a99d2-141">Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="a99d2-142">I criteri di conservazione conservano gli elementi della cassetta postale per l'utente per tutta la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="a99d2-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="a99d2-143">Questo attributo è condiviso con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a99d2-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-144">Nuovo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a99d2-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-145">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="a99d2-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="a99d2-146">Questo attributo archivia le informazioni relative ai provider di servizi di audioconferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-147">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-148">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="a99d2-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="a99d2-149">Questo attributo punta alla voce del servizio attendibile per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-150">Nuovo in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-151">msRTCSIP-Application</span><span class="sxs-lookup"><span data-stu-id="a99d2-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="a99d2-152">Questo attributo contiene un elenco delle applicazioni ospitate nel server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a99d2-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-153">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-154">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="a99d2-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="a99d2-155">Questo attributo consente di specificare le opzioni per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-156">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-157">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="a99d2-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="a99d2-158">Questo attributo contiene la lingua principale per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-159">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-160">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="a99d2-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="a99d2-161">Questo attributo multivalore contiene le lingue secondarie per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-162">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-163">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="a99d2-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="a99d2-164">Questo attributo contiene un elenco di server applicazioni appartenenti al pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-164">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="a99d2-165">Il collegamento in avanti corrispondente a questo attributo di collegamento a ritroso è <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-165">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-166">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-167">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="a99d2-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="a99d2-168">Questo attributo punta al pool a cui appartiene il server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a99d2-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="a99d2-169">Si tratta del collegamento in avanti.</span><span class="sxs-lookup"><span data-stu-id="a99d2-169">This is the forward link.</span></span> <span data-ttu-id="a99d2-170">Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-171">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-172">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-173">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-174">Obsoleto in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-175">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-176">Questo attributo specifica l'impostazione predefinita globale all'interno del limite della foresta per l'archiviazione di tutte le comunicazioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a99d2-176">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="a99d2-177">Questo viene applicato dal livello dell'agente di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-177">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="a99d2-178">L'intervallo di valori per questo attributo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a99d2-178">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-179"><strong>True</strong>: archivia tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="a99d2-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="a99d2-180"><strong>False</strong>: non archiviare tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="a99d2-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="a99d2-181">Questo attributo controlla globalmente, all'interno del limite della foresta, la modalità di archiviazione delle comunicazioni degli utenti all'interno di una rete interna.</span><span class="sxs-lookup"><span data-stu-id="a99d2-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="a99d2-182"><strong>Comportamento di Live Communications Server 2005 (ora ritirato)</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="a99d2-183">L'intervallo di valori per questo attributo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a99d2-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-184">0: archivia il corpo del messaggio [bit 0]</span><span class="sxs-lookup"><span data-stu-id="a99d2-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="a99d2-185">1: non archiviare il corpo del messaggio [bit 0]</span><span class="sxs-lookup"><span data-stu-id="a99d2-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="a99d2-186"><strong>Comportamento di Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="a99d2-187">L'intervallo di valori per questo attributo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a99d2-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-188">0: ArchiveFederationDefaultWithoutBody (ritirato)</span><span class="sxs-lookup"><span data-stu-id="a99d2-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-189">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="a99d2-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="a99d2-190">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="a99d2-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="a99d2-191">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="a99d2-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="a99d2-192">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="a99d2-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a99d2-193">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="a99d2-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a99d2-194">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="a99d2-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="a99d2-195">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="a99d2-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a99d2-196">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="a99d2-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a99d2-197">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="a99d2-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a99d2-198">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="a99d2-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="a99d2-199">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="a99d2-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="a99d2-200">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="a99d2-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="a99d2-201">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="a99d2-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="a99d2-202">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="a99d2-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-203">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-204">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-205">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-206">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-207">Obsoleto in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-208">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-209">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-210">Obsoleto in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-211">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="a99d2-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="a99d2-212">Questo attributo è un numero intero utilizzato come campo di bit per controllare se le comunicazioni di un singolo utente devono essere archiviate.</span><span class="sxs-lookup"><span data-stu-id="a99d2-212">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="a99d2-213">Questo controllo viene applicato dal livello dell'agente di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-213">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="a99d2-214">È contrassegnata per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-214">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a99d2-215">L'ambito di questo attributo è specifico di un singolo utente o di un contatto.</span><span class="sxs-lookup"><span data-stu-id="a99d2-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="a99d2-216">Di seguito sono riportati i valori validi (e le posizioni dei bit associati) in Lync Server:</span><span class="sxs-lookup"><span data-stu-id="a99d2-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-217">0: non archiviare (nessun bit impostato)</span><span class="sxs-lookup"><span data-stu-id="a99d2-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-218">1: ritirato (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="a99d2-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-219">2: ritirato (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="a99d2-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-220">4: archiviazione delle comunicazioni interne (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="a99d2-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-221">8: archiviare le comunicazioni federate (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="a99d2-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="a99d2-222">I valori precedentemente validi in Live Communications Server 2005 sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-223">0: utilizzare il valore predefinito definito da <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation (</strong> nell'ordine di precedenza:</span><span class="sxs-lookup"><span data-stu-id="a99d2-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-224">1: Archivio</span><span class="sxs-lookup"><span data-stu-id="a99d2-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="a99d2-225">2: non archiviare</span><span class="sxs-lookup"><span data-stu-id="a99d2-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="a99d2-226">3: archiviare senza il corpo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a99d2-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-227">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-228">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-229">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-230">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-231">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-232">Questo attributo definisce la versione del servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-232">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="a99d2-233">Questo attributo è un tipo di valore integer con incremento monotona che si incrementa con ogni versione ufficiale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="a99d2-233">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="a99d2-234">I valori validi possibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-234">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-235">Indefinito: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a99d2-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="a99d2-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a99d2-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="a99d2-237">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a99d2-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="a99d2-238">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a99d2-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a99d2-239">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a99d2-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-240">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-241">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-242">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="a99d2-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="a99d2-243">Questo attributo consente di specificare il nome di dominio completo del server back-end del pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-243">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="a99d2-244">Poiché può essere presente un solo server back-end per pool, si tratta di un attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-244">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="a99d2-245">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-246">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-247">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="a99d2-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="a99d2-248">Questo attributo contiene l'identificatore del pool che ospita la directory conferenze.</span><span class="sxs-lookup"><span data-stu-id="a99d2-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-249">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-250">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="a99d2-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="a99d2-251">Questo attributo contiene l'identificatore di una directory conferenze.</span><span class="sxs-lookup"><span data-stu-id="a99d2-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-252">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-253">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="a99d2-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="a99d2-254">Questo attributo contiene l'identificatore del pool in cui viene spostata la directory conferenze.</span><span class="sxs-lookup"><span data-stu-id="a99d2-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-255">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-256">msRTCSIP-default</span><span class="sxs-lookup"><span data-stu-id="a99d2-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="a99d2-257">Questo attributo booleano definisce se l'utilizzo del telefono è un utilizzo predefinito.</span><span class="sxs-lookup"><span data-stu-id="a99d2-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="a99d2-258">Se questo attributo è impostato su <strong>true</strong>, l'utilizzo del telefono è un utilizzo predefinito e non può essere eliminato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="a99d2-259">Se questo attributo è impostato su <strong>false</strong>, l'utilizzo può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="a99d2-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-260">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-261">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="a99d2-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="a99d2-262">Questo attributo identifica l'URL di Communicator Web Access per gli utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-263">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-264">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="a99d2-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="a99d2-265">Questo attributo identifica l'URL di Communicator Web Access per gli utenti che si trovano all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-266">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-267">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-268">Questo attributo a valore singolo contiene il nome distinto (DN) di un oggetto classe del profilo percorso assegnato.</span><span class="sxs-lookup"><span data-stu-id="a99d2-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="a99d2-269">Collegamento in avanti: <strong>Link ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="a99d2-270">Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-271">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-272">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-273">Questo attributo booleano specifica se il criterio è un criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="a99d2-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="a99d2-274">Il criterio è un criterio predefinito quando è impostato su <strong>true</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-275">Nuovo in Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a99d2-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="a99d2-276">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-277">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-278">Questo attributo specifica il nome di dominio completo del server perimetrale che esegue il servizio Access Edge, se è possibile accedervi direttamente oppure del dispositivo di bilanciamento del carico hardware per un pool di server che eseguono il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="a99d2-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="a99d2-279">Se è possibile accedere ai server che eseguono il servizio Access Edge solo tramite uno o più amministratori, questo attributo specifica il nome di dominio completo e, facoltativamente, il numero di porta del Director o del dispositivo di bilanciamento del carico hardware che serve un pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="a99d2-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="a99d2-280">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-281">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-282">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-284">Questo attributo rappresenta il numero di porta da utilizzare per la connessione al server che esegue il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="a99d2-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="a99d2-285">Il valore valido è un valore intero che specifica la porta da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a99d2-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="a99d2-286">Il valore predefinito è 5061.</span><span class="sxs-lookup"><span data-stu-id="a99d2-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-287">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-288">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-290">Questo attributo rappresenta il periodo di timeout della sottoscrizione di presenza predefinita.</span><span class="sxs-lookup"><span data-stu-id="a99d2-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-291">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-292">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-293">Questo attributo rappresenta la finestra di timeout predefinita per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-294">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-296">Questo attributo rappresenta la finestra di timeout predefinita per la sottoscrizione dei dati di roaming.</span><span class="sxs-lookup"><span data-stu-id="a99d2-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-297">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-298">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="a99d2-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="a99d2-299">Questo attributo viene utilizzato in una topologia di domini divisi e contiene un nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a99d2-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="a99d2-300">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-301">msRTCSIP-Description (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-302">Questo attributo di stringa UNICODE a valore singolo contiene una descrizione descrittiva della regola di normalizzazione o della linea telefonica.</span><span class="sxs-lookup"><span data-stu-id="a99d2-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-303">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-304">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-305">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="a99d2-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-306">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-307">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="a99d2-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="a99d2-308">Questo attributo rappresenta un dominio configurato per il servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-309">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="a99d2-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-310">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-311">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-312">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-313">Questo attributo consente di specificare il nome di dominio completo del server che esegue il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="a99d2-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="a99d2-314">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-315">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-316">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-317">Questo attributo consente di controllare se un server genera una richiesta di notifica per i migliori tentativi, anziché una richiesta di notifica, in risposta a una richiesta di sottoscrizione da un client.</span><span class="sxs-lookup"><span data-stu-id="a99d2-317">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="a99d2-318">La notifica è un'estensione per l'ottimizzazione delle prestazioni per l'handshake delle notifiche di sottoscrizione in cui il server genera le richieste di notifica, anziché le richieste di notifica normali.</span><span class="sxs-lookup"><span data-stu-id="a99d2-318">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="a99d2-319">Il vantaggio delle prestazioni è che una richiesta di notifica non richiede una risposta di 200 OK da parte del client come richiesto dalla richiesta NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="a99d2-319">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="a99d2-320">I valori validi sono <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a99d2-321">Live Communications Server 2003 non supporta le richieste di notifica.</span><span class="sxs-lookup"><span data-stu-id="a99d2-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="a99d2-322">Per interagire con le applicazioni server scritte con l'API del server Live Communications Server 2003 in esecuzione su Live Communications Server 2005 e server di terze parti, è possibile disabilitare le richieste di notifica impostando il relativo valore su <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="a99d2-323">La notifica non è attualmente parte del processo di standardizzazione SIP di IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="a99d2-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="a99d2-324">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-325">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-326">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-327">Questo attributo è un'opzione globale che gli amministratori IT utilizzano per configurare se gli utenti sono autorizzati a comunicare con utenti di altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a99d2-327">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="a99d2-328">Consente a un amministratore di sovrascrivere l'attributo <strong>FederationEnabled</strong> di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-328">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="a99d2-329">Questo attributo può essere utile per proteggere la rete interna da attacchi Internet che possono essere causati da worm, virus o attacchi mirati per la società.</span><span class="sxs-lookup"><span data-stu-id="a99d2-329">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="a99d2-330">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="a99d2-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-331">1: abilitato per la connettività per la messaggistica istantanea pubblica (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="a99d2-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-332">2: riservato (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="a99d2-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-333">4: riservato (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="a99d2-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-334">8: riservato (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="a99d2-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-335">16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</span><span class="sxs-lookup"><span data-stu-id="a99d2-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-336">64: AllowOrganizeMeetingWithAnonymousParticipants (Consenti agli utenti di invitare utenti anonimi alle riunioni (posizione bit 6)</span><span class="sxs-lookup"><span data-stu-id="a99d2-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-337">128: UCEnabled (abilitare gli utenti per le comunicazioni unificate) (posizione bit 7)</span><span class="sxs-lookup"><span data-stu-id="a99d2-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-338">256: EnabledForEnhancedPresence (abilitare l'utente per la connettività per la messaggistica istantanea pubblica) (posizione bit 8)</span><span class="sxs-lookup"><span data-stu-id="a99d2-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-339">512: RemoteCallControlDualMode (posizione bit 9)</span><span class="sxs-lookup"><span data-stu-id="a99d2-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-340">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-341">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-342">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="a99d2-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="a99d2-343">Questo attributo indica se i servizi Enterprise sono caricati sul server specificato.</span><span class="sxs-lookup"><span data-stu-id="a99d2-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-344">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a99d2-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-345">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-346">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="a99d2-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="a99d2-347">Questo attributo contiene il codice di chiamata per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a99d2-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-348">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-349">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="a99d2-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="a99d2-350">Questo attributo consente di controllare se un singolo utente è abilitato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-350">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="a99d2-351">Viene applicato dal livello Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="a99d2-351">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="a99d2-352">È contrassegnata per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-352">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a99d2-353">I valori validi sono <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-354">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="a99d2-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="a99d2-356">Questo attributo è un elenco multivalore dei nomi di dominio di tutti i server Enterprise Edition associati a un pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="a99d2-357">Collegamento a ritroso: <strong>Link ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="a99d2-358">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-359">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-360">msRTCSIP-Gateways (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-361">Questo attributo di stringa multivalore contiene un elenco di gateway e porte (per gateway).</span><span class="sxs-lookup"><span data-stu-id="a99d2-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="a99d2-362">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-363">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-364">Questo attributo archivia le coppie nome: valore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-364">This attribute stores name:value pairs.</span></span> <span data-ttu-id="a99d2-365">La coppia nome-valore già definita è per l'impostazione <strong>Consenti polling per la presenza</strong> .</span><span class="sxs-lookup"><span data-stu-id="a99d2-365">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-366">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-367">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="a99d2-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="a99d2-368">Questo attributo è un identificatore univoco di un gruppo utilizzato per raggruppare le voci della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="a99d2-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-369">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-370">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-371">Nuovo in Live Communications Server 2003 (non utilizzato).</span><span class="sxs-lookup"><span data-stu-id="a99d2-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="a99d2-372">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-373">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-374">Nuovo in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="a99d2-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="a99d2-375">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-376">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-377">Nuovo in Live Communications Server 2003 (non utilizzato).</span><span class="sxs-lookup"><span data-stu-id="a99d2-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="a99d2-378">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-379">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="a99d2-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="a99d2-380">Questo attributo consente di controllare se un singolo utente è abilitato per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="a99d2-380">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="a99d2-381">Viene applicato dal livello Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="a99d2-381">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="a99d2-382">È contrassegnata per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-382">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a99d2-383">I valori validi sono <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-384">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-385">msRTCSIP-Master (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-386">Nuovo in Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a99d2-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="a99d2-387">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-388">msRTCSIP-line</span><span class="sxs-lookup"><span data-stu-id="a99d2-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="a99d2-389">Questo attributo a valore singolo contiene l'ID del dispositivo, ovvero l'URI SIP o l'URI TEL del telefono utilizzato dai controlli utente, utilizzati da Lync per la telefonia.</span><span class="sxs-lookup"><span data-stu-id="a99d2-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="a99d2-390">Questo attributo è contrassegnato per la replica del catalogo globale ed è indicizzato.</span><span class="sxs-lookup"><span data-stu-id="a99d2-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="a99d2-391">Se un utente è abilitato per VoIP aziendale, questo attributo archivia la versione normalizzata E. 164 del numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-392">Nuovo in Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a99d2-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-393">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="a99d2-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="a99d2-394">Questo attributo a valore singolo contiene l'URI SIP del server gateway CSTA-SIP.</span><span class="sxs-lookup"><span data-stu-id="a99d2-394">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="a99d2-395">Questo attributo è contrassegnato per la replica del catalogo globale ma non è indicizzato.</span><span class="sxs-lookup"><span data-stu-id="a99d2-395">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-396">Nuovo in Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a99d2-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-397">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-398">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-399">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-400">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-401">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-402">Questo attributo multivalore contiene un elenco di nomi distinti (DN) di normalizzazione locali associati a questo profilo località.</span><span class="sxs-lookup"><span data-stu-id="a99d2-402">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="a99d2-403">Il tipo di questo attributo è un file binario DN.</span><span class="sxs-lookup"><span data-stu-id="a99d2-403">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="a99d2-404">Esiste una relazione uno-a-molti tra il profilo percorso e le regole di normalizzazione locali.</span><span class="sxs-lookup"><span data-stu-id="a99d2-404">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="a99d2-405">L'ordinamento dell'elenco dei DNs di normalizzazione locale deve essere mantenuto nell'ordine specificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-405">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="a99d2-406">La conservazione dell'ordine viene mantenuta dalla parte binaria del file binario DN, che specifica l'indice dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="a99d2-406">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="a99d2-407">Collegamento in avanti: <strong>Link ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="a99d2-408">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-locationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-409">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-410">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-411">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="a99d2-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="a99d2-412">Questo attributo contiene un elenco di opzioni per la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-413">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-414">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-415">Questo attributo a valore singolo contiene un nome descrittivo per il profilo percorso che indica la posizione rappresentata dal profilo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-415">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="a99d2-416">Poiché è possibile disporre di più profili percorso, l'amministratore deve disporre di un modo per distinguere i diversi profili.</span><span class="sxs-lookup"><span data-stu-id="a99d2-416">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-417">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-418">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-419">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-420">Questo attributo multivalore contiene un elenco dei nomi distinti del profilo percorso.</span><span class="sxs-lookup"><span data-stu-id="a99d2-420">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="a99d2-421">Questo attributo consente di specificare il collegamento a ritroso a uno o più profili percorso.</span><span class="sxs-lookup"><span data-stu-id="a99d2-421">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="a99d2-422">Collegamento a ritroso: <strong>Link ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="a99d2-423">Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-424">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-425">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-426">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-427">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-428">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-429">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-430">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="a99d2-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="a99d2-431">Questo attributo contiene le opzioni per il profilo località.</span><span class="sxs-lookup"><span data-stu-id="a99d2-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-432">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-433">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="a99d2-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="a99d2-434">Questo attributo multivalore contiene un elenco di contatti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-435">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-436">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="a99d2-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="a99d2-437">Questo attributo multivalore contiene un elenco di profili località.</span><span class="sxs-lookup"><span data-stu-id="a99d2-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-438">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-440">Questo attributo rappresenta il numero massimo di richieste di ricerca in sospeso per ogni server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-441">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-443">L'attributo rappresenta il numero massimo di sottoscrizioni per utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-444">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-446">Questo attributo rappresenta la finestra di timeout massima per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-447">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-448">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-449">Questo attributo rappresenta la finestra di timeout massima per le registrazioni.</span><span class="sxs-lookup"><span data-stu-id="a99d2-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-450">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-452">Questo attributo rappresenta la finestra di timeout massima per le sottoscrizioni dei dati di roaming.</span><span class="sxs-lookup"><span data-stu-id="a99d2-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-453">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-454">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="a99d2-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-455">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-456">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-457">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="a99d2-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="a99d2-458">Questo attributo è un attributo del punto di controllo del servizio nella classe computer che specifica un collegamento alla Factory di unità di controllo multipunto a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="a99d2-458">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="a99d2-459">Questo punto di controllo del servizio e l'attributo viene creato per ogni MCU Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a99d2-459">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="a99d2-460">Ogni MCU Microsoft deve individuare il server back-end del pool a cui appartiene, per poter recuperare le impostazioni a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-460">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="a99d2-461">Il valore di questo attributo è il nome distinto (DN) della factory MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-461">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="a99d2-462">Si tratta di un attributo a valore singolo e contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-462">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a99d2-463">Collegamento in avanti: <strong>Link ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="a99d2-464">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-465">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-466">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="a99d2-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-467">Si tratta di un attributo riservato a più stringhe.</span><span class="sxs-lookup"><span data-stu-id="a99d2-467">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="a99d2-468">Le impostazioni archiviate in questo attributo sono rappresentate come coppie nome = valore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-468">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="a99d2-469">Le coppie nome/valore attualmente definite sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-469">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="a99d2-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-471">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-472">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="a99d2-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="a99d2-473">Si tratta di un attributo a valore singolo che contiene il nome distinto (DN) di una singola factory MCU associata a un pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="a99d2-474">Collegamento in avanti: <strong>Link ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="a99d2-475">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-476">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-477">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="a99d2-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="a99d2-478">Questo attributo è una stringa a valore singolo che specifica il GUID del provider di factory MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="a99d2-479">In base al valore GUID, il processo di factory MCU determina se si desidera eseguire il servizio di questo tipo di MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="a99d2-480">Se il valore GUID è <strong>{F0810510-424f-46ef-84fe-6CC720DF1791}</strong>, il processo factory MCU (disponibile per impostazione predefinita in Lync Server) lo elaborerà.</span><span class="sxs-lookup"><span data-stu-id="a99d2-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="a99d2-481">Per qualsiasi altro valore GUID, il processo di factory MCU non servirà il tipo di MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-482">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-483">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="a99d2-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="a99d2-484">Questo attributo è un elenco multivalore di nomi distinti (DN).</span><span class="sxs-lookup"><span data-stu-id="a99d2-484">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="a99d2-485">Questo attributo contiene un elenco di tutti i server MCU dello stesso tipo e fornitore associato a questa factory MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-485">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="a99d2-486">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-486">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="a99d2-487">Collegamento a ritroso: Link ID 11027</span><span class="sxs-lookup"><span data-stu-id="a99d2-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="a99d2-488">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-489">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-490">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="a99d2-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="a99d2-491">Questo attributo è una stringa a valore singolo che specifica il supporto che può essere gestito dalla MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="a99d2-492">I tipi validi supportati sono:</span><span class="sxs-lookup"><span data-stu-id="a99d2-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-493">riunione</span><span class="sxs-lookup"><span data-stu-id="a99d2-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="a99d2-494">audio-video</span><span class="sxs-lookup"><span data-stu-id="a99d2-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="a99d2-495">Chat</span><span class="sxs-lookup"><span data-stu-id="a99d2-495">chat</span></span></p></li>
<li><p><span data-ttu-id="a99d2-496">telefono-conf</span><span class="sxs-lookup"><span data-stu-id="a99d2-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-497">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-498">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="a99d2-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="a99d2-499">Questo attributo è una stringa a valore singolo che specifica il nome di un fornitore di MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-499">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="a99d2-500">Tutti i MCU di Microsoft specificano questo attributo come <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-500">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-501">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-502">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-503">Questo attributo definisce diverse opzioni di riunione che sono abilitate a livello globale per tutti gli utenti o gli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="a99d2-503">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="a99d2-504">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="a99d2-504">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="a99d2-505">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="a99d2-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-506">0: AllowOrganizeMeetingWithAnonymousParticipants è None (non consentire agli utenti di invitare utenti anonimi alle riunioni) (nessun bit impostato)</span><span class="sxs-lookup"><span data-stu-id="a99d2-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-507">4: AllowOrganizeMeetingWithAnonymousParticipants è Everyone (Consenti a tutti gli utenti di invitare utenti anonimi alle riunioni) (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="a99d2-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-508">8: AllowOrganizeMeetingWithAnonymousParticipants è UsePerUserSetting (consente agli utenti di invitare utenti anonimi alle riunioni in base all'impostazione per utente) (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="a99d2-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-509">16: UserPerUserMeetingPolicy (il criterio di riunione è definito per utente) (posizione bit 4)</span><span class="sxs-lookup"><span data-stu-id="a99d2-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-510">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-511">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-512">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-513">Questo attributo specifica il nome distinto (DN) del criterio che l'amministratore ha assegnato per l'utente come attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-514">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-515">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-517">Questo attributo rappresenta la finestra di timeout della sottoscrizione di presenza minima.</span><span class="sxs-lookup"><span data-stu-id="a99d2-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-518">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-519">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-520">Questo attributo rappresenta la finestra di timeout minima per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-521">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-522">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-524">Questo attributo rappresenta la finestra di timeout minima per la sottoscrizione dei dati di roaming.</span><span class="sxs-lookup"><span data-stu-id="a99d2-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-525">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-526">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-527">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a99d2-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="a99d2-528">Questo attributo viene utilizzato per archiviare il backend di SQL Server con mirroring utilizzato dal pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a99d2-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-529">Nuovo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a99d2-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-530">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="a99d2-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="a99d2-531">Questo attributo contiene le opzioni e i flag che definiscono le impostazioni per i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="a99d2-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-532">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-533">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="a99d2-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="a99d2-534">Questo attributo contiene il nome distinto per un oggetto dei criteri per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="a99d2-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-535">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-536">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-537">Questo attributo rappresenta il numero consentito di dispositivi in cui un utente può registrarsi per le comunicazioni SIP e sottoscrivere la presenza.</span><span class="sxs-lookup"><span data-stu-id="a99d2-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-538">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-539">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-540">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="a99d2-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="a99d2-541">Questo attributo consente di specificare le opzioni abilitate per l'utente o l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="a99d2-541">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="a99d2-542">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="a99d2-542">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="a99d2-543">Ogni opzione è rappresentata da un bit.</span><span class="sxs-lookup"><span data-stu-id="a99d2-543">Each option is represented by a bit.</span></span> <span data-ttu-id="a99d2-544">Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-544">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a99d2-545">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="a99d2-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-546">1: abilitato per la connettività di messaggistica istantanea pubblica (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="a99d2-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-547">2: riservato (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="a99d2-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-548">4: riservato (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="a99d2-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-549">8: riservato (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="a99d2-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-550">16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</span><span class="sxs-lookup"><span data-stu-id="a99d2-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-551">64: AllowOrganizeMeetingWithAnonymousParticipants (Consenti agli utenti di invitare utenti anonimi alle riunioni (posizione bit 6)</span><span class="sxs-lookup"><span data-stu-id="a99d2-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-552">128: UCEnabled (Abilita gli utenti per UC) (posizione bit 7)</span><span class="sxs-lookup"><span data-stu-id="a99d2-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-553">256: EnabledForEnhancedPresence (abilitare l'utente per la connettività per la messaggistica istantanea pubblica) (posizione bit 8)</span><span class="sxs-lookup"><span data-stu-id="a99d2-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-554">512: RemoteCallControlDualMode (posizione bit 9)</span><span class="sxs-lookup"><span data-stu-id="a99d2-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-555">Nuovo in Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a99d2-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-556">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="a99d2-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="a99d2-557">Questo attributo viene utilizzato nelle topologie a foresta centrale e a risorse per abilitare l'accesso Single Sign-on quando un utente di attributo objectSID dall'account principale di Windows NT viene copiato in questo attributo dell'oggetto utente o contatto corrispondente nella foresta di risorse o nel bosco centrale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="a99d2-558">Communicator Web Access esegue la ricerca di un utente in servizi di dominio Active Directory utilizzando questo attributo o l'attributo objectSid dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="a99d2-559">Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-560">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="a99d2-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="a99d2-561">Questo attributo è il nome dell'URN (Uniform Resource Name) del proprietario per un contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-562">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-563">msRTCSIP-pattern (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-564">Questo attributo di stringa a valore singolo contiene un modello utilizzato per la corrispondenza dei numeri di composizione nel formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="a99d2-564">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="a99d2-565">Se il numero di composizione corrisponde a questo modello, la conversione viene applicata al numero composto.</span><span class="sxs-lookup"><span data-stu-id="a99d2-565">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-566">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-567">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-568">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-569">Questo attributo multivalore contiene un elenco di nomi distinti (DN) della route telefonica.</span><span class="sxs-lookup"><span data-stu-id="a99d2-569">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="a99d2-570">Questo attributo consente di specificare il collegamento a ritroso a una o più route telefoniche.</span><span class="sxs-lookup"><span data-stu-id="a99d2-570">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="a99d2-571">Collegamento a ritroso: <strong>Link ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="a99d2-572">Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-573">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-574">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-575">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-576">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-577">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-578">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-579">Questo attributo di stringa UNICODE a valore singolo specifica il nome descrittivo della route telefonica, in modo che sia possibile fare riferimento facilmente all'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-580">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-581">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-582">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-583">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-584">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-585">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-586">Questo attributo è una stringa Unicode a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-586">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="a99d2-587">Questo attributo stringa contiene la definizione dei criteri in formato XML.</span><span class="sxs-lookup"><span data-stu-id="a99d2-587">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="a99d2-588">La definizione dello schema XML è comune nei diversi tipi di criteri, solo le impostazioni sono diverse per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="a99d2-588">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="a99d2-589">La definizione dello schema XML (XSD) è definita nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a99d2-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="a99d2-590">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-591">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-592">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-593">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-594">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-595">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-596">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-597">Questo attributo di stringa Unicode a valore singolo contiene il tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="a99d2-597">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="a99d2-598">I tipi di criteri validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-598">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-599">riunione</span><span class="sxs-lookup"><span data-stu-id="a99d2-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="a99d2-600">telefonia</span><span class="sxs-lookup"><span data-stu-id="a99d2-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-601">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-602">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="a99d2-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="a99d2-604">Questo attributo consente di specificare un collegamento al pool a cui appartiene un computer.</span><span class="sxs-lookup"><span data-stu-id="a99d2-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="a99d2-605">Questo attributo è impostato indipendentemente dal fatto che il computer esegua la versione Standard Edition o Enterprise Edition di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="a99d2-606">Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a99d2-607">Il valore valido è il nome di dominio del pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="a99d2-608">Collegamento in avanti: <strong>Link ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="a99d2-609">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-610">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="a99d2-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="a99d2-612">Questo attributo multivalore contiene un elenco dei nomi distinti (DN) dei pool a cui è associata la factory MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="a99d2-613">Collegamento a ritroso: <strong>Link ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="a99d2-614">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-615">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-616">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="a99d2-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-617">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-618">Nuovo in Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a99d2-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-619">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="a99d2-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="a99d2-620">Questo attributo consente di specificare un nome arbitrario per un pool visualizzato dalla console di gestione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-620">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="a99d2-621">Questo nome può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-621">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="a99d2-622">Il valore valido è una stringa che rappresenta il nome di un pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-623">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-624">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-625">Questo attributo è un valore stringa a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-625">This attribute is a single-valued string value.</span></span> <span data-ttu-id="a99d2-626">Il valore di questo attributo, se presente, rappresenta il nome di dominio completo del pool se l'amministratore vuole creare un pool Front end con un FQDN che non sia conforme alla struttura di dominio Active Directory in cui viene creato il pool Front End, ad esempio uno spazio dei nomi SIP disgiunto dallo spazio dei nomi DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="a99d2-626">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="a99d2-627">È consigliabile mappare l'FQDN del dominio del pool Front end alla porzione del nome di dominio come dominio Active Directory in cui risiede il pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-627">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="a99d2-628">Pertanto, quando nell'attributo non è presente alcun valore, il nome di dominio completo del pool Front End verrà impostato come predefinito per la struttura di domini di Active Directory, come indicato dall'attributo <strong>dNSHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="a99d2-628">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-629">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-630">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="a99d2-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="a99d2-631">Un elenco multivalore dei nomi di dominio di tutti i server Lync Server, Enterprise Edition associati a un pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="a99d2-632">Questo attributo di tipo Integer definisce se il pool è in grado di messaggistica istantanea e presenza e riunioni.</span><span class="sxs-lookup"><span data-stu-id="a99d2-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="a99d2-633">I possibili tipi di valore validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-634">Indefinito: servizio di messaggistica istantanea e presenza (Live Communications Server 2005 e 2003)</span><span class="sxs-lookup"><span data-stu-id="a99d2-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-635">1: servizio di messaggistica istantanea e presenza (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="a99d2-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-636">2: servizio di messaggistica istantanea e presenza e riunione (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="a99d2-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-637">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-638">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="a99d2-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="a99d2-639">Questo attributo specifica se in un pool di server è in esecuzione il server Standard Edition o il server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a99d2-639">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="a99d2-640">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="a99d2-640">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="a99d2-641">Ogni opzione è rappresentata da un bit.</span><span class="sxs-lookup"><span data-stu-id="a99d2-641">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="a99d2-642">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="a99d2-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-643">1: Server Standard Edition, utenti host (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="a99d2-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-644">2: Server Enterprise Edition, utenti host (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="a99d2-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-645">4: Server Standard Edition, applicazioni host (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="a99d2-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-646">8: Server Enterprise Edition, applicazioni host (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="a99d2-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="a99d2-647">Poiché Lync Server non supporta i pool che ospitano solo le applicazioni, gli unici valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-648">5: Server Standard Edition, ospita utenti e applicazioni (posizioni di bit 0 e 2)</span><span class="sxs-lookup"><span data-stu-id="a99d2-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-649">10: Server Enterprise Edition, ospita utenti e applicazioni (posizioni di bit 1 e 3)</span><span class="sxs-lookup"><span data-stu-id="a99d2-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-650">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-651">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="a99d2-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="a99d2-652">Questo attributo definisce la versione del pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-652">This attribute defines the pool version.</span></span> <span data-ttu-id="a99d2-653">Si tratta di un tipo intero che viene incrementato con ogni versione di prodotto principale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-653">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="a99d2-654">I possibili tipi di valore validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-655">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a99d2-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="a99d2-656">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a99d2-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="a99d2-657">2: Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a99d2-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="a99d2-658">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a99d2-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a99d2-659">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a99d2-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="a99d2-660">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a99d2-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-661">Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a99d2-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-662">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="a99d2-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="a99d2-663">Questo attributo contiene le opzioni e i flag che definiscono le impostazioni di presenza.</span><span class="sxs-lookup"><span data-stu-id="a99d2-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-664">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-665">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="a99d2-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="a99d2-666">Questo attributo contiene il nome distinto per un oggetto criterio di presenza.</span><span class="sxs-lookup"><span data-stu-id="a99d2-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-667">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-668">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="a99d2-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="a99d2-669">Questo attributo consente a un utente o a un contatto per la messaggistica SIP.</span><span class="sxs-lookup"><span data-stu-id="a99d2-669">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="a99d2-670">Viene aggiunto alla classe Contact perché nella topologia della foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="a99d2-670">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="a99d2-671">Il valore valido è il nome distinto del server Standard Edition o del pool Enterprise Edition front end in cui è ospitato un utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-672">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="a99d2-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="a99d2-674">Questo attributo contiene l'indirizzo SIP di un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="a99d2-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-675">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="a99d2-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="a99d2-676">Questo attributo contiene l'ID del dispositivo della linea privata.</span><span class="sxs-lookup"><span data-stu-id="a99d2-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-677">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-678">msRTCSIP-instradabile</span><span class="sxs-lookup"><span data-stu-id="a99d2-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="a99d2-679">Questo attributo è un attributo booleano utilizzato per determinare se Lync Server è autorizzato a eseguire il routing a questo servizio utilizzando il relativo indirizzo GRUU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="a99d2-680">Se questo valore è impostato su <strong>true</strong>, Lync Server è autorizzato a eseguire il routing a questo servizio.</span><span class="sxs-lookup"><span data-stu-id="a99d2-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="a99d2-681">Se questo valore è impostato su <strong>false</strong>, Lync Server non è autorizzato a eseguire il routing a questo servizio.</span><span class="sxs-lookup"><span data-stu-id="a99d2-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-682">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-683">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-684">Questo attributo di stringa UNICODE a valore singolo definisce un attributo che qualifica l'utilizzo di una route telefonica.</span><span class="sxs-lookup"><span data-stu-id="a99d2-684">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="a99d2-685">La selezione di una route telefonica è determinata in base a due elementi: l'attributo Usage assegnato alla route Phone e gli attributi di utilizzo dei criteri consentiti dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="a99d2-685">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="a99d2-686">Viene selezionata la prima route telefonica con un attributo di utilizzo che corrisponde all'utilizzo consentito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a99d2-686">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-687">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-688">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-689">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-690">Questo attributo con nome distinto (DN) multivalore contiene un elenco di nomi distinti per l'utilizzo delle route.</span><span class="sxs-lookup"><span data-stu-id="a99d2-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="a99d2-691">Collegamento in avanti: <strong>Link ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="a99d2-692">Questo attributo è un collegamento in avanti per il collegamento a ritroso corrispondente <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-693">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-694">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-695">Questo attributo contiene il nome distinto che punta al pool che tutto il traffico SIP indirizzato a questa MCU o a un servizio attendibile deve passare attraverso.</span><span class="sxs-lookup"><span data-stu-id="a99d2-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-696">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-697">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-698">Questo attributo di stringa UNICODE a valore singolo specifica il nome descrittivo della regola di normalizzazione, in modo che possa essere facilmente referenziato da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-699">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-700">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-701">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="a99d2-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="a99d2-702">Questo attributo rappresenta la versione dello schema attualmente distribuita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a99d2-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-703">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-704">Questo attributo consente di limitare il numero di risultati di ricerca da restituire da una ricerca di directory quando un utente cerca un contatto tramite Communicator.</span><span class="sxs-lookup"><span data-stu-id="a99d2-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="a99d2-705">Questo attributo ignorerà il valore fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="a99d2-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-706">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-707">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-708">Questo attributo limita il numero di richieste di ricerca restituite.</span><span class="sxs-lookup"><span data-stu-id="a99d2-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-709">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="a99d2-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="a99d2-711">Questo attributo multivalore è un collegamento a ritroso contenente un elenco di nomi distinti (DN).</span><span class="sxs-lookup"><span data-stu-id="a99d2-711">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="a99d2-712">Tali DNs puntano a un oggetto pool o <strong>TrustedService</strong> .</span><span class="sxs-lookup"><span data-stu-id="a99d2-712">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="a99d2-713">Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-714">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-715">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="a99d2-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-716">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-717">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-718">Questo attributo multivalore contiene un elenco di nomi distinti.</span><span class="sxs-lookup"><span data-stu-id="a99d2-718">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="a99d2-719">Questi nomi distinti sono collegamenti indietro che fanno riferimento ad altri oggetti server a cui è possibile assegnare un profilo percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="a99d2-719">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="a99d2-720">Collegamento a ritroso: <strong>Link ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="a99d2-721">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="a99d2-722">Questo attributo di collegamento a ritroso fa riferimento solo ai pool e ai Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-723">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-724">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-725">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a99d2-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="a99d2-726">Questo attributo definisce le informazioni sulla versione del server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-726">This attribute defines the version information of the server.</span></span> <span data-ttu-id="a99d2-727">Questo numero di versione si applica a tutti i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-727">This version number applies to all server roles.</span></span> <span data-ttu-id="a99d2-728">Si tratta di un numero intero monotonamente crescente che si incrementi con ogni versione del prodotto ufficiale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-728">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="a99d2-729">I possibili valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-730">Indefinito: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a99d2-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="a99d2-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a99d2-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="a99d2-732">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a99d2-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="a99d2-733">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a99d2-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a99d2-734">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a99d2-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="a99d2-735">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a99d2-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="a99d2-736">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a99d2-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-737">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-738">msRTCSIP-tipooggettoorigine</span><span class="sxs-lookup"><span data-stu-id="a99d2-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="a99d2-739">Questo attributo a valore singolo di tipo integer specifica il tipo di oggetto a cui punta <strong>msDS-SourceObjectDN</strong> , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a99d2-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-740">null | 0x00000001: rappresenta un oggetto utente principale di Windows NT Server da una foresta diversa</span><span class="sxs-lookup"><span data-stu-id="a99d2-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="a99d2-741">Gli attributi seguenti rappresentano un tipo di gruppo proveniente da una foresta diversa per l'espansione del gruppo di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="a99d2-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a99d2-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a99d2-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a99d2-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a99d2-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a99d2-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a99d2-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a99d2-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a99d2-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="a99d2-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="a99d2-747">0x90000000: rappresenta un oggetto di accesso sottoscrittore o operatore automatico dalla stessa foresta o da una foresta diversa</span><span class="sxs-lookup"><span data-stu-id="a99d2-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-748">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-749">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-750">Nuovo in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="a99d2-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="a99d2-751">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-752">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="a99d2-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="a99d2-753">Questo attributo consente di spostare un utente o un oggetto contatto da un pool di Lync Server a un altro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="a99d2-754">Questo attributo viene aggiunto alla classe Contact, poiché nella topologia della foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="a99d2-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="a99d2-755">Il valore valido è il nome distinto del server di destinazione Standard Edition o del pool Front end a cui deve essere spostato un utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-756">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-757">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-758">Questo attributo di stringa a valore singolo contiene un modello o un intervallo di numeri di telefono da instradare ai gateway specificati definiti in <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-759">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-760">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="a99d2-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="a99d2-761">Questo attributo archivia le coppie nome/valore per i criteri di destinazione per gli utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-762">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-763">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="a99d2-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="a99d2-764">Questo attributo archivia l'identificatore univoco per un tenant.</span><span class="sxs-lookup"><span data-stu-id="a99d2-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-765">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-766">msRTCSIP-Translation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-767">Questo attributo viene utilizzato dalla funzionalità vocale di Lync Server e contiene la stringa di conversione da applicare al numero composto, se viene trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="a99d2-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-768">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a99d2-769">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-770">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="a99d2-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-771">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-772">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-773">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-774">Questo attributo è un valore stringa che contiene il nome di dominio completo dell'MCU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-774">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="a99d2-775">Si tratta di un attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-775">This is a single-valued attribute.</span></span> <span data-ttu-id="a99d2-776">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-776">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-777">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-778">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="a99d2-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-779">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-780">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-781">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-782">Questo attributo è un valore stringa che contiene il nome di dominio completo del server che esegue il server proxy.</span><span class="sxs-lookup"><span data-stu-id="a99d2-782">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="a99d2-783">Questo attributo è a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-783">This attribute is single-valued.</span></span> <span data-ttu-id="a99d2-784">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-784">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-785">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-786">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="a99d2-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-787">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-788">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-789">Questo attributo è un attributo a valore singolo che rappresenta il nome di dominio completo di un server attendibile.</span><span class="sxs-lookup"><span data-stu-id="a99d2-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-790">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-791">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="a99d2-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="a99d2-792">Questo attributo consente di specificare il numero di versione di un server nell'elenco dei server attendibili.</span><span class="sxs-lookup"><span data-stu-id="a99d2-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="a99d2-793">I possibili valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-794">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a99d2-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="a99d2-795">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a99d2-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="a99d2-796">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a99d2-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a99d2-797">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a99d2-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="a99d2-798">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a99d2-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="a99d2-799">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a99d2-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-800">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-801">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="a99d2-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="a99d2-802">Questo attributo definisce le opzioni abilitate per il servizio attendibile.</span><span class="sxs-lookup"><span data-stu-id="a99d2-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-803">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-804">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="a99d2-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="a99d2-805">Questo attributo multivalore contiene un elenco di nomi distinti (DN) che fanno riferimento a un oggetto servizio attendibile, ad esempio un servizio di autenticazione di inoltro multimediale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="a99d2-806">Un servizio di autenticazione di inoltro multimediale (collocato fisicamente nel server perimetrale che esegue il servizio A/V Conferencing) deve essere associato a un pool per il supporto degli scenari audio per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="a99d2-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="a99d2-807">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-808">UC</span><span class="sxs-lookup"><span data-stu-id="a99d2-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-809">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="a99d2-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="a99d2-810">Questo attributo è un valore integer che definisce il numero di porta utilizzato per la connessione al servizio di GRUU.</span><span class="sxs-lookup"><span data-stu-id="a99d2-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-811">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-812">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="a99d2-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="a99d2-813">Questo attributo è un valore stringa che definisce il tipo di servizio di GRUU che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="a99d2-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="a99d2-814">I tipi di servizio GRUU validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="a99d2-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="a99d2-816">Gateway</span><span class="sxs-lookup"><span data-stu-id="a99d2-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="a99d2-817">Servizio di autenticazione di MRAS (Media Relay Authentication Service)</span><span class="sxs-lookup"><span data-stu-id="a99d2-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="a99d2-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="a99d2-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="a99d2-819">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="a99d2-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-820">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-821">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="a99d2-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-822">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-823">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-824">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="a99d2-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="a99d2-825">Questo attributo è un valore stringa che contiene il nome di dominio completo di IIS in cui sono in esecuzione i servizi Web di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="a99d2-826">Si tratta di un attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="a99d2-826">This is a single-valued attribute.</span></span> <span data-ttu-id="a99d2-827">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a99d2-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-828">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-829">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-830">Questo attributo definisce diverse opzioni UC che sono abilitate a livello globale a tutti gli oggetti utente o contatti.</span><span class="sxs-lookup"><span data-stu-id="a99d2-830">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="a99d2-831">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="a99d2-831">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="a99d2-832">Ogni opzione è rappresentata dalla presenza di un bit.</span><span class="sxs-lookup"><span data-stu-id="a99d2-832">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="a99d2-833">Il valore possibile valido (e la posizione bit associata) è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a99d2-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-834">4: UsePerUserUCPolicy (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="a99d2-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="a99d2-835">Quando questo bit è impostato, il criterio UC è definito per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-836">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-837">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-838">Questo attributo a valore singolo contiene il nome distinto (DN) del criterio UC che l'amministratore ha assegnato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-839">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-840">msRTCSIP-UserDomainList (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a99d2-841">Questo attributo fornisce un elenco di tutti i domini in una foresta che ospitano gli utenti abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="a99d2-841">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="a99d2-842">L'impostazione predefinita è un elenco vuoto che indica che tutti i domini nella foresta sono abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="a99d2-842">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="a99d2-843">I valori validi sono più stringhe che rappresentano i nomi di dominio di singoli domini.</span><span class="sxs-lookup"><span data-stu-id="a99d2-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-844">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a99d2-845">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-846">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="a99d2-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="a99d2-847">Questo attributo determina se l'utente è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-848">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="a99d2-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="a99d2-849">Questo attributo multivalore contiene un elenco di coppie nome/valore nel formato &quot; nome = valore. &quot; Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a99d2-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-850">Nuovo in Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a99d2-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-851">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="a99d2-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="a99d2-852">Questo attributo contiene il nome distinto (DN) che punta a un oggetto profilo percorso.</span><span class="sxs-lookup"><span data-stu-id="a99d2-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-853">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a99d2-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-854">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="a99d2-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="a99d2-855">Questo attributo archivia le coppie nome/valore per i criteri utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-856">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a99d2-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-857">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="a99d2-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="a99d2-858">Si tratta di un attributo multivalore contenente un elenco di nomi distinti con Binary (DN_WITH_BINARY) che puntano ai criteri utente globali di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="a99d2-858">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="a99d2-859">La parte binaria indica il tipo di criterio a cui fa riferimento la parte DN.</span><span class="sxs-lookup"><span data-stu-id="a99d2-859">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="a99d2-860">I valori binari validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99d2-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-861">0x00000001: criteri per le riunioni</span><span class="sxs-lookup"><span data-stu-id="a99d2-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="a99d2-862">0x00000002: criteri UC</span><span class="sxs-lookup"><span data-stu-id="a99d2-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="a99d2-863">0x00000005: criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="a99d2-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-864">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-865">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a99d2-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="a99d2-866">Questo è l'ID del gruppo di routing SIP.</span><span class="sxs-lookup"><span data-stu-id="a99d2-866">This is the SIP routing group ID.</span></span> <span data-ttu-id="a99d2-867">Gli utenti dello stesso gruppo registreranno lo stesso front end server.</span><span class="sxs-lookup"><span data-stu-id="a99d2-867">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-868">Nuovo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a99d2-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-869">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="a99d2-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="a99d2-870">Si tratta di un attributo multivalore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-870">This is a multi-valued attribute.</span></span> <span data-ttu-id="a99d2-871">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a99d2-871">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-872">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-873">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="a99d2-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="a99d2-874">Questo attributo a valore singolo punta al pool o al server Standard Edition a cui appartengono i componenti Web.</span><span class="sxs-lookup"><span data-stu-id="a99d2-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="a99d2-875">Collegamento in avanti: <strong>Link ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="a99d2-876">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-877">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-878">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="a99d2-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="a99d2-879">Questo attributo è un elenco multivalore di nomi distinti.</span><span class="sxs-lookup"><span data-stu-id="a99d2-879">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="a99d2-880">Questo attributo contiene un elenco di tutti i server Web associati al pool.</span><span class="sxs-lookup"><span data-stu-id="a99d2-880">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="a99d2-881">Collegamento a ritroso: <strong>Link ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="a99d2-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="a99d2-882">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="a99d2-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-883">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a99d2-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-884">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a99d2-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a99d2-885">Nuovo in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="a99d2-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="a99d2-886">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a99d2-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="a99d2-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="a99d2-888">Questo attributo esistente di Active Directory viene utilizzato dalla telefonia per specificare l'elenco di indirizzi TCP/IP alternativi per un telefono.</span><span class="sxs-lookup"><span data-stu-id="a99d2-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-889">Nuovo sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a99d2-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-890">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="a99d2-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="a99d2-891">Questo attributo esistente di Active Directory viene utilizzato dai componenti vocali in Lync Server, solo per gli oggetti contatto, allo scopo di eseguire il routing delle chiamate ai numeri di accesso del Sottoscrittore e dell'operatore automatico di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="a99d2-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="a99d2-892">L'indirizzo di inoltro di chiamata incondizionato è memorizzato in questo attributo multivalore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="a99d2-893">Questo account viene creato per lo scopo specifico dell'operatore automatico e dell'accesso sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="a99d2-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="a99d2-894">Gli attributi di questo account non devono essere modificati dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="a99d2-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-895">Nuovo nel sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a99d2-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a99d2-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a99d2-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a99d2-897">Questo attributo multivalore di Active Directory esistente fa parte dello schema di base di Active Directory introdotto in Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a99d2-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="a99d2-898">Questo attributo contiene i vari indirizzi X400, X500 e SMTP del messaggio di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="a99d2-899">In Live Communications Server 2003 e versioni successive, l'URI SIP dell'utente viene aggiunto all'elenco, utilizzando il &quot; tag SIP: &quot; .</span><span class="sxs-lookup"><span data-stu-id="a99d2-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="a99d2-900">Le applicazioni seguenti cercano l'URI SIP dell'utente da questo attributo:</span><span class="sxs-lookup"><span data-stu-id="a99d2-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="a99d2-901">Client di messaggistica e collaborazione di Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="a99d2-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="a99d2-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="a99d2-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a99d2-903">Nuovo nel sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a99d2-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a99d2-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="a99d2-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="a99d2-905">Questo attributo esistente di Active Directory contiene il numero di telefono per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a99d2-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="a99d2-906">Nuovo nel sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a99d2-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

