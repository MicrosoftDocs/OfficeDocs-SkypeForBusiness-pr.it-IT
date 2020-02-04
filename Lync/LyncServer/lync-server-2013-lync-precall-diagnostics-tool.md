---
title: 'Lync Server 2013: strumento di diagnostica prechiamata di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Strumento di diagnostica prechiamata di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-11-04_

Lo strumento di diagnostica prechiamata di Lync (PCD) è un'applicazione basata sul client che consente di verificare in che modo lo stato corrente della rete potrebbe avere un impatto sulla qualità audio in una chiamata vocale aziendale imminente.

PCD è molto utile in situazioni in cui l'ultimo hop di una rete rischia di essere il più debole, ad esempio con i computer portatili in una rete WiFi pubblica o con utenti privati. PCD crea un piccolo flusso di pacchetti che attraversa questo segmento finale della rete. Lo strumento analizza quindi il flusso di pacchetti per stimare in che modo il jitter e la perdita lungo questa gamba potrebbero avere un impatto sulla qualità delle chiamate e quindi fornire un report. Puoi eseguire continuamente PCD nel client, anche quando vengono inserite le chiamate. Il flusso di pacchetti non ha un effetto significativo sulla larghezza di banda.

**L'ultima versione di PCD, versione 1,1, include i miglioramenti seguenti:**

  - Supporto per le password più lunghe, che ora possono contenere fino a 127 caratteri

  - Diagnostica aggiuntiva per i problemi di accesso all'autenticazione

  - Supporto migliore per distribuzioni ibride di Lync

  - Aggiornamenti di selezione credenziali

  - Miglioramenti della stabilità

Apprezziamo qualsiasi feedback. Inviare tutte le domande o i problemi di supporto all'alias di [feedback PCD](mailto:pcdfb@microsoft.com) <pcdfb@microsoft.com>.

Questo argomento include le sezioni seguenti:

  - Versioni di Lync PCD

  - Requisiti di sistema di Lync PCD

  - Caratteristiche di Lync PCD

  - Eseguire Lync PCD

  - Disinstallazione di Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versioni di Lync PCD

Questo argomento descrive le versioni seguenti dello strumento, disponibile per il download gratuito:

  - App desktop di Windows[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Requisiti di sistema di Lync PCD

<div>


> [!NOTE]  
> PCD richiede l'installazione e la configurazione di Unified Communications Web API (UCWA) per supportare i client mobili nella distribuzione di Lync Server. UCWA viene installato con Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Requisiti per le app desktop di Windows

  - Tutte le edizioni del sistema operativo Windows 7 o Windows 8

  - Microsoft .NET Framework 4,5 disponibile all'indirizzo[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Caratteristiche di Lync PCD

Lync PCD include le caratteristiche seguenti:

  - Esegui in default su richiesta (2 minuti di burst)

  - Esecuzione in modalità sempre attiva (fino a 24 ore in visualizzazione ancorata)

  - Visualizzazione cronologica delle esecuzioni dei test

  - Diagnosticare gli errori di accesso (solo Lync PCD per Windows 8)

![Cattura di schermata di accesso in corso alle funzionalità di Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Cattura di schermata di accesso in corso alle funzionalità di Lync PCD")

  - Visualizzazione grafica delle metriche di rete: MOS di rete, perdita di pacchetti e jitter di interarrivo a schermo intero e visualizzazione in blocco.

**Visualizzazione a schermo intero**

![Grafici dei risultati del test eseguito con lo strumento PreCall Diagnostic](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Grafici dei risultati del test eseguito con lo strumento PreCall Diagnostic")

**Visualizzazione bloccata**

![Risultati del test di utilizzo dello strumento PreCall Diagnostic](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Risultati del test di utilizzo dello strumento PreCall Diagnostic")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Eseguire Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Eseguire l'app desktop di Windows

1.  Per avviare il PCD in un sistema Windows 7, selezionare **diagnostica prechiamata** dal menu **Start** .
    
    Per avviare il PCD in un sistema Windows 8, selezionare l'icona nella schermata Start oppure cercare "diagnostica prechiamata".
    
    ![Icona dello strumento PreCall Diagnostic](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icona dello strumento PreCall Diagnostic")

2.  Quando lo strumento viene avviato, selezionare il metodo preferito per fornire le credenziali e selezionare la modalità di funzionamento della rete nella finestra di dialogo **Opzioni strumento di diagnostica prechiamata** , quindi scegliere **OK**:

3.  Selezionare il pulsante **Avvia test** per iniziare a eseguire la diagnostica.
    
    Se è stata selezionata l'opzione **Usa credenziali di rete** , il test inizia immediatamente.
    
    Se è stata selezionata l'opzione **Consenti immissione credenziali personali** , viene visualizzata la finestra di dialogo **sicurezza di Windows** . Dopo aver immesso le credenziali, viene avviato il test.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Disinstallazione di Lync PCD

Per rimuovere Lync PCD, seguire la procedura per il sistema operativo in uso:

  - In un sistema Windows 7 aprire il **Pannello di controllo**, selezionare **programmi e funzionalità**e fare doppio clic su **Lync 2013 PreCall Diagnostics**.

  - In un sistema Windows 8 fare clic con il pulsante destro del mouse sul riquadro PCD e scegliere **Disinstalla** dalla barra dell'app nella parte inferiore della schermata Start.

</div>

</div>

<span> </span>

</div>

</div>

</div>

