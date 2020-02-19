---
title: 'Lync Server 2013: elenco delle tabelle del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d9fe9db5ad22a0d6ad2d68d0afdbd5b0969608
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="f3ec3-102">Elenco delle tabelle del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3ec3-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3ec3-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f3ec3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f3ec3-104">Lo schema del database di chat persistente è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="f3ec3-105">Sincronizzazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="f3ec3-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3ec3-106">tavolo</span><span class="sxs-lookup"><span data-stu-id="f3ec3-106">Table</span></span></th>
<th><span data-ttu-id="f3ec3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3ec3-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-109">Include i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="f3ec3-110">Ogni riga corrisponde a un dominio di servizi di dominio Active Directory in cui il server Chat persistente sta monitorando attivamente le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="f3ec3-111">(Solo i domini di Active Directory rilevanti per il server Chat persistente sono rappresentati in questa tabella).</span><span class="sxs-lookup"><span data-stu-id="f3ec3-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-113">Contiene le modifiche apportate all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblADUpdates) utilizzate nel primo passaggio della sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="f3ec3-114">Le modifiche delle appartenenza sono archiviate e/o elaborate solo per i gruppi che sono elencati nella tabella tblPrincipal o che includono membri già elencati in tale tabella.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-116">Contiene le modifiche apportate ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblPrincipalMemberDifference) utilizzata nel primo passaggio di Active Directory Sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="f3ec3-117">Le modifiche apportate a Active Directory sono archiviate, elaborate o entrambe solo per le entità che sono già elencate nella tabella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-119">Include le appartenenze delle entità.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-121">Contiene le entità che devono essere aggiornate da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-123">Contiene le affiliazioni che non è stato possibile aggiornare per qualche motivo, in genere a causa di errori di accesso di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="f3ec3-p102">Questa tabella è esclusivamente per scopi informativi. Il relativo contenuto non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="f3ec3-126">Le entità di cui non è stato possibile aggiornare correttamente le affiliazioni sono contenute nella tabella tblPrincipalMeta e dispongono di un'altra possibilità di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="f3ec3-127">Entità, affiliazioni, nodi, ambiti e ruoli</span><span class="sxs-lookup"><span data-stu-id="f3ec3-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3ec3-128">tavolo</span><span class="sxs-lookup"><span data-stu-id="f3ec3-128">Table</span></span></th>
<th><span data-ttu-id="f3ec3-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3ec3-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-130"><a href="lync-server-2013-tblprincipaltype.md">PrincipalType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-p103">Include i tipi di entità per classificare il contenuto della tabella tblPrincipal. Questa tabella è statica, viene configurata durante la creazione del database e non è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-134"><a href="lync-server-2013-tblprincipal.md">Tabella tblPrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-135">Include tutte le entità, ovvero utenti, cartelle, gruppi e così via.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="f3ec3-136">Il server Chat persistente lo gestisce come elenco eterogeneo piano.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="f3ec3-137">Diverse colonne sono basate sul tipo di ogni entità.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="f3ec3-138">La maggior parte di queste entità sono copie memorizzate nella cache degli oggetti archiviati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="f3ec3-139">La creazione della copia memorizzata nella cache nella tabella principale di questi oggetti di Active Directory viene indicata come <em>provisioning</em>.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="f3ec3-140">Alcune entità vengono create in modo più aggressivo rispetto ad altre e alcuni oggetti di Active Directory vengono ignorati del tutto.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-142">Contiene le affiliazioni principali che descrivono le appartenenze ai gruppi di sicurezza di Active Directory, ai contenitori di Active Directory e così via.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-144">Contiene il nodo della categoria, come gestito nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-146">Include i tipi di ruolo e gli insiemi di autorizzazioni associati.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="f3ec3-147">Questa tabella di ricerca è statica.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-149">Include gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-151">Include i ruoli assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-153">Include i componenti aggiuntivi registrati che possono essere associati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-155">Contiene solo gli attributi di &quot;visibilità&quot; e &quot;comportamento&quot; hardcoded che vengono utilizzati nella tabella tblNode.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-156"><a href="lync-server-2013-tblenumvalue.md">Nella in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-157">Contiene i valori degli attributi di &quot;visibilità hardcoded "e" dei&quot; comportamenti che vengono utilizzati nella tabella tblNode.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="f3ec3-158">Inviti, chat e altro supporto client</span><span class="sxs-lookup"><span data-stu-id="f3ec3-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3ec3-159">tavolo</span><span class="sxs-lookup"><span data-stu-id="f3ec3-159">Table</span></span></th>
<th><span data-ttu-id="f3ec3-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3ec3-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-162">Include inviti per tutti gli utenti di cui è stato eseguito il provisioning nel sistema per tutti i nodi con Auto Invite abilitato.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-164">Include tutti i messaggi di chat.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-166">Include l'ID dell'ultimo invito generato e usato nella tabella tblPrincipalInvites per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-167"><a href="lync-server-2013-tbllastchatid.md">LastChatId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-168">Include l'ID dell'ultima chat generata e usata nella tabella tblChat per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-170">Include le preferenze client degli utenti (usate solo dai client legacy).</span><span class="sxs-lookup"><span data-stu-id="f3ec3-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-172">Include token temporanei per il trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="f3ec3-173">Ogni volta che un file viene caricato o scaricato, il servizio chat persistente genera un token utilizzato dal client per accedere all'archivio file del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="f3ec3-174">Supporto server</span><span class="sxs-lookup"><span data-stu-id="f3ec3-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3ec3-175">tavolo</span><span class="sxs-lookup"><span data-stu-id="f3ec3-175">Table</span></span></th>
<th><span data-ttu-id="f3ec3-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3ec3-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-177"><a href="lync-server-2013-tblserveridentity.md">Tabella tblServerIdentity in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-178">Contiene i server attivi nel pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-p108">Include il blocco amministratore per l'esecuzione di alcuni comandi dell'amministratore. La voce di revisione di sistema nella tabella tblSystemRevision viene incrementata dopo ogni rilascio del blocco.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-183">Include il numero di revisione usato insieme alla tabella tblAdminLock per garantire la coerenza tra più client.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ec3-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-185">Contiene le connessioni peer-to-peer correnti tra i servizi di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ec3-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f3ec3-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3ec3-187">Contiene la configurazione non supportata del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

