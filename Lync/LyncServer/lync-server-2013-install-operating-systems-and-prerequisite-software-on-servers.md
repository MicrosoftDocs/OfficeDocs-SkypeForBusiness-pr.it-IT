---
title: Installare i sistemi operativi e il software prerequisito nei server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Installare i sistemi operativi e il software prerequisito nei server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-07-24_

Dopo aver configurato l'infrastruttura hardware e di sistema, è necessario installare i sistemi operativi e gli aggiornamenti appropriati di Windows, oltre a tutti gli altri software prerequisiti in ogni server che si sta distribuendo. Questo include ogni ruolo del server Lync Server 2013 e tutti i server di infrastruttura o i server aggiuntivi che esegue SQL Server necessari per la distribuzione.

<div>


> [!NOTE]
> Questa sezione descrive l'installazione di sistemi operativi e software prerequisito per i server interni. Se si distribuisce Edge Server per supportare l'accesso degli utenti esterni, è necessario installare anche sistemi operativi e software prerequisito per questi server, inclusi i server perimetrali e i server proxy inverso. Per informazioni dettagliate sulla preparazione dei server per il supporto dell'accesso degli utenti esterni, vedere <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">preparazione per l'installazione di server nella rete perimetrale per Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Installare sistemi operativi Windows nei server

In ogni server che si sta distribuendo installare il sistema operativo Windows appropriato nel modo seguente:

  - **Server che effettuano Lync Server 2013**   per informazioni dettagliate sui requisiti del sistema operativo per i server che utilizzano Lync Server 2013, vedere [supporto dei sistemi operativi per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

  - **Server di database**   per informazioni dettagliate sui requisiti di sistema operativo per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server. Per SQL Server 2012, vedere la documentazione online di [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)sql Server 2012.

<div>


> [!NOTE]
> Se si sta installando Lync Server 2013 in Windows&nbsp;server&nbsp;2008 R2 con SP1, è necessario installare prima di tutto l'aggiornamento descritto nell'articolo della Microsoft Knowledge based 2646886, "FIX: il danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5", at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>È inoltre necessario modificare il registro di sistema come descritto nell'articolo della Knowledge fine, gli <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">ID evento 32402, 61045 vengono registrati nei server front end di Lync server 2013 installati in Windows Server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Installare Windows Update nei server

Installare gli aggiornamenti seguenti da Windows Update in ogni server:

  - **Windows Update per i server che esegue Lync Server 2013**   per informazioni dettagliate sugli aggiornamenti di Windows Update necessari per i server che usano Lync Server 2013, vedere [requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

  - **Server di database**   per informazioni dettagliate sugli aggiornamenti di Windows Update necessari per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, vedere la documentazione di SQL Server 2012. Per SQL Server 2012, vedere la documentazione online di [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)sql Server 2012.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Installare altri software prerequisiti nei server

Lync Server 2013 richiede l'installazione del software aggiuntivo seguente nei server:

  - **Software prerequisito per i server che utilizzano Lync Server 2013**   i prerequisiti software aggiuntivi per i server che utilizzano Lync Server 2013 dipendono dal ruolo del server distribuito. Per informazioni dettagliate sui requisiti software specifici per ogni server, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.

  - **Windows Identity Foundation**   Lync Server 2013 richiede l'installazione di Windows Identity Foundation per supportare scenari di autenticazione da server a server. Per verificare che sia già stato installato nel computer, aprire il pannello di controllo, fare clic su **programmi e funzionalità**, **visualizzare gli aggiornamenti installati**e cercare in **Microsoft Windows**. Per informazioni dettagliate sull'installazione di Windows Identity Foundation [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657), vedere.

  - **Microsoft .NET Framework 4,5**   è necessaria la versione a 64 bit di Microsoft .NET Framework 4,5 per Lync Server 2013.

  - **Software prerequisito per i server**   di database per informazioni dettagliate sul Windows Update necessario per i server di database, inclusi il database back-end, il database di archiviazione e il database di monitoraggio, [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)vedere la documentazione di SQL Server 2012.
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 installa automaticamente Microsoft SQL Server 2012 Express in ogni server Standard Edition e ogni server in cui è in uso Lync Server 2013 in cui si trova l'archivio di configurazione locale.

    
    </div>

  - **Windows Media Format Runtime**   tutti i server front-end e i server Standard Edition in cui verranno distribuiti i servizi di conferenza devono avere installato Windows Media Format Runtime. Windows Media Format Runtime è necessario per eseguire i file di Windows Media Audio (con estensione WMA) che vengono riprodotti dalle applicazioni Park, annuncio e Response Group per gli annunci e la musica.
    
    <div>
    

    > [!NOTE]
    > Per Windows Server 2012 e Windows Server 2012 R2 Windows Media Format Runtime viene installato con Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Per Windows Server&nbsp;2008 e windows server&nbsp;2008&nbsp;R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows. È consigliabile installare Windows Desktop Experience prima di installare Lync Server 2013. Se Lync Server 2013 non trova il software sul server, verrà richiesto di installarlo e quindi sarà necessario riavviare il server per completare l'installazione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

