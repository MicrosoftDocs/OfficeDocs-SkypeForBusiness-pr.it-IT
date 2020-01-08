---
title: 'Lync Server 2013: Requisiti tecnici per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c03c3b99e911766d2c60eec2a5515b3750d29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Requisiti tecnici per il parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

Questa sezione descrive i requisiti tecnici seguenti per il parcheggio delle chiamate:

  - Requisiti hardware

  - Requisiti software

  - Requisiti della porta

  - Requisiti per i file audio

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

L'applicazione Call Park ha gli stessi requisiti hardware dei server front-end. Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

L'applicazione Call Park ha gli stessi requisiti del sistema operativo e i prerequisiti software come server front-end. Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Tutti i server front-end e i server Standard Edition in cui è distribuita l'applicazione Parcheggio di chiamata devono avere installato Windows Media Format Runtime per i server che utilizzano Windows Server 2008 R2 o Microsoft Media Foundation per i server che utilizzano Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows. Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che chiamano Play Park per la musica in attesa.

</div>

<div>

## <a name="port-requirements"></a>Requisiti della porta

L'applicazione Call Park USA la porta seguente:

  - **Porta 5075**   usata per le richieste di ascolto SIP.

<div>


> [!NOTE]  
> Questa porta è un'impostazione predefinita che puoi modificare usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisiti per i file audio

L'applicazione Call Park supporta solo file con estensione WMA (Windows Media Audio) per la musica in attesa. È possibile usare Microsoft Expression Encoder 4 per personalizzare i file per la musica in attesa. Per scaricare Expression Encoder 4, vedere "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843). Usare lo strumento per convertire il file in un formato WMA. Il formato consigliato per i file musicali di Call Park-in-blocco è l'audio multimediale 9, 44 kHz, 16 bit, mono, CBR, 32 kbps.

<div>


> [!NOTE]  
> Il file convertito viene riprodotto al telefono solo a 16 kHz, anche se è stato registrato in 44 kHz.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

