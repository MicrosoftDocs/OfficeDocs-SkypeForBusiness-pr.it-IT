---
title: Requisiti di IIS per pool Front End e server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d804df614eab49eeabe82cca9d304e082d9ced3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Requisiti di IIS per pool Front End e server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-19_

Per i server standard e i server front-end e gli amministratori, il programma di installazione di Lync Server 2013 crea directory virtuali in Internet Information Services (IIS) per gli scopi seguenti:

  - Per consentire agli utenti di scaricare file dal servizio Rubrica

  - Per consentire ai client di ottenere aggiornamenti

  - Per abilitare i servizi di conferenza

  - Per consentire agli utenti di scaricare il contenuto della riunione

  - Per consentire agli utenti di espandere i gruppi di distribuzione

  - Per abilitare i servizi di conferenza telefonica

  - Per abilitare le caratteristiche di Response Group

Inoltre, l'aggiornamento cumulativo per Lync Server 2010: il programma di installazione di novembre 2011 crea directory virtuali in IIS per gli scopi seguenti:

  - In server front-end o Standard Edition per supportare la funzionalità di mobilità, ad esempio messaggistica istantanea e presenza, nei dispositivi mobili

  - In server front-end o server standard e amministratori per consentire ai dispositivi mobili di individuare automaticamente le risorse di mobilità



> [!NOTE]
> Se si distribuisce la mobilità, è consigliabile usare IIS 7,5. Il programma di installazione del servizio di mobilità di Lync Server imposta alcuni contrassegni ASP.NET per migliorare le prestazioni. IIS 7,5 viene installato per impostazione predefinita in Windows Server 2008 R2 e il programma di installazione del servizio di mobilità modifica automaticamente le impostazioni di ASP.NET. Se si usa IIS 7,0 in Windows Server 2008, è necessario modificare manualmente queste impostazioni.



Lync Server richiede l'installazione dei seguenti moduli IIS:


> [!IMPORTANT]
> Se l'organizzazione richiede l'individuazione di IIS e tutti i servizi Web in un'unità diversa da quella dell'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Lync Server nella finestra di dialogo Imposta. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Lync Server verrà distribuito nell'unità. Per informazioni dettagliate su come rilocare il INETPUB distribuito da Windows Server Manager durante l'installazione di <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>IIS, vedere.


  - Contenuto statico

  - Documento predefinito

  - Errori HTTP

  - ASP.NET

  - Estensibilità .NET

  - Estensioni ISAPI (Internet Server API)

  - Filtri ISAPI

  - Registrazione HTTP

  - Strumenti di registrazione

  - Traccia

  - Autenticazione di Windows

  - Filtro delle richieste

  - Compressione del contenuto statico

  - Compressione del contenuto dinamico

  - Console di gestione di IIS

  - Script e strumenti di gestione di IIS

  - Autenticazione anonima (installata per impostazione predefinita durante l'installazione di IIS)

  - Autenticazione del mapping dei certificati client

La tabella seguente elenca gli URI per le directory virtuali per l'accesso interno e le risorse del file System a cui si riferiscono.

### <a name="virtual-directories-for-internal-access"></a>Directory virtuali per l'accesso interno

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>URI della directory virtuale</th>
<th>Fa riferimento a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server Rubrica</p></td>
<td><p>https://&lt;FQDN&gt;interno/ABS/int/handler</p></td>
<td><p>Posizione del server Rubrica scaricare i file per gli utenti interni.</p></td>
</tr>
<tr class="even">
<td><p>Servizio di individuazione automatica</p></td>
<td><p>https://&lt;FQDN&gt;interno/autodiscover</p></td>
<td><p>Posizione del servizio di individuazione automatica di Lync Server che individua le risorse di mobilità per gli utenti di dispositivi mobili interni.</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamenti del client</p></td>
<td><p>http://&lt;FQDN&gt;interno/AutoUpdate/int</p></td>
<td><p>Posizione dei file di aggiornamento per i client interni basati su computer.</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>http://&lt;FQDN&gt;interno/conf/int</p></td>
<td><p>Posizione delle risorse di conferenza per gli utenti interni.</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamenti del dispositivo</p></td>
<td><p>FQDN&lt;&gt;interno http:///DeviceUpdateFiles_Int</p></td>
<td><p>Posizione dei file di aggiornamento del dispositivo UC (Unified Communications) per i dispositivi UC interni.</p></td>
</tr>
<tr class="even">
<td><p>Riunione</p></td>
<td><p>http://&lt;FQDN&gt;interno/etc/place/null</p></td>
<td><p>Posizione del contenuto della riunione per gli utenti interni.</p></td>
</tr>
<tr class="odd">
<td><p>Servizio mobilità</p></td>
<td><p>https://&lt;FQDN&gt;interno/MCX</p></td>
<td><p>Posizione delle risorse del servizio di mobilità per gli utenti di dispositivi mobili interni.</p></td>
</tr>
<tr class="even">
<td><p>Servizio query Web di espansione e Rubrica di gruppo</p></td>
<td><p>http://&lt;FQDN&gt;interno/GroupExpansion/int/Service.asmx</p></td>
<td><p>Posizione del servizio Web che consente l'espansione dei gruppi per gli utenti interni. Inoltre, la posizione del servizio query Web della rubrica che fornisce informazioni sull'elenco indirizzi globale ai client mobili di Lync Mobile Microsoft Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Servizi di conferenza telefonica</p></td>
<td><p>http://&lt;FQDN&gt;interno/PhoneConferencing/int</p></td>
<td><p>Posizione dei dati di conferenza telefonica per gli utenti interni.</p></td>
</tr>
<tr class="even">
<td><p>Aggiornamenti del dispositivo</p></td>
<td><p>http://&lt;FQDN&gt;interno/RequestHandler</p></td>
<td><p>Posizione del gestore di richieste di servizio Web Update per dispositivi che consente ai dispositivi UC interni di caricare i log e verificare la disponibilità di aggiornamenti.</p></td>
</tr>
<tr class="odd">
<td><p>Response Group Application</p></td>
<td><p>http://&lt;FQDN&gt;interno/rgsconfig</p>
<p>http://&lt;FQDN&gt;interno/RgsClients</p></td>
<td><p>Posizione dello strumento di configurazione di Response Group.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Per i pool Front-end in una configurazione consolidata, è necessario distribuire IIS prima di poter aggiungere server al pool.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>È necessario usare lo snap-in di amministrazione di IIS per assegnare il certificato usato dal server del componente Web IIS.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

