---
title: 'Lync Server 2013: Verificare la connettività per gli utenti esterni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1f8a9bbda54c596a9ccae8451b15ce7300bffd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Verificare la connettività per gli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

La convalida della connettività per gli utenti esterni richiede la garanzia della connettività degli utenti al server e alla porta per il servizio Access Edge.

Una risorsa preziosa per confermare la configurazione e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari necessari per l'accesso degli utenti esterni è il sito dell'analizzatore connettività remota (<http://www.testocsconnectivity.com>). Il sito viene gestito e mantenuto dal supporto Microsoft. Per accedere all'analizzatore connettività remota, aprire il sito Web in un browser e seguire le istruzioni per selezionare lo scenario.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Testare la connettività degli utenti esterni e dell'accesso esterno

I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti:

  - Utenti di almeno un dominio federato e test di messaggistica istantanea, presenza, A/V e condivisione desktop.

  - Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning).

  - Utenti anonimi.

  - Utenti all'interno dell'organizzazione che hanno effettuato l'accesso in Lync in remoto, ma non con VPN.

Questi test determinano se il server perimetrale è:

  - Ascolto sulle porte necessarie usando un client Telnet all'esterno della rete.
    
      - Esempio: Telnet sip.contoso.com 443
    
      - Eseguire il test precedente sulle porte in uso nel pool di Edge Server o Edge Server a seconda della distribuzione.

  - Esecuzione di una risoluzione DNS esterna accurata.
    
      - Dall'esterno della rete eseguire il ping di ogni FQDN esterno del pool di Edge o Edge. Anche se il ping non riesce, verranno visualizzati gli indirizzi IP, che è possibile confrontare con quelli assegnati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

