---
title: Installare i sistemi operativi e il software prerequisito nei server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 266e8b049bd5de97fbb8f8d5d1e89b7280db3d4f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Installare i sistemi operativi e il software prerequisito sui server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-07-24_

Dopo aver configurato l'hardware e l'infrastruttura del sistema, è necessario installare i sistemi operativi e gli aggiornamenti Windows appropriati, oltre a tutti gli altri prerequisiti software, in ogni server che si desidera distribuire. Questo include ogni ruolo del server Lync Server 2013 e qualsiasi server o server dell'infrastruttura aggiuntivi che eseguono SQL Server necessari per la distribuzione.

<div>


> [!NOTE]
> In questa sezione viene descritta l'installazione dei sistemi operativi e del software prerequisito per i server interni. Se si distribuiscono server perimetrali per il supporto dell'accesso degli utenti esterni, è inoltre necessario installare i sistemi operativi e il software prerequisito per tali server, inclusi i server perimetrali e i server proxy inversi. Per informazioni dettagliate sulla preparazione dei server per il supporto dell'accesso degli utenti esterni, vedere <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">preparazione per l'installazione di server nella rete perimetrale per Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Installare il sistema operativo Windows nei server

In ogni server che si sta distribuendo, installare il sistema operativo Windows appropriato come indicato di seguito:

  - **Server che eseguono Lync Server 2013**   per informazioni dettagliate sui requisiti del sistema operativo per i server che eseguono Lync Server 2013, vedere [Server and Tools Operating System Support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

  - **Server di database**   per informazioni dettagliate sui requisiti del sistema operativo per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server. Per SQL Server 2012, vedere la documentazione in linea di SQL Server [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)2012 all'indirizzo.

<div>


> [!NOTE]
> Se si sta installando Lync Server 2013 su Windows&nbsp;server&nbsp;2008 R2 con SP1, è innanzitutto necessario installare l'aggiornamento descritto nell'articolo 2646886 della Microsoft Knowledge Base "FIX: l'heap danneggiati si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5", a <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>È inoltre necessario modificare il registro di sistema come descritto nell'articolo della Knowledge base, gli <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">ID evento 32402, 61045 vengono registrati nei server front end di Lync server 2013 installati in Windows Server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Installare l'aggiornamento di Windows nei server

Installare gli aggiornamenti seguenti da Windows Update su ogni server:

  - **Windows Update per i server che eseguono Lync Server 2013**   per informazioni dettagliate sugli aggiornamenti da Windows Update necessari per i server che eseguono Lync Server 2013, vedere [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

  - **Server di database**   per informazioni dettagliate sugli aggiornamenti da Windows Update necessari per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server 2012. Per SQL Server 2012, vedere la documentazione in linea di SQL Server [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)2012 all'indirizzo.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Installare altro software prerequisito nei server

Lync Server 2013 richiede l'installazione del software aggiuntivo seguente nei server:

  - **Software prerequisito per i server che eseguono Lync Server 2013**   i prerequisiti software aggiuntivi per i server che eseguono Lync Server 2013 dipendono dal ruolo del server in fase di distribuzione. Per informazioni dettagliate sui requisiti software specifici per ogni server, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

  - **Windows Identity Foundation**   Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare gli scenari di autenticazione da server a server. Per verificare che sia già stato installato nel computer, andare al pannello di controllo, fare clic su **programmi e funzionalità**, **visualizzare gli aggiornamenti installati**e guardare in **Microsoft Windows**. Per informazioni dettagliate sull'installazione di Windows Identity Foundation [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657), vedere.

  - **Microsoft .NET Framework 4,5**   l'edizione a 64 bit di Microsoft .NET Framework 4,5 è obbligatoria per Lync Server 2013.

  - **Software prerequisito per i server**   di database per informazioni dettagliate su Windows Update necessario per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)vedere la documentazione di SQL Server 2012 all'indirizzo.
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 installa automaticamente Microsoft SQL Server 2012 Express in ogni server Standard Edition e in ogni server che esegue Lync Server 2013 in cui si trova l'archivio di configurazione locale.

    
    </div>

  - **Runtime formato Windows Media**   tutti i Front End Server e i server Standard Edition in cui verrà distribuito il servizio di conferenza devono avere installato Windows Media Format Runtime. Runtime formato Windows Media è necessario per l'esecuzione di file Windows Media Audio (con estensione wma) riprodotti dalle applicazioni Parcheggio di chiamata, Annuncio e Response Group per gli annunci e la musica.
    
    <div>
    

    > [!NOTE]
    > Per Windows Server 2012 e Windows Server 2012 R2, il runtime del formato Windows Media viene installato con Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Per Windows Server&nbsp;2008 e windows server&nbsp;2008&nbsp;R2, il runtime del formato Windows Media viene installato come parte dell'esperienza desktop di Windows. È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013. Se Lync Server 2013 non trova questo software nel server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

