---
title: "Lync Server 2013: Componenti utilizzati dall'applicazione Annuncio"
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
ms.openlocfilehash: 52ef0b1da665f8797f29582e9ce9e1d311287d61
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Componenti utilizzati dall'applicazione Annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-13_

In Lync Server 2013 l'applicazione di annuncio è un componente dell'applicazione Response Group. Quando si distribuisce VoIP aziendale, l'applicazione di annuncio viene automaticamente installata e attivata insieme all'applicazione Response Group. In questa sezione vengono descritti i componenti che supportano l'applicazione di annuncio.

<div>

## <a name="announcement-application-components"></a>Componenti dell'applicazione di annuncio

I componenti di Lync Server seguenti supportano l'applicazione di annuncio:

  - **Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazioni unificate. Il servizio applicazione viene installato automaticamente in ogni server front-end in un pool Front-end e in ogni server Standard Edition.

  - **Response Group Application**   l'applicazione Response Group è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione. Quando un intervallo di numeri di telefono non assegnato è configurato per l'instradamento a un annuncio, è necessaria l'applicazione Response Group per instradare le chiamate effettuate al numero di telefono. L'applicazione Response Group non è necessaria se tutti gli intervalli sono configurati per l'instradamento alla messaggistica unificata di Exchange.

  - ****   Per gli annunci vengono usati file audio per i file audio.

  - **Archivio file l'**   applicazione di annuncio USA archivio file per archiviare i file audio.

  - **Pannello di controllo di Lync Server**   è possibile usare il pannello di controllo di Lync Server per configurare la tabella dei numeri non assegnati.

  - **Lync Server Management Shell**   è possibile usare i cmdlet di Lync Server Management Shell per configurare le impostazioni degli annunci e la tabella dei numeri non assegnati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

