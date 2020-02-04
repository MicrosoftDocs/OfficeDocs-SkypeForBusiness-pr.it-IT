---
title: 'Lync Server 2013: Acquisizione di una posizione'
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
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Acquisizione di una posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

In una distribuzione di E9-1-1 di Lync Server 2013, ogni client Lync o Lync Phone Edition, connesso internamente, acquisisce la propria posizione. Dopo la registrazione SIP, il client fornisce tutte le informazioni di connettività di rete che conosce da sola in una richiesta di posizione al servizio informazioni sulla posizione, un servizio Web supportato da un database di SQL Server replicato. Ogni pool di sito centrale include un servizio di informazioni sulla posizione, che usa le informazioni di rete per eseguire query sui record per una posizione corrispondente. Se c'è una corrispondenza, il servizio informazioni sulla posizione restituisce un percorso al client. Se non è presente una corrispondenza, all'utente potrebbe essere richiesto di immettere manualmente una posizione (a seconda delle impostazioni dei criteri di posizione). I dati della posizione vengono trasmessi al client in un formato XML standardizzato di Internet Engineering Task Force (IETF), denominato oggetto location Data Format Information (PIDF-LO).

Il client Lync Server include i dati di PIDF-LO come parte di una chiamata di emergenza e questi dati vengono usati dal provider di servizi E9-1-1 per determinare la PSAP appropriata e instradare la chiamata a tale PSAP insieme al ESQK corretto, che consente al dispatcher di PSAP di ottenere l' posizione del chiamante.

Il diagramma seguente mostra il modo in cui un client Lync Server acquisisce una posizione (ad eccezione del metodo di posizione basato su indirizzo MAC del client di terze parti):

![Diagramma della modalità con cui il client acquisisce una posizione](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Diagramma della modalità con cui il client acquisisce una posizione")

Affinché un client acquisisca una posizione, è necessario eseguire la procedura seguente:

1.  L'amministratore compila il database del servizio informazioni sulla posizione con il wiremap di rete (tabelle che mappano vari tipi di indirizzi di rete ai corrispondenti percorsi di risposta di emergenza (posizioni ERL)).

2.  Se si usa un provider di servizi E9-1-1 trunk SIP, l'amministratore convalida le parti degli indirizzi civici di posizioni ERL in base a un database di stradario (Master Street Address Guide) gestito dal provider di servizi E9-1-1. Se si usa un gateway ELIN, l'amministratore garantisce che il gestore PSTN carichi i numeri ELIN nel database ALI (Automatic Location Identification).

3.  Durante la registrazione o ogni volta che si verifica un cambiamento di rete, un client connesso internamente invia una richiesta di posizione che contiene gli indirizzi di rete individuati del client al servizio informazioni sulla posizione.

4.  Il servizio informazioni sulla posizione esegue una query sui record pubblicati per una posizione e, se viene trovata una corrispondenza, restituisce gli elfi al client in formato PIDF-LO.

</div>

<span> </span>

</div>

</div>

</div>

