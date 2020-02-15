---
title: 'Lync Server 2013: gestione delle posizioni per i provider di servizi trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ffa9b16a2c582af2de990eab52b55c175121bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Per configurare Lync Server per l'individuazione automatica dei client all'interno di una rete, è necessario popolare il database del servizio informazioni percorso con una rete wiremap e pubblicare i percorsi oppure collegarsi a un database esterno che già contiene la corretta mapping. Come parte di questo processo, è necessario convalidare gli indirizzi civici dei percorsi con il provider di servizi E9-1-1. Per ulteriori informazioni, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

È possibile popolare il database del servizio informazioni percorso con un percorso di risposta di emergenza, che è costituito da un indirizzo civico e dall'indirizzo specifico all'interno di un edificio. Il **campo percorso del servizio informazioni** percorso, che corrisponde alla posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi). Tentare di includere, in tale lunghezza, gli elementi seguenti:

  - Un nome di facile comprensione che identifichi la posizione del chiamante del servizio di emergenza (911), per consentire agli addetti del servizio di emergenza di trovare immediatamente la posizione specifica quando si recano all'indirizzo. Questo nome di posizione può includere il numero di edificio, l'indicazione della scala, il numero del piano, il numero di porta e così via. Evitare nomi alternativi noti solo ai dipendenti, che potrebbero indirizzare gli addetti del servizio di emergenza nel posto sbagliato.

  - Un identificatore di posizione che consenta agli utenti di verificare facilmente che il proprio client Lync abbia selezionato la posizione corretta. Il client Lync concatena e visualizza automaticamente i campi **Location** e **City** rilevati nell'intestazione. Una buona procedura consiste nell'aggiungere l'indirizzo civico dell'edificio a ogni identificatore di posizione (ad esempio, "numero \<\>civico del primo piano"). Se non viene specificato l'indirizzo, un identificatore di posizione generico come "1° piano" potrebbe riferirsi a qualsiasi edificio della città.

  - Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola Near, ad esempio "Near 1st floor 1234".

<div>


> [!NOTE]  
> I percorsi aggiunti al database delle posizioni centrali non sono disponibili per il client finché non vengono pubblicati utilizzando un comando di Lync Server Management Shell e vengono replicati negli archivi locali del pool. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database delle posizioni da Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Nelle sezioni seguenti vengono illustrate le considerazioni che è necessario prendere in considerazione durante la compilazione e la gestione del database delle posizioni.

<div>

## <a name="populating-the-location-database"></a>Popolamento del database delle posizioni

Le domande seguenti possono essere utili per determinare come popolare il database delle posizioni.

  - **Valutare quale processo verrà utilizzato per popolare il database delle posizioni.**  
    Esaminare dove si trovano i dati e quali operazioni è necessario eseguire per convertirli nel formato richiesto dal database delle posizioni. Considerare inoltre se le posizioni verranno aggiunte singolarmente o in gruppo tramite un file CSV.

<!-- end list -->

  - **Valutare se si dispone di un database di terze parti contenente già un mapping di posizioni.**  
    Se si utilizza l'opzione servizio informazioni percorso secondario di Lync Server per la connessione a un database di terze parti, è possibile raggruppare e gestire percorsi tramite una piattaforma offline. Uno dei vantaggi di questo approccio è che le posizioni possono essere associate non solo a identificatori di rete, ma anche a un utente. Questo significa che il servizio informazioni percorso può restituire più indirizzi, provenienti dal servizio informazioni percorso secondario, a un client di Lync Server. L'utente può quindi scegliere la posizione più appropriata.
    
    Per l'integrazione con il servizio informazioni percorso, è necessario che il database di terze parti segua lo schema di richiesta/risposta percorso di Lync Server. Per informazioni dettagliate, vedere\["MS-\]E911WS: Web Service per la specifica del protocollo di <http://go.microsoft.com/fwlink/p/?linkid=213819>supporto di E911" all'indirizzo. Per informazioni dettagliate sulla distribuzione di un servizio informazioni percorso secondario, vedere [Configure a Secondary Location Information Service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sul popolamento del database delle posizioni, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Gestione del database delle posizioni

Dopo aver popolato il database delle posizioni, è necessario sviluppare una strategia per aggiornarlo in base alle modifiche di configurazione della rete. Le considerazioni seguenti possono essere utili per determinare come verrà gestito il database delle posizioni.

  - **Valutare come verrà aggiornato il database delle posizioni.**  
    Sono disponibili diversi scenari che richiedono un aggiornamento al database delle posizioni, tra cui l'aggiunta di WAP, il ricablaggio di Office (con l'assegnazione di diverse assegnazioni di switch) e l'espansione della subnet. Considerare se si prevede di aggiornare direttamente ogni singola posizione o di eseguire un aggiornamento in blocco delle posizioni mediante un file CSV.

<!-- end list -->

  - **Considerare se verrà utilizzata un'applicazione SNMP per creare una corrispondenza tra gli indirizzi MAC dei client Lync e gli identificatori di porte e commutatori,**  
    Se si utilizza un'applicazione SNMP, è necessario sviluppare un processo manuale per mantenere la coerenza a livello di informazioni su porte e chassis dei commutatori tra l'applicazione SNMP e il database delle posizioni. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni percorso non sarà in grado di restituire un percorso al client.

</div>

</div>

<span> </span>

</div>

</div>

</div>

