---
title: 'Lync Server 2013: Componenti VoIP di front end server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0be06c357fd3b02b2a44f4ba8f4aebfaab99f609
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Componenti VoIP di front end server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

I componenti VoIP presenti nei front end server sono i seguenti:

  - Servizio di conversione

  - Componente di routing in ingresso

  - Componente di routing in uscita

  - Componente di routing per Messaggistica unificata di Exchange

  - Componente di routing tra cluster

  - [Componente Mediation Server in Lync Server 2013](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>Servizio di conversione

Il servizio di conversione è il componente server responsabile della conversione di un numero composto nel formato E.164 o in un altro formato, in base alle regole di normalizzazione definite dall'amministratore. Questo servizio può eseguire la conversione in formati diversi dal formato E.164 se nell'organizzazione viene utilizzato un sistema di numerazione privato oppure un gateway o un PBX che non supporta il formato E.164.

</div>

<div>

## <a name="inbound-routing-component"></a>Componente di routing in ingresso

Il componente di routing in ingresso gestisce le chiamate in ingresso tenendo generalmente conto delle preferenze specificate dagli utenti nei client di Enterprise Voice. Consente inoltre di utilizzare le funzionalità di chiamata ai delegati e di squillo simultaneo, se configurate dall'utente. Gli utenti possono ad esempio specificare se le chiamate senza risposta devono essere inoltrate o semplicemente registrate a scopo di notifica. Se l'inoltro di chiamata è abilitato, gli utenti possono specificare se le chiamate senza risposta devono essere inoltrate a un altro numero o a un server di messaggistica unificata di Exchange configurato per fornire il risponditore automatico. Il componente di routing in ingresso viene installato per impostazione predefinita in tutti i server Standard Edition e front end server.

</div>

<div>

## <a name="outbound-routing-component"></a>Componente di routing in uscita

Il componente di routing in uscita instrada le chiamate a destinazioni PBX o PSTN. Applica ai chiamanti le regole di autorizzazione per le chiamate, secondo quanto definito dal criterio vocale dell'utente, e determina il gateway PSTN ottimale per il routing di ogni chiamata. Il componente di routing in uscita viene installato per impostazione predefinita in tutti i server Standard Edition e front end server.

La logica di routing utilizzata dal componente di routing in uscita viene in buona parte configurata dagli amministratori di rete o di telefonia in base ai requisiti dell'organizzazione.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Componente di routing per Messaggistica unificata di Exchange

Il componente di routing della messaggistica unificata di Exchange gestisce il routing tra Lync Server e i server che eseguono la messaggistica unificata di Exchange, per integrare Lync Server con le funzionalità di messaggistica unificata.

Il componente di routing della messaggistica unificata di Exchange gestisce anche il reinstradamento della segreteria telefonica tramite la rete PSTN se i server Messaggistica unificata di Exchange Se si dispone di utenti di VoIP aziendale nei siti di succursale che non dispongono di un collegamento WAN resiliente a un sito centrale, il Survivable Branch Appliance distribuito nel sito di succursale fornisce la sopravvivenza dei messaggi vocali per gli utenti di succursale durante un'interruzione della rete WAN. Quando il collegamento WAN non è disponibile, Survivable Branch Appliance effettua le operazioni seguenti:

  - Reinstrada le chiamate senza risposta sulla rete PSTN verso il server di Messaggistica unificata di Exchange nel sito centrale

  - Consente a un utente di recuperare i messaggi di segreteria telefonica sulla rete PSTN

  - Accoda le notifiche di chiamate senza risposta e quindi le carica nel server di Messaggistica unificata di Exchange quando viene ripristinato il collegamento WAN

Per abilitare il rerouting della segreteria telefonica, è consigliabile che l'amministratore di Exchange configuri l'operatore automatico di messaggistica unificata di Exchange per accettare solo i messaggi.

Per informazioni dettagliate su queste funzionalità, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [pianificazione della resilienza di VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), rispettivamente.

</div>

<div>

## <a name="intercluster-routing-component"></a>Componente di routing tra cluster

Il componente di routing tra cluster è responsabile del routing delle chiamate al pool di registrazione principale del destinatario della chiamata. Se il pool non è disponibile, il componente instrada la chiamata al pool di registrazione di backup del destinatario della chiamata. Se i pool di registrazione principale e di backup del destinatario della chiamata non sono raggiungibili sulla rete IP, il componente di routing tra cluster reinstrada la chiamata sulla rete PSTN al numero di telefono dell'utente.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Altri componenti di Front End Server necessari per VoIP

Gli altri componenti che risiedono nel front end server o nel Director che forniscono un supporto essenziale per VoIP, ma non sono propri componenti VoIP, includono quanto segue:

  - **Servizi utente.** Consente di eseguire la ricerca inversa nel numero di telefono di destinazione per ogni chiamata in arrivo e di associare tale numero all'URI SIP dell'utente di destinazione. Queste informazioni vengono usate dal componente di routing in ingresso per distribuire la chiamata agli endpoint SIP registrati dell'utente. Servizi utente è un componente di base di tutti i Front End Server e direttori.

  - **User Replicator.** Estrae i numeri di telefono degli utenti da servizi di dominio Active Directory e li scrive nelle tabelle del database RTC, in cui sono disponibili per i servizi utente e per il server della Rubrica. User Replicator è un componente di base di tutti i Front End Server.

  - **Server della Rubrica.** Fornisce informazioni sull'elenco indirizzi globale da servizi di dominio Active Directory ai client di Lync Server. Vengono inoltre recuperate le informazioni relative a utenti e contatti dal database RTC, vengono scritte le informazioni nei file della Rubrica e quindi i file vengono archiviati in una cartella condivisa in cui vengono scaricati dai client Lync. Il server della Rubrica scrive le informazioni nel database di RTCAb, che viene utilizzato dal servizio di query Web della Rubrica per rispondere alle query di ricerca degli utenti da Microsoft Lync 2010 mobile. Facoltativamente normalizza i numeri di telefono degli utenti dell'organizzazione scritti nel database RTC allo scopo di provisioning dei contatti utente in Lync. Il servizio Rubrica è installato per impostazione predefinita in tutti i Front End Server. Il servizio query Web della Rubrica viene installato per impostazione predefinita con i servizi Web in ogni Front End Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

