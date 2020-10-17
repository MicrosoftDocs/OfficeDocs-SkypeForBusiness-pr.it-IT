---
title: 'Lync Server 2013: risorse necessarie per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156a3ffef41782760124f0eb791cf2fdb71a1235
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511943"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Risorse necessarie per il server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-02-05_

La disponibilità elevata e il ripristino di emergenza per il server Chat persistente richiedono ulteriori risorse oltre a ciò che in genere è necessario per l'operazione completa. Prima di configurare il server Chat persistente per la disponibilità elevata e il ripristino di emergenza, verificare di disporre delle risorse seguenti oltre a quelle necessarie per l'operazione standard del server Chat persistente. Per ulteriori informazioni sulla configurazione, vedere [Configuring Persistent Chat Server in Lync server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Un'istanza di database dedicata che si trova nello stesso data center fisico in cui si trova l'Home Front-end del servizio server Chat persistente. Questo database fungerà da mirror di SQL Server per il database di Persistent Chat principale. Facoltativamente, designare un ulteriore server SQL per fungere da controllo del mirroring se si desidera un failover automatizzato per il database mirror.

  - Un'istanza di database dedicata nell'altro data center fisico. Questo database fungerà da database secondario di log shipping di SQL Server per il database nel data center principale.

  - Un'istanza di database dedicata che funge da mirror di SQL Server per il database secondario. Facoltativamente, è possibile designare un ulteriore SQL Server per il server come testimone del mirroring. Entrambi devono trovarsi nello stesso data center fisico del database secondario.

  - Se è abilitata la conformità del server Chat persistente, sono necessarie altre tre istanze di database dedicate. La distribuzione è identica a quella descritta in precedenza per il database di chat persistente. Sebbene sia possibile che il database di conformità condivida la stessa istanza di SQL Server del database di chat persistente, è consigliabile disporre di istanze autonome per la disponibilità elevata e il ripristino di emergenza.

  - È necessario creare una condivisione file e designarla per i log delle transazioni di log shipping di SQL Server. Tutti i server SQL in entrambi i data center che eseguono i database di Persistent Chat devono avere accesso in lettura/scrittura alla condivisione di file. Tale condivisione non è definita come parte di un ruolo FileStore.

  - Una condivisione file nel server di database secondario che funge da cartella di destinazione per i registri delle transazioni di SQL Server che vengono copiati dalla condivisione file del server primario.

<div>


> [!NOTE]  
> I server di chat persistente attivi in un pool di server Chat persistente devono risiedere nello stesso fuso orario del pool di Lync hop successivo definito nella topologia.



</div>

Nelle figure seguenti vengono forniti esempi di come è possibile configurare l'intero pool di server Chat persistente nelle due topologie di pool estese diverse:

  - Pool di server Persistent Chat esteso quando i data center sono georilevati con un'elevata larghezza di banda e una bassa latenza.

  - Pool di server Persistent Chat esteso quando i data center sono georilevati con una bassa larghezza di banda e un'elevata latenza.

Nella figura seguente viene illustrata una topologia del pool di server Chat persistente estesa in cui i Data Center sono geolocalizzati con elevata larghezza di banda e bassa latenza.

**Pool di server Persistent Chat esteso quando i data center sono georilevati con un'elevata larghezza di banda e una bassa latenza.**

![Esame di configurazione del pool di server Chat persistente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Esame di configurazione del pool di server Chat persistente HBW")

Nella figura seguente viene illustrata una topologia del pool di server Chat persistente estesa in cui i Data Center sono geolocalizzati con una bassa larghezza di banda e un'elevata latenza

**Pool di server Persistent Chat esteso quando i data center sono georilevati con una bassa larghezza di banda e un'elevata latenza.**

![Esame di configurazione del pool di server Chat persistente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Esame di configurazione del pool di server Chat persistente LBW")

</div>

<span> </span>

</div>

</div>

</div>

