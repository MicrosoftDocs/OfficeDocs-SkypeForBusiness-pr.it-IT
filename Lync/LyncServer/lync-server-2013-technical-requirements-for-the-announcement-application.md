---
title: "Lync Server 2013: Requisiti tecnici per l'applicazione Annuncio"
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
ms.openlocfilehash: 8812dca81d656e68fc506c4a87c3c80481040bf6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Requisiti tecnici per l'applicazione Annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

Questa sezione descrive i requisiti tecnici seguenti per l'applicazione di annuncio:

  - Requisiti hardware

  - Requisiti software

  - Requisiti della porta

  - Requisiti per i file audio

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

L'applicazione di annuncio ha gli stessi requisiti hardware dei server front-end. Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

L'applicazione di annuncio ha gli stessi requisiti di sistema operativo e prerequisiti software come server front-end. Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Tutti i server front-end o i server Standard Edition che eseguono l'applicazione annunci devono avere installato Windows Media Format Runtime per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows. Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che l'applicazione di annuncio riproduce per gli annunci e la musica.

</div>

<div>

## <a name="port-requirements"></a>Requisiti della porta

L'applicazione di annuncio usa la porta seguente:

  - **Porta 5071**   usata per le richieste di ascolto SIP

<div>


> [!NOTE]  
> Questa porta è l'impostazione predefinita, che può essere modificata usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisiti per i file audio

L'applicazione di annuncio supporta il formato di file Wave (con estensione wav) e il formato di file WMA (Windows Media Audio) per musica e annunci. I requisiti per i file audio per l'applicazione di annuncio sono gli stessi per l'applicazione Response Group. Per informazioni dettagliate, vedere [requisiti tecnici per il gruppo di risposte in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

