---
title: 'Lync Server 2013: Preparazione della foresta'
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
ms.openlocfilehash: 8a485ba2a406fd762d70ba4e8ff621d2d6af3801
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Preparazione della foresta per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

La preparazione della foresta crea le impostazioni globali di Active Directory e gli oggetti e i gruppi universali di Active Directory per l'uso da Lync Server 2013 e concede le autorizzazioni di accesso appropriate per gli oggetti Active Directory. Per una descrizione dei gruppi universali e delle impostazioni globali e degli oggetti creati dalla preparazione della foresta, vedere [le modifiche apportate dalla preparazione della foresta in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

La preparazione della foresta crea inoltre oggetti che contengono set di proprietà e indicatori di visualizzazione usati da Lync Server 2013 e li archivia nel contenitore di configurazione.

<div>


> [!IMPORTANT]  
> Verificare che le modifiche apportate alla preparazione dello schema vengano replicate in tutti i controller di dominio prima di eseguire la procedura di preparazione della foresta. Se la replica non viene completata, si verifica un errore.



</div>

Se si esegue una nuova distribuzione di Lync Server, è necessario archiviare le impostazioni globali nel contenitore di configurazione. Se si esegue l'aggiornamento da una versione precedente e si memorizzano ancora le impostazioni globali nel contenitore di sistema, è possibile continuare a usare il contenitore di sistema.

Per eseguire questa procedura, è necessario essere membri del gruppo amministratori dell'organizzazione o Domain Admins per il dominio radice della foresta.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Esecuzione della preparazione della foresta per Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

