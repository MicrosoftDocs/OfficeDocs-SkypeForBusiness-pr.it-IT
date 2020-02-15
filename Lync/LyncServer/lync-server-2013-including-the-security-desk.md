---
title: 'Lync Server 2013: incluso il desk di sicurezza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99f35087d03b046fade741140dc3f5522e6c6d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a>Inclusione del desk di sicurezza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Nella propria azienda potrebbe essere necessario coinvolgere il desk di sicurezza in una chiamata di emergenza. Per decidere come integrare il desk di sicurezza nella distribuzione del servizio per chiamate di emergenza E9-1-1, è consigliabile rispondere alle domande riportate di seguito.

  - **Si desidera che il desk di sicurezza riceva notifica in caso di una chiamata di emergenza?**  
    È possibile configurare il criterio percorso in modo che Lync Server invii avvisi di messaggistica istantanea agli indirizzi SIP Lync di uno o più addetti alla sicurezza. Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e consentono al personale della sicurezza di fornire più facilmente assistenza per la situazione di emergenza.

<!-- end list -->

  - **Si desidera invitare il desk di sicurezza in conferenza per ogni chiamata di emergenza?**  
    Se supportato dal provider dei servizi di emergenza, è possibile configurare i criteri di percorso in modo da includere un numero di richiamata per ogni chiamata di emergenza. Questo numero viene quindi utilizzato dal provider per invitare il personale della sicurezza dell'organizzazione a partecipare in conferenza alle chiamate di emergenza. Nei criteri di percorso, questa funzionalità di conferenza può essere configurata come unidirezionale (solo ascolto) o bidirezionale.

<div>


> [!NOTE]  
> Se lo si desidera, è possibile configurare personale di emergenza diverso per i singoli criteri di percorso. In questo modo è possibile personalizzare la risposta per aree diverse nella società o creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno anziché dall'esterno della rete. Per specificare il personale a cui inviare la notifica, è possibile usare gruppi di distribuzione.



</div>

</div>

<span> </span>

</div>

</div>

</div>

