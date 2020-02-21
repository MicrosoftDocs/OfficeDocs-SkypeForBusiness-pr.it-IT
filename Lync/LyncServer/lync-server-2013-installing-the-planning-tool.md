---
title: 'Lync Server 2013: installazione dello strumento di pianificazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5ba88a00ed00a36005f9c1a60806e18253d2ce1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a>Installazione dello strumento di pianificazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

Prima di iniziare la progettazione e la pianificazione dell'infrastruttura Lync Server 2013 utilizzando Microsoft Lync Server 2013, strumento di pianificazione, è necessario innanzitutto installare lo strumento di pianificazione. Non è necessario distribuire lo strumento di pianificazione su una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Lync Server 2013. Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'utilizzo dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono riportate in questo argomento per maggiore chiarezza.

<div>


> [!IMPORTANT]  
> Lo strumento di pianificazione richiede l'installazione da parte di un utente con autorizzazioni e diritti di amministratore nel computer in cui deve essere installato lo strumento.



</div>

I sistemi operativi supportati per l'installazione e l'esecuzione dello strumento di pianificazione sono i seguenti:

  - Windows 8

  - Windows 8.1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7, edizione a 32 bit

  - Windows 7, edizione a 64 bit con Windows on Win32 (WOW)

  - Windows Server 2008 R2, con WOW

Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4,5.

Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.

<div>

## <a name="to-install-the-planning-tool"></a>Per installare lo strumento di pianificazione

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Se si utilizza Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.

3.  Individuare il LyncPlanningTool. msi. In Esplora risorse fare doppio clic sul file. Nella finestra di comando, digitare il nome del file e quindi premere **invio** per eseguire il file.

4.  Nella pagina iniziale dell' **installazione guidata dello strumento di pianificazione di Microsoft Lync Server 2013**fare clic su **Avanti**.

5.  Leggere il **Contratto di Licenza con l'utente finale**, selezionare **Accetto i termini del Contratto di Licenza** se si sceglie di accettare le condizioni per l'utilizzo riportate nel contratto e quindi fare clic su **Avanti**.

6.  Scegliere dove installare i file dello strumento di pianificazione. Il percorso predefinito è C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool. Se si desidera cambiarlo, fare clic su **Cambia**. In **Modifica cartella di destinazione**, individuare o digitare il percorso in cui installare i file, fare clic su **OK** e quindi su **Avanti**.

7.  Il programma di installazione è ora pronto per installare lo strumento di pianificazione. Fare clic su **Installa** per avviare il processo di installazione.

8.  L'installazione verrà avviata e verrà visualizzato il relativo stato. Al termine dell'installazione, fare clic su **Fine**.

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

