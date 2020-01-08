---
title: 'Lync Server 2013: convalida della normalizzazione e del routing del numero di voce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be8f09304ccf077eb24daf707e536e9c90f84dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Convalida della normalizzazione e del routing del numero di voce in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-19_

La normalizzazione e il routing dei numeri è molto importante per l'ambiente VoIP aziendale funzionale. Soprattutto durante le migrazioni da PBX (Private Branch Exchange) a un ambiente autonomo di Lync Server, una delle chiavi per la migrazione corretta consiste nel rivelare e documentare tutte le regole di chiamata esistenti e creare regole di normalizzazione appropriate, criteri vocali, usi e rotte telefoniche.

La convalida della normalizzazione e del routing dei numeri è importante non solo durante le migrazioni, ma anche durante il normale funzionamento stabile del sistema.

È consigliabile eseguire questa convalida giornalmente usando il pannello di controllo di Lync Server, a partire dallo sviluppo di un set di test case robusto rispetto al set corrente di regole di normalizzazione pubblicate nelle impostazioni globali di Lync Server. Questi test case devono essere eseguiti ogni giorno per evidenziare eventuali modifiche indesiderate apportate e impegnate nel dial plan.

Il pannello di controllo di Lync Server consente inoltre di visualizzare, testare, modificare, archiviare e condividere le informazioni di configurazione relative al routing vocale e a modificare le regole di normalizzazione del numero di telefono aziendale, i dial plan, i criteri vocali e le route. Include funzionalità aggiuntive per eseguire le operazioni seguenti:

  - Esportare e importare o eseguire il backup dei dati di routing vocale tra sistemi.

  - Testare le modifiche alla configurazione prima di caricarle in un sistema dinamico.

  - Creare ed eseguire test case di configurazione per garantire l'usabilità dei dati di routing dopo aver apportato modifiche, ma prima di eseguire il commit delle modifiche apportate a un sistema distribuito.

  - Creazione e modifica di regole di normalizzazione dei numeri, profili di posizione, criteri vocali e dati di routing senza scrivere le espressioni regolari necessarie.

  - Analisi di un profilo di posizione per la compatibilità con Lync Server Phone Edition.

  - Altre informazioni sui test di routing vocale sono disponibili in [test Voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)

<div>

## <a name="see-also"></a>Vedere anche


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

