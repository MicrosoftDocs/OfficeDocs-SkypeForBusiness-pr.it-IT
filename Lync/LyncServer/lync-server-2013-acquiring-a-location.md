---
title: 'Lync Server 2013: acquisizione di una posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de591298d6509ce14b9a4b1ebe55e0a327d517b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Acquisizione di una posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-06_

In una distribuzione di Lync Server 2013 E9-1-1, ogni client Lync o Lync Phone Edition connesso internamente acquisisce la propria posizione. Dopo la registrazione SIP, il client fornisce tutte le informazioni di connettività di rete che conosce se stesso in una richiesta di percorso al servizio informazioni percorso, che è un servizio Web di cui è stato eseguito il backup da un database di SQL Server replicato. Ogni pool di sito centrale dispone di un servizio informazioni percorso, che utilizza le informazioni di rete per eseguire una query sui record per un percorso corrispondente. Se esiste una corrispondenza, il servizio informazioni percorso restituirà una posizione al client. Se non viene trovata una corrispondenza, può venire richiesto all'utente di immettere manualmente una posizione (a seconda delle impostazioni dei criteri percorso). I dati sulla posizione vengono trasmessi di nuovo al client in un formato XML basato su standard IETF (Internet Engineering Task Force) denominato PIDF-LO (Presence Information Data Format Location Object).

Il client di Lync Server include i dati di PIDF-LO nell'ambito di una chiamata di emergenza e questi dati vengono utilizzati dal provider di servizi E9-1-1 per determinare le PSAP appropriate e instradare la chiamata a tale PSAP insieme al ESQK corretto, che consente al dispatcher di PSAP di ottenere il posizione del chiamante.

Nel diagramma seguente viene illustrato il modo in cui un client di Lync Server acquisisce una posizione (ad eccezione del metodo percorso basato sull'indirizzo MAC di terze parti):

![Modalità di acquisizione del diagramma di un percorso da parte del client](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Modalità di acquisizione del diagramma di un percorso da parte del client")

Per consentire a un client di acquisire una posizione, sono necessari i passaggi seguenti:

1.  L'amministratore compila il database del servizio informazioni percorso con la rete wiremap (tabelle che mappano diversi tipi di indirizzi di rete ai corrispondenti percorsi di risposta alle emergenze (posizioni ERL)).

2.  Se si utilizza un provider di servizi E9-1-1 tramite trunk SIP, l'amministratore convalida le parti dell'indirizzo civico della posizione ERL in base a un database dello stradario generale gestito dal provider di servizi E9-1-1. Se si utilizza una gateway ELIN, l'amministratore verifica che i numeri ELIN vengano caricati dal gestore PSTN nel database ALI (Automatic Location Identification).

3.  Durante la registrazione o ogni volta che si verifica una modifica di rete, un client connesso internamente invia una richiesta di posizione contenente gli indirizzi di rete individuati del client al servizio informazioni percorso.

4.  Il servizio informazioni percorso esegue una query sui record pubblicati per una posizione e, se viene trovata una corrispondenza, restituisce gli oggetti di tipo PIDF-LO per il client in formato.

</div>

<span> </span>

</div>

</div>

</div>

