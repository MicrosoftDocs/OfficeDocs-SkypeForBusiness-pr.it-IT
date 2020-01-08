---
title: 'Lync Server 2013: Installazione dello strumento di pianificazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e528062d5fd04e1a11df934cbc01b2dc8c92aa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a>Installazione dello strumento di pianificazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

Prima di iniziare a progettare e pianificare l'infrastruttura di Lync Server 2013 utilizzando Microsoft Lync Server 2013, strumento di pianificazione, è necessario prima di tutto installare lo strumento di pianificazione. Lo strumento di pianificazione non deve essere distribuito in una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Lync Server 2013. Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'uso dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono duplicate qui per chiarezza.

<div>


> [!IMPORTANT]  
> Lo strumento di pianificazione richiede l'installazione da parte di un utente con diritti e autorizzazioni di amministratore nel computer in cui deve essere installato lo strumento.



</div>

I sistemi operativi supportati per l'installazione e il funzionamento dello strumento di pianificazione sono i seguenti:

  - Windows 8

  - Windows 8.1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7, 32 bit Edition

  - Windows 7, 64 bit Edition con Windows su Win32 (WOW)

  - Windows Server 2008 R2 con WOW

Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4,5.

Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.

<div>

## <a name="to-install-the-planning-tool"></a>Per installare lo strumento di pianificazione

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Usando Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.

3.  Individuare il file LyncPlanningTool. msi. In Esplora risorse fare doppio clic sul file. Nella finestra di comando digitare il nome del file e quindi premere **invio** per eseguire il file.

4.  Nella pagina di benvenuto di **Microsoft Lync Server 2013, configurazione guidata strumento di pianificazione**, fare clic su **Avanti**.

5.  Esaminare il **contratto di licenza con l'utente finale**, selezionare **Accetto i termini del contratto di licenza** se si sceglie di accettare le condizioni per l'uso nel contratto di licenza e quindi fare clic su **Avanti**.

6.  Scegliere la posizione in cui installare i file dello strumento di pianificazione. Il percorso predefinito è C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool. Se si vuole modificare il percorso di installazione, fare clic su **Cambia**. In **modifica cartella di destinazione**selezionare o digitare la posizione in cui installare i file, fare clic su **OK**e quindi su **Avanti**.

7.  Il programma di installazione è ora pronto per l'installazione dello strumento di pianificazione. Fare clic su **Installa** per avviare il processo di installazione.

8.  L'installazione verrà avviata e verrà visualizzato lo stato di avanzamento. Dopo aver completato l'installazione, fare clic su **fine**.

9.  Lo strumento di pianificazione è pronto per l'uso.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Installazione di software facoltativo in Lync Server 2013](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

