---
title: 'Lync Server 2013: Funzionalità di resilienza dei siti di succursale'
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
ms.openlocfilehash: a490de36322914235346cbc141784aab2c24f2ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Funzionalità di resilienza dei siti di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-10_

Se si specifica la resilienza del sito di succursale, se la connessione WAN di un sito di succursale a un sito centrale non riesce o se il sito centrale non è raggiungibile, è necessario che le caratteristiche vocali seguenti continuino a essere disponibili:

<div>


  - Chiamate PSTN (Public Switched Telephone Network) in ingresso e in uscita

  - Chiamate aziendali tra utenti sia nello stesso sito che tra due siti diversi

  - Gestione delle chiamate di base, incluso il blocco delle chiamate, il recupero e il trasferimento

  - Messaggistica istantanea a due parti

  - Inoltro di chiamata, squillo simultaneo di endpoint, delega delle chiamate e servizi di chiamata del team, ma solo se il delegante e il delegato, ad esempio un Manager e l'amministratore del responsabile, o tutti i membri del team, sono configurati nello stesso sito

  - Record dettagli chiamata (CDRs)

  - Servizi di conferenza telefonica con accesso esterno PSTN con l'operatore automatico di conferenza

  - Funzionalità della segreteria telefonica se si configurano le impostazioni di reinstradamento della segreteria telefonica. Per informazioni dettagliate, vedere [requisiti di resilienza dei siti secondari per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Autenticazione e autorizzazione dell'utente

Le caratteristiche seguenti saranno disponibili solo se la soluzione di resilienza è una distribuzione su vasta scala di Lync Server presso il sito della filiale:

  - Servizi di conferenza di messaggistica istantanea, Web e A/V

  - Routing basato su presenza e non disturbare (DND) (dove le chiamate non squillano in estensioni con DND attivato)

  - Aggiornamento delle impostazioni di inoltro di chiamata

  - Applicazione Response Group Application e Call Park

  - Provisioning di nuovi telefoni e client, ma solo se i servizi di dominio Active Directory sono presenti nel sito della filiale.

  - Enhanced 9-1-1 (E9-1-1)
    
    Se E9-1-1 è distribuito e il trunk SIP nel sito centrale non è disponibile perché il collegamento WAN è in calo, il Survivable Branch Appliance instraderà le chiamate E9-1-1 al gateway della filiale locale. Per abilitare questa funzionalità, i criteri vocali degli utenti del sito della filiale devono instradare le chiamate al gateway locale in caso di errore WAN.

<div>


> [!NOTE]  
> SBA (Survivable Branch Office) non è supportato per XMPP. Gli utenti ospitati in una configurazione SBA non saranno in grado di inviare messaggi istantanei o vedere la presenza con contatti XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

