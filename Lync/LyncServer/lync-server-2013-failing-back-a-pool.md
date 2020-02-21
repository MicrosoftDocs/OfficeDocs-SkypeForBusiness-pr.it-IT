---
title: 'Lync Server 2013: failover di un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72019a1bc95bd1c9c2b8cd69a623311ad6f249ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Failover di un pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Dopo aver riportato online il pool in cui si è verificata la situazione di emergenza (ovvero Pool1 in questo esempio), eseguire le operazioni seguenti per ripristinare uno stato di funzionamento regolare per la distribuzione.

Si noti che per il completamento del processo di failback sono richiesti vari minuti. A titolo di riferimento, sono previsti fino a 60 minuti per un pool di 20.000 utenti.

1.  Eseguire il failback degli utenti ospitati in origine in Pool1 e di cui è stato eseguito il failover in Pool2 digitando il comando di cmdlet seguente:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Non sono necessari altri passaggi. Se si è verificato un errore nel server di gestione centrale, è possibile lasciarlo in Pool2.

</div>

<span> </span>

</div>

</div>

</div>

