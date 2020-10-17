---
title: Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9ac7b7851cf5862210c7b343bc80b72b92c08e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527543"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Quando un account utente viene spostato da Lync Server 2010 a un server Lync Server 2013, le informazioni seguenti vengono spostate con l'account utente seguente:

  - **Le riunioni già pianificate dall'utente**. Vengono spostate anche le directory e i dati delle conferenze.

  - **Il PIN dell'utente**. Il PIN corrente dell'utente continua a funzionare fino alla scadenza o alla richiesta di un nuovo PIN da parte dell'utente stesso.

Le seguenti informazioni sull'account utente non vengono spostate nel nuovo server.

  - **Contenuto delle riunioni**. Per spostare il contenuto condiviso durante una riunione, ad esempio PowerPoint, Lavagna, allegati o dati dei sondaggi, usare il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser**.

</div>

<span> </span>

</div>

</div>

</div>

