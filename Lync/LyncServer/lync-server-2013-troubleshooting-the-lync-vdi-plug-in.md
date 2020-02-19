---
title: 'Lync Server 2013: risoluzione dei problemi relativi al plug-in VDI di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad67f17f3d12f72472ee8ddbc0e7605cf58dab52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Risoluzione dei problemi relativi al plug-in VDI di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Risoluzione dei problemi relativi all'installazione del plug-in VDI di Lync in un thin client

In caso di problemi durante l'installazione del plug-in VDI in un thin client, controllare quanto segue:

  - Verificare che nella cartella specificata vi sia sufficiente spazio per le variabili di sistema TEMP e TMP.

  - Verificare che la protezione dalla scrittura sia disattivata. Per istruzioni, consultare la documentazione del produttore del dispositivo.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Risoluzione dei problemi di abbinamento

Quando l'abbinamento del plug-in VDI non riesce, nell'icona in basso a destra viene visualizzata una "X" rossa come mostrato di seguito:

![Icona di Lync VDI che mostra un accoppiamento corretto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icona di Lync VDI che mostra un accoppiamento corretto")

Di seguito vengono elencate le possibili cause degli errori e le azioni correttive che è possibile intraprendere.

  - **Sono state inserite credenziali non corrette durante l'accesso.**
    
    L'utente deve disconnettersi da Lync ed eseguire nuovamente l'accesso con le credenziali corrette. Verrà visualizzata di nuovo la finestra di dialogo di abbinamento che segnalerà se l'abbinamento è andato a buon fine.

  - **È in esecuzione un'altra istanza del client desktop remoto.**
    
    Se si utilizza la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:
    
    1.  Avviare Gestione attività: premere **Alt+Ctrl+Canc** e quindi fare clic su **Avvia Gestione attività**.
    
    2.  Fare clic sulla scheda **Processi** e cercare tutti i processi denominati **mstsc.exe** nell'elenco.
    
    3.  Selezionare ogni processo **mstsc.exe** e fare clic su **Termina processo**.
    
    4.  Avviare una nuova sessione di desktop remoto e riprovare a connettersi.

  - **I file necessari non sono installati correttamente.**
    
    Dopo aver installato il plug-in nel computer locale, è necessario che i file seguenti siano presenti in C\\: Program\\Files Microsoft\\Office Office15 (o la lettera di unità appropriata):
    
      - LyncVdiPlugin. dll
    
      - UcVdi. dll
    
    In caso di problemi di abbinamento VDI, controllare che questi file siano presenti nel computer locale.

  - **Il client Lync è in esecuzione nel computer locale.**
    
    Per utilizzare il plug-in di Lync VDI, non è necessario che un client Lync sia in esecuzione nel computer locale, altrimenti l'accoppiamento avrà esito negativo. Come procedura consigliata, l'utente non deve installare un client Lync nel computer locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

