---
title: 'Lync Server 2013: risoluzione dei problemi relativi al plug-in di Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7afaa0067e4ca06f8bb40ff201b090a45c66f442
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Risoluzione dei problemi relativi al plug-in di Lync VDI in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Risoluzione dei problemi relativi all'installazione del plug-in di Lync VDI in un thin client

In caso di problemi con l'installazione del plug-in VDI in un thin client, vedere quanto segue:

  - Verificare che nella cartella specificata nelle variabili di sistema TEMP e TMP sia disponibile spazio sufficiente.

  - Verificare che la protezione da scrittura sia disattivata. Per istruzioni, vedere la documentazione del produttore del dispositivo.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Risoluzione dei problemi di associazione

Quando l'associazione del plug-in VDI non riesce, l'icona di associazione nell'angolo in basso a destra viene visualizzata come "X" rossa, come illustrato di seguito:

![Icona di Lync VDI che mostra l'associazione corretta]di(images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI con l'associazione corretta")

Di seguito sono riportate le possibili cause degli errori e le azioni correttive che è possibile eseguire.

  - **L'utente ha immesso credenziali non corrette durante l'accesso.**
    
    L'utente deve disconnettersi da Lync ed eseguire di nuovo l'accesso con le credenziali corrette. La finestra di dialogo Associazione verrà ricomparsa e mostrerà se l'associazione ha esito positivo.

  - **È in corso un'altra istanza del client desktop remoto.**
    
    Se si usa la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:
    
    1.  Avviare Task Manager: premere **ALT + CTRL + CANC**e quindi fare clic su **Avvia Gestione attività**.
    
    2.  Fare clic sulla scheda **processi** e cercare tutti i processi denominati **mstsc. exe** nell'elenco.
    
    3.  Evidenziare ogni processo **mstsc. exe** e quindi fare clic su **Termina processo**.
    
    4.  Avviare una nuova sessione di desktop remoto e riprovare a connettersi.

  - **I file necessari non sono stati installati correttamente.**
    
    Dopo aver installato il plug-in nel computer locale, i file seguenti devono essere presenti in C:\\programmi\\Microsoft Office\\Office15 (o la lettera di unità appropriata):
    
      - LyncVdiPlugin. dll
    
      - UcVdi. dll
    
    In caso di problemi con l'associazione VDI, verificare che questi file siano presenti nel computer locale.

  - **Il client Lync è in uso nel computer locale.**
    
    Per usare il plug-in di Lync VDI, non è necessario che un client Lync sia in esecuzione nel computer locale, altrimenti l'associazione non riuscirà. Come procedura consigliata, l'utente non deve installare un client Lync nel computer locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

