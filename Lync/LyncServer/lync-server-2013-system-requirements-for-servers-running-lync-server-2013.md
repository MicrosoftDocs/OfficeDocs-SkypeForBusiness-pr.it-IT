---
title: 'Lync Server 2013: Requisiti di sistema per i server Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 301cd234e2218fc806423a9ffe9beb49994402f2
ms.sourcegitcommit: 208179a3dd166f53b5a3058242cb84207909f4ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2020
ms.locfileid: "41104495"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Requisiti di sistema per i server Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-07-24_

<div>


> [!NOTE]  
> Per informazioni dettagliate sui requisiti hardware, vedere <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware server per Lync server 2013</A>.



</div>

I server Standard Edition e Enterprise Edition condividono gli stessi requisiti software.

I server che usano Lync Server 2013 Enterprise Edition sono destinati alle organizzazioni di grandi dimensioni come principale distribuzione dell'organizzazione. Enterprise Edition Server è progettato per scalare fino a circa 80.000 utenti ospitati per ogni pool. I server che usano Lync Server 2013, Standard Edition sono destinati a organizzazioni più piccole e a posizioni remote dalla distribuzione principale dell'organizzazione. Una coppia di server Standard Edition può supportare fino a 5.000 utenti. Per informazioni dettagliate sulle differenze tra i server Standard Edition e i server Enterprise Edition, vedere [Panoramica della distribuzione per Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Installazione del sistema operativo

<div>


> [!IMPORTANT]  
> Lync Server 2013 è disponibile solo in una versione a 64 bit, che richiede hardware a 64 bit e un'edizione a 64 bit del sistema operativo Windows Server. Una versione di 32 bit di Lync Server 2013 non è disponibile con questo rilascio.



</div>

Standard Edition e Enterprise Edition Server possono usare una delle opzioni seguenti:

  - Windows Server 2008 R2 SP1 o Service Pack più recente

  - Windows Server 2012

  - Windows Server 2012 R2

Installare il software del sistema operativo nel server Standard Edition o nel front-end di Enterprise Edition. Applica tutti gli aggiornamenti per riportare il sistema operativo all'aggiornamento più recente e al livello di aggiornamento richiesto coerente con gli standard dell'organizzazione. Per altre informazioni sui requisiti operativi, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

> [!NOTE] L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013.  È necessario distribuire un pool separato e eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso.

<div>


> [!NOTE]  
> Per Lync Server 2013 per l'utilizzo in Windows Server 2012 R2, potrebbe essere necessario modificare il valore di una chiave del registro di sistema in Windows Server. Questa modifica può essere necessaria affinché i certificati funzionino correttamente e i client vengano registrati con Survivable Branch Appliances. Per altre informazioni, vedere <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Software aggiuntivo per Lync Server 2013

Oltre agli aggiornamenti necessari per il sistema operativo, Lync Server 2013 richiede l'uso di ruoli, funzionalità e software del sistema operativo. Per informazioni dettagliate sul software aggiuntivo che deve essere installato prima di pubblicare la topologia e installare Lync Server 2013, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Software aggiuntivo necessario per tutti i ruoli del server

In tutti i ruoli del server devi anche verificare che l'interfaccia della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 siano installati.

Inoltre, le interfacce della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 sono necessarie in qualsiasi computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3,0

Lync Server 2013 richiede l'installazione di Windows PowerShell 3,0 in ogni computer che prenderà parte alla topologia di Lync Server. Per informazioni dettagliate sull'installazione di Windows PowerShell 3,0, vedere [installazione di Windows powershell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]  
> In Windows Server&nbsp;2008&nbsp;R2 con SP1 l'interfaccia della riga di comando di Windows PowerShell 3,0 non può essere installata prima di installare Microsoft .NET Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4,5

Quando si installa Microsoft .NET Framework 4,5 nei server in cui viene eseguito Lync Server 2013 in Windows Server 2012 o Windows Server 2012 R2, è necessario eseguire un ulteriore passaggio. Dopo l'installazione di .NET Framework 4,5, usare Server Manager per installare l'attivazione HTTP.

**Per installare l'attivazione HTTP di .NET 4,5 in Windows Server 2012 o Windows Server 2012 R2**

1.  Nel menu **Start** fare clic su **programmi**, quindi su **strumenti di amministrazione**e quindi su **Gestione server**.

2.  In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.

3.  Espandere **.NET Framework 4,5**.

4.  Selezionare l' **attivazione di WCF** se non è già selezionata. Quindi seleziona **attivazione http**.

5.  Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

