---
title: 'Lync Server 2013: Requisiti tecnici per i Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd87cb270d527753d9c6404ded4162791b542f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Requisiti tecnici per i Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

In questa sezione vengono descritti i requisiti tecnici seguenti per l'applicazione Response Group:

  - Requisiti hardware

  - Requisiti software

  - Requisiti della porta

  - Requisiti per i file audio

  - Requisiti dello strumento di configurazione dei gruppi di risposta

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

L'applicazione Response Group ha gli stessi requisiti hardware dei server front-end. Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

L'applicazione Response Group offre gli stessi requisiti del sistema operativo e i prerequisiti software come server front-end. Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Se si usano file di Windows Media Audio (con estensione WMA) per la musica e gli annunci di Response Group, tutti i server front-end o le edizioni standard che eseguono l'applicazione Response Group devono avere installato Windows Media Format Runtime per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per server che utilizzano Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.

Per altre informazioni sui requisiti audio, vedere "requisiti per i file audio" più avanti in questa sezione.

</div>

<div>

## <a name="port-requirements"></a>Requisiti della porta

L'applicazione Response Group usa le porte seguenti:

  - **Porta 5071**   usata per le richieste di ascolto SIP

  - **Porta 8404**   usata per le comunicazioni interserver
    
    <div>
    

    > [!NOTE]  
    > Questa porta viene usata per il servizio di creazione delle corrispondenze ed è necessaria quando l'applicazione Response Group viene distribuita in un pool che ha più di un server front-end.

    
    </div>

<div>


> [!NOTE]  
> Queste porte sono impostazioni predefinite che è possibile modificare usando il cmdlet <STRONG>Set-CsApplicationServer</STRONG> . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Requisiti per i file audio

L'applicazione Response Group supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (con estensione WMA) per i messaggi di Response Group, la musica in attesa o le domande di risposta vocale interattiva (IVR).

Il formato di file audio Windows Media richiede che Windows Media Format Runtime sia installato nei server front-end in cui è in esecuzione Windows Server 2008 R2 e Windows Server 2008. Per altri dettagli, vedere "requisiti software" in questa sezione.

<div>

## <a name="supported-wave-file-formats"></a>Formati di file Wave supportati

Tutti i file Wave devono soddisfare i requisiti seguenti:

  - file a 8 bit o a 16 bit

  - Modulazione del codice pulsazione lineare (LPCM), A-Law o mu-Law Format

  - Mono o stereo

  - 4 MB o meno

Per ottenere prestazioni ottimali, è consigliabile un file Wave da 16 kHz, mono e a 16 bit.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Formati di file audio Windows Media supportati

Se si usa un file audio Windows Media, valutare l'uso di velocità in bit bassi e verificare le prestazioni del sistema in Load.

Puoi usare Microsoft Expression Encoder 4 per convertire un file nel formato audio di Windows Media. Per scaricare Expression Encoder 4, vedere [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Requisiti dello strumento di configurazione dei gruppi di risposta

Lo strumento di configurazione Response Group supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.

<div>


> [!NOTE]  
> sono supportate le versioni a 32 bit o a bit 64 dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemi operativi e browser Web supportati

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

## <a name="response-group-agent-console"></a>Console agente di Response Group

La console agente supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.

<div>


> [!NOTE]  
> sono supportate le versioni a 32 bit o a bit 64 dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemi operativi e browser Web supportati

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
<p>Firefox 10,0</p>
<p>Chrome 18,0</p></td>
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
<p>Firefox 10,0</p>
<p>Chrome 18,0</p></td>
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

