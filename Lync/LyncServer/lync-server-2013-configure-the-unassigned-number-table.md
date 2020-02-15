---
title: 'Lync Server 2013: configurare la tabella dei numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3aa60273439c94a5d936efe826e77dcc683be
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Configurare la tabella dei numeri non assegnati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

In Lync Server 2013, è possibile specificare cosa succede alle chiamate in arrivo per i numeri di telefono validi per l'organizzazione, ma non vengono assegnati a un utente o a un telefono. I chiamanti possono ascoltare un messaggio, essere instradati verso un'altra destinazione oppure entrambe le opzioni.

La configurazione della tabella dei numeri non assegnati dipende dal modo in cui si desidera utilizzarla. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene richiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile modificare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e quindi assegnarlo a un annuncio in cui viene indicato il nuovo numero.

<div>


> [!IMPORTANT]  
> Prima di configurare la tabella dei numeri non assegnati, è necessario che nel sistema siano già stati definiti annunci o che sia stato impostato un operatore automatico di messaggistica unificata di Exchange.



</div>

<div>


> [!TIP]  
> Quando qualcuno chiama un numero non assegnato, Lync Server esegue la ricerca nella tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo corrispondente. Pertanto, per l'ultimo intervallo della tabella è consigliabile specificare un'azione che si desidera venga eseguita come ultima risorsa.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

[Creare o modificare un intervallo di numeri non assegnati in Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [creare un annuncio in Lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

