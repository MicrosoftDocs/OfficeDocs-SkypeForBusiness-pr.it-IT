---
title: "Lync Server 2013: componenti utilizzati dall'applicazione annuncio"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a16690a1dee49c3b28b1f951894c216666d1eec9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Componenti utilizzati dall'applicazione annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-13_

In Lync Server 2013, l'applicazione annuncio è un componente dell'applicazione Response Group. Quando si distribuisce VoIP aziendale, l'applicazione annuncio viene automaticamente installata e attivata insieme all'applicazione Response Group. In questa sezione vengono descritti i componenti che supportano l'applicazione annuncio.

<div>

## <a name="announcement-application-components"></a>Componenti dell'applicazione Annuncio

I componenti di Lync Server seguenti supportano l'applicazione annuncio:

  - **Application Service**   Application Service fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazioni unificate. Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.

  - **Response Group**   Application l'applicazione Response Group è una delle applicazioni di comunicazione unificate ospitate dal servizio applicazione. Quando un intervallo di numeri di telefono non assegnato è configurato in modo da instradare un annuncio, è necessario che l'applicazione Response Group INSTRADE le chiamate effettuate al numero di telefono. (L'applicazione Response Group non è obbligatoria se tutti gli intervalli sono configurati in modo da instradare la messaggistica unificata di Exchange).

  - **I file audio vengono**utilizzati per gli annunci.   

  - **Archivio file l'**   applicazione annuncio utilizza l'archivio file per archiviare i file audio.

  - **Pannello di controllo di Lync Server**   è possibile utilizzare il pannello di controllo di Lync Server per configurare la tabella dei numeri non assegnati.

  - **Lync Server Management Shell**   è possibile utilizzare i cmdlet di Lync Server Management Shell per configurare le impostazioni degli annunci e la tabella dei numeri non assegnati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

