---
title: "Lync Server 2013: requisiti tecnici per l'applicazione annuncio"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a1a752159f27cf2d1bdadc149c2f26131c5ab06
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Requisiti tecnici per l'applicazione annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

In questa sezione vengono descritti i requisiti tecnici seguenti per l'applicazione annuncio:

  - Requisiti hardware

  - Requisiti software

  - Requisiti delle porte

  - Requisiti dei file audio

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

L'applicazione annuncio ha gli stessi requisiti hardware dei Front End Server. Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

L'applicazione annuncio ha gli stessi requisiti del sistema operativo e i prerequisiti software dei Front End Server. Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Tutti i Front End Server o i server Standard Edition che eseguono l'applicazione annuncio devono disporre del runtime del formato Windows Media per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, il runtime del formato Windows Media viene installato come parte dell'esperienza desktop di Windows. Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file Windows Media Audio (con estensione WMA) che l'applicazione annuncio riproduce per gli annunci e la musica.

</div>

<div>

## <a name="port-requirements"></a>Requisiti delle porte

L'applicazione annuncio utilizza la porta seguente:

  - **Porta 5071**   utilizzata per le richieste di attesa SIP

<div>


> [!NOTE]  
> Questa porta è l'impostazione predefinita, che può essere modificata utilizzando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Annuncio supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (. WMA) per la musica e gli annunci. I requisiti dei file audio per l'applicazione annuncio sono identici a quelli dell'applicazione Response Group. Per informazioni dettagliate, vedere [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

