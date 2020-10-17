---
title: 'Lync Server 2013: funzionalità di resilienza dei siti di succursale'
description: 'Lync Server 2013: funzionalità di resilienza dei siti di succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552202"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Funzionalità di resilienza dei siti di succursale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-10_

Se si fornisce la resilienza dei siti derivati, in caso di errore della connessione WAN di un sito derivato con un sito centrale o qualora il sito centrale non sia raggiungibile, le funzionalità vocali seguenti devono continuare a essere disponibili:

<div>


  - Chiamate PSTN in entrata e in uscita

  - Chiamate Enterprise tra utenti dello stesso sito e di due siti diversi

  - Gestione di base delle chiamate inclusi la messa in attesa, il recupero e il trasferimento

  - Messaggistica istantanea tra due parti

  - Inoltro di chiamata, squillo simultaneo degli endpoint, delega delle chiamate e servizi di intercettazione team, ma solo se delegante e delegato (ad esempio un capo e l'amministratore del capo), oppure tutti i membri del team, sono configurati nello stesso sito

  - Registrazione dettagli chiamata (CDR)

  - Conferenze telefoniche con accesso esterno PSTN con Operatore automatico conferenza

  - Funzionalità di segreteria telefonica, se si configurano le impostazioni di rerouting della segreteria telefonica. Per informazioni dettagliate, vedere [requisiti di resilienza dei siti di succursale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Autenticazione e autorizzazione utente

Le funzionalità seguenti saranno disponibili solo se la soluzione di resilienza è una distribuzione di Lync Server su vasta scala nel sito di succursale:

  - Conferenze di messaggistica istantanea, Web e audio/video

  - Routing in base a presenza e Non disturbare (le chiamate non squillano agli interni che hanno il Non disturbare attivato)

  - Aggiornamento delle impostazioni di inoltro di chiamata.

  - Applicazione Response Group e applicazione Parcheggio di chiamata

  - Provisioning di nuovi telefoni e client, ma solo se i servizi di dominio Active Directory sono presenti nel sito di succursale.

  - Enhanced 9-1-1 (E9-1-1)
    
    Se si distribuisce il servizio E9-1-1 e il trunk SIP nel sito centrale non è disponibile perché il collegamento WAN è inattivo, il Survivable Branch Appliance instraderà le chiamate di E9-1-1 al gateway di succursale locale. Per abilitare questa funzionalità, i criteri vocali degli utenti del sito di succursale devono eseguire il routing delle chiamate al gateway locale in caso di errore della WAN.

<div>


> [!NOTE]  
> SBA (Survivable Branch Office) non è supportato per XMPP. Gli utenti ospitati in una configurazione SBA non saranno in grado di inviare messaggi istantanei o vedere presenza con contatti XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

