---
title: 'Lync Server 2013: strumento di diagnostica PreCall di Lync'
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
ms.openlocfilehash: 19051eb183dc12f091de0d90ebb707bc6cee8fc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525153"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync PreCall Diagnostics Tool in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-11-04_

Lync PreCall Diagnostics Tool (PCD) è un'applicazione basata su client che consente di vedere in che modo lo stato corrente della rete potrebbe influire sulla qualità audio in una chiamata VoIP aziendale imminente.

PCD è particolarmente utile in situazioni in cui l'ultimo hop di una rete rischia di essere il più debole (ad esempio, con laptop su una rete Wi-Fi pubblica o su utenti privati). PCD crea un flusso di pacchetti di piccole dimensioni che attraversa la tappa finale della rete. Lo strumento analizza quindi il flusso di pacchetti per valutare il modo in cui l'instabilità e la perdita lungo la gamba possono influire sulla qualità delle chiamate e quindi fornisce un report. È possibile eseguire continuamente PCD sul client, anche quando vengono inserite le chiamate. Il flusso di pacchetti non ha un effetto significativo sulla larghezza di banda.

**L'ultima versione di PCD, versione 1,1, include i seguenti miglioramenti:**

  - Supporto per password più lunghe, che possono essere fino a 127 caratteri

  - Diagnostica aggiuntiva per i problemi di accesso all'autenticazione

  - Supporto migliore per le distribuzioni ibride di Lync

  - Aggiornamenti per la selezione delle credenziali

  - Miglioramenti della stabilità

Apprezziamo eventuali commenti e suggerimenti. Inviare tutte le domande o i problemi di supporto all'alias dei [commenti e suggerimenti PCD](mailto:pcdfb@microsoft.com) all'indirizzo <pcdfb@microsoft.com> .

In questo argomento sono incluse le sezioni seguenti:

  - Versioni di Lync PCD

  - Requisiti di sistema di Lync PCD

  - Funzionalità di Lync PCD

  - Esecuzione di Lync PCD

  - Disinstallazione di Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versioni di Lync PCD

In questo argomento vengono descritte le versioni seguenti dello strumento, disponibili per il download gratuito:

  - App desktop di Windows ( [https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914) )

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Requisiti di sistema di Lync PCD

<div>


> [!NOTE]  
> PCD richiede che Unified Communications Web API (UCWA) venga installata e configurata per supportare i client mobili nella distribuzione di Lync Server. UCWA viene installato con Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Requisiti per le app desktop di Windows

  - Qualsiasi edizione del sistema operativo Windows 7 o Windows 8

  - Microsoft .NET Framework 4,5 disponibile all'indirizzo [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Funzionalità di Lync PCD

Lync PCD include le funzionalità seguenti:

  - Esecuzione in predefinita su richiesta (burst di 2 minuti)

  - Eseguire la modalità sempre attiva (fino a 24 ore nella visualizzazione bloccata)

  - Visualizzazione cronologica delle esecuzioni dei test

  - Diagnosticare gli errori di accesso (solo Lync PCD per Windows 8)

![Schermate di accesso alle funzionalità di Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Schermate di accesso alle funzionalità di Lync PCD")

  - Visualizzazione grafica delle metriche di rete – MOS di rete, perdita di pacchetti e instabilità di interarrivo a schermo intero e visualizzazione a scatto.

**Visualizzazione a schermo intero**

![Grafico dei risultati del test dello strumento di diagnostica PreCall](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Grafico dei risultati del test dello strumento di diagnostica PreCall")

**Visualizzazione bloccata**

![Risultati dei test per l'utilizzo dello strumento di diagnostica PreCall](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Risultati dei test per l'utilizzo dello strumento di diagnostica PreCall")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Esecuzione di Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Esecuzione dell'app desktop di Windows

1.  Per avviare PCD su un sistema Windows 7, selezionare **PreCall Diagnostics** dal menu **Start** .
    
    Per avviare il PCD su un sistema Windows 8, selezionare l'icona nella schermata Start oppure cercare "PreCall Diagnostics".
    
    ![Icona dello strumento di diagnostica PreCall](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icona dello strumento di diagnostica PreCall")

2.  Quando si avvia lo strumento, selezionare il metodo preferito per specificare le credenziali e selezionare la modalità di funzionamento della rete nella finestra di dialogo **Opzioni dello strumento di diagnostica PreCall** e quindi fare clic su **OK**:

3.  Selezionare il pulsante **Avvia test** per iniziare a eseguire la diagnostica.
    
    Se è stata selezionata l'opzione **Usa credenziali di rete** , il test inizia immediatamente.
    
    Se è stata selezionata l'opzione **let me Enter my credentials** , viene visualizzata la finestra di dialogo **sicurezza di Windows** . Dopo aver immesso le credenziali, viene avviato il test.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Disinstallazione di Lync PCD

Per rimuovere Lync PCD, seguire la procedura per il sistema operativo in uso:

  - In un sistema Windows 7, aprire il **Pannello di controllo**, selezionare **programmi e funzionalità**e fare doppio clic su **Lync 2013 PreCall Diagnostics**.

  - In un sistema Windows 8, fare clic con il pulsante destro del mouse sul riquadro PCD e scegliere **Disinstalla** dalla barra dell'app nella parte inferiore della schermata iniziale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

