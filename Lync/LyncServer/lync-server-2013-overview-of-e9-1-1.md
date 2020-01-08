---
title: 'Lync Server 2013: Panoramica dei servizi di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Panoramica dei servizi di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Microsoft Lync Server 2013 supporta le chiamate avanzate 9-1-1 (E9-1-1) dai client Lync e dai dispositivi Lync Phone Edition. Quando si configura Lync Server per E9-1-1, le chiamate di emergenza effettuate da Lync 2013 o Lync Phone Edition includono le informazioni sulla posizione di risposta alle emergenze dal database del servizio informazioni sulla posizione. Posizioni ERL è costituito da indirizzi civici (ovvero Street) e altre informazioni utili per identificare una posizione più precisa negli edifici di Office e in altre strutture multitenant. Quando un utente effettua una chiamata di emergenza, Lync Server instrada l'audio della chiamata, insieme alla posizione e alle informazioni di callback, tramite un Mediation Server a un provider di servizi E9-1-1. Il provider di servizi E9-1-1 USA l'indirizzo civico del chiamante per instradare la chiamata al punto di PSAP (Public Safety Answering Point) che serve la posizione del chiamante e invia lungo una chiave di query del servizio di emergenza (ESQK) che PSAP USA per cercare gli Elfi del chiamante.

Lync Server supporta due metodi per il routing delle chiamate di emergenza a un provider di servizi E9-1-1:

  - Connessione trunk SIP (Session Initiation Protocol) a un provider di servizi E9-1-1 qualificato

  - Un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone)

Quando si usa un provider di servizi E9-1-1 trunk SIP, è possibile aggiungere posizioni ERL al database del servizio informazioni sulla posizione e quindi convalidare le posizioni in base a una guida all'indirizzo Master Street (stradario) gestita dal provider di servizi E9-1-1. Se un provider di servizi E9-1-1 riceve una chiamata che non ha informazioni sulla posizione o ha una posizione che non è stata convalidata rispetto a stradario, il provider di servizi E9-1-1 instrada la chiamata a un centro di risposta alle chiamate di emergenza nazionale/regionale (ECRC), con personale specializzato che ottiene verbalmente la posizione del chiamante, se possibile, e instrada manualmente la chiamata al PSAP appropriato. Alcuni provider di servizi E9-1-1 del trunk SIP forniscono anche ai clienti un numero di chiamate PSTN Direct inwarding (DID) per il ECRC, che fornisce un mezzo alternativo per il routing delle telefonate di 9-1-1, se il trunk SIP non riesce per qualsiasi motivo.

A differenza del TDM (Time Division Multiplexing) e dei telefoni PBX (Private Branch Exchange) basati su IP, che hanno posizioni fisse, un endpoint Lync può essere molto mobile. Quando si distribuisce la funzionalità E9-1-1, Lync Server garantisce che non importa dove si trova un chiamante, la chiamata di emergenza può essere instradata al PSAP che serve la posizione del chiamante. Ad esempio, se l'ufficio principale di un utente si trova a Redmond, Washington, ma l'utente inserisce una chiamata di emergenza da un computer in una filiale di Wichita, Kansas, il trunk SIP o il provider di servizi E9-1-1 Basato su PSTN instradano la chiamata a PSAP in Wichita , non al PSAP di Redmond.

Quando si usa un gateway ELIN, si aggiunge anche posizioni ERL al database del servizio informazioni sulla posizione, ma si include anche un numero ELIN per ogni posizione. Il numero ELIN diventa il numero delle chiamate di emergenza durante la chiamata di emergenza. Devi quindi verificare che il gestore PSTN carichi i dati ELIN nel database ALI (Automatic Location Identification).

<div>


> [!NOTE]  
> I dispositivi analogici connessi a Lync non possono ricevere informazioni sulla posizione dal servizio informazioni sulla posizione o trasmettere il percorso al provider di servizi E9-1-1. Se si usa l'opzione del provider di servizi E9-1-1 SIP trunk ed è necessario supportare E9-1-1 da telefoni analogici, sono disponibili due opzioni: 
> <UL>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opzione&nbsp;tradizionale&nbsp;PS-Ali se si dispone di gateway PSTN locali in ogni sito in cui sono distribuiti telefoni analogici e ogni telefono analogico ha un servizio, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con un provider di servizi di switch privato/identificazione automatica della posizione (PS-Ali). In questo caso, devi configurare i criteri vocali di Lync appositamente predisposti e assegnarli agli oggetti contatto del dispositivo analogico in modo che le chiamate E9-1-1 da questi telefoni vengano indirizzate direttamente attraverso il gateway locale al provider PSTN che assiste il sito (invece di instradare il chiamata a un trunk SIP del provider di servizi E9-1-1. Quando viene inserita una chiamata di emergenza, un database di un provider PS-ALI associato al trunk PSTN esegue il mapping dell'DID di ogni telefono analogico in una posizione fisica e fornisce questa posizione al PSAP. Questi record devono essere aggiornati con il provider di servizi PS-ALI ogni volta che i telefoni vengono spostati in posizioni ERL diversi.</P>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opzione&nbsp;provider&nbsp;di servizi E9-1-1 è possibile registrare il telefono analogico DIDs e il relativo posizioni ERL con il provider di servizi E9-1-1, se supportato dal provider di servizi E9-1-1. Se il provider riceve una chiamata da Lync Server che non include dati di PIDF-LO, il provider può verificare se esiste una corrispondenza di database nel numero DID della parte chiamante. Usando gli elfi recuperati dal relativo database, il provider può instradare automaticamente la chiamata di emergenza al PSAP corretto e PSAP riceverà l'DID del dispositivo analogico e un record ESQK che consente al dispatcher di cercare la posizione del chiamante.</P></LI></UL>Se si usa l'opzione gateway ELIN ed è necessario supportare E9-1-1 da telefoni analogici, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con il provider di servizi PS-ALI, come descritto nella prima opzione precedente.



</div>

Dal punto di vista di Lync Server, il processo E9-1-1 può essere separato in due fasi:

  - Fase 1: acquisizione di una posizione

  - Fase 2: routing della chiamata di emergenza a un provider di servizi E9-1-1

Questa sezione descrive il funzionamento di queste fasi.

Se si prevede di configurare l'infrastruttura per rilevare automaticamente la posizione del client, è prima di tutto necessario decidere quali elementi di rete verranno usati per eseguire il mapping dei chiamanti alle posizioni. Per informazioni dettagliate sulle possibili opzioni, vedere [definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Acquisizione di una posizione in Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Routing delle chiamate di emergenza tramite un trunk SIP in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Routing delle chiamate di emergenza tramite un gateway ELIN in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

