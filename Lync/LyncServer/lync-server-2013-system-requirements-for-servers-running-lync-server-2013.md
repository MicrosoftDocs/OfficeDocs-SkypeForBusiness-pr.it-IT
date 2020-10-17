---
title: 'Lync Server 2013: requisiti di sistema per i server che eseguono Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d25be2132fdaba58024ba58081656b830ea9fe4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497333"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Requisiti di sistema per i server che eseguono Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-07-24_

<div>


> [!NOTE]
> Per informazioni dettagliate sui requisiti hardware, vedere <A href="lync-server-2013-server-hardware-platforms.md">server hardware Platforms for Lync server 2013</A>.



</div>

I server Standard Edition e Enterprise Edition condividono gli stessi requisiti software.

I server che eseguono Lync Server 2013, Enterprise Edition sono progettati per le organizzazioni di grandi dimensioni come principale distribuzione organizzativa. Il Server Enterprise è progettato per consentire la scalabilità di circa 80.000 utenti che risiedono in ogni pool. I server che eseguono Lync Server 2013, Standard Edition sono destinati a organizzazioni di piccole dimensioni e a percorsi remoti dalla distribuzione dell'organizzazione principale. Una coppia di server Standard Edition è in grado di supportare fino a 5.000 utenti. Per informazioni dettagliate sulle differenze tra i server Standard Edition e i server Enterprise Edition, vedere [Deployment Overview for Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Installazione del sistema operativo

<div>


> [!IMPORTANT]
> Lync Server 2013 è disponibile solo in un'edizione a 64 bit, che richiede hardware a 64 bit e un'edizione a 64 bit del sistema operativo Windows Server. L'edizione a 32 bit di Lync Server 2013 non è disponibile con questa versione.



</div>

Il server Standard Edition e Enterprise Edition è in grado di utilizzare una delle opzioni seguenti:

  - Windows Server 2008 R2 SP1 o Service Pack più recente

  - Windows Server 2012

  - Windows Server 2012 R2

Installare il software del sistema operativo nel server Standard Edition o Enterprise Edition Front End Server. Applicare tutti gli aggiornamenti per portare il sistema operativo al livello di aggiornamento più recente necessario in base agli standard dell'organizzazione. Per ulteriori informazioni sui requisiti operativi, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

> [!NOTE] 
> L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013.  È necessario distribuire un pool separato ed eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso.

<div>


> [!NOTE]
> Affinché Lync Server 2013 funzioni su Windows Server 2012 R2, potrebbe essere necessario modificare il valore di una chiave del registro di sistema in Windows Server. Questa modifica potrebbe essere necessaria affinché i certificati funzionino correttamente e i client possano registrarsi con Survivable Branch Appliance. Per ulteriori informazioni, vedere <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Software aggiuntivo per Lync Server 2013

Oltre agli aggiornamenti necessari per il sistema operativo, Lync Server 2013 richiede ruoli del sistema operativo, funzionalità e software per l'utilizzo. Per informazioni dettagliate sul software aggiuntivo che deve essere installato prima di pubblicare la topologia e l'installazione di Lync Server 2013, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Software aggiuntivo necessario per tutti i ruoli del server

In tutti i ruoli del server, è inoltre necessario verificare che l'interfaccia della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 siano installati.

Inoltre, l'interfaccia della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 sono necessari in tutti i computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 richiede l'installazione di Windows PowerShell 3,0 su ogni computer che prenderà parte alla topologia di Lync Server. Per informazioni dettagliate sull'installazione di Windows PowerShell 3,0, vedere [Installing Windows powershell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]
> In Windows Server &nbsp; 2008 &nbsp; R2 con SP1, l'interfaccia della riga di comando di windows PowerShell 3,0 non può essere installata prima dell'installazione di Microsoft .net Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Quando si installa Microsoft .NET Framework 4,5 nei server che eseguiranno Lync Server 2013 su Windows Server 2012 o Windows Server 2012 R2, è necessario eseguire un ulteriore passaggio. Dopo l'installazione di .NET Framework 4,5, utilizzare Server Manager per installare l'attivazione HTTP.

**Per installare l'attivazione di .NET 4,5 HTTP su Windows Server 2012 o Windows Server 2012 R2**

1.  Fare clic sul pulsante **Start** , scegliere **programmi**, quindi **strumenti di amministrazione**e quindi fare clic su **Server Manager**.

2.  In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.

3.  Espandere **.NET Framework 4,5**.

4.  Selezionare **attivazione WCF** se non è già selezionata. Quindi selezionare **attivazione http**.

5.  Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

