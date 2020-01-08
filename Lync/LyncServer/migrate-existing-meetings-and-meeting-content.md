---
title: Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Quando un account utente viene spostato da Lync Server 2010 a un server Lync Server 2013, le informazioni seguenti vengono spostate con l'account utente seguente:

  - **Riunioni già programmate dall'utente**. Questo include lo spostamento delle directory di conferenza e dei dati di conferenza.

  - **Pin (Personal Identification Number) dell'utente**. Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.

Le informazioni dell'account utente seguenti non vengono spostati nel nuovo server.

  - **Contenuto della riunione**. Per poter trasferire il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati di sondaggio, usa il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser** .

</div>

<span> </span>

</div>

</div>

</div>

