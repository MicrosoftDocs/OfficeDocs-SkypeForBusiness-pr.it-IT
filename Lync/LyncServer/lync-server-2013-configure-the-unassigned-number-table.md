---
title: 'Lync Server 2013: Configurare la tabella dei numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59b44b31eececd002434b74085be85eaec9cbec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Configurare la tabella dei numeri non assegnati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

In Lync Server 2013 è possibile specificare cosa accade alle chiamate in arrivo per i numeri di telefono validi per l'organizzazione, ma non sono assegnati a un utente o un telefono. I chiamanti possono ascoltare un messaggio o possono essere instradati a un'altra destinazione o entrambi.

La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se si includono estensioni non assegnate nella tabella, è possibile modificare l'azione che si verifica per i numeri specifici. Ad esempio, se si modifica l'estensione per il servizio di assistenza clienti, è possibile includere il vecchio numero di servizio clienti nella tabella e quindi assegnarlo a un annuncio che fornisce il nuovo numero.

<div>


> [!IMPORTANT]  
> Prima di configurare la tabella dei numeri non assegnati, è necessario che il sistema disponga già di annunci definiti o di un operatore automatico di messaggistica UNIFICAta di Exchange.



</div>

<div>


> [!TIP]  
> Quando qualcuno chiama un numero non assegnato, Lync Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo corrispondente. Deve quindi essere specificata un'azione che si vuole eseguire come ultima risorsa per l'ultimo intervallo della tabella.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

[Creare o modificare un intervallo di numeri non assegnati in Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [creare un annuncio in Lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

