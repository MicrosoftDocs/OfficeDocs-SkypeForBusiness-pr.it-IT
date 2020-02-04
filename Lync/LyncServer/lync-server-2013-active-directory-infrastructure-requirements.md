---
title: "Lync Server 2013: Requisiti dell'infrastruttura di Active Directory"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75278700623ae7251fe7cebec36e959a38f325dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Requisiti dell'infrastruttura di Active Directory per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

Prima di avviare il processo di preparazione dei servizi di dominio Active Directory per Lync Server 2013, verificare che l'infrastruttura di Active Directory soddisfi i prerequisiti seguenti:

  - Tutti i controller di dominio (che includono tutti i server di catalogo globale) nella foresta in cui si distribuisce Lync Server eseguono uno dei sistemi operativi seguenti:
    
      - Sistema operativo Windows Server 2012 R2
    
      - Sistema operativo Windows Server 2012
    
      - Sistema operativo Windows Server 2008 R2
    
      - Sistema operativo Windows Server 2008
    
      - Windows Server 2008 Enterprise 32 bit
    
      - versioni di 32 bit o 64 del sistema operativo Windows Server 2003 R2
    
      - versioni di 32 bit o 64 del sistema operativo Windows Server 2003

  - Tutti i domini in cui si distribuisce Lync Server vengono generati a livello di funzionalità del dominio di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.

  - La foresta in cui si distribuisce Lync Server viene generata in base a un livello di funzionalità della foresta di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.
    
    <div>
    

    > [!NOTE]  
    > Per modificare il livello di funzionalità del dominio o della foresta, vedere "innalzamento dei livelli di funzionalità del dominio e <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>della foresta" nella raccolta TechNet.

    
    </div>

  - Un catalogo globale viene distribuito in tutti i domini in cui si distribuiscono computer o utenti di Lync Server.

Lync Server 2013 supporta i gruppi universali nei sistemi operativi Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003. I membri dei gruppi universali possono includere altri gruppi e account da qualsiasi dominio nell'albero di dominio o nella foresta e possono essere assegnate autorizzazioni in qualsiasi dominio nell'albero o nella foresta del dominio. Il supporto del gruppo universale, combinato con la delega dell'amministratore, semplifica la gestione di una distribuzione di Lync Server. Ad esempio, non è necessario aggiungere un dominio a un altro per consentire a un amministratore di gestire entrambe le proprie esigenze.

</div>

<span> </span>

</div>

</div>

</div>

