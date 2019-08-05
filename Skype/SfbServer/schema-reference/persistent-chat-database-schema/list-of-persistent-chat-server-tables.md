---
title: Elenco delle tabelle del server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Lo schema del database della chat persistente è costituito dalle tabelle seguenti.
ms.openlocfilehash: 6a6c0bc2c2cc2d5e5ba59f9f636ed9cea2189bed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194713"
---
# <a name="list-of-persistent-chat-server-tables"></a>Elenco delle tabelle del server Chat persistente
 
Lo schema del database della chat persistente è costituito dalle tabelle seguenti.
  
## <a name="active-directory-sync"></a>Sincronizzazione di Active Directory

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti. Ogni riga corrisponde a un dominio di servizi di dominio Active Directory che il server di chat persistente sta monitorando attivamente per le modifiche. In questa tabella sono rappresentati solo i domini di Active Directory rilevanti per il server di chat persistente.  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contiene le modifiche alle appartenenze ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dalle successive operazioni di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblADUpdates) che viene usata nel primo passaggio della sincronizzazione di Active Directory.  <br/> Le modifiche apportate all'appartenenza sono archiviate, elaborate o entrambe, solo per i gruppi elencati nella tabella tblPrincipal o che hanno già membri elencati.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contiene le modifiche apportate ai servizi di dominio Active Directory che non sono ancora state elaborate dalle successive operazioni di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblPrincipalMemberDifference) che viene usata nel primo passaggio di Active Directory Sync.  <br/> Le modifiche apportate a Active Directory vengono archiviate, elaborate o entrambe solo per le entità già elencate nella tabella tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Contiene le appartenenze principali.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contiene le entità che devono essere aggiornate da Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contiene le affiliazioni che non è stato possibile aggiornare per qualche motivo, in genere a causa di errori di accesso a Active Directory.  <br/> Questa tabella è a scopo informativo. Il contenuto non viene usato.  <br/> Le entità con affiliazioni che non è stato possibile aggiornare correttamente vengono mantenute nella tabella tblPrincipalMeta e vengono fornite un'altra possibilità di essere aggiornate.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entità, affiliazioni, nodi, ambiti e ruoli

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal. Questa tabella è statica. La configurazione viene configurata durante la creazione di database e non cambia.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Contiene tutte le entità (utenti, cartelle, gruppi e così via). Il server di chat persistente lo gestisce come elenco di piatti eterogenei. Le varie colonne si basano sul tipo di ogni entità.  <br/> La maggior parte di queste entità sono copie memorizzate nella cache degli oggetti archiviati in Active Directory. La creazione della copia memorizzata nella cache nella tabella principale di questi oggetti Active Directory viene definita provisioning.  <br/> Alcune entità vengono create in modo più aggressivo rispetto ad altre e alcuni oggetti Active Directory vengono ignorati complessivamente.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contiene le affiliazioni principali che descrivono l'appartenenza a gruppi di sicurezza di Active Directory, contenitori di Active Directory e così via.  <br/> |
|[tblNode](tblnode.md) <br/> |Contiene il nodo Category, come gestito nel pannello di controllo.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Contiene i tipi di ruolo e i set di autorizzazioni associati. Questa tabella di ricerca è statica.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Contiene gli ambiti assegnati ai nodi.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Contiene ruoli assegnati ai nodi.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Contiene i componenti aggiuntivi registrati che possono essere associati ai nodi.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Contiene solo gli attributi "Visibility" e "Behavior" hardcoded usati nella tabella tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contiene i valori degli attributi "Visibility" e "Behavior" hardcoded usati nella tabella tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Inviti, chat e altro supporto client

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Contiene invita per tutti gli utenti con provisioning nel sistema per tutti i nodi con l'invito automatico abilitato.  <br/> |
|[tblChat](tblchat.md) <br/> |Contiene tutti i messaggi di chat.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Contiene l'ultimo ID invite generato (e usato nella tabella tblPrincipalInvites) per ogni utente.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Contiene le preferenze del client utente (usate solo dai client legacy).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Contiene token temporanei per scopi di trasferimento di file. Ogni volta che viene caricato o scaricato un file, il servizio chat persistente genera un token che il client usa per accedere al file Store del servizio Web.  <br/> |
   
## <a name="server-support"></a>Supporto server

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contiene i server attivi nel pool del server di chat persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Contiene il blocco dell'amministratore per eseguire alcuni comandi di amministratore. La voce di revisione del sistema nella tabella tblSystemRevision viene incrementata dopo ogni rilascio del blocco.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Contiene la voce del numero di revisione usata (insieme alla tabella tblAdminLock) per ottenere la coerenza tra più server.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contiene connessioni peer-to-peer correnti tra servizi di chat persistenti.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contiene la configurazione del server di chat persistente non supportata.  <br/> |
   

