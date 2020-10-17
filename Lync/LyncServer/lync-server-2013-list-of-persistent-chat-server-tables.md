---
title: 'Lync Server 2013: elenco delle tabelle del server Chat persistente'
description: 'Lync Server 2013: elenco delle tabelle del server Chat persistente.'
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
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550052"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="d1912-103">Elenco delle tabelle del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1912-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1912-104">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d1912-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d1912-105">Lo schema del database di chat persistente è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="d1912-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="d1912-106">Sincronizzazione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="d1912-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1912-107">tavolo</span><span class="sxs-lookup"><span data-stu-id="d1912-107">Table</span></span></th>
<th><span data-ttu-id="d1912-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1912-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1912-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-110">Include i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="d1912-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="d1912-111">Ogni riga corrisponde a un dominio di servizi di dominio Active Directory in cui il server Chat persistente sta monitorando attivamente le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d1912-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="d1912-112">(Solo i domini di Active Directory rilevanti per il server Chat persistente sono rappresentati in questa tabella).</span><span class="sxs-lookup"><span data-stu-id="d1912-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-114">Contiene le modifiche apportate all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblADUpdates) utilizzate nel primo passaggio della sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1912-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="d1912-115">Le modifiche delle appartenenza sono archiviate e/o elaborate solo per i gruppi che sono elencati nella tabella tblPrincipal o che includono membri già elencati in tale tabella.</span><span class="sxs-lookup"><span data-stu-id="d1912-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-117">Contiene le modifiche apportate ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblPrincipalMemberDifference) utilizzata nel primo passaggio della sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1912-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="d1912-118">Le modifiche apportate a Active Directory sono archiviate, elaborate o entrambe solo per le entità che sono già elencate nella tabella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d1912-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-120">Include le appartenenze delle entità.</span><span class="sxs-lookup"><span data-stu-id="d1912-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-122">Contiene le entità che devono essere aggiornate da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1912-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-124">Contiene le affiliazioni che non è stato possibile aggiornare per qualche motivo, in genere a causa di errori di accesso di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1912-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="d1912-p102">Questa tabella è esclusivamente per scopi informativi. Il relativo contenuto non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d1912-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="d1912-127">Le entità di cui non è stato possibile aggiornare correttamente le affiliazioni sono contenute nella tabella tblPrincipalMeta e dispongono di un'altra possibilità di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d1912-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="d1912-128">Entità, affiliazioni, nodi, ambiti e ruoli</span><span class="sxs-lookup"><span data-stu-id="d1912-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1912-129">tavolo</span><span class="sxs-lookup"><span data-stu-id="d1912-129">Table</span></span></th>
<th><span data-ttu-id="d1912-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1912-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1912-131"><a href="lync-server-2013-tblprincipaltype.md">PrincipalType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-p103">Include i tipi di entità per classificare il contenuto della tabella tblPrincipal. Questa tabella è statica, viene configurata durante la creazione del database e non è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="d1912-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-135"><a href="lync-server-2013-tblprincipal.md">Tabella tblPrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-136">Include tutte le entità, ovvero utenti, cartelle, gruppi e così via.</span><span class="sxs-lookup"><span data-stu-id="d1912-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="d1912-137">Il server Chat persistente lo gestisce come elenco eterogeneo piano.</span><span class="sxs-lookup"><span data-stu-id="d1912-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="d1912-138">Diverse colonne sono basate sul tipo di ogni entità.</span><span class="sxs-lookup"><span data-stu-id="d1912-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="d1912-139">La maggior parte di queste entità sono copie memorizzate nella cache degli oggetti archiviati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1912-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="d1912-140">La creazione della copia memorizzata nella cache nella tabella principale di questi oggetti di Active Directory viene indicata come <em>provisioning</em>.</span><span class="sxs-lookup"><span data-stu-id="d1912-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="d1912-141">Alcune entità vengono create in modo più aggressivo rispetto ad altre e alcuni oggetti di Active Directory vengono ignorati del tutto.</span><span class="sxs-lookup"><span data-stu-id="d1912-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-143">Contiene le affiliazioni principali che descrivono le appartenenze ai gruppi di sicurezza di Active Directory, ai contenitori di Active Directory e così via.</span><span class="sxs-lookup"><span data-stu-id="d1912-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-145">Contiene il nodo della categoria, come gestito nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1912-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-147">Include i tipi di ruolo e gli insiemi di autorizzazioni associati.</span><span class="sxs-lookup"><span data-stu-id="d1912-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="d1912-148">Questa tabella di ricerca è statica.</span><span class="sxs-lookup"><span data-stu-id="d1912-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-150">Include gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="d1912-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-152">Include i ruoli assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="d1912-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-154">Include i componenti aggiuntivi registrati che possono essere associati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="d1912-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-156">Contiene solo gli &quot; &quot; attributi di visibilità e &quot; comportamento hardcoded &quot; che vengono utilizzati nella tabella tblNode.</span><span class="sxs-lookup"><span data-stu-id="d1912-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-157"><a href="lync-server-2013-tblenumvalue.md">Nella in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-158">Contiene i valori degli &quot; attributi di visibilità hardcoded "e" dei comportamenti &quot; che vengono utilizzati nella tabella tblNode.</span><span class="sxs-lookup"><span data-stu-id="d1912-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="d1912-159">Inviti, chat e altro supporto client</span><span class="sxs-lookup"><span data-stu-id="d1912-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1912-160">tavolo</span><span class="sxs-lookup"><span data-stu-id="d1912-160">Table</span></span></th>
<th><span data-ttu-id="d1912-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1912-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1912-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-163">Include inviti per tutti gli utenti di cui è stato eseguito il provisioning nel sistema per tutti i nodi con Auto Invite abilitato.</span><span class="sxs-lookup"><span data-stu-id="d1912-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-165">Include tutti i messaggi di chat.</span><span class="sxs-lookup"><span data-stu-id="d1912-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-167">Include l'ID dell'ultimo invito generato e usato nella tabella tblPrincipalInvites per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="d1912-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-168"><a href="lync-server-2013-tbllastchatid.md">LastChatId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-169">Include l'ID dell'ultima chat generata e usata nella tabella tblChat per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="d1912-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-171">Include le preferenze client degli utenti (usate solo dai client legacy).</span><span class="sxs-lookup"><span data-stu-id="d1912-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-173">Include token temporanei per il trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="d1912-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="d1912-174">Ogni volta che un file viene caricato o scaricato, il servizio chat persistente genera un token utilizzato dal client per accedere all'archivio file del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="d1912-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="d1912-175">Supporto server</span><span class="sxs-lookup"><span data-stu-id="d1912-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1912-176">tavolo</span><span class="sxs-lookup"><span data-stu-id="d1912-176">Table</span></span></th>
<th><span data-ttu-id="d1912-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1912-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1912-178"><a href="lync-server-2013-tblserveridentity.md">Tabella tblServerIdentity in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-179">Contiene i server attivi nel pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1912-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-p108">Include il blocco amministratore per l'esecuzione di alcuni comandi dell'amministratore. La voce di revisione di sistema nella tabella tblSystemRevision viene incrementata dopo ogni rilascio del blocco.</span><span class="sxs-lookup"><span data-stu-id="d1912-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-184">Include il numero di revisione usato insieme alla tabella tblAdminLock per garantire la coerenza tra più client.</span><span class="sxs-lookup"><span data-stu-id="d1912-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1912-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-186">Contiene le connessioni peer-to-peer correnti tra i servizi di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1912-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1912-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d1912-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d1912-188">Contiene la configurazione non supportata del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d1912-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

