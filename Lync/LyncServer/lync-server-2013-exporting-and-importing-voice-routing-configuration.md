---
title: 'Lync Server 2013: esportazione e importazione della configurazione del routing vocale'
description: 'Lync Server 2013: esportazione e importazione della configurazione del routing vocale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94a9c02672debae9f5b30e3a1a96856050d6ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564772"
---
# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a>Esportazione e importazione della configurazione del routing vocale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Se si desidera salvare la configurazione del routing vocale senza pubblicarla, eseguire la procedura seguente per utilizzare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale. Quando si importa un file di configurazione per il routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo di **routing vocale** nel pannello di controllo di Lync Server indicheranno che sono state apportate modifiche non salvate al routing vocale. Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.

<div>


> [!IMPORTANT]  
> Se sono state apportate modifiche di cui non è stato eseguito il commit alle impostazioni di una pagina all'interno del gruppo <STRONG>Routing vocale</STRONG>, le modifiche vengono salvate nel file di configurazione vocale esportato ( con estensione vcfg). In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante diverse sessioni del pannello di controllo di Lync Server prima di pubblicare le modifiche.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Esportare un file di configurazione di route vocali in Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [Importare un file di configurazione di route vocali in Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a>Sezioni correlate

</div>

</div>

<span> </span>

</div>

</div>

</div>

