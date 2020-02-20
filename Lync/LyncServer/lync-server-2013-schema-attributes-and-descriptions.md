---
title: 'Lync Server 2013: attributi e descrizioni dello schema'
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
ms.openlocfilehash: c95fa0450a85aea4ffdd53dfcb61ddb5b97ed532
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="2a589-102">Attributi e descrizioni dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a589-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a589-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="2a589-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="2a589-104">In questa sezione vengono descritti tutti gli attributi dello schema utilizzati da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a589-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="2a589-105">Per le classi associate agli attributi, vedere [schema Attributes by Class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="2a589-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="2a589-106">Per un elenco di classi e attributi nuovi in Lync Server 2013, vedere [modifiche dello schema in Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="2a589-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="2a589-107">Gli attributi che sono coppie collegate sono specificati come collegamenti inoltrati o collegamenti indietro.</span><span class="sxs-lookup"><span data-stu-id="2a589-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="2a589-108">Un attributo che fa riferimento a un altro oggetto è un collegamento in avanti. l'attributo dell'altro oggetto che fa riferimento al primo oggetto è un collegamento a ritroso.</span><span class="sxs-lookup"><span data-stu-id="2a589-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="2a589-109">I collegamenti inoltrati sono aggiornabili, mentre i collegamenti indietro sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="2a589-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="2a589-110">Alcuni attributi hanno un valore di maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="2a589-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="2a589-111">Per questi attributi, ogni impostazione è rappresentata da un bit e il valore decimale visualizzato rappresenta la posizione del bit.</span><span class="sxs-lookup"><span data-stu-id="2a589-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="2a589-112">Le posizioni dei bit iniziano con il bit 0.</span><span class="sxs-lookup"><span data-stu-id="2a589-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="2a589-113">Ad esempio, 1 (binario) è il bit 0 set e 10000 (binario) è bit 4 set.</span><span class="sxs-lookup"><span data-stu-id="2a589-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="2a589-114">Ogni bit rappresenta una proprietà.</span><span class="sxs-lookup"><span data-stu-id="2a589-114">Each bit represents a property.</span></span> <span data-ttu-id="2a589-115">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="2a589-115">The following are some examples:</span></span>

  - <span data-ttu-id="2a589-116">10000 (binario) ha un valore decimale pari a 16, ovvero il bit 4 è impostato.</span><span class="sxs-lookup"><span data-stu-id="2a589-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="2a589-117">100 milioni (binario) ha un valore decimale pari a 256 (ovvero il bit 8 è impostato).</span><span class="sxs-lookup"><span data-stu-id="2a589-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="2a589-118">1100 (binario) ha un valore decimale pari a 12 (ovvero i bit 2 e 3 sono impostati, le proprietà rappresentate da entrambi i bit sono abilitate).</span><span class="sxs-lookup"><span data-stu-id="2a589-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="2a589-119">1111000001 (binario) ha un valore decimale di 961 (ovvero i bit 0, 6, 7, 8 e 9 sono impostati, le proprietà per ognuno di questi bit sono abilitate).</span><span class="sxs-lookup"><span data-stu-id="2a589-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="2a589-120">Attributi dello schema per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a589-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a589-121">Attributo</span><span class="sxs-lookup"><span data-stu-id="2a589-121">Attribute</span></span></th>
<th><span data-ttu-id="2a589-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a589-122">Description</span></span></th>
<th><span data-ttu-id="2a589-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="2a589-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a589-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="2a589-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="2a589-125">Un attributo esistente nei servizi di dominio Active Directory che ora è associato alle classi <strong>msRTCSIP-Pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="2a589-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="2a589-126">Questo attributo consente di specificare il nome di dominio completo (FQDN) di un pool o di un Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="2a589-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="2a589-127">Un valore valido per ogni segmento è di 63 caratteri; un valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2a589-128">Nuovo in Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="2a589-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-130">Questo attributo contiene la rappresentazione di stringa del nome distinto (DN) dell'oggetto in un'altra foresta corrispondente a questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="2a589-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="2a589-131">Questo attributo viene utilizzato per l'espansione del gruppo di distribuzione e la frequenza automatica.</span><span class="sxs-lookup"><span data-stu-id="2a589-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="2a589-132">Questo attributo è definito nello schema predefinito di Active Directory per Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="2a589-133">Per evitare di richiedere un aggiornamento di AD DS a Windows Server 2003 R2, la preparazione dello schema di Active Directory estende lo schema di Windows Server 2003 con questa definizione di attributo.</span><span class="sxs-lookup"><span data-stu-id="2a589-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="2a589-134">Nuovo in Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="2a589-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="2a589-136">Questo attributo multivalore contiene le impostazioni della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="2a589-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="2a589-137">Questo attributo è condiviso con la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a589-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="2a589-138">Nuovo in Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="2a589-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="2a589-140">Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="2a589-141">I criteri di conservazione conservano gli elementi della cassetta postale per l'utente per tutta la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="2a589-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="2a589-142">Questo attributo è condiviso con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2a589-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="2a589-143">Nuovo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a589-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="2a589-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="2a589-145">Questo attributo archivia le informazioni relative ai provider di servizi di audioconferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="2a589-146">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="2a589-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="2a589-148">Questo attributo punta alla voce del servizio attendibile per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2a589-149">Nuovo in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-150">msRTCSIP-Application</span><span class="sxs-lookup"><span data-stu-id="2a589-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="2a589-151">Questo attributo contiene un elenco delle applicazioni ospitate nel server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2a589-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="2a589-152">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="2a589-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="2a589-154">Questo attributo consente di specificare le opzioni per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2a589-155">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="2a589-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="2a589-157">Questo attributo contiene la lingua principale per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2a589-158">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="2a589-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="2a589-160">Questo attributo multivalore contiene le lingue secondarie per il contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2a589-161">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="2a589-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="2a589-163">Questo attributo contiene un elenco di server applicazioni appartenenti al pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="2a589-164">Il collegamento in avanti corrispondente a questo attributo di collegamento a ritroso è <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-165">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="2a589-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="2a589-167">Questo attributo punta al pool a cui appartiene il server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2a589-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="2a589-168">Si tratta del collegamento in avanti.</span><span class="sxs-lookup"><span data-stu-id="2a589-168">This is the forward link.</span></span> <span data-ttu-id="2a589-169">Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-170">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-171">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-172">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-173">Obsoleto in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-174">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-175">Questo attributo specifica l'impostazione predefinita globale all'interno del limite della foresta per l'archiviazione di tutte le comunicazioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a589-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="2a589-176">Questo viene applicato dal livello dell'agente di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="2a589-177">L'intervallo di valori per questo attributo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2a589-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-178"><strong>True</strong>: archivia tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="2a589-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="2a589-179"><strong>False</strong>: non archiviare tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="2a589-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="2a589-180">Questo attributo controlla globalmente, all'interno del limite della foresta, la modalità di archiviazione delle comunicazioni degli utenti all'interno di una rete interna.</span><span class="sxs-lookup"><span data-stu-id="2a589-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="2a589-181"><strong>Comportamento di Live Communications Server 2005 (ora ritirato)</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="2a589-182">L'intervallo di valori per questo attributo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2a589-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-183">0: archivia il corpo del messaggio [bit 0]</span><span class="sxs-lookup"><span data-stu-id="2a589-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="2a589-184">1: non archiviare il corpo del messaggio [bit 0]</span><span class="sxs-lookup"><span data-stu-id="2a589-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="2a589-185"><strong>Comportamento di Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="2a589-186">L'intervallo di valori per questo attributo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2a589-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-187">0: ArchiveFederationDefaultWithoutBody (ritirato)</span><span class="sxs-lookup"><span data-stu-id="2a589-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="2a589-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="2a589-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="2a589-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="2a589-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="2a589-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="2a589-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="2a589-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="2a589-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2a589-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="2a589-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2a589-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="2a589-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="2a589-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="2a589-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2a589-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="2a589-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2a589-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="2a589-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2a589-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="2a589-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="2a589-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="2a589-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="2a589-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="2a589-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="2a589-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="2a589-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="2a589-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="2a589-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-202">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-203">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-204">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-205">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-206">Obsoleto in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-207">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-208">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-209">Obsoleto in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="2a589-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="2a589-211">Questo attributo è un numero intero utilizzato come campo di bit per controllare se le comunicazioni di un singolo utente devono essere archiviate.</span><span class="sxs-lookup"><span data-stu-id="2a589-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="2a589-212">Questo controllo viene applicato dal livello dell'agente di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="2a589-213">È contrassegnata per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2a589-214">L'ambito di questo attributo è specifico di un singolo utente o di un contatto.</span><span class="sxs-lookup"><span data-stu-id="2a589-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="2a589-215">Di seguito sono riportati i valori validi (e le posizioni dei bit associati) in Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2a589-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-216">0: non archiviare (nessun bit impostato)</span><span class="sxs-lookup"><span data-stu-id="2a589-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="2a589-217">1: ritirato (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="2a589-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2a589-218">2: ritirato (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="2a589-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2a589-219">4: archiviazione delle comunicazioni interne (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="2a589-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2a589-220">8: archiviare le comunicazioni federate (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="2a589-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="2a589-221">I valori precedentemente validi in Live Communications Server 2005 sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-222">0: utilizzare il valore predefinito definito da <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation (</strong> nell'ordine di precedenza:</span><span class="sxs-lookup"><span data-stu-id="2a589-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-223">1: Archivio</span><span class="sxs-lookup"><span data-stu-id="2a589-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="2a589-224">2: non archiviare</span><span class="sxs-lookup"><span data-stu-id="2a589-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="2a589-225">3: archiviare senza il corpo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2a589-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="2a589-226">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-227">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-228">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-229">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-230">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-231">Questo attributo definisce la versione del servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="2a589-232">Questo attributo è un tipo di valore integer con incremento monotona che si incrementa con ogni versione ufficiale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="2a589-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="2a589-233">I valori validi possibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-234">Indefinito: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2a589-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="2a589-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2a589-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="2a589-236">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="2a589-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="2a589-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2a589-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2a589-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2a589-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-239">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-240">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="2a589-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="2a589-242">Questo attributo consente di specificare il nome di dominio completo del server back-end del pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="2a589-243">Poiché può essere presente un solo server back-end per pool, si tratta di un attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="2a589-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="2a589-244">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2a589-245">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="2a589-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="2a589-247">Questo attributo contiene l'identificatore del pool che ospita la directory conferenze.</span><span class="sxs-lookup"><span data-stu-id="2a589-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="2a589-248">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="2a589-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="2a589-250">Questo attributo contiene l'identificatore di una directory conferenze.</span><span class="sxs-lookup"><span data-stu-id="2a589-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="2a589-251">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="2a589-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="2a589-253">Questo attributo contiene l'identificatore del pool in cui viene spostata la directory conferenze.</span><span class="sxs-lookup"><span data-stu-id="2a589-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="2a589-254">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-255">msRTCSIP-default</span><span class="sxs-lookup"><span data-stu-id="2a589-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="2a589-256">Questo attributo booleano definisce se l'utilizzo del telefono è un utilizzo predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a589-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="2a589-257">Se questo attributo è impostato su <strong>true</strong>, l'utilizzo del telefono è un utilizzo predefinito e non può essere eliminato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="2a589-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="2a589-258">Se questo attributo è impostato su <strong>false</strong>, l'utilizzo può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="2a589-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="2a589-259">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="2a589-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="2a589-261">Questo attributo identifica l'URL di Communicator Web Access per gli utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="2a589-262">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="2a589-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="2a589-264">Questo attributo identifica l'URL di Communicator Web Access per gli utenti che si trovano all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="2a589-265">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-266">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-267">Questo attributo a valore singolo contiene il nome distinto (DN) di un oggetto classe del profilo percorso assegnato.</span><span class="sxs-lookup"><span data-stu-id="2a589-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="2a589-268">Collegamento in avanti: <strong>Link ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="2a589-269">Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-270">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-271">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-272">Questo attributo booleano specifica se il criterio è un criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a589-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="2a589-273">Il criterio è un criterio predefinito quando è impostato su <strong>true</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-274">Nuovo in Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2a589-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="2a589-275">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-276">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-277">Questo attributo specifica il nome di dominio completo del server perimetrale che esegue il servizio Access Edge, se è possibile accedervi direttamente oppure del dispositivo di bilanciamento del carico hardware per un pool di server che eseguono il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="2a589-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="2a589-278">Se è possibile accedere ai server che eseguono il servizio Access Edge solo tramite uno o più amministratori, questo attributo specifica il nome di dominio completo e, facoltativamente, il numero di porta del Director o del dispositivo di bilanciamento del carico hardware che serve un pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="2a589-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="2a589-279">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2a589-280">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-281">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-283">Questo attributo rappresenta il numero di porta da utilizzare per la connessione al server che esegue il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="2a589-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="2a589-284">Il valore valido è un valore intero che specifica la porta da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2a589-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="2a589-285">Il valore predefinito è 5061.</span><span class="sxs-lookup"><span data-stu-id="2a589-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="2a589-286">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-287">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-289">Questo attributo rappresenta il periodo di timeout della sottoscrizione di presenza predefinita.</span><span class="sxs-lookup"><span data-stu-id="2a589-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="2a589-290">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-291">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-292">Questo attributo rappresenta la finestra di timeout predefinita per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-293">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-295">Questo attributo rappresenta la finestra di timeout predefinita per la sottoscrizione dei dati di roaming.</span><span class="sxs-lookup"><span data-stu-id="2a589-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-296">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="2a589-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="2a589-298">Questo attributo viene utilizzato in una topologia di domini divisi e contiene un nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="2a589-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="2a589-299">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-300">msRTCSIP-Description (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-301">Questo attributo di stringa UNICODE a valore singolo contiene una descrizione descrittiva della regola di normalizzazione o della linea telefonica.</span><span class="sxs-lookup"><span data-stu-id="2a589-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="2a589-302">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-303">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="2a589-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="2a589-305">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="2a589-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="2a589-307">Questo attributo rappresenta un dominio configurato per il servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="2a589-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="2a589-309">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-310">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="2a589-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-312">Questo attributo consente di specificare il nome di dominio completo del server che esegue il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="2a589-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="2a589-313">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2a589-314">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-315">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-316">Questo attributo consente di controllare se un server genera una richiesta di notifica per i migliori tentativi, anziché una richiesta di notifica, in risposta a una richiesta di sottoscrizione da un client.</span><span class="sxs-lookup"><span data-stu-id="2a589-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="2a589-317">La notifica è un'estensione per l'ottimizzazione delle prestazioni per l'handshake delle notifiche di sottoscrizione in cui il server genera le richieste di notifica, anziché le richieste di notifica normali.</span><span class="sxs-lookup"><span data-stu-id="2a589-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="2a589-318">Il vantaggio delle prestazioni è che una richiesta di notifica non richiede una risposta di 200 OK da parte del client come richiesto dalla richiesta NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="2a589-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="2a589-319">I valori validi sono <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2a589-320">Live Communications Server 2003 non supporta le richieste di notifica.</span><span class="sxs-lookup"><span data-stu-id="2a589-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="2a589-321">Per interagire con le applicazioni server scritte con l'API del server Live Communications Server 2003 in esecuzione su Live Communications Server 2005 e server di terze parti, è possibile disabilitare le richieste di notifica impostando il relativo valore su <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2a589-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="2a589-322">La notifica non è attualmente parte del processo di standardizzazione SIP di IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="2a589-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="2a589-323">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-324">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-325">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-326">Questo attributo è un'opzione globale che gli amministratori IT utilizzano per configurare se gli utenti sono autorizzati a comunicare con utenti di altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2a589-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="2a589-327">Consente a un amministratore di sovrascrivere l'attributo <strong>FederationEnabled</strong> di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="2a589-328">Questo attributo può essere utile per proteggere la rete interna da attacchi Internet che possono essere causati da worm, virus o attacchi mirati per la società.</span><span class="sxs-lookup"><span data-stu-id="2a589-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="2a589-329">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="2a589-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-330">1: abilitato per la connettività per la messaggistica istantanea pubblica (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="2a589-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2a589-331">2: riservato (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="2a589-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2a589-332">4: riservato (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="2a589-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2a589-333">8: riservato (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="2a589-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="2a589-334">16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</span><span class="sxs-lookup"><span data-stu-id="2a589-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="2a589-335">64: AllowOrganizeMeetingWithAnonymousParticipants (Consenti agli utenti di invitare utenti anonimi alle riunioni (posizione bit 6)</span><span class="sxs-lookup"><span data-stu-id="2a589-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="2a589-336">128: UCEnabled (abilitare gli utenti per le comunicazioni unificate) (posizione bit 7)</span><span class="sxs-lookup"><span data-stu-id="2a589-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="2a589-337">256: EnabledForEnhancedPresence (abilitare l'utente per la connettività per la messaggistica istantanea pubblica) (posizione bit 8)</span><span class="sxs-lookup"><span data-stu-id="2a589-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="2a589-338">512: RemoteCallControlDualMode (posizione bit 9)</span><span class="sxs-lookup"><span data-stu-id="2a589-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-339">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-340">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="2a589-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="2a589-342">Questo attributo indica se i servizi Enterprise sono caricati sul server specificato.</span><span class="sxs-lookup"><span data-stu-id="2a589-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="2a589-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="2a589-344">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="2a589-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="2a589-346">Questo attributo contiene il codice di chiamata per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="2a589-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="2a589-347">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="2a589-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="2a589-349">Questo attributo consente di controllare se un singolo utente è abilitato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="2a589-350">Viene applicato dal livello Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="2a589-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="2a589-351">È contrassegnata per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2a589-352">I valori validi sono <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-353">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="2a589-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="2a589-355">Questo attributo è un elenco multivalore dei nomi di dominio di tutti i server Enterprise Edition associati a un pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="2a589-356">Collegamento a ritroso: <strong>Link ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="2a589-357">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-358">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-359">msRTCSIP-Gateways (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-360">Questo attributo di stringa multivalore contiene un elenco di gateway e porte (per gateway).</span><span class="sxs-lookup"><span data-stu-id="2a589-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="2a589-361">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-362">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-363">Questo attributo archivia le coppie nome: valore.</span><span class="sxs-lookup"><span data-stu-id="2a589-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="2a589-364">La coppia nome-valore già definita è per l'impostazione <strong>Consenti polling per la presenza</strong> .</span><span class="sxs-lookup"><span data-stu-id="2a589-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="2a589-365">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="2a589-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="2a589-367">Questo attributo è un identificatore univoco di un gruppo utilizzato per raggruppare le voci della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="2a589-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="2a589-368">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-369">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-370">Nuovo in Live Communications Server 2003 (non utilizzato).</span><span class="sxs-lookup"><span data-stu-id="2a589-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="2a589-371">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-372">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-373">Nuovo in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2a589-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="2a589-374">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-375">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-376">Nuovo in Live Communications Server 2003 (non utilizzato).</span><span class="sxs-lookup"><span data-stu-id="2a589-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="2a589-377">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="2a589-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="2a589-379">Questo attributo consente di controllare se un singolo utente è abilitato per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="2a589-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="2a589-380">Viene applicato dal livello Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="2a589-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="2a589-381">È contrassegnata per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2a589-382">I valori validi sono <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-383">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-384">msRTCSIP-Master (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-385">Nuovo in Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2a589-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="2a589-386">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-387">msRTCSIP-line</span><span class="sxs-lookup"><span data-stu-id="2a589-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="2a589-388">Questo attributo a valore singolo contiene l'ID del dispositivo, ovvero l'URI SIP o l'URI TEL del telefono utilizzato dai controlli utente, utilizzati da Lync per la telefonia.</span><span class="sxs-lookup"><span data-stu-id="2a589-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="2a589-389">Questo attributo è contrassegnato per la replica del catalogo globale ed è indicizzato.</span><span class="sxs-lookup"><span data-stu-id="2a589-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="2a589-390">Se un utente è abilitato per VoIP aziendale, questo attributo archivia la versione normalizzata E. 164 del numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="2a589-391">Nuovo in Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="2a589-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="2a589-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="2a589-393">Questo attributo a valore singolo contiene l'URI SIP del server gateway CSTA-SIP.</span><span class="sxs-lookup"><span data-stu-id="2a589-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="2a589-394">Questo attributo è contrassegnato per la replica del catalogo globale ma non è indicizzato.</span><span class="sxs-lookup"><span data-stu-id="2a589-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="2a589-395">Nuovo in Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="2a589-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-396">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-397">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-398">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-399">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-400">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-401">Questo attributo multivalore contiene un elenco di nomi distinti (DN) di normalizzazione locali associati a questo profilo località.</span><span class="sxs-lookup"><span data-stu-id="2a589-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="2a589-402">Il tipo di questo attributo è un file binario DN.</span><span class="sxs-lookup"><span data-stu-id="2a589-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="2a589-403">Esiste una relazione uno-a-molti tra il profilo percorso e le regole di normalizzazione locali.</span><span class="sxs-lookup"><span data-stu-id="2a589-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="2a589-404">L'ordinamento dell'elenco dei DNs di normalizzazione locale deve essere mantenuto nell'ordine specificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="2a589-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="2a589-405">La conservazione dell'ordine viene mantenuta dalla parte binaria del file binario DN, che specifica l'indice dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="2a589-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="2a589-406">Collegamento in avanti: <strong>Link ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="2a589-407">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-locationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-408">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-409">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="2a589-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="2a589-411">Questo attributo contiene un elenco di opzioni per la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="2a589-412">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-413">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-414">Questo attributo a valore singolo contiene un nome descrittivo per il profilo percorso che indica la posizione rappresentata dal profilo.</span><span class="sxs-lookup"><span data-stu-id="2a589-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="2a589-415">Poiché è possibile disporre di più profili percorso, l'amministratore deve disporre di un modo per distinguere i diversi profili.</span><span class="sxs-lookup"><span data-stu-id="2a589-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="2a589-416">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-417">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-418">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-419">Questo attributo multivalore contiene un elenco dei nomi distinti del profilo percorso.</span><span class="sxs-lookup"><span data-stu-id="2a589-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="2a589-420">Questo attributo consente di specificare il collegamento a ritroso a uno o più profili percorso.</span><span class="sxs-lookup"><span data-stu-id="2a589-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="2a589-421">Collegamento a ritroso: <strong>Link ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="2a589-422">Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-423">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-424">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-425">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-426">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-427">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-428">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="2a589-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="2a589-430">Questo attributo contiene le opzioni per il profilo località.</span><span class="sxs-lookup"><span data-stu-id="2a589-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="2a589-431">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="2a589-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="2a589-433">Questo attributo multivalore contiene un elenco di contatti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="2a589-434">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="2a589-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="2a589-436">Questo attributo multivalore contiene un elenco di profili località.</span><span class="sxs-lookup"><span data-stu-id="2a589-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="2a589-437">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-439">Questo attributo rappresenta il numero massimo di richieste di ricerca in sospeso per ogni server.</span><span class="sxs-lookup"><span data-stu-id="2a589-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="2a589-440">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-442">L'attributo rappresenta il numero massimo di sottoscrizioni per utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="2a589-443">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-445">Questo attributo rappresenta la finestra di timeout massima per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="2a589-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-446">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-447">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-448">Questo attributo rappresenta la finestra di timeout massima per le registrazioni.</span><span class="sxs-lookup"><span data-stu-id="2a589-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-449">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-451">Questo attributo rappresenta la finestra di timeout massima per le sottoscrizioni dei dati di roaming.</span><span class="sxs-lookup"><span data-stu-id="2a589-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-452">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="2a589-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="2a589-454">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-455">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="2a589-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="2a589-457">Questo attributo è un attributo del punto di controllo del servizio nella classe computer che specifica un collegamento alla Factory di unità di controllo multipunto a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="2a589-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="2a589-458">Questo punto di controllo del servizio e l'attributo viene creato per ogni MCU Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a589-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="2a589-459">Ogni MCU Microsoft deve individuare il server back-end del pool a cui appartiene, per poter recuperare le impostazioni a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="2a589-460">Il valore di questo attributo è il nome distinto (DN) della factory MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="2a589-461">Si tratta di un attributo a valore singolo e contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2a589-462">Collegamento in avanti: <strong>Link ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="2a589-463">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-464">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="2a589-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="2a589-466">Si tratta di un attributo riservato a più stringhe.</span><span class="sxs-lookup"><span data-stu-id="2a589-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="2a589-467">Le impostazioni archiviate in questo attributo sono rappresentate come coppie nome = valore.</span><span class="sxs-lookup"><span data-stu-id="2a589-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="2a589-468">Le coppie nome/valore attualmente definite sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="2a589-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-470">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="2a589-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="2a589-472">Si tratta di un attributo a valore singolo che contiene il nome distinto (DN) di una singola factory MCU associata a un pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="2a589-473">Collegamento in avanti: <strong>Link ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="2a589-474">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-475">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="2a589-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="2a589-477">Questo attributo è una stringa a valore singolo che specifica il GUID del provider di factory MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="2a589-478">In base al valore GUID, il processo di factory MCU determina se si desidera eseguire il servizio di questo tipo di MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="2a589-479">Se il valore GUID è <strong>{F0810510-424f-46ef-84fe-6CC720DF1791}</strong>, il processo factory MCU (disponibile per impostazione predefinita in Lync Server) lo elaborerà.</span><span class="sxs-lookup"><span data-stu-id="2a589-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="2a589-480">Per qualsiasi altro valore GUID, il processo di factory MCU non servirà il tipo di MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="2a589-481">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="2a589-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="2a589-483">Questo attributo è un elenco multivalore di nomi distinti (DN).</span><span class="sxs-lookup"><span data-stu-id="2a589-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="2a589-484">Questo attributo contiene un elenco di tutti i server MCU dello stesso tipo e fornitore associato a questa factory MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="2a589-485">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="2a589-486">Collegamento a ritroso: Link ID 11027</span><span class="sxs-lookup"><span data-stu-id="2a589-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="2a589-487">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-488">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="2a589-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="2a589-490">Questo attributo è una stringa a valore singolo che specifica il supporto che può essere gestito dalla MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="2a589-491">I tipi validi supportati sono:</span><span class="sxs-lookup"><span data-stu-id="2a589-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-492">riunione</span><span class="sxs-lookup"><span data-stu-id="2a589-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="2a589-493">audio-video</span><span class="sxs-lookup"><span data-stu-id="2a589-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="2a589-494">Chat</span><span class="sxs-lookup"><span data-stu-id="2a589-494">chat</span></span></p></li>
<li><p><span data-ttu-id="2a589-495">telefono-conf</span><span class="sxs-lookup"><span data-stu-id="2a589-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-496">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="2a589-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="2a589-498">Questo attributo è una stringa a valore singolo che specifica il nome di un fornitore di MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="2a589-499">Tutti i MCU di Microsoft specificano questo attributo come <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-500">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-501">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-502">Questo attributo definisce diverse opzioni di riunione che sono abilitate a livello globale per tutti gli utenti o gli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="2a589-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="2a589-503">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="2a589-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="2a589-504">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="2a589-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-505">0: AllowOrganizeMeetingWithAnonymousParticipants è None (non consentire agli utenti di invitare utenti anonimi alle riunioni) (nessun bit impostato)</span><span class="sxs-lookup"><span data-stu-id="2a589-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="2a589-506">4: AllowOrganizeMeetingWithAnonymousParticipants è Everyone (Consenti a tutti gli utenti di invitare utenti anonimi alle riunioni) (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="2a589-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2a589-507">8: AllowOrganizeMeetingWithAnonymousParticipants è UsePerUserSetting (consente agli utenti di invitare utenti anonimi alle riunioni in base all'impostazione per utente) (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="2a589-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="2a589-508">16: UserPerUserMeetingPolicy (il criterio di riunione è definito per utente) (posizione bit 4)</span><span class="sxs-lookup"><span data-stu-id="2a589-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-509">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-510">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-511">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-512">Questo attributo specifica il nome distinto (DN) del criterio che l'amministratore ha assegnato per l'utente come attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="2a589-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="2a589-513">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-514">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-516">Questo attributo rappresenta la finestra di timeout della sottoscrizione di presenza minima.</span><span class="sxs-lookup"><span data-stu-id="2a589-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-517">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-518">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-519">Questo attributo rappresenta la finestra di timeout minima per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-520">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-521">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-523">Questo attributo rappresenta la finestra di timeout minima per la sottoscrizione dei dati di roaming.</span><span class="sxs-lookup"><span data-stu-id="2a589-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2a589-524">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-525">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="2a589-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="2a589-527">Questo attributo viene utilizzato per archiviare il backend di SQL Server con mirroring utilizzato dal pool Front end.</span><span class="sxs-lookup"><span data-stu-id="2a589-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="2a589-528">Nuovo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a589-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="2a589-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="2a589-530">Questo attributo contiene le opzioni e i flag che definiscono le impostazioni per i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2a589-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="2a589-531">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="2a589-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="2a589-533">Questo attributo contiene il nome distinto per un oggetto dei criteri per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2a589-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="2a589-534">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-535">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-536">Questo attributo rappresenta il numero consentito di dispositivi in cui un utente può registrarsi per le comunicazioni SIP e sottoscrivere la presenza.</span><span class="sxs-lookup"><span data-stu-id="2a589-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="2a589-537">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-538">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="2a589-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="2a589-540">Questo attributo consente di specificare le opzioni abilitate per l'utente o l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="2a589-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="2a589-541">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="2a589-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="2a589-542">Ogni opzione è rappresentata da un bit.</span><span class="sxs-lookup"><span data-stu-id="2a589-542">Each option is represented by a bit.</span></span> <span data-ttu-id="2a589-543">Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2a589-544">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="2a589-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-545">1: abilitato per la connettività di messaggistica istantanea pubblica (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="2a589-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2a589-546">2: riservato (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="2a589-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2a589-547">4: riservato (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="2a589-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2a589-548">8: riservato (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="2a589-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="2a589-549">16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</span><span class="sxs-lookup"><span data-stu-id="2a589-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="2a589-550">64: AllowOrganizeMeetingWithAnonymousParticipants (Consenti agli utenti di invitare utenti anonimi alle riunioni (posizione bit 6)</span><span class="sxs-lookup"><span data-stu-id="2a589-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="2a589-551">128: UCEnabled (Abilita gli utenti per UC) (posizione bit 7)</span><span class="sxs-lookup"><span data-stu-id="2a589-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="2a589-552">256: EnabledForEnhancedPresence (abilitare l'utente per la connettività per la messaggistica istantanea pubblica) (posizione bit 8)</span><span class="sxs-lookup"><span data-stu-id="2a589-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="2a589-553">512: RemoteCallControlDualMode (posizione bit 9)</span><span class="sxs-lookup"><span data-stu-id="2a589-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-554">Nuovo in Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="2a589-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="2a589-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="2a589-556">Questo attributo viene utilizzato nelle topologie a foresta centrale e a risorse per abilitare l'accesso Single Sign-on quando un utente di attributo objectSID dall'account principale di Windows NT viene copiato in questo attributo dell'oggetto utente o contatto corrispondente nella foresta di risorse o nel bosco centrale.</span><span class="sxs-lookup"><span data-stu-id="2a589-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="2a589-557">Communicator Web Access esegue la ricerca di un utente in servizi di dominio Active Directory utilizzando questo attributo o l'attributo objectSid dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="2a589-558">Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="2a589-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="2a589-560">Questo attributo è il nome dell'URN (Uniform Resource Name) del proprietario per un contatto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="2a589-561">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-562">msRTCSIP-pattern (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-563">Questo attributo di stringa a valore singolo contiene un modello utilizzato per la corrispondenza dei numeri di composizione nel formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="2a589-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="2a589-564">Se il numero di composizione corrisponde a questo modello, la conversione viene applicata al numero composto.</span><span class="sxs-lookup"><span data-stu-id="2a589-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="2a589-565">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-566">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-567">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-568">Questo attributo multivalore contiene un elenco di nomi distinti (DN) della route telefonica.</span><span class="sxs-lookup"><span data-stu-id="2a589-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="2a589-569">Questo attributo consente di specificare il collegamento a ritroso a una o più route telefoniche.</span><span class="sxs-lookup"><span data-stu-id="2a589-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="2a589-570">Collegamento a ritroso: <strong>Link ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="2a589-571">Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-572">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-573">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-574">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-575">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-576">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-577">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-578">Questo attributo di stringa UNICODE a valore singolo specifica il nome descrittivo della route telefonica, in modo che sia possibile fare riferimento facilmente all'amministratore.</span><span class="sxs-lookup"><span data-stu-id="2a589-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="2a589-579">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-580">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-581">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-582">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-583">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-584">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-585">Questo attributo è una stringa Unicode a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="2a589-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="2a589-586">Questo attributo stringa contiene la definizione dei criteri in formato XML.</span><span class="sxs-lookup"><span data-stu-id="2a589-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="2a589-587">La definizione dello schema XML è comune nei diversi tipi di criteri, solo le impostazioni sono diverse per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="2a589-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="2a589-588">La definizione dello schema XML (XSD) è definita nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="2a589-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="2a589-589">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-590">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-591">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-592">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-593">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-594">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-595">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-596">Questo attributo di stringa Unicode a valore singolo contiene il tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="2a589-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="2a589-597">I tipi di criteri validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-598">riunione</span><span class="sxs-lookup"><span data-stu-id="2a589-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="2a589-599">telefonia</span><span class="sxs-lookup"><span data-stu-id="2a589-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-600">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-601">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="2a589-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="2a589-603">Questo attributo consente di specificare un collegamento al pool a cui appartiene un computer.</span><span class="sxs-lookup"><span data-stu-id="2a589-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="2a589-604">Questo attributo è impostato indipendentemente dal fatto che il computer esegua la versione Standard Edition o Enterprise Edition di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a589-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="2a589-605">Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2a589-606">Il valore valido è il nome di dominio del pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="2a589-607">Collegamento in avanti: <strong>Link ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="2a589-608">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-609">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="2a589-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="2a589-611">Questo attributo multivalore contiene un elenco dei nomi distinti (DN) dei pool a cui è associata la factory MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="2a589-612">Collegamento a ritroso: <strong>Link ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="2a589-613">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-614">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="2a589-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="2a589-616">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-617">Nuovo in Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="2a589-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="2a589-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="2a589-619">Questo attributo consente di specificare un nome arbitrario per un pool visualizzato dalla console di gestione.</span><span class="sxs-lookup"><span data-stu-id="2a589-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="2a589-620">Questo nome può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="2a589-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="2a589-621">Il valore valido è una stringa che rappresenta il nome di un pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="2a589-622">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="2a589-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-624">Questo attributo è un valore stringa a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="2a589-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="2a589-625">Il valore di questo attributo, se presente, rappresenta il nome di dominio completo del pool se l'amministratore vuole creare un pool Front end con un FQDN non conforme alla struttura di dominio Active Directory in cui è stato creato il pool Front End, ad esempio un SIP spazio dei nomi disgiunto dallo spazio dei nomi DNS (Domain Name System)).</span><span class="sxs-lookup"><span data-stu-id="2a589-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="2a589-626">È consigliabile mappare l'FQDN del dominio del pool Front end alla porzione del nome di dominio come dominio Active Directory in cui risiede il pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="2a589-627">Pertanto, quando nell'attributo non è presente alcun valore, il nome di dominio completo del pool Front End verrà impostato come predefinito per la struttura di domini di Active Directory, come indicato dall'attributo <strong>dNSHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="2a589-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="2a589-628">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="2a589-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="2a589-630">Un elenco multivalore dei nomi di dominio di tutti i server Lync Server, Enterprise Edition associati a un pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="2a589-631">Questo attributo di tipo Integer definisce se il pool è in grado di messaggistica istantanea e presenza e riunioni.</span><span class="sxs-lookup"><span data-stu-id="2a589-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="2a589-632">I possibili tipi di valore validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-633">Indefinito: servizio di messaggistica istantanea e presenza (Live Communications Server 2005 e 2003)</span><span class="sxs-lookup"><span data-stu-id="2a589-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="2a589-634">1: servizio di messaggistica istantanea e presenza (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="2a589-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="2a589-635">2: servizio di messaggistica istantanea e presenza e riunione (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="2a589-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-636">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="2a589-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="2a589-638">Questo attributo specifica se in un pool di server è in esecuzione il server Standard Edition o il server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2a589-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="2a589-639">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="2a589-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="2a589-640">Ogni opzione è rappresentata da un bit.</span><span class="sxs-lookup"><span data-stu-id="2a589-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="2a589-641">Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</span><span class="sxs-lookup"><span data-stu-id="2a589-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-642">1: Server Standard Edition, utenti host (posizione bit 0)</span><span class="sxs-lookup"><span data-stu-id="2a589-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2a589-643">2: Server Enterprise Edition, utenti host (posizione bit 1)</span><span class="sxs-lookup"><span data-stu-id="2a589-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2a589-644">4: Server Standard Edition, applicazioni host (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="2a589-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2a589-645">8: Server Enterprise Edition, applicazioni host (posizione bit 3)</span><span class="sxs-lookup"><span data-stu-id="2a589-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="2a589-646">Poiché Lync Server non supporta i pool che ospitano solo le applicazioni, gli unici valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-647">5: Server Standard Edition, ospita utenti e applicazioni (posizioni di bit 0 e 2)</span><span class="sxs-lookup"><span data-stu-id="2a589-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="2a589-648">10: Server Enterprise Edition, ospita utenti e applicazioni (posizioni di bit 1 e 3)</span><span class="sxs-lookup"><span data-stu-id="2a589-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-649">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="2a589-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="2a589-651">Questo attributo definisce la versione del pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-651">This attribute defines the pool version.</span></span> <span data-ttu-id="2a589-652">Si tratta di un tipo intero che viene incrementato con ogni versione di prodotto principale.</span><span class="sxs-lookup"><span data-stu-id="2a589-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="2a589-653">I possibili tipi di valore validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2a589-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="2a589-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2a589-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="2a589-656">2: Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="2a589-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="2a589-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2a589-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2a589-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2a589-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="2a589-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2a589-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-660">Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="2a589-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="2a589-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="2a589-662">Questo attributo contiene le opzioni e i flag che definiscono le impostazioni di presenza.</span><span class="sxs-lookup"><span data-stu-id="2a589-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="2a589-663">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="2a589-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="2a589-665">Questo attributo contiene il nome distinto per un oggetto criterio di presenza.</span><span class="sxs-lookup"><span data-stu-id="2a589-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="2a589-666">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="2a589-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="2a589-668">Questo attributo consente a un utente o a un contatto per la messaggistica SIP.</span><span class="sxs-lookup"><span data-stu-id="2a589-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="2a589-669">Viene aggiunto alla classe Contact perché nella topologia della foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="2a589-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="2a589-670">Il valore valido è il nome distinto del server Standard Edition o del pool Enterprise Edition front end in cui è ospitato un utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="2a589-671">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="2a589-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="2a589-673">Questo attributo contiene l'indirizzo SIP di un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="2a589-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="2a589-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="2a589-675">Questo attributo contiene l'ID del dispositivo della linea privata.</span><span class="sxs-lookup"><span data-stu-id="2a589-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="2a589-676">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-677">msRTCSIP-instradabile</span><span class="sxs-lookup"><span data-stu-id="2a589-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="2a589-678">Questo attributo è un attributo booleano utilizzato per determinare se Lync Server è autorizzato a eseguire il routing a questo servizio utilizzando il relativo indirizzo GRUU.</span><span class="sxs-lookup"><span data-stu-id="2a589-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="2a589-679">Se questo valore è impostato su <strong>true</strong>, Lync Server è autorizzato a eseguire il routing a questo servizio.</span><span class="sxs-lookup"><span data-stu-id="2a589-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="2a589-680">Se questo valore è impostato su <strong>false</strong>, Lync Server non è autorizzato a eseguire il routing a questo servizio.</span><span class="sxs-lookup"><span data-stu-id="2a589-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="2a589-681">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-682">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-683">Questo attributo di stringa UNICODE a valore singolo definisce un attributo che qualifica l'utilizzo di una route telefonica.</span><span class="sxs-lookup"><span data-stu-id="2a589-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="2a589-684">La selezione di una route telefonica è determinata in base a due elementi: l'attributo Usage assegnato alla route Phone e gli attributi di utilizzo dei criteri consentiti dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="2a589-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="2a589-685">Viene selezionata la prima route telefonica con un attributo di utilizzo che corrisponde all'utilizzo consentito del chiamante.</span><span class="sxs-lookup"><span data-stu-id="2a589-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="2a589-686">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-687">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-688">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-689">Questo attributo con nome distinto (DN) multivalore contiene un elenco di nomi distinti per l'utilizzo delle route.</span><span class="sxs-lookup"><span data-stu-id="2a589-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="2a589-690">Collegamento in avanti: <strong>Link ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="2a589-691">Questo attributo è un collegamento in avanti per il collegamento a ritroso corrispondente <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-692">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="2a589-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-694">Questo attributo contiene il nome distinto che punta al pool che tutto il traffico SIP indirizzato a questa MCU o a un servizio attendibile deve passare attraverso.</span><span class="sxs-lookup"><span data-stu-id="2a589-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="2a589-695">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-696">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-697">Questo attributo di stringa UNICODE a valore singolo specifica il nome descrittivo della regola di normalizzazione, in modo che possa essere facilmente referenziato da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="2a589-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="2a589-698">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-699">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="2a589-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="2a589-701">Questo attributo rappresenta la versione dello schema attualmente distribuita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a589-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-702">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-703">Questo attributo consente di limitare il numero di risultati di ricerca da restituire da una ricerca di directory quando un utente cerca un contatto tramite Communicator.</span><span class="sxs-lookup"><span data-stu-id="2a589-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="2a589-704">Questo attributo ignorerà il valore fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="2a589-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="2a589-705">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-706">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-707">Questo attributo limita il numero di richieste di ricerca restituite.</span><span class="sxs-lookup"><span data-stu-id="2a589-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="2a589-708">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="2a589-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="2a589-710">Questo attributo multivalore è un collegamento a ritroso contenente un elenco di nomi distinti (DN).</span><span class="sxs-lookup"><span data-stu-id="2a589-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="2a589-711">Tali DNs puntano a un oggetto pool o <strong>TrustedService</strong> .</span><span class="sxs-lookup"><span data-stu-id="2a589-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="2a589-712">Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-713">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="2a589-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="2a589-715">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-716">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-717">Questo attributo multivalore contiene un elenco di nomi distinti.</span><span class="sxs-lookup"><span data-stu-id="2a589-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="2a589-718">Questi nomi distinti sono collegamenti indietro che fanno riferimento ad altri oggetti server a cui è possibile assegnare un profilo percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a589-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="2a589-719">Collegamento a ritroso: <strong>Link ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="2a589-720">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="2a589-721">Questo attributo di collegamento a ritroso fa riferimento solo ai pool e ai Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="2a589-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="2a589-722">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-723">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="2a589-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="2a589-725">Questo attributo definisce le informazioni sulla versione del server.</span><span class="sxs-lookup"><span data-stu-id="2a589-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="2a589-726">Questo numero di versione si applica a tutti i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="2a589-726">This version number applies to all server roles.</span></span> <span data-ttu-id="2a589-727">Si tratta di un numero intero monotonamente crescente che si incrementi con ogni versione del prodotto ufficiale.</span><span class="sxs-lookup"><span data-stu-id="2a589-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="2a589-728">I possibili valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-729">Indefinito: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2a589-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="2a589-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2a589-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="2a589-731">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="2a589-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="2a589-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2a589-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2a589-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2a589-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="2a589-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2a589-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="2a589-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a589-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-736">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-737">msRTCSIP-tipooggettoorigine</span><span class="sxs-lookup"><span data-stu-id="2a589-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="2a589-738">Questo attributo a valore singolo di tipo integer specifica il tipo di oggetto a cui punta <strong>msDS-SourceObjectDN</strong> , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2a589-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-739">null | 0x00000001: rappresenta un oggetto utente principale di Windows NT Server da una foresta diversa</span><span class="sxs-lookup"><span data-stu-id="2a589-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="2a589-740">Gli attributi seguenti rappresentano un tipo di gruppo proveniente da una foresta diversa per l'espansione del gruppo di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="2a589-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2a589-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2a589-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2a589-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2a589-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2a589-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2a589-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2a589-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2a589-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="2a589-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="2a589-746">0x90000000: rappresenta un oggetto di accesso sottoscrittore o operatore automatico dalla stessa foresta o da una foresta diversa</span><span class="sxs-lookup"><span data-stu-id="2a589-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="2a589-747">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-748">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-749">Nuovo in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2a589-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="2a589-750">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="2a589-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="2a589-752">Questo attributo consente di spostare un utente o un oggetto contatto da un pool di Lync Server a un altro.</span><span class="sxs-lookup"><span data-stu-id="2a589-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="2a589-753">Questo attributo viene aggiunto alla classe Contact, poiché nella topologia della foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="2a589-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="2a589-754">Il valore valido è il nome distinto del server di destinazione Standard Edition o del pool Front end a cui deve essere spostato un utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="2a589-755">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-756">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-757">Questo attributo di stringa a valore singolo contiene un modello o un intervallo di numeri di telefono da instradare ai gateway specificati definiti in <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-758">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="2a589-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="2a589-760">Questo attributo archivia le coppie nome/valore per i criteri di destinazione per gli utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a589-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="2a589-761">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="2a589-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="2a589-763">Questo attributo archivia l'identificatore univoco per un tenant.</span><span class="sxs-lookup"><span data-stu-id="2a589-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="2a589-764">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-765">msRTCSIP-Translation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-766">Questo attributo viene utilizzato dalla funzionalità vocale di Lync Server e contiene la stringa di conversione da applicare al numero composto, se viene trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="2a589-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="2a589-767">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2a589-768">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="2a589-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="2a589-770">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-771">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="2a589-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-773">Questo attributo è un valore stringa che contiene il nome di dominio completo dell'MCU.</span><span class="sxs-lookup"><span data-stu-id="2a589-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="2a589-774">Si tratta di un attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="2a589-774">This is a single-valued attribute.</span></span> <span data-ttu-id="2a589-775">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2a589-776">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="2a589-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="2a589-778">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-779">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="2a589-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-781">Questo attributo è un valore stringa che contiene il nome di dominio completo del server che esegue il server proxy.</span><span class="sxs-lookup"><span data-stu-id="2a589-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="2a589-782">Questo attributo è a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="2a589-782">This attribute is single-valued.</span></span> <span data-ttu-id="2a589-783">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2a589-784">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="2a589-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="2a589-786">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="2a589-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-788">Questo attributo è un attributo a valore singolo che rappresenta il nome di dominio completo di un server attendibile.</span><span class="sxs-lookup"><span data-stu-id="2a589-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="2a589-789">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="2a589-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="2a589-791">Questo attributo consente di specificare il numero di versione di un server nell'elenco dei server attendibili.</span><span class="sxs-lookup"><span data-stu-id="2a589-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="2a589-792">I possibili valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2a589-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="2a589-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2a589-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="2a589-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2a589-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2a589-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2a589-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="2a589-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2a589-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="2a589-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a589-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-799">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="2a589-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="2a589-801">Questo attributo definisce le opzioni abilitate per il servizio attendibile.</span><span class="sxs-lookup"><span data-stu-id="2a589-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="2a589-802">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="2a589-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="2a589-804">Questo attributo multivalore contiene un elenco di nomi distinti (DN) che fanno riferimento a un oggetto servizio attendibile, ad esempio un servizio di autenticazione di inoltro multimediale.</span><span class="sxs-lookup"><span data-stu-id="2a589-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="2a589-805">Un servizio di autenticazione di inoltro multimediale (collocato fisicamente nel server perimetrale che esegue il servizio A/V Conferencing) deve essere associato a un pool per il supporto degli scenari audio per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="2a589-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="2a589-806">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-807">UC</span><span class="sxs-lookup"><span data-stu-id="2a589-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="2a589-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="2a589-809">Questo attributo è un valore integer che definisce il numero di porta utilizzato per la connessione al servizio di GRUU.</span><span class="sxs-lookup"><span data-stu-id="2a589-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="2a589-810">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="2a589-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="2a589-812">Questo attributo è un valore stringa che definisce il tipo di servizio di GRUU che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="2a589-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="2a589-813">I tipi di servizio GRUU validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="2a589-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="2a589-815">Gateway</span><span class="sxs-lookup"><span data-stu-id="2a589-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="2a589-816">Servizio di autenticazione di MRAS (Media Relay Authentication Service)</span><span class="sxs-lookup"><span data-stu-id="2a589-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="2a589-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="2a589-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="2a589-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="2a589-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-819">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="2a589-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="2a589-821">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-822">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="2a589-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="2a589-824">Questo attributo è un valore stringa che contiene il nome di dominio completo di IIS in cui sono in esecuzione i servizi Web di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a589-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="2a589-825">Si tratta di un attributo a valore singolo.</span><span class="sxs-lookup"><span data-stu-id="2a589-825">This is a single-valued attribute.</span></span> <span data-ttu-id="2a589-826">Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a589-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2a589-827">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-828">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-829">Questo attributo definisce diverse opzioni UC che sono abilitate a livello globale a tutti gli oggetti utente o contatti.</span><span class="sxs-lookup"><span data-stu-id="2a589-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="2a589-830">Questo attributo è un valore della maschera di bit di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="2a589-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="2a589-831">Ogni opzione è rappresentata dalla presenza di un bit.</span><span class="sxs-lookup"><span data-stu-id="2a589-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="2a589-832">Il valore possibile valido (e la posizione bit associata) è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2a589-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-833">4: UsePerUserUCPolicy (posizione bit 2)</span><span class="sxs-lookup"><span data-stu-id="2a589-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="2a589-834">Quando questo bit è impostato, il criterio UC è definito per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="2a589-835">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-836">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-837">Questo attributo a valore singolo contiene il nome distinto (DN) del criterio UC che l'amministratore ha assegnato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="2a589-838">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-839">msRTCSIP-UserDomainList (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2a589-840">Questo attributo fornisce un elenco di tutti i domini in una foresta che ospitano gli utenti abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="2a589-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="2a589-841">L'impostazione predefinita è un elenco vuoto che indica che tutti i domini nella foresta sono abilitati per SIP.</span><span class="sxs-lookup"><span data-stu-id="2a589-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="2a589-842">I valori validi sono più stringhe che rappresentano i nomi di dominio di singoli domini.</span><span class="sxs-lookup"><span data-stu-id="2a589-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="2a589-843">Nuovo in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2a589-844">Obsoleto in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="2a589-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="2a589-846">Questo attributo determina se l'utente è attualmente abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a589-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="2a589-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="2a589-848">Questo attributo multivalore contiene un elenco di coppie nome/valore nel formato &quot;nome = valore. &quot; Questo attributo è contrassegnato per la replica del catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="2a589-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="2a589-849">Nuovo in Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="2a589-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="2a589-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="2a589-851">Questo attributo contiene il nome distinto (DN) che punta a un oggetto profilo percorso.</span><span class="sxs-lookup"><span data-stu-id="2a589-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="2a589-852">Nuovo in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2a589-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="2a589-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="2a589-854">Questo attributo archivia le coppie nome/valore per i criteri utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="2a589-855">Nuovo in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a589-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="2a589-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="2a589-857">Si tratta di un attributo multivalore contenente un elenco di nomi distinti con Binary (DN_WITH_BINARY) che puntano ai criteri utente globali di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="2a589-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="2a589-858">La parte binaria indica il tipo di criterio a cui fa riferimento la parte DN.</span><span class="sxs-lookup"><span data-stu-id="2a589-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="2a589-859">I valori binari validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a589-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-860">0x00000001: criteri per le riunioni</span><span class="sxs-lookup"><span data-stu-id="2a589-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="2a589-861">0x00000002: criteri UC</span><span class="sxs-lookup"><span data-stu-id="2a589-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="2a589-862">0x00000005: criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="2a589-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-863">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="2a589-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="2a589-865">Questo è l'ID del gruppo di routing SIP.</span><span class="sxs-lookup"><span data-stu-id="2a589-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="2a589-866">Gli utenti dello stesso gruppo registreranno lo stesso front end server.</span><span class="sxs-lookup"><span data-stu-id="2a589-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="2a589-867">Nuovo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a589-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="2a589-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="2a589-869">Si tratta di un attributo multivalore.</span><span class="sxs-lookup"><span data-stu-id="2a589-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="2a589-870">Questo attributo è riservato per uso futuro.</span><span class="sxs-lookup"><span data-stu-id="2a589-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2a589-871">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="2a589-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="2a589-873">Questo attributo a valore singolo punta al pool o al server Standard Edition a cui appartengono i componenti Web.</span><span class="sxs-lookup"><span data-stu-id="2a589-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="2a589-874">Collegamento in avanti: <strong>Link ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="2a589-875">Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-876">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="2a589-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="2a589-878">Questo attributo è un elenco multivalore di nomi distinti.</span><span class="sxs-lookup"><span data-stu-id="2a589-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="2a589-879">Questo attributo contiene un elenco di tutti i server Web associati al pool.</span><span class="sxs-lookup"><span data-stu-id="2a589-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="2a589-880">Collegamento a ritroso: <strong>Link ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="2a589-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="2a589-881">Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="2a589-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2a589-882">Nuovo in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2a589-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-883">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="2a589-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2a589-884">Nuovo in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2a589-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="2a589-885">Obsoleto in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2a589-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="2a589-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="2a589-887">Questo attributo esistente di Active Directory viene utilizzato dalla telefonia per specificare l'elenco di indirizzi TCP/IP alternativi per un telefono.</span><span class="sxs-lookup"><span data-stu-id="2a589-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="2a589-888">Nuovo sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="2a589-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="2a589-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="2a589-890">Questo attributo esistente di Active Directory viene utilizzato dai componenti vocali in Lync Server, solo per gli oggetti contatto, allo scopo di eseguire il routing delle chiamate ai numeri di accesso del Sottoscrittore e dell'operatore automatico di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="2a589-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="2a589-891">L'indirizzo di inoltro di chiamata incondizionato è memorizzato in questo attributo multivalore.</span><span class="sxs-lookup"><span data-stu-id="2a589-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="2a589-892">Questo account viene creato per lo scopo specifico dell'operatore automatico e dell'accesso sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="2a589-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="2a589-893">Gli attributi di questo account non devono essere modificati dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="2a589-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="2a589-894">Nuovo nel sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2a589-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a589-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2a589-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="2a589-896">Questo attributo multivalore di Active Directory esistente fa parte dello schema di base di Active Directory introdotto in Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2a589-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="2a589-897">Questo attributo contiene i vari indirizzi X400, X500 e SMTP del messaggio di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="2a589-898">In Live Communications Server 2003 e versioni successive, l'URI SIP dell'utente viene aggiunto all'elenco, utilizzando il &quot;Tag SIP&quot; :.</span><span class="sxs-lookup"><span data-stu-id="2a589-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="2a589-899">Le applicazioni seguenti cercano l'URI SIP dell'utente da questo attributo:</span><span class="sxs-lookup"><span data-stu-id="2a589-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a589-900">Client di messaggistica e collaborazione di Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="2a589-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="2a589-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="2a589-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2a589-902">Nuovo nel sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2a589-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a589-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="2a589-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="2a589-904">Questo attributo esistente di Active Directory contiene il numero di telefono per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2a589-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="2a589-905">Nuovo nel sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2a589-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

