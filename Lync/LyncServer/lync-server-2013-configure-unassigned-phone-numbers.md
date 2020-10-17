---
title: 'Lync Server 2013: configurare i numeri di telefono non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd933ac87addf4a2094009e9f437c29437d882a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520233"
---
# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Configurare i numeri di telefono non assegnati in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Lync Server consente di configurare cosa accade alle chiamate in arrivo ai numeri di telefono validi per l'organizzazione, ma non vengono assegnati a un utente o a un telefono. Per configurare la gestione di tali chiamate, è possibile impostare una tabella dei numeri non assegnati. È possibile utilizzare la tabella per instradare le chiamate a un'applicazione annuncio o a un server Messaggistica unificata di Exchange.

La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile personalizzare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e assegnarlo a un annuncio in cui viene indicato il nuovo numero.

<div>


> [!IMPORTANT]  
> Prima di configurare la tabella dei numeri non assegnati, è necessario che siano già stati definiti uno o più annunci oppure che sia stato configurato un operatore automatico di messaggistica unificata di Exchange. Per informazioni dettagliate sulla creazione di annunci, vedere <A href="lync-server-2013-create-an-announcement.md">creare un annuncio in Lync Server 2013</A>. Per sapere se sono state configurate le impostazioni di messaggistica unificata di Exchange, eseguire il cmdlet <STRONG>Get-CsExUmContact</STRONG> . Per informazioni dettagliate, <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Creare o modificare un intervallo di numeri non assegnati in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Eliminare un intervallo di numeri non assegnati in Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

