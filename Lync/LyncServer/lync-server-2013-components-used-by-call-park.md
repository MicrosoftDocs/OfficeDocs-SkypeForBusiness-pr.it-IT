---
title: 'Lync Server 2013: Componenti utilizzati dal parcheggio di chiamata'
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
ms.openlocfilehash: ae458d7ef3245e366e4f2bdd61f192401909213b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Componenti utilizzati dal parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-13_

L'applicazione Call Park viene automaticamente installata quando si distribuisce VoIP aziendale. Si Abilita il parcheggio delle chiamate configurando il criterio vocale. I componenti di Lync Server 2013 seguenti supportano l'applicazione Parcheggio di chiamata:

  - **Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione di applicazioni di comunicazioni unificate, ad esempio l'applicazione Call Park. Il servizio applicazione viene installato automaticamente in ogni server front-end in un pool Front-end e in ogni server Standard Edition.

  - **Call Park application**   l'applicazione Call Park è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione. Viene incluso automaticamente quando si distribuisce VoIP aziendale. Chiama parchi parcheggiati e recupera le chiamate e gestisce le orbite di Call Park.

  - **Musica in attesa-file**   se la musica è abilitata, il file musicale viene riprodotto durante il parcheggio di una chiamata. Viene incluso un file di musica predefinito quando viene installata l'applicazione Parcheggio di chiamata.

  - **Archivio file l'**   applicazione Call Park USA archivio file per contenere file audio personalizzati.

  - **Pannello di controllo di Lync Server**   è possibile usare il pannello di controllo di Lync Server per configurare la tabella Orbit di Call Park e per abilitare il parcheggio delle chiamate per gli utenti.

  - **Lync Server Management Shell**   tutte le configurazioni delle applicazioni di Call Park possono essere eseguite usando i cmdlet di Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

