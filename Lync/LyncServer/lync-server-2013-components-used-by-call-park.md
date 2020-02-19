---
title: 'Lync Server 2013: componenti utilizzati dal parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4a833736368fe6060dad4fbb62e6a528e91b6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Componenti utilizzati dal parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-13_

L'applicazione Parcheggio di chiamata viene automaticamente installata quando si distribuisce VoIP aziendale. Si Abilita il parcheggio di chiamata configurando il criterio vocale. I componenti di Lync Server 2013 seguenti supportano l'applicazione Parcheggio di chiamata:

  - **Application Service**   Application Service fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificata, ad esempio l'applicazione Parcheggio di chiamata. Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.

  - **Applicazione Parcheggio di chiamata**   l'applicazione Parcheggio di chiamata è una delle applicazioni di comunicazione unificata ospitate dal servizio applicazione. Viene inclusa automaticamente quando si distribuisce VoIP aziendale. Parchi parcheggio di chiamata e recupera le chiamate e gestisce le orbite del parcheggio di chiamata.

  - **Music-on Hold-file**   se la musica è abilitata, il file musicale viene riprodotto mentre una chiamata è parcheggiata. Quando è installata l'applicazione Parcheggio di chiamata, viene incluso un file di musica predefinito.

  - **Archivio file l'**   applicazione Parcheggio di chiamata utilizza l'archivio file per conservare i file audio personalizzati.

  - **Pannello di controllo di Lync Server**   è possibile utilizzare il pannello di controllo di Lync Server per configurare la tabella di orbit del parcheggio di chiamata e per abilitare il parcheggio di chiamata per gli utenti.

  - **Lync Server Management Shell**   tutte le configurazioni dell'applicazione Parcheggio di chiamata possono essere eseguite utilizzando i cmdlet di Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

