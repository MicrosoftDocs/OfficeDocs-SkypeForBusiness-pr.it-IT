---
title: 'Lync Server 2013: preparazione della foresta'
description: 'Lync Server 2013: preparazione della foresta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580002"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a>Preparazione della foresta per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

La preparazione della foresta crea gli oggetti e le impostazioni globali di Active Directory e i gruppi universali di Active Directory per l'utilizzo da parte di Lync Server 2013 e garantisce autorizzazioni di accesso appropriate per gli oggetti di Active Directory. Per una descrizione dei gruppi universali e delle impostazioni globali e degli oggetti creati dalla preparazione della foresta, vedere [changes made by Forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

La preparazione della foresta consente inoltre di creare oggetti che contengono insiemi di proprietà e gli identificatori di visualizzazione utilizzati da Lync Server 2013 e li archivia nel contenitore di configurazione.

<div>


> [!IMPORTANT]  
> Verificare che le modifiche alla preparazione dello schema siano state replicate in tutti i controller di dominio prima di eseguire la procedura di preparazione della foresta. Se la replica non è completa, si verifica un errore.



</div>

Se si sta eseguendo una nuova distribuzione di Lync Server, è necessario archiviare le impostazioni globali nel contenitore di configurazione. Se si esegue l'aggiornamento da una versione precedente e si archiviano ancora le impostazioni globali nel contenitore di sistema, è possibile continuare a utilizzare il contenitore di sistema.

Per eseguire questa procedura, è necessario essere membri del gruppo Enterprise Admins o Domain Admins per il dominio radice della foresta.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Esecuzione della preparazione della foresta per Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

