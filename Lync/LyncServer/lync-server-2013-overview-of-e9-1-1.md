---
title: 'Lync Server 2013: Panoramica del servizio E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6bc8d1f743db31cd248b750a67121c0c6664d07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Panoramica del servizio E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Microsoft Lync Server 2013 supporta la chiamata avanzata 9-1-1 (E9-1-1) dai client Lync e dai dispositivi Lync Phone Edition. Quando si configura Lync Server per il servizio E9-1-1, le chiamate di emergenza effettuate da Lync 2013 o Lync Phone Edition includono le informazioni di Emergency Response Location (elfi) dal database dei servizi di informazioni sulla posizione. Le informazioni ERL includono gli indirizzi civici (ovvero la via) e altri dati che consentono di individuare la posizione con maggiore precisione in edifici di uffici e altre strutture con più occupanti. Quando un utente effettua una chiamata di emergenza, Lync Server instrada l'audio della chiamata, insieme al percorso e alle informazioni di callback, tramite un Mediation Server a un provider di servizi E9-1-1. Tale provider utilizza l'indirizzo civico del chiamante per instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP) responsabile per l'area in cui si trova il chiamante, quindi invia la chiave di query del servizio di emergenza (ESQK, Emergency Service Query Key) che verrà utilizzata dal centro PSAP per cercare le informazioni ERL del chiamante.

Lync Server supporta due metodi per il routing delle chiamate di emergenza a un provider di servizi E9-1-1:

  - Una connessione trunk SIP (Session Initiation Protocol) a un provider di servizi E9-1-1 qualificato

  - Un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 basato su PSTN (Public Switched Telephone Network)

Quando si utilizza un provider di servizi E9-1-1 trunk SIP, è possibile aggiungere posizioni ERL al database del servizio informazioni percorso e quindi convalidare le posizioni in base a una guida (allo stradario generale) gestita dal provider di servizi E9-1-1. Se un provider di servizi E9-1-1 riceve una chiamata senza informazioni sulla posizione o con una posizione che non può essere verificata nello stradario, il provider instrada la chiamata a un centro di risposta alle chiamate di emergenza (ECRC) nazionale/regionale con personale formato appositamente che tenta di ottenere la posizione del chiamante verbalmente, se possibile, e instrada manualmente la chiamata al centro PSAP appropriato. Alcuni provider di servizi E9-1-1 su trunk SIP inoltre forniscono ai clienti un numero DID (Direct Inward Dialing) PSTN per il centro ECRC, offrendo un mezzo alternativo per il routing delle chiamate 9-1-1 in caso di malfunzionamento del trunk SIP per un motivo qualsiasi.

A differenza del TDM (Time Division Multiplexing) e dei telefoni PBX (Private Branch Exchange) basati su IP, che dispongono di posizioni fisse, un endpoint Lync può essere molto mobile. Quando si distribuisce la funzionalità E9-1-1, Lync Server consente di garantire che non vi siano informazioni sul luogo in cui si trova il chiamante, la chiamata di emergenza può essere instradata al PSAP che serve la posizione del chiamante. Se l'ufficio principale dell'utente si trova a Milano, ma l'utente effettua una chiamata di emergenza da un computer in una succursale a Roma, il provider di servizi E9-1-1 su PSTN o su trunk SIP instraderà la chiamata al centro PSAP di Roma e non a quello di Milano.

Quando si utilizza un gateway ELIN, è inoltre possibile aggiungere posizioni ERL al database del servizio informazioni percorso, ma è anche necessario includere un numero ELIN per ogni percorso. Il numero ELIN diventa il numero chiamante durante la chiamata di emergenza. È quindi necessario verificare che la portante PSTN carichi i numeri ELIN nel database ALI (Automatic Location Identification).

<div>


> [!NOTE]  
> I dispositivi analogici connessi a Lync non sono in grado di ricevere informazioni sul percorso dal servizio informazioni percorso o di trasmissione al provider di servizi E9-1-1. Se si utilizzata l'opzione del provider di servizi E9-1-1 su trunk SIP ed è necessario supportare i servizi E9-1-1 da telefoni analogici, sono disponibili due opzioni: 
> <UL>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opzione&nbsp;tradizionale&nbsp;PS-Ali se si dispone di gateway PSTN locali in ogni sito in cui vengono distribuiti telefoni analogici e che ogni telefono analogico ha un did, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con un provider di servizi switch privato/rilevamento automatico località (PS-Ali). In questo caso, è necessario configurare criteri vocali di Lync appositi e assegnarli agli oggetti contatto dei dispositivi analogici, in modo che le chiamate E9-1-1 da tali telefoni vengano instradate direttamente tramite il gateway locale al provider PSTN che fornisce i servizi al sito, anziché instradare la chiamata al trunk SIP di un provider di servizi E9-1-1. Quando viene effettuata una chiamata di emergenza, un database presso un provider PS-ALI associato al trunk PSTN mappa il DID di ogni telefono analogico a una posizione fisica, quindi fornisce tale posizione al centro PSAP. Questi record devono essere aggiornati presso il provider di servizi PS-ALI ogni volta che i telefoni vengono spostati in posizioni ERL diverse.</P>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opzione&nbsp;del&nbsp;provider di servizi E9-1-1 è possibile registrare le DIDs del telefono analogico e le corrispondenti posizioni ERL con il provider di servizi E9-1-1, se questo è supportato dal provider di servizi E9-1-1. Se il provider riceve una chiamata da Lync Server che non include dati di PIDF-LO, il provider può vedere se esiste una corrispondenza di database sul numero DID della parte chiamante. In base alle informazioni ERL recuperate dal database, il provider può instradare automaticamente la chiamata di emergenza al centro PSAP corretto, che riceverà il DID del dispositivo analogico e un record ESQK che consente al dispatcher di cercare la posizione del chiamante.</P></LI></UL>Se si utilizza l'opzione del gateway ELIN ed è necessario supportare i servizi E9-1-1 da telefoni analogici, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con il provider di servizi PS-ALI, come descritto in precedenza nella prima opzione.</div>

Dal punto di vista di Lync Server, il processo di E9-1-1 può essere suddiviso in due fasi:

  - Fase 1: acquisizione di una posizione

  - Fase 2: instradamento della chiamata di emergenza a un provider di servizi E9-1-1

In questa sezione viene descritto il funzionamento di queste due fasi.

Se si prevede di configurare l'infrastruttura per il rilevamento automatico della posizione dei client, è innanzitutto necessario decidere quali elementi di rete verranno utilizzati per il mapping tra chiamanti e posizioni. Per informazioni dettagliate sulle possibili opzioni, vedere [definizione degli elementi di rete utilizzati per determinare la posizione in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Acquisizione di una posizione in Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Routing delle chiamate al servizio E9-1-1 tramite un trunk SIP in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Routing delle chiamate al servizio E9-1-1 tramite un gateway ELIN in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

