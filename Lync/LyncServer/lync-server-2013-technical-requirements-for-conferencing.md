---
title: 'Lync Server 2013: Requisiti tecnici per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Requisiti tecnici per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-25_

Per Lync Server 2013, i servizi di conferenza telefonica con accesso esterno, le conferenze A/V, i servizi di messaggistica istantanea (IM) e le funzionalità di conferenza Web vengono sempre eseguiti nei server front-end.

Questa sezione descrive i requisiti hardware e software per questi server, insieme alla collocazione supportata.

I servizi di conferenza telefonica con accesso esterno sono una funzionalità che include una vasta gamma di componenti. Alcuni componenti sono specifici per i servizi di conferenza telefonica con accesso esterno e alcuni sono componenti di VoIP aziendale. Questa sezione descrive i requisiti per i componenti specifici dei servizi di conferenza telefonica con accesso esterno. Per informazioni dettagliate sui requisiti del gateway di Mediation Server e PSTN (Public Switched Telephone Network), vedere [Componente Mediation Server in Lync server 2013](lync-server-2013-mediation-server-component.md) e [topologie per Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

Poiché i servizi di conferenza Web e le conferenze A/V sono collocati con il front end server, i requisiti hardware del server sono gli stessi per i server front-end. Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità. I componenti seguenti necessari per i servizi di conferenza telefonica con accesso esterno hanno anche gli stessi requisiti hardware dei server front-end:

  - Servizio applicazione

  - Applicazione Supervisore conferenza

  - Applicazione per l'annuncio di conferenza

I requisiti hardware per il server front-end sono gli stessi che per molti altri ruoli del server in Lync Server 2013 sono descritti nella tabella seguente.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

Poiché i servizi di conferenza Web e le conferenze A/V sono collocati con il front end server, i requisiti software server sono gli stessi per i server front-end. Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Per le conferenze Web, Lync Server 2013 richiede anche Office Web Apps e il server Office Web Apps (in precedenza noto come server WAC) per gestire le presentazioni di PowerPoint. Per informazioni dettagliate, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Per i servizi di conferenza telefonica con accesso esterno, il servizio applicazione, l'applicazione di conferenza e l'applicazione di annunci di conferenza hanno gli stessi requisiti di sistema operativo di front end server. Per informazioni dettagliate sui requisiti software, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

L'applicazione per i servizi di conferenza e l'applicazione per le conferenze richiede che Windows Media Format Runtime sia installato nei server front-end. Windows Media Format Runtime è necessario per riprodurre file di Windows Media Audio (WMA) usati per la musica in attesa, i nomi registrati e le istruzioni. Ad eccezione di Windows Server 2012 e Windows Server 2012 R2, Windows Media Format Runtime viene installato automaticamente come parte dell'esperienza desktop di Windows quando si esegue il programma di installazione, ma potrebbe essere necessario riavviare il computer. Per questo motivo, ti consigliamo di installare come parte dell'esperienza desktop di Windows, che include Windows Media Format Runtime prima di eseguire la configurazione. Windows Server 2012 e Windows Server 2012 R2 richiede Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Requisiti della porta per i servizi di conferenza telefonica con accesso esterno

La tabella seguente descrive le porte usate dai servizi di conferenza telefonica con accesso esterno. Se si usa un bilanciamento del carico, verificare che il bilanciamento del carico sia configurato per le porte usate da qualsiasi applicazione che verrà eseguita nel pool.

Queste porte sono impostazioni predefinite che è possibile modificare usando il cmdlet **Set-CsApplicationServer** . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.

<div>


> [!NOTE]  
> Tutte le istanze della stessa applicazione in un pool usano la stessa porta di ascolto SIP.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Porte usate dai servizi di conferenza telefonica con accesso esterno

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero di porta</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>Usato dall'applicazione di assistente conferenza per le richieste di ascolto SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Usato dall'applicazione di annuncio per conferenze per le richieste di ascolto SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Client supportati per i servizi di conferenza telefonica con accesso esterno

Per pianificare conferenze locali che supportano l'accesso esterno, è possibile usare il client seguente:

  - Componente aggiuntivo riunione online per Lync 2013 (installato automaticamente durante l'installazione di Lync 2013 o partecipante)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Requisiti della pagina Impostazioni conferenza telefonica con accesso esterno

La pagina delle impostazioni per i servizi di conferenza telefonica con accesso esterno supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.

<div>


> [!NOTE]  
> sono supportate le versioni di 32 bit e 64 bit dei sistemi operativi.



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
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisiti per i file audio per i servizi di conferenza telefonica con accesso esterno

Lync Server 2013 non supporta la personalizzazione delle istruzioni vocali e della musica per i servizi di conferenza telefonica con accesso esterno. Tuttavia, se si ha bisogno di cambiare i file audio predefiniti, vedere l'articolo 961177 della Microsoft Knowledge base [su come personalizzare le richieste vocali o i file musicali per i servizi di conferenza telefonica con accesso esterno in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

È anche possibile usare l'utilità per la gestione delle [richieste vocali personalizzate di Microsoft Lync Server Conferencing](http://go.microsoft.com/fwlink/p/?linkid=396880) , che consente agli amministratori di sostituire le richieste vocali predefinite usate quando un chiamante di un telefono entra in una riunione Lync con istruzioni personalizzate per creare un'esperienza di partecipazione a una riunione diversa. Le istruzioni vocali personalizzate possono essere installate in un server in cui è in uso Lync Server 2010 o Lync Server 2013, Enterprise o Standard Edition.

Applicazione per i servizi di conferenza e l'applicazione di annuncio di conferenza sono i requisiti seguenti per la musica in attesa, il nome registrato e i file di prompt audio:

  - Formato di file di Windows Media Audio (WMA)

  - 16 bit mono

  - CBR a due passaggi di 48 kbps (velocità in bit costante)

  - Livello di riconoscimento vocale at-24DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Requisiti degli utenti per i servizi di conferenza telefonica con accesso esterno

Gli utenti dei servizi di conferenza telefonica con accesso esterno devono avere un numero o un'estensione di telefono univoco assegnati al proprio account. Questo requisito supporta l'autenticazione durante i servizi di conferenza telefonica con accesso esterno. Gli utenti aziendali, ovvero gli utenti che hanno credenziali di servizi di dominio Active Directory e gli account di Lync Server all'interno dell'organizzazione, immettono il proprio numero di telefono (o estensione) e un PIN per accedere alle conferenze come utente autenticato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

