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
ms.openlocfilehash: da3069fdd039cb394308f3901ae9805b9023e15d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513883"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Elenco delle tabelle del server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Lo schema del database di chat persistente è costituito dalle tabelle seguenti.

<div>

## <a name="active-directory-sync"></a>Sincronizzazione di Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></p></td>
<td><p>Include i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti. Ogni riga corrisponde a un dominio di servizi di dominio Active Directory in cui il server Chat persistente sta monitorando attivamente le modifiche. (Solo i domini di Active Directory rilevanti per il server Chat persistente sono rappresentati in questa tabella).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></p></td>
<td><p>Contiene le modifiche apportate all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblADUpdates) utilizzate nel primo passaggio della sincronizzazione di Active Directory.</p>
<p>Le modifiche delle appartenenza sono archiviate e/o elaborate solo per i gruppi che sono elencati nella tabella tblPrincipal o che includono membri già elencati in tale tabella.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></p></td>
<td><p>Contiene le modifiche apportate ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblPrincipalMemberDifference) utilizzata nel primo passaggio della sincronizzazione di Active Directory.</p>
<p>Le modifiche apportate a Active Directory sono archiviate, elaborate o entrambe solo per le entità che sono già elencate nella tabella tabella tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></p></td>
<td><p>Include le appartenenze delle entità.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></p></td>
<td><p>Contiene le entità che devono essere aggiornate da Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></p></td>
<td><p>Contiene le affiliazioni che non è stato possibile aggiornare per qualche motivo, in genere a causa di errori di accesso di Active Directory.</p>
<p>Questa tabella è esclusivamente per scopi informativi. Il relativo contenuto non viene utilizzato.</p>
<p>Le entità di cui non è stato possibile aggiornare correttamente le affiliazioni sono contenute nella tabella tblPrincipalMeta e dispongono di un'altra possibilità di aggiornamento.</p></td>
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
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">PrincipalType in Lync Server 2013</a></p></td>
<td><p>Include i tipi di entità per classificare il contenuto della tabella tblPrincipal. Questa tabella è statica, viene configurata durante la creazione del database e non è soggetta a modifiche.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Tabella tblPrincipal in Lync Server 2013</a></p></td>
<td><p>Include tutte le entità, ovvero utenti, cartelle, gruppi e così via. Il server Chat persistente lo gestisce come elenco eterogeneo piano. Diverse colonne sono basate sul tipo di ogni entità.</p>
<p>La maggior parte di queste entità sono copie memorizzate nella cache degli oggetti archiviati in Active Directory. La creazione della copia memorizzata nella cache nella tabella principale di questi oggetti di Active Directory viene indicata come <em>provisioning</em>.</p>
<p>Alcune entità vengono create in modo più aggressivo rispetto ad altre e alcuni oggetti di Active Directory vengono ignorati del tutto.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></p></td>
<td><p>Contiene le affiliazioni principali che descrivono le appartenenze ai gruppi di sicurezza di Active Directory, ai contenitori di Active Directory e così via.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></p></td>
<td><p>Contiene il nodo della categoria, come gestito nel pannello di controllo di Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></p></td>
<td><p>Include i tipi di ruolo e gli insiemi di autorizzazioni associati. Questa tabella di ricerca è statica.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></p></td>
<td><p>Include gli ambiti assegnati ai nodi.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></p></td>
<td><p>Include i ruoli assegnati ai nodi.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></p></td>
<td><p>Include i componenti aggiuntivi registrati che possono essere associati ai nodi.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></p></td>
<td><p>Contiene solo gli &quot; &quot; attributi di visibilità e &quot; comportamento hardcoded &quot; che vengono utilizzati nella tabella tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Nella in Lync Server 2013</a></p></td>
<td><p>Contiene i valori degli &quot; attributi di visibilità hardcoded "e" dei comportamenti &quot; che vengono utilizzati nella tabella tblNode.</p></td>
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
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></p></td>
<td><p>Include inviti per tutti gli utenti di cui è stato eseguito il provisioning nel sistema per tutti i nodi con Auto Invite abilitato.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></p></td>
<td><p>Include tutti i messaggi di chat.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></p></td>
<td><p>Include l'ID dell'ultimo invito generato e usato nella tabella tblPrincipalInvites per ogni utente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">LastChatId in Lync Server 2013</a></p></td>
<td><p>Include l'ID dell'ultima chat generata e usata nella tabella tblChat per ogni utente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></p></td>
<td><p>Include le preferenze client degli utenti (usate solo dai client legacy).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></p></td>
<td><p>Include token temporanei per il trasferimento di file. Ogni volta che un file viene caricato o scaricato, il servizio chat persistente genera un token utilizzato dal client per accedere all'archivio file del servizio Web.</p></td>
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
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Tabella tblServerIdentity in Lync Server 2013</a></p></td>
<td><p>Contiene i server attivi nel pool di server Chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></p></td>
<td><p>Include il blocco amministratore per l'esecuzione di alcuni comandi dell'amministratore. La voce di revisione di sistema nella tabella tblSystemRevision viene incrementata dopo ogni rilascio del blocco.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></p></td>
<td><p>Include il numero di revisione usato insieme alla tabella tblAdminLock per garantire la coerenza tra più client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></p></td>
<td><p>Contiene le connessioni peer-to-peer correnti tra i servizi di chat persistente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></p></td>
<td><p>Contiene la configurazione non supportata del server Chat persistente.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

