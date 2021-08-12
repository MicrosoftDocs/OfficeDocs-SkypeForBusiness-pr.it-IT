---
title: Elenco di tabelle del server Chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Lo schema del database di Persistent Chat è costituito dalle tabelle seguenti.
ms.openlocfilehash: bc7189eac8e8fbd42cdaa5786b82d5652c616a69ae3fc4fc180c189416a94468
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280939"
---
# <a name="list-of-persistent-chat-server-tables"></a>Elenco di tabelle del server Chat persistente
 
Lo schema del database di Persistent Chat è costituito dalle tabelle seguenti.
  
## <a name="active-directory-sync"></a>Sincronizzazione di Active Directory

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Include i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti. Ogni riga corrisponde a un dominio di Servizi di dominio Active Directory che il server Chat persistente sta monitorando attivamente per le modifiche. In questa tabella sono rappresentati solo i domini di Active Directory rilevanti per il server Chat persistente.  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Contiene le modifiche di appartenenza ai gruppi (sia membri aggiunti che rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblADUpdates) utilizzate nel primo passaggio di sincronizzazione di Active Directory.  <br/> Le modifiche delle appartenenza sono archiviate e/o elaborate solo per i gruppi che sono elencati nella tabella tblPrincipal o che includono membri già elencati in tale tabella.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Contiene le modifiche apportate a Servizi di dominio Active Directory che non sono state ancora elaborate dai passaggi successivi di sincronizzazione di Active Directory ed è una delle tabelle temporanee (insieme alla tabella tblPrincipalMemberDifference) utilizzate nel primo passaggio di sincronizzazione di Active Directory.  <br/> Le modifiche ad Active Directory vengono archiviate, elaborate o entrambe solo per le entità già elencate nella tabella tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Include le appartenenze delle entità.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Contiene le entità che devono essere aggiornate da Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Contiene affiliazioni che non è stato possibile aggiornare per qualche motivo, in genere a causa di errori di accesso ad Active Directory.  <br/> Questa tabella è esclusivamente per scopi informativi. Il relativo contenuto non viene utilizzato.  <br/> Le entità di cui non è stato possibile aggiornare correttamente le affiliazioni sono contenute nella tabella tblPrincipalMeta e dispongono di un'altra possibilità di aggiornamento.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Entità, affiliazioni, nodi, ambiti e ruoli

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Include i tipi di entità per classificare il contenuto della tabella tblPrincipal. Questa tabella è statica, viene configurata durante la creazione del database e non è soggetta a modifiche.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Include tutte le entità, ovvero utenti, cartelle, gruppi e così via. Il server Chat persistente gestisce questa operazione come un elenco eterogeneo semplice. Diverse colonne sono basate sul tipo di ogni entità.  <br/> La maggior parte di queste entità sono copie memorizzate nella cache di oggetti archiviati in Active Directory. La creazione della copia memorizzata nella cache nella tabella Principal di questi oggetti di Active Directory viene definita provisioning.  <br/> Alcune entità vengono create in modo più aggressivo rispetto ad altre e alcuni oggetti di Active Directory vengono ignorati del tutto.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Contiene affiliazioni principali che descrivono le appartenenze ai gruppi di sicurezza di Active Directory, ai contenitori di Active Directory e così via.  <br/> |
|[tblNode](tblnode.md) <br/> |Contiene il nodo di categoria, come gestito nel pannello di controllo.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Include i tipi di ruolo e gli insiemi di autorizzazioni associati. Questa tabella di ricerca è statica.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Include gli ambiti assegnati ai nodi.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Include i ruoli assegnati ai nodi.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Include i componenti aggiuntivi registrati che possono essere associati ai nodi.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Include solo gli attributi hardcoded "Visibility" e "Behavior" usati nella tabella tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Contiene i valori degli attributi hardcoded "Visibility" e "Behavior" utilizzati nella tabella tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Inviti, chat e altro supporto client

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Include inviti per tutti gli utenti di cui è stato eseguito il provisioning nel sistema per tutti i nodi con Auto Invite abilitato.  <br/> |
|[tblChat](tblchat.md) <br/> |Include tutti i messaggi di chat.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Include l'ID dell'ultimo invito generato e usato nella tabella tblPrincipalInvites per ogni utente.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Include l'ID dell'ultima chat generata e usata nella tabella tblChat per ogni utente.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Include le preferenze client degli utenti (usate solo dai client legacy).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Include token temporanei per il trasferimento di file. Ogni volta che un file viene caricato o scaricato, il servizio Persistent Chat genera un token utilizzato dal client per accedere all'archivio file del servizio Web.  <br/> |
   
## <a name="server-support"></a>Supporto server

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Contiene i server attivi nel pool di server Chat persistente.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Include il blocco amministratore per l'esecuzione di alcuni comandi dell'amministratore. La voce di revisione di sistema nella tabella tblSystemRevision viene incrementata dopo ogni rilascio del blocco.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Include il numero di revisione usato insieme alla tabella tblAdminLock per garantire la coerenza tra più client.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Contiene le connessioni peer-to-peer correnti tra i servizi Chat persistente.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Contiene la configurazione del server Chat persistente non supportata.  <br/> |
   

