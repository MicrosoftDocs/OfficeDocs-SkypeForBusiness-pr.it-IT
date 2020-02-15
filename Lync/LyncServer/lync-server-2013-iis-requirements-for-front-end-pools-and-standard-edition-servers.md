---
title: Requisiti di IIS per pool Front end e server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-19_

Per i server Standard Edition e front end server e Director, il programma di installazione di Lync Server 2013 crea directory virtuali in Internet Information Services (IIS) per gli scopi seguenti:

  - Consentire agli utenti di scaricare file dal servizio Rubrica

  - Per consentire ai client di ottenere gli aggiornamenti

  - Abilitare le conferenze

  - Consentire agli utenti di scaricare il contenuto delle riunioni

  - Consentire agli utenti di espandere i gruppi di distribuzione

  - Abilitare le conferenze telefoniche

  - Abilitare le funzionalità di Response Group

Inoltre, l'aggiornamento cumulativo per Lync Server 2010: il programma di installazione di novembre 2011 crea directory virtuali in IIS per gli scopi seguenti:

  - Nei Front End Server o nei server Standard Edition per supportare la funzionalità per dispositivi mobili, ad esempio messaggistica istantanea e presenza, per i telefoni cellulari

  - Nei Front End Server o nei server Standard Edition e nei direttori per consentire ai dispositivi mobili di individuare automaticamente le risorse mobili



> [!NOTE]
> Se si distribuiscono dispositivi mobili, è consigliabile utilizzare IIS 7.5. Il programma di installazione di Lync Server Mobility Service imposta alcuni flag di ASP.NET per migliorare le prestazioni. IIS 7.5 viene installato per impostazione predefinita in Windows Server 2008 R2 e le impostazioni ASP.NET vengono modificate automaticamente dal programma di installazione del servizio per dispositivi mobili. Se si utilizza IIS 7.0 in Windows Server 2008, è necessario modificare manualmente queste impostazioni.



Per l'installazione di Lync Server, è necessario installare i seguenti moduli IIS:


> [!IMPORTANT]
> Se l'organizzazione richiede l'individuazione di IIS e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Lync Server nella finestra di dialogo Imposta. Se si installano i file di installazione in questo percorso, incluso OCSCore. msi, anche gli altri file di Lync Server verranno distribuiti nell'unità. Per informazioni dettagliate su come spostare il INETPUB distribuito da Windows Server Manager durante l'installazione di IIS, <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>vedere.


  - Contenuto statico

  - Documento predefinito

  - Errori HTTP

  - ASP.NET

  - Estendibilità .NET

  - Estensioni ISAPI (Internet Server API)

  - Filtri ISAPI

  - Registrazione HTTP

  - Strumenti di registrazione

  - Analisi della

  - Autenticazione di Windows

  - Filtro richieste

  - Compressione contenuto statico

  - Compressione contenuto dinamico

  - Console di gestione IIS

  - Strumenti e script di gestione IIS

  - Autenticazione anonima (installata per impostazione predefinita insieme a IIS)

  - Autenticazione mapping certificati client

Nella tabella seguente vengono elencati gli URI delle directory virtuali per l'accesso interno e le risorse del file system a cui si riferiscono.

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
<th>URI directory virtuale</th>
<th>Riferimento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server della Rubrica</p></td>
<td><p>/ABS/int/Handler&lt;d'FQDN&gt;interno https://</p></td>
<td><p>Percorso dei file di download del server della Rubrica per gli utenti interni.</p></td>
</tr>
<tr class="even">
<td><p>Servizio di individuazione automatica</p></td>
<td><p>/Autodiscover&lt;d'FQDN&gt;interno https://</p></td>
<td><p>Percorso del servizio di individuazione automatica di Lync Server che individua le risorse mobili per gli utenti di dispositivi mobili interni.</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamenti client</p></td>
<td><p>/AutoUpdate/int&lt;d'FQDN&gt;interno http://</p></td>
<td><p>Percorso dei file di aggiornamento per i client interni basati su computer.</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>/Conf/int&lt;d'FQDN&gt;interno http://</p></td>
<td><p>Percorso delle risorse per conferenze per utenti interni.</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamenti per i dispositivi</p></td>
<td><p>FQDN&lt;&gt;interno/DeviceUpdateFiles_Int di http://</p></td>
<td><p>Percorso dei file di aggiornamento per i dispositivi interni per comunicazioni unificate.</p></td>
</tr>
<tr class="even">
<td><p>Riunione</p></td>
<td><p>/etc/place/null&lt;d'FQDN&gt;interno http://</p></td>
<td><p>Percorso del contenuto della riunione per utenti interni.</p></td>
</tr>
<tr class="odd">
<td><p>Servizio per dispositivi mobili</p></td>
<td><p>/MCX&lt;d'FQDN&gt;interno https://</p></td>
<td><p>Percorso delle risorse del servizio per dispositivi mobili per utenti interni.</p></td>
</tr>
<tr class="even">
<td><p>Servizio di espansione gruppo e query Web della Rubrica</p></td>
<td><p>/GroupExpansion/int/Service.asmx&lt;d'FQDN&gt;interno http://</p></td>
<td><p>Percorso del servizio Web che consente l'espansione gruppo per utenti interni. Inoltre, la posizione del servizio di query Web della rubrica che fornisce informazioni sugli elenchi di indirizzi globali ai client mobili di Lync Mobile Microsoft Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Phone Conferencing</p></td>
<td><p>/PhoneConferencing/int&lt;d'FQDN&gt;interno http://</p></td>
<td><p>Percorso dei dati relativi alle conferenze telefoniche per utenti interni.</p></td>
</tr>
<tr class="even">
<td><p>Aggiornamenti per i dispositivi</p></td>
<td><p>/RequestHandler&lt;d'FQDN&gt;interno http://</p></td>
<td><p>Percorso del gestore richieste del servizio Web di aggiornamento dispositivi che consente ai dispositivi per comunicazioni unificate interni di caricare registri e verificare la presenza di aggiornamenti.</p></td>
</tr>
<tr class="odd">
<td><p>Applicazione Response Group</p></td>
<td><p>/RgsConfig&lt;d'FQDN&gt;interno http://</p>
<p>/RgsClients&lt;d'FQDN&gt;interno http://</p></td>
<td><p>Percorso dello strumento di configurazione di Response Group.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Per i pool Front end in una configurazione consolidata, è necessario distribuire IIS prima di poter aggiungere server al pool.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

