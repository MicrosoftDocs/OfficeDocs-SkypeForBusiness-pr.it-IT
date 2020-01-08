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

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Elenco delle tabelle del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

Lo schema del database della chat persistente è costituito dalle tabelle seguenti.

<div>

## <a name="active-directory-sync"></a>Sincronizzazione di Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></p></td>
<td><p>Contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti. Ogni riga corrisponde a un dominio di servizi di dominio Active Directory che il server di chat persistente sta monitorando attivamente per le modifiche. In questa tabella sono rappresentati solo i domini di Active Directory rilevanti per il server di chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></p></td>
<td><p>Contiene le modifiche alle appartenenze ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dalle successive operazioni di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblADUpdates) che viene usata nel primo passaggio della sincronizzazione di Active Directory.</p>
<p>Le modifiche apportate all'appartenenza sono archiviate, elaborate o entrambe, solo per i gruppi elencati nella tabella tblPrincipal o che hanno già membri elencati.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></p></td>
<td><p>Contiene le modifiche apportate ai servizi di dominio Active Directory che non sono ancora state elaborate dalle successive operazioni di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblPrincipalMemberDifference) che viene usata nel primo passaggio di Active Directory Sync.</p>
<p>Le modifiche apportate a Active Directory vengono archiviate, elaborate o entrambe solo per le entità già elencate nella tabella tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></p></td>
<td><p>Contiene le appartenenze principali.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></p></td>
<td><p>Contiene le entità che devono essere aggiornate da Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></p></td>
<td><p>Contiene le affiliazioni che non è stato possibile aggiornare per qualche motivo, in genere a causa di errori di accesso a Active Directory.</p>
<p>Questa tabella è a scopo informativo. Il contenuto non viene usato.</p>
<p>Le entità con affiliazioni che non è stato possibile aggiornare correttamente vengono mantenute nella tabella tblPrincipalMeta e vengono fornite un'altra possibilità di essere aggiornate.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entità, affiliazioni, nodi, ambiti e ruoli


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></p></td>
<td><p>Contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal. Questa tabella è statica. La configurazione viene configurata durante la creazione di database e non cambia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></p></td>
<td><p>Contiene tutte le entità (utenti, cartelle, gruppi e così via). Il server di chat persistente lo gestisce come elenco di piatti eterogenei. Le varie colonne si basano sul tipo di ogni entità.</p>
<p>La maggior parte di queste entità sono copie memorizzate nella cache degli oggetti archiviati in Active Directory. La creazione della copia memorizzata nella cache nella tabella principale di questi oggetti Active Directory viene definita <em>provisioning</em>.</p>
<p>Alcune entità vengono create in modo più aggressivo rispetto ad altre e alcuni oggetti Active Directory vengono ignorati complessivamente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></p></td>
<td><p>Contiene le affiliazioni principali che descrivono l'appartenenza a gruppi di sicurezza di Active Directory, contenitori di Active Directory e così via.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></p></td>
<td><p>Contiene il nodo Category, come gestito nel pannello di controllo di Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></p></td>
<td><p>Contiene i tipi di ruolo e i set di autorizzazioni associati. Questa tabella di ricerca è statica.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></p></td>
<td><p>Contiene gli ambiti assegnati ai nodi.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></p></td>
<td><p>Contiene ruoli assegnati ai nodi.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></p></td>
<td><p>Contiene i componenti aggiuntivi registrati che possono essere associati ai nodi.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></p></td>
<td><p>Contiene solo gli attributi di &quot;visibilità&quot; e &quot;comportamento&quot; hardcoded usati nella tabella tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></p></td>
<td><p>Contiene i valori degli attributi di &quot;visibilità hardcoded "e" di&quot; comportamento usati nella tabella tblNode.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Inviti, chat e altro supporto client


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></p></td>
<td><p>Contiene invita per tutti gli utenti con provisioning nel sistema per tutti i nodi con l'invito automatico abilitato.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></p></td>
<td><p>Contiene tutti i messaggi di chat.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></p></td>
<td><p>Contiene l'ultimo ID invite generato (e usato nella tabella tblPrincipalInvites) per ogni utente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></p></td>
<td><p>Contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></p></td>
<td><p>Contiene le preferenze del client utente (usate solo dai client legacy).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></p></td>
<td><p>Contiene token temporanei per scopi di trasferimento di file. Ogni volta che viene caricato o scaricato un file, il servizio chat persistente genera un token che il client usa per accedere al file Store del servizio Web.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>Supporto server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></p></td>
<td><p>Contiene i server attivi nel pool del server di chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></p></td>
<td><p>Contiene il blocco dell'amministratore per eseguire alcuni comandi di amministratore. La voce di revisione del sistema nella tabella tblSystemRevision viene incrementata dopo ogni rilascio del blocco.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></p></td>
<td><p>Contiene la voce del numero di revisione usata (insieme alla tabella tblAdminLock) per ottenere la coerenza tra più server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></p></td>
<td><p>Contiene connessioni peer-to-peer correnti tra servizi di chat persistenti.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></p></td>
<td><p>Contiene la configurazione del server di chat persistente non supportata.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

