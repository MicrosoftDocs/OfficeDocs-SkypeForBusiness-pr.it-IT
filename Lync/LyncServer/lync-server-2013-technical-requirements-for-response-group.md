---
title: 'Lync Server 2013: requisiti tecnici per Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b07ddfa11f23c7e5183c243020c441db7219660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Requisiti tecnici per Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

In questa sezione vengono descritti i requisiti tecnici seguenti per l'applicazione Response Group:

  - Requisiti hardware

  - Requisiti software

  - Requisiti delle porte

  - Requisiti dei file audio

  - Requisiti dello strumento di configurazione di Response Group

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

L'applicazione Response Group ha gli stessi requisiti hardware dei Front End Server. Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

L'applicazione Response Group ha gli stessi requisiti del sistema operativo e i prerequisiti software dei Front End Server. Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Se si utilizzano file di Windows Media Audio (con estensione WMA) per la musica e gli annunci di Response Group, tutti i Front End Server o i server Standard Edition che eseguono l'applicazione Response Group devono disporre del runtime di Windows Media Format installato per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime è installato come parte dell'esperienza desktop di Windows.

Per ulteriori dettagli sui requisiti audio, vedere "Requisiti dei file audio" più avanti in questa sezione.

</div>

<div>

## <a name="port-requirements"></a>Requisiti delle porte

L'applicazione Response Group utilizza le porte seguenti:

  - **Porta 5071**   utilizzata per le richieste di attesa SIP

  - **Porta 8404**   utilizzata per le comunicazioni tra server
    
    <div>
    

    > [!NOTE]  
    > Questa porta viene utilizzata per il servizio di ricerca delle corrispondenze ed è necessaria quando l'applicazione Response Group viene distribuita in un pool con più server front-end.

    
    </div>

<div>


> [!NOTE]  
> Tali porte vengono utilizzate per impostazione predefinita e possono essere cambiate mediante il cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Response Group supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (. WMA) per i messaggi di Response Group, la musica di attesa o le domande del sistema IVR (Interactive Voice Response).

Il formato di file Windows Media Audio richiede che il runtime del formato Windows Media sia installato nei front end server che eseguono Windows Server 2008 R2 e Windows Server 2008. Per ulteriori dettagli, vedere i "Requisiti software" presi già in esame in questa sezione.

<div>

## <a name="supported-wave-file-formats"></a>Formati di file wave supportati

Tutti i file wave devono soddisfare i requisiti seguenti:

  - File a 8 bit o a 16 bit

  - LPCM (Linear Pulse Code Modulation), formato A-Law o mu-Law

  - Mono o stereo

  - Massimo 4 MB

Per ottenere prestazioni ottimali con i file wave, è consigliabile utilizzare un file wave mono a 16 bit e 16 kHz.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Formati di file Windows Media Audio supportati

Se si utilizza un file Windows Media Audio, è consigliabile utilizzare velocità in bit basse e verificare le prestazioni del sistema sotto carico.

Per convertire un file nel formato Windows Media Audio, è possibile utilizzare Microsoft Expression Encoder 4. Per scaricare Expression Encoder 4, vedere [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Requisiti dello Strumento di configurazione Response Group

Lo strumento di configurazione di Response Group supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.

<div>


> [!NOTE]  
> Sono supportate sia le versioni a 32 bit che a 64 bit dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemi operativi e Web browser supportati

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operativo</th>
<th>Web browser</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista con Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 con Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>Console degli agenti di Response Group

La console degli agenti supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.

<div>


> [!NOTE]  
> Sono supportate sia le versioni a 32 bit che a 64 bit dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemi operativi e Web browser supportati

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operativo</th>
<th>Web browser</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista con Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 con Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 con Service Pack 1</p></td>
<td><p>Internet Explorer 8 (modalità nativa)</p>
<p>Internet Explorer 9 (modalità nativa)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

