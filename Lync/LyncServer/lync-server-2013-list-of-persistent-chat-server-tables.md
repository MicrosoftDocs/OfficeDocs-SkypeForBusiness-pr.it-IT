---
title: 'Lync Server 2013: Elenco delle tabelle del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d5c16160d51373fe1eef5b7cbaefe728b904545
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="b096c-102">Elenco delle tabelle del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b096c-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b096c-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b096c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b096c-104">Lo schema del database della chat persistente è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="b096c-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="b096c-105">Sincronizzazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="b096c-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b096c-106">Tabella</span><span class="sxs-lookup"><span data-stu-id="b096c-106">Table</span></span></th>
<th><span data-ttu-id="b096c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b096c-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b096c-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-109">Contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="b096c-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="b096c-110">Ogni riga corrisponde a un dominio di servizi di dominio Active Directory che il server di chat persistente sta monitorando attivamente per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b096c-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="b096c-111">In questa tabella sono rappresentati solo i domini di Active Directory rilevanti per il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b096c-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-113">Contiene le modifiche alle appartenenze ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dalle successive operazioni di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblADUpdates) che viene usata nel primo passaggio della sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b096c-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="b096c-114">Le modifiche apportate all'appartenenza sono archiviate, elaborate o entrambe, solo per i gruppi elencati nella tabella tblPrincipal o che hanno già membri elencati.</span><span class="sxs-lookup"><span data-stu-id="b096c-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-116">Contiene le modifiche apportate ai servizi di dominio Active Directory che non sono ancora state elaborate dalle successive operazioni di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblPrincipalMemberDifference) che viene usata nel primo passaggio di Active Directory Sync.</span><span class="sxs-lookup"><span data-stu-id="b096c-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="b096c-117">Le modifiche apportate a Active Directory vengono archiviate, elaborate o entrambe solo per le entità già elencate nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b096c-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-119">Contiene le appartenenze principali.</span><span class="sxs-lookup"><span data-stu-id="b096c-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-121">Contiene le entità che devono essere aggiornate da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b096c-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-123">Contiene le affiliazioni che non è stato possibile aggiornare per qualche motivo, in genere a causa di errori di accesso a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b096c-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="b096c-124">Questa tabella è a scopo informativo.</span><span class="sxs-lookup"><span data-stu-id="b096c-124">This table is for informational purposes only.</span></span> <span data-ttu-id="b096c-125">Il contenuto non viene usato.</span><span class="sxs-lookup"><span data-stu-id="b096c-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="b096c-126">Le entità con affiliazioni che non è stato possibile aggiornare correttamente vengono mantenute nella tabella tblPrincipalMeta e vengono fornite un'altra possibilità di essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="b096c-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="b096c-127">Entità, affiliazioni, nodi, ambiti e ruoli</span><span class="sxs-lookup"><span data-stu-id="b096c-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b096c-128">Tabella</span><span class="sxs-lookup"><span data-stu-id="b096c-128">Table</span></span></th>
<th><span data-ttu-id="b096c-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b096c-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b096c-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-131">Contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b096c-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="b096c-132">Questa tabella è statica.</span><span class="sxs-lookup"><span data-stu-id="b096c-132">This table is static.</span></span> <span data-ttu-id="b096c-133">La configurazione viene configurata durante la creazione di database e non cambia.</span><span class="sxs-lookup"><span data-stu-id="b096c-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-135">Contiene tutte le entità (utenti, cartelle, gruppi e così via).</span><span class="sxs-lookup"><span data-stu-id="b096c-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="b096c-136">Il server di chat persistente lo gestisce come elenco di piatti eterogenei.</span><span class="sxs-lookup"><span data-stu-id="b096c-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="b096c-137">Le varie colonne si basano sul tipo di ogni entità.</span><span class="sxs-lookup"><span data-stu-id="b096c-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="b096c-138">La maggior parte di queste entità sono copie memorizzate nella cache degli oggetti archiviati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b096c-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="b096c-139">La creazione della copia memorizzata nella cache nella tabella principale di questi oggetti Active Directory viene definita <em>provisioning</em>.</span><span class="sxs-lookup"><span data-stu-id="b096c-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="b096c-140">Alcune entità vengono create in modo più aggressivo rispetto ad altre e alcuni oggetti Active Directory vengono ignorati complessivamente.</span><span class="sxs-lookup"><span data-stu-id="b096c-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-142">Contiene le affiliazioni principali che descrivono l'appartenenza a gruppi di sicurezza di Active Directory, contenitori di Active Directory e così via.</span><span class="sxs-lookup"><span data-stu-id="b096c-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-144">Contiene il nodo Category, come gestito nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b096c-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-146">Contiene i tipi di ruolo e i set di autorizzazioni associati.</span><span class="sxs-lookup"><span data-stu-id="b096c-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="b096c-147">Questa tabella di ricerca è statica.</span><span class="sxs-lookup"><span data-stu-id="b096c-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-149">Contiene gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="b096c-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-151">Contiene ruoli assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="b096c-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-153">Contiene i componenti aggiuntivi registrati che possono essere associati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="b096c-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-155">Contiene solo gli attributi di &quot;visibilità&quot; e &quot;comportamento&quot; hardcoded usati nella tabella tblNode.</span><span class="sxs-lookup"><span data-stu-id="b096c-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-157">Contiene i valori degli attributi di &quot;visibilità hardcoded "e" di&quot; comportamento usati nella tabella tblNode.</span><span class="sxs-lookup"><span data-stu-id="b096c-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="b096c-158">Inviti, chat e altro supporto client</span><span class="sxs-lookup"><span data-stu-id="b096c-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b096c-159">Tabella</span><span class="sxs-lookup"><span data-stu-id="b096c-159">Table</span></span></th>
<th><span data-ttu-id="b096c-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b096c-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b096c-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-162">Contiene invita per tutti gli utenti con provisioning nel sistema per tutti i nodi con l'invito automatico abilitato.</span><span class="sxs-lookup"><span data-stu-id="b096c-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-164">Contiene tutti i messaggi di chat.</span><span class="sxs-lookup"><span data-stu-id="b096c-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-166">Contiene l'ultimo ID invite generato (e usato nella tabella tblPrincipalInvites) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="b096c-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-168">Contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="b096c-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-170">Contiene le preferenze del client utente (usate solo dai client legacy).</span><span class="sxs-lookup"><span data-stu-id="b096c-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-172">Contiene token temporanei per scopi di trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="b096c-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="b096c-173">Ogni volta che viene caricato o scaricato un file, il servizio chat persistente genera un token che il client usa per accedere al file Store del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="b096c-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="b096c-174">Supporto server</span><span class="sxs-lookup"><span data-stu-id="b096c-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b096c-175">Tabella</span><span class="sxs-lookup"><span data-stu-id="b096c-175">Table</span></span></th>
<th><span data-ttu-id="b096c-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b096c-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b096c-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-178">Contiene i server attivi nel pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b096c-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-180">Contiene il blocco dell'amministratore per eseguire alcuni comandi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b096c-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="b096c-181">La voce di revisione del sistema nella tabella tblSystemRevision viene incrementata dopo ogni rilascio del blocco.</span><span class="sxs-lookup"><span data-stu-id="b096c-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-183">Contiene la voce del numero di revisione usata (insieme alla tabella tblAdminLock) per ottenere la coerenza tra più server.</span><span class="sxs-lookup"><span data-stu-id="b096c-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b096c-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-185">Contiene connessioni peer-to-peer correnti tra servizi di chat persistenti.</span><span class="sxs-lookup"><span data-stu-id="b096c-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b096c-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b096c-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b096c-187">Contiene la configurazione del server di chat persistente non supportata.</span><span class="sxs-lookup"><span data-stu-id="b096c-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

