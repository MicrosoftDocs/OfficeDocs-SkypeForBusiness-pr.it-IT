---
title: Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-09-26_

Un'applicazione server MSPL (Microsoft SIP Processing Language) è un'applicazione di sola scrittura che usa un linguaggio di scripting anziché l'API Microsoft Lync 2010. MSPL offre un controllo più granulare sui comportamenti di filtro e proxy, oltre a una funzionalità per l'invio di messaggi specifici alle applicazioni SIP basate sulle transazioni. MSPL viene usato in modo specifico per filtrare e instradare i messaggi SIP. Le applicazioni MSPL vengono eseguite nello stesso processo del modulo UserServices, mentre un programma basato sull'API Lync 2010 viene eseguito in un processo separato.

È possibile usare la pagina dell' **applicazione server** nel gruppo **topologia** del pannello di controllo di Lync Server per visualizzare un elenco di applicazioni server MSPL eseguite nei server front-end nell'ambiente Lync Server 2013. L'elenco Mostra gli script disponibili per ogni pool, nonché se sono abilitati o critici. Gli script vengono eseguiti nell'ordine in cui sono elencati.

Questi script includono i seguenti:

  - ClientVersionFilter fornisce all'amministratore un modo per specificare la versione dei client supportati da un pool. Il filtro della versione client controlla la versione client e può impedire al client di eseguire l'accesso o presentare l'utente con un messaggio che indica che sta usando un client non supportato. Il filtro della versione client può anche essere configurato per visualizzare un messaggio per l'utente che contiene l'URL dell'ultima versione scaricabile del client.

  - TranslationService converte un numero che un utente compone in un numero E. 164 in base alle regole di normalizzazione definite dall'amministratore. Per informazioni dettagliate, vedere [regole di traduzione in Lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation impone la convalida della Federazione a livello di tenant per i messaggi in arrivo e tra tenant provenienti da distribuzioni esterne.

  - UserServices è il componente di registrazione, presenza e conferenza SIP di un server front-end. Offre funzionalità di messaggistica istantanea, presenza e conferenza strettamente integrate basate sul proxy SIP.

  - InterClusterRouting è responsabile per il routing delle chiamate al pool di registrar principale del destinatario. Per informazioni dettagliate, vedere [componenti VoIP di front end server per Lync server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (Intelligent IM Filter) blocca i messaggi che contengono URL selezionabili o che tentano di avviare i trasferimenti di file. IIMFilter controlla anche la versione client per conto del server. IIMFilter influisce sui trasferimenti di file avviati tramite Lync Server o Communicator. Per impostazione predefinita, i collegamenti selezionabili vengono disabilitati aggiungendo un carattere di sottolineatura prima del primo carattere del collegamento. Un amministratore può modificare questo comportamento in modo che il collegamento sia bloccato, in questo caso i messaggi che contengono URL selezionabili o che tentano di avviare un trasferimento di file vengono bloccati dal server per raggiungere le destinazioni desiderate. IIMFilter è installato in tutti i server che utilizzano Lync Server eccetto i server proxy e i server di archiviazione.

  - UserPinService viene usato per verificare i pin (User Personal Identification Numbers) per i servizi di conferenza telefonica con accesso esterno.

  - DefaultRouting è l'applicazione di routing predefinita per i server che utilizzano Lync Server. È abilitata per impostazione predefinita. L'applicazione di routing è installata in tutti i server Standard Edition e Enterprise Edition.

  - ExumRouting instrada le chiamate alla messaggistica unificata di Exchange Server. ExumRouting determina il server di messaggistica unificata di Exchange appropriato per instradare la chiamata quando viene depositato un nuovo messaggio di segreteria telefonica. ExumRouting gestisce anche altri aspetti di integrazione della messaggistica unificata di Exchange, incluso il routing per l'operatore automatico e l'accesso sottoscrittore.

  - OutboundRouting determina il gateway che instrada una chiamata a un numero di telefono in base al numero selezionato e all'autorizzazione di chiamata dell'utente. OutboundRouting gestisce anche il reinstradamento delle chiamate se un gateway non è in grado di elaborare una chiamata.

  - QoEAgent riceve i report di dati QoE (Quality of Experience) dagli endpoint tramite le richieste di servizio SIP e invia i dati alla coda di destinazione nel server di monitoraggio o a utenti di terze parti che usano HTTP POST. Per informazioni dettagliate, vedere [distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation impone la convalida della Federazione a livello di tenant per i messaggi che vanno a una distribuzione esterna di destinazione.

  - AcpRouting proxy invita le richieste destinate al provider di servizi di audioconferenza al gateway del provider di servizi di audioconferenza.

Gli script eseguiti in Edge Server includono i seguenti:

  - IIMFilter

  - OptionsHandler risponde alle richieste di opzioni in arrivo con **200 OK** se la richiesta è destinata al server corrente. Viene usato per la convalida della topologia.

<div>

## <a name="see-also"></a>Vedere anche


[Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Contrassegnare un'applicazione MSPL (Microsoft SIP Processing Language) come critica o non critica in Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

