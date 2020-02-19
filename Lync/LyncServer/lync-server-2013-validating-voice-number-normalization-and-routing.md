---
title: 'Lync Server 2013: convalidare la normalizzazione e il routing dei numeri vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92809d018bf8b69e6bc3fd5cc640c40836249de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Convalidare la normalizzazione e il routing dei numeri vocali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-19_

La normalizzazione e il routing dei numeri corretti è molto importante per l'ambiente funzionale VoIP aziendale. Soprattutto durante le migrazioni da PBX (Private Branch Exchange) a un ambiente Lync Server autonomo, una delle chiavi per la migrazione corretta è quella di rivelare e documentare tutte le regole di composizione esistenti e creare regole di normalizzazione appropriate, criteri vocali, utilizzi e route del telefono.

La convalida della normalizzazione e del routing dei numeri è importante non solo durante la migrazione, ma anche durante il normale e stabile funzionamento del sistema.

È consigliabile eseguire questa convalida giornalmente utilizzando il pannello di controllo di Lync Server, iniziando con lo sviluppo di un set di test case robusto rispetto all'insieme corrente di regole di normalizzazione pubblicate nelle impostazioni globali di Lync Server. Questi test case devono essere eseguiti ogni giorno per evidenziare eventuali modifiche indesiderate apportate e salvate nel dial plan.

Il pannello di controllo di Lync Server consente inoltre di visualizzare, testare, modificare, archiviare e condividere informazioni sulla configurazione del routing vocale e di modificare le regole di normalizzazione dei numeri di VoIP aziendale, dial plan, criteri vocali e route. Sono disponibili funzionalità aggiuntive per eseguire le operazioni seguenti:

  - Esportare e importare o eseguire il backup dei dati di routing vocale tra sistemi.

  - Verifica delle modifiche apportate alla configurazione prima del caricamento in un sistema attivo.

  - Creazione ed esecuzione di test case di configurazione per garantire l'usabilità dei dati di routing dopo aver apportato le modifiche, ma prima di eseguire il commit delle modifiche apportate a un sistema distribuito.

  - Creazione e modifica di regole di normalizzazione dei numeri, profili località, criteri vocali e dati di routing senza scrivere le espressioni regolari necessarie.

  - Analisi di un profilo percorso per la compatibilità con Lync Server Phone Edition.

  - Per ulteriori informazioni sui test di routing vocale, vedere [test Voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)

<div>

## <a name="see-also"></a>Vedere anche


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

