---
title: 'Lync Server 2013: requisiti tecnici per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b5fb5f86dd575daf603bd0a21235184346bca05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533953"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Requisiti tecnici per il parcheggio di chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

In questa sezione vengono descritti i requisiti tecnici seguenti per il parcheggio di chiamata:

  - Requisiti hardware

  - Requisiti software

  - Requisiti delle porte

  - Requisiti dei file audio

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

L'applicazione Parcheggio di chiamata ha gli stessi requisiti hardware dei Front End Server. Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

L'applicazione Parcheggio di chiamata ha gli stessi requisiti del sistema operativo e i prerequisiti software dei Front End Server. Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Tutti i Front End Server e i server Standard Edition in cui è distribuita l'applicazione Parcheggio di chiamata devono disporre del runtime del formato Windows Media per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime è installato come parte dell'esperienza desktop di Windows. Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file Windows Media Audio (. WMA) che il parcheggio di chiamata gioca per la musica di attesa.

</div>

<div>

## <a name="port-requirements"></a>Requisiti delle porte

L'applicazione Parcheggio di chiamata utilizza la porta seguente:

  - **Porta 5075**     Utilizzato per le richieste di attesa SIP.

<div>


> [!NOTE]  
> Questa porta è un'impostazione predefinita che può essere modificata usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Parcheggio di chiamata supporta solo i file di Windows Media Audio (WMA) per la musica di attesa. Per personalizzare i file per la musica di attesa, è possibile usare Microsoft Expression Encoder 4. Per scaricare Expression Encoder 4, vedere "Expression Encoder 4" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) . Utilizzare lo strumento per convertire il file in un formato wma. Il formato consigliato per i file musicali del parcheggio di chiamata è media audio 9, 44 kHz, 16 bit, mono, CBR, 32 kbps.

<div>


> [!NOTE]  
> Il file convertito viene riprodotto nel telefono solo a 16 kHz, anche se è stato registrato a 44 kHz.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

