---
title: 'Lync Server 2013: Risorse necessarie per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Risorse necessarie per il server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-02-05_

La disponibilità elevata e il ripristino di emergenza per il server di chat persistente richiedono risorse aggiuntive oltre a quelle in genere necessarie per l'operazione completa. Prima di configurare il server di chat persistente per l'elevata disponibilità e il ripristino di emergenza, verificare di disporre delle risorse seguenti, oltre a quelle necessarie per l'operazione standard del server di chat persistente. Per altre informazioni sulla configurazione, vedere [configurazione del server di chat persistente in Lync server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Un'istanza di database dedicata situata nello stesso centro dati fisico in cui si trova la parte anteriore iniziale del servizio server di chat persistente. Questo database fungerà da mirror di SQL Server per il database principale della chat persistente. Facoltativamente, è possibile designare un altro server SQL per fungere da Witness per il mirroring se si vuole un failover automatizzato nel database mirror.

  - Un'istanza di database dedicata situata nell'altro centro dati fisico. Questo database fungerà da database secondario di SQL Server log shipping per il database nel centro dati principale.

  - Un'istanza del database dedicata che funge da mirror di SQL Server per il database secondario. Facoltativamente, è possibile designare un altro server SQL in server come witness di mirroring. Entrambi devono essere situati nello stesso centro dati fisico del database secondario.

  - Se è abilitata la conformità del server di chat persistente, sono necessarie altre tre istanze di database dedicate. La distribuzione è uguale a quelle descritte in precedenza per il database della chat persistente. Mentre è possibile che il database di conformità condivida la stessa istanza di SQL Server del database della chat persistente, consigliamo istanze autonome per l'elevata disponibilità e il ripristino di emergenza.

  - Una condivisione file deve essere creata e designata per i registri delle transazioni di log di SQL Server. Tutti i server SQL in entrambi i centri dati che eseguono database di chat permanenti devono avere accesso in lettura/scrittura alla condivisione file. Questa condivisione non è definita come parte di un ruolo di filestore.

  - Una condivisione file nel server di database secondario per fungere da cartella di destinazione per i registri delle transazioni di SQL Server copiati dalla condivisione file del server principale.

<div>


> [!NOTE]  
> I server di chat permanenti attivi in un pool di server di chat persistente devono trovarsi nello stesso fuso orario del pool di Lync hop successivo definito nella topologia.



</div>

Le figure seguenti illustrano come configurare l'intero pool di server di chat persistente nelle due topologie di pool estese diverse:

  - Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda elevata/bassa latenza.

  - Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda ridotta/alta latenza.

La figura seguente mostra una topologia di pool di server di chat persistente allungata in cui i centri dati sono ubicati geograficamente con larghezza di banda elevata/bassa

**Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda elevata/bassa latenza.**

![](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Esame di configurazione") del pool di HBW PERSISTEnt chat server HBW

La figura seguente mostra una topologia di pool di server di chat persistente allungata in cui i centri dati sono ubicati geograficamente con larghezza di banda ridotta/elevata.

**Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda ridotta/alta latenza.**

![](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Esame di configurazione") del pool di LBW PERSISTEnt chat server LBW

</div>

<span> </span>

</div>

</div>

</div>

