---
title: 'Lync Server 2013: gestione delle posizioni per i provider di servizi trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba237ae4e984169a354339ce0222dfd58f324c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Per configurare Lync Server in modo da individuare automaticamente i client all'interno di una rete, è necessario popolare il database del servizio informazioni sulla posizione con una rete wiremap e pubblicare le posizioni oppure creare un collegamento a un database esterno che contiene già il corretto mapping. Nell'ambito di questo processo devi convalidare gli indirizzi civici dei percorsi con il provider di servizi E9-1-1. Per informazioni dettagliate, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

Il database del servizio informazioni sulla posizione viene compilato con un percorso di risposta di emergenza (elfi), che è costituito da un indirizzo civico e dall'indirizzo specifico all'interno di un edificio. Il campo **percorso** del servizio informazioni posizione, ovvero la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi). In tale lunghezza limitata, provare a includere le operazioni seguenti:

  - Un nome di facile comprensione che identifica la posizione del chiamante di 911 per evitare che i soccorritori di emergenza trovino la posizione specifica subito quando arrivano all'indirizzo civico. Questo nome di posizione può includere un numero di edificio, un numero di piano, un designatore alare, un numero di camera e così via. Evitare i soprannomi noti solo ai dipendenti, in modo che i soccorritori di emergenza possano accedere alla posizione errata.

  - Un identificatore di posizione che consente agli utenti di vedere facilmente che il client Lync ha rilevato la posizione corretta. Il client Lync concatena automaticamente e visualizza la **posizione** e i campi della **città** individuati nella relativa intestazione. Una buona procedura consiste nell'aggiungere l'indirizzo di strada dell'edificio a ogni identificatore di posizione, ad esempio "numero \<\>civico 1 ° piano". Senza l'indirizzo stradale, un identificatore di posizione generico come "primo piano" può essere applicato a qualsiasi edificio della città.

  - Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola Near, ad esempio "near 1 ° piano 1234".

<div>


> [!NOTE]  
> I percorsi aggiunti al database della posizione centrale non sono disponibili per il client finché non vengono pubblicati usando un comando Lync Server Management Shell e vengono replicati negli archivi locali del pool. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database della posizione da Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Nelle sezioni seguenti vengono illustrate le considerazioni che è necessario tenere in considerazione durante la compilazione e la gestione del database della posizione.

<div>

## <a name="populating-the-location-database"></a>Popolamento del database della posizione

Le domande seguenti consentono di determinare come popolare il database della posizione.

  - **Quale processo verrà usato per popolare il database della posizione?**  
    Dove sono i dati e quali sono i passaggi da eseguire per convertire i dati nel formato richiesto dal database della posizione? Si aggiungono percorsi singolarmente o in blocco usando un file CSV?

<!-- end list -->

  - **Si dispone di un database di terze parti che contiene già una mappatura delle posizioni?**  
    Se si usa l'opzione del servizio informazioni posizione secondaria di Lync Server per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni usando una piattaforma offline. Un vantaggio per questo approccio è che, oltre ad associare le posizioni agli identificatori di rete, è possibile associare le posizioni a un utente. Ciò significa che il servizio informazioni sulla posizione può restituire più indirizzi, provenienti dal servizio informazioni posizione secondaria, a un client Lync Server. L'utente può quindi scegliere la posizione più appropriata.
    
    Per l'integrazione con il servizio informazioni sulla posizione, il database di terze parti deve seguire lo schema di richiesta/risposta della posizione del server Lync. Per informazioni dettagliate, vedere\["MS-\]E911WS: Web Service for E911 support Protocol Specification" <http://go.microsoft.com/fwlink/p/?linkid=213819>at. Per informazioni dettagliate sulla distribuzione di un servizio di informazioni sulla posizione secondaria, vedere [configurare un servizio informazioni sulla posizione secondaria in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sulla compilazione del database della posizione, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Manutenzione del database della posizione

Dopo aver popolato il database della posizione, è necessario sviluppare una strategia per l'aggiornamento del database durante la modifica della configurazione della rete. Le domande seguenti consentono di determinare come gestire il database della posizione.

  - **Come si aggiorna il database della posizione?**  
    Sono disponibili diversi scenari che richiedono un aggiornamento per il database della posizione, tra cui l'aggiunta di WAP, il ricablaggio di Office (con le diverse assegnazioni degli switch) e l'espansione della subnet. Si aggiorna direttamente ogni singola posizione o si esegue un aggiornamento in blocco di tutte le posizioni usando un file CSV?

<!-- end list -->

  - **Si utilizzerà un'applicazione SNMP per corrispondere agli indirizzi MAC client di Lync alla porta e agli identificatori di switch?**  
    Se si usa un'applicazione SNMP, è necessario sviluppare un processo manuale che contenga la coerenza tra l'applicazione SNMP e il database della posizione e le informazioni sulla porta. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni sulla posizione non sarà in grado di restituire una posizione al client.

</div>

</div>

<span> </span>

</div>

</div>

</div>

