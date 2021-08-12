---
title: Componenti VoIP di Front End Server per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Informazioni sui componenti VoIP aziendale che si trovano nei Front End Server in Skype for Business Server, tra cui il servizio di traduzione e vari componenti di routing.
ms.openlocfilehash: 5df2937d0329796f634c5b4fac21b6921001d65bf3795589ce718ba08ecd9c36
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333118"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componenti VoIP di Front End Server per Skype for Business Server

Informazioni sui componenti VoIP aziendale che si trovano nei Front End Server in Skype for Business Server, tra cui il servizio di traduzione e vari componenti di routing.

I componenti VoIP presenti nei Front End Server sono i seguenti:

- Servizio di conversione

- Componente di routing in ingresso

- Componente di routing in uscita

- Componente di routing per Messaggistica unificata di Exchange

- Componente di routing tra cluster

- [Componente Mediation Server in Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Servizio di conversione

Il servizio di conversione è il componente server responsabile della conversione di un numero composto nel formato E.164 o in un altro formato, in base alle regole di normalizzazione definite dall'amministratore. Questo servizio può eseguire la conversione in formati diversi dal formato E.164 se nell'organizzazione viene utilizzato un sistema di numerazione privato oppure un gateway o un PBX che non supporta il formato E.164.

## <a name="inbound-routing-component"></a>Componente di routing in ingresso

Il componente di routing in ingresso gestisce le chiamate in ingresso tenendo generalmente conto delle preferenze specificate dagli utenti nei client di Enterprise Voice. Consente inoltre di utilizzare le funzionalità di chiamata ai delegati e di squillo simultaneo, se configurate dall'utente. Gli utenti possono ad esempio specificare se le chiamate senza risposta devono essere inoltrate o semplicemente registrate a scopo di notifica. Se l'inoltro di chiamata è abilitato, gli utenti possono specificare se le chiamate senza risposta devono essere inoltrate a un altro numero o a un server Messaggistica unificata di Exchange configurato per fornire il risponditore automatico. Il componente di routing in ingresso viene installato per impostazione predefinita in edizione Standard server e Front End Server.

## <a name="outbound-routing-component"></a>Componente di routing in uscita

Il componente di routing in uscita instrada le chiamate a destinazioni PBX o PSTN. Applica le regole di autorizzazione delle chiamate, come definito dal criterio vocale dell'utente, ai chiamanti e determina il gateway PSTN ottimale per il routing di ogni chiamata. Il componente routing in uscita viene installato per impostazione predefinita in edizione Standard server e Front End Server.

La logica di routing utilizzata dal componente di routing in uscita viene in buona parte configurata dagli amministratori di rete o di telefonia in base ai requisiti dell'organizzazione.

## <a name="exchange-um-routing-component"></a>Componente di routing per Messaggistica unificata di Exchange

Il Exchange di routing di messaggistica unificata gestisce il routing tra Skype for Business Server e i server che eseguono la messaggistica unificata di Exchange per integrare Skype for Business Server con le funzionalità di messaggistica unificata.

Il Exchange di routing di messaggistica unificata gestisce anche il reindirizzamento della posta vocale sulla rete PSTN se i Exchange messaggistica unificata non sono disponibili. Se sono disponibili utenti VoIP aziendale nei siti di succursale che non dispongono di un collegamento WAN resiliente a un sito centrale, il Survivable Branch Appliance distribuito nel sito di succursale garantisce la sopravvivenza della segreteria telefonica per gli utenti di succursale durante un'interruzione della rete WAN. Quando il collegamento WAN non è disponibile, Survivable Branch Appliance effettua le operazioni seguenti:

- Reinstrada le chiamate senza risposta sulla rete PSTN verso il server di Messaggistica unificata di Exchange nel sito centrale

- Consente a un utente di recuperare i messaggi di segreteria telefonica sulla rete PSTN

- Accoda le notifiche di chiamate senza risposta e quindi le carica nel server di Messaggistica unificata di Exchange quando viene ripristinato il collegamento WAN

Per abilitare il reindirizzamento della segreteria telefonica, è consigliabile che l'amministratore Exchange configurare Exchange messaggistica unificata Operatore automatico (AA) in modo che accetti solo i messaggi.

Per informazioni dettagliate su queste funzionalità, vedere rispettivamente [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) e [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency).

## <a name="intercluster-routing-component"></a>Componente di routing tra cluster

Il componente di routing Intercluster è responsabile del routing delle chiamate al pool di registrazione principale del chiamato. Se non è disponibile, il componente instrada la chiamata al pool di registrazione di backup del chiamato. Se i pool di registrazione principale e di backup del chiamato non sono raggiungibili sulla rete IP, il componente di routing tra cluster reinstraderà la chiamata tramite PSTN al numero di telefono dell'utente.

## <a name="other-front-end-server-components-required-for-voip"></a>Altri componenti di Front End Server necessari per VoIP

Altri componenti che risiedono nel Front End Server o nel Director che forniscono il supporto essenziale per VoIP, ma non sono essi stessi componenti VoIP, includono quanto segue:

- **Servizi utente.** Consente di eseguire la ricerca inversa nel numero di telefono di destinazione per ogni chiamata in arrivo e di associare tale numero all'URI SIP dell'utente di destinazione. Utilizzando queste informazioni, il componente di routing in ingresso distribuisce la chiamata agli endpoint SIP registrati dell'utente. Servizi utente è un componente di base in tutti i Front End Server e i Director.

- **User Replicator.** Estrae i numeri di telefono degli utenti da Servizi di dominio Active Directory e li scrive nelle tabelle del database RTC, dove sono disponibili per Servizi utente e il server della Rubrica. User Replicator è un componente di base in tutti i Front End Server.

- **Server della Rubrica.** Fornisce informazioni sull'elenco indirizzi globale da Servizi di dominio Active Directory Skype for Business Server client. Recupera inoltre le informazioni relative a utenti e contatti dal database RTC, le scrive nei file della Rubrica e quindi archivia i file in una cartella condivisa in cui vengono scaricati dai Skype for Business client. Il server della Rubrica scrive le informazioni nel database RTCAb, utilizzato dal servizio Address Book Web Query per rispondere alle query di ricerca degli utenti da Skype for Business mobile. Facoltativamente, normalizza i numeri di telefono degli utenti aziendali scritti nel database RTC allo scopo di effettuare il provisioning dei contatti utente in Skype for Business. Il servizio Rubrica viene installato per impostazione predefinita in tutti i Front End Server. Il servizio Query Web rubrica viene installato per impostazione predefinita con i servizi Web in ogni Front End Server.