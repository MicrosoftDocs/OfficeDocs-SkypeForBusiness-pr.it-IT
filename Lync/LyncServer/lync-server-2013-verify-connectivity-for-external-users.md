---
title: 'Lync Server 2013: verificare la connettività per gli utenti esterni'
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
ms.openlocfilehash: a8d85b72572ba065f52e93ee34e6cb9324c2f647
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518643"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Verificare la connettività per gli utenti esterni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

La convalida della connettività per gli utenti esterni garantisce la connettività dagli utenti al server e alla porta per il servizio Access Edge.

Una risorsa importante per confermare la configurazione e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari necessari per l'accesso degli utenti esterni è il sito analizzatore connettività remota ( <http://www.testocsconnectivity.com> ). Il sito è gestito e mantenuto dal supporto tecnico Microsoft. Per accedere a Remote Connectivity Analyzer, aprire il sito Web in un browser e seguire le istruzioni per selezionare lo scenario.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Testare la connettività degli utenti esterni e l'accesso esterno

I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito:

  - Utenti da almeno un dominio federato, con testing di messaggistica istantanea, presenza, audio/video e condivisione del desktop.

  - Utenti di ogni provider di servizi di messaggistica istantanea pubblica supportati dall'organizzazione e per i quali è stato completato il provisioning.

  - Utenti anonimi.

  - Utenti nell'organizzazione connessi a Lync in remoto, ma che non utilizzano una rete VPN.

Questi test determinano se il server perimetrale:

  - È in attesa sulle porte necessarie tramite un client telnet dall'esterno della rete.
    
      - Esempio: telnet sip.contoso.com 443
    
      - Eseguire il test precedente sulle porte utilizzate nel server perimetrale o nel pool di server perimetrali, a seconda della distribuzione.

  - Esegue la risoluzione DNS esterna in modo accurato.
    
      - Dall'esterno della rete, eseguire il ping di ognuno degli FQDN esterni del server perimetrale o del pool di server perimetrali. Anche se il ping non riesce verranno visualizzati gli indirizzi IP, confrontabili con quelli assegnati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

