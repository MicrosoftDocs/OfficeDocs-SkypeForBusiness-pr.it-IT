---
title: 'Lync Server 2013: prerequisiti del plug-in VDI di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7be6cd7dcf58cae1cfe794c6a27d27fc5aaa5193
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Prerequisiti del plug-in VDI di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-03-07_

In un ambiente VDI (Virtual Desktop Infrastructure), le macchine virtuali e il computer locale dell'utente devono soddisfare i requisiti descritti in questa sezione.

<div>


> [!NOTE]  
> Per informazioni dettagliate su come installare e distribuire l'ambiente virtualizzato, fare riferimento al provider di soluzioni di virtualizzazione. Per informazioni sulla distribuzione di un ambiente virtualizzato basato su Hyper-V e Servizi Desktop remoto, vedere i seguenti articoli della Microsoft TechNet Library: 
> <UL>
> <LI>
> <P>Hyper-V in<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Servizi Desktop remoto in Windows Server&nbsp;2008&nbsp;R2 all'indirizzo<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

Di seguito sono elencati i requisiti per le macchine virtuali in esecuzione nel computer del Data Center:

  - Le macchine virtuali devono essere configurate con Windows 10, Windows 8,1, Windows 8, Windows 7 o Windows Server 2008 R2 con i Service Pack più recenti.

Di seguito sono elencati i requisiti per l'utente e il computer locale dell'utente:

  - L'utente deve essere ospitato in Lync Server 2013.

  - È necessario che il computer locale esegua Windows Embedded Standard 7 con SP1, Windows 7 con SP1, Windows 8, Windows 8,1 Embedded o Windows 8,1 (non incorporato).

  - Se si utilizzano Servizi Desktop remoto, il plug-in VDI di Lync bit (ovvero se l'applicazione è 32 bit o 64 bit) deve corrispondere al sistema operativo del computer locale bit. Non è necessario che la bit del sistema operativo nel computer locale e il sistema operativo della macchina virtuale corrispondano. Se si utilizza un'altra soluzione o piattaforma di virtualizzazione, fare riferimento alle indicazioni del provider di soluzioni di virtualizzazione sui requisiti di bit.

  - È necessario che il computer locale esegua la versione più recente del client desktop remoto. Installare gli aggiornamenti più recenti del client dei Servizi Desktop remoto da Microsoft o dall'ultimo software client desktop remoto dal provider di soluzioni di virtualizzazione. Per gli aggiornamenti più recenti dei Servizi Desktop remoto [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032), vedere.

  - Nel computer locale, è necessario configurare le impostazioni del client desktop remoto in modo che le riproduzioni audio sul computer locale e sulla registrazione remota siano disabilitate. Per configurare queste impostazioni per la connessione Desktop remoto in Windows, vedere la sezione successiva "per configurare le impostazioni di connessione Desktop remoto".

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>Per configurare le impostazioni di connessione Desktop remoto

Per preparare la connessione Desktop remoto in Windows per il plug-in VDI di Lync, attenersi alla seguente procedura.

1.  Se il computer locale esegue Windows 8, ignorare questo passaggio. Se il computer locale esegue Windows 7 con SP1, installare la versione più recente di Windows 8 del client Servizi Desktop remoto, disponibile all' [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)indirizzo.

2.  Avviare il client Servizi Desktop remoto facendo clic sul pulsante **Start**e quindi su **Connessione desktop remoto**.

3.  Fare clic su **Opzioni**.

4.  Fare clic sulla scheda **risorse locali** . In **audio remoto**fare clic su **Impostazioni**e quindi eseguire le operazioni seguenti:
    
      - In **riproduzione audio remota**selezionare **Riproduci su questo computer**.
    
      - In **registrazione audio remota**selezionare **non registrare**.
    
      - Fare clic su **OK**.

5.  Fare clic sulla scheda **Experience** . In **prestazioni**, deselezionare la casella di controllo relativa alla **memorizzazione nella cache della bitmap persistente** .

6.  Fare clic sulla scheda **generale** . In **computer**, digitare il nome della macchina virtuale, quindi fare clic su **Connetti**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

