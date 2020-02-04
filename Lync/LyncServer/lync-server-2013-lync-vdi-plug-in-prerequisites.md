---
title: 'Lync Server 2013: Prerequisiti del plug-in VDI di Lync'
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
ms.openlocfilehash: 51fb0081188618b6a5ea2951968effb0d55c4af7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Prerequisiti del plug-in VDI di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-03-07_

In un ambiente VDI (Virtual Desktop Infrastructure) le macchine virtuali e il computer locale dell'utente devono soddisfare i requisiti descritti in questa sezione.

<div>


> [!NOTE]  
> Per informazioni dettagliate su come installare e distribuire l'ambiente virtualizzato, vedere il provider di soluzioni di virtualizzazione. Per informazioni sulla distribuzione di un ambiente virtualizzato basato su Hyper-V e Servizi Desktop remoto, vedere gli articoli seguenti nella raccolta Microsoft TechNet: 
> <UL>
> <LI>
> <P>Hyper-V at<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Servizi Desktop remoto in Windows Server&nbsp;2008&nbsp;R2 at<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

Di seguito sono riportati i requisiti per le macchine virtuali in uso nel computer centro dati:

  - Le macchine virtuali devono essere configurate con Windows 10, Windows 8,1, Windows 8, Windows 7 o Windows Server 2008 R2 con i Service Pack più recenti.

Di seguito sono riportati i requisiti per l'utente e il computer locale dell'utente:

  - L'utente deve essere ospitato in Lync Server 2013.

  - Il computer locale deve eseguire Windows Embedded Standard 7 con SP1, Windows 7 con SP1, Windows 8, Windows 8,1 Embedded o Windows 8,1 (non incorporato).

  - Se si usano servizi desktop remoto, il plug-in di Lync VDI bit, ovvero se l'applicazione è di 32 bit o 64 bit, deve corrispondere al sistema operativo del computer locale bit. Non è necessario che la bit del sistema operativo nel computer locale e il sistema operativo della macchina virtuale corrispondano. Se si usa un'altra soluzione di virtualizzazione o una piattaforma, vedere le indicazioni del provider di soluzioni di virtualizzazione sui requisiti di bit.

  - Il computer locale deve eseguire la versione più recente del client desktop remoto. Installare gli aggiornamenti più recenti del client di Servizi Desktop remoto da Microsoft o dal software client desktop remoto più recente del provider di soluzioni di virtualizzazione. Per gli aggiornamenti più recenti di Servizi Desktop remoto [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032), vedere.

  - Nel computer locale le impostazioni client desktop remoto devono essere configurate in modo che le riproduzioni audio nel computer locale e la registrazione remota siano disattivate. Per configurare queste impostazioni per la connessione Desktop remoto in Windows, vedere la sezione successiva "per configurare le impostazioni di connessione Desktop remoto".

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>Per configurare le impostazioni di connessione Desktop remoto

Per preparare la connessione Desktop remoto in Windows per il plug-in Lync VDI, seguire questa procedura.

1.  Se il computer locale è in uso in Windows 8, ignorare questo passaggio. Se nel computer locale è in esecuzione Windows 7 con SP1, installare la versione più recente di Windows 8 del client di Servizi Desktop remoto [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032), disponibile all'indirizzo.

2.  Avviare il client Servizi Desktop remoto facendo clic su **Start**e quindi su **Connessione desktop remoto**.

3.  Fare clic su **Opzioni**.

4.  Fare clic sulla scheda **risorse locali** . In **audio remoto**fare clic su **Impostazioni**e quindi eseguire le operazioni seguenti:
    
      - In **riproduzione audio remota**selezionare **Riproduci in questo computer**.
    
      - In **registrazione audio remota**selezionare non **registrare**.
    
      - Fare clic su **OK**.

5.  Fare clic sulla scheda **esperienza** . In **prestazioni**deselezionare la casella di controllo **memorizzazione nella cache persistente della bitmap** .

6.  Fare clic sulla scheda **generale** . In **computer**Digitare il nome della macchina virtuale e quindi fare clic su **Connetti**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

