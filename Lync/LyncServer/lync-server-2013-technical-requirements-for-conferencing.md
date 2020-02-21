---
title: Lync Server 2013 requisiti tecnici per le conferenze
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
ms.openlocfilehash: b6f28effa3ac80f4a2bca1fa062fcc3dfafb5d7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Requisiti tecnici per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-25_

Per Lync Server 2013, servizi di conferenza telefonica con accesso esterno, A/V Conferencing, messaggistica istantanea e funzionalità di Web Conferencing vengono sempre eseguiti nei Front End Server.

In questa sezione vengono fornite informazioni dettagliate sui requisiti hardware e software per questi server, insieme alla collocazione supportata.

La funzionalità di conferenza telefonica con accesso esterno include una vasta gamma di componenti. Alcuni dei componenti sono specifici delle conferenze telefoniche con accesso esterno, mentre altri sono componenti di VoIP aziendale. In questa sezione vengono descritti i requisiti per i componenti specifici delle conferenze telefoniche con accesso esterno. Per informazioni dettagliate sui requisiti del gateway PSTN (Mediation Server e Public Switched Telephone Network), vedere [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) e [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="hardware-requirements"></a>Requisiti hardware

Poiché Web Conferencing e A/V Conferencing sono collocati con Front End Server, i requisiti hardware del server sono uguali a quelli dei Front End Server. Per informazioni dettagliate sui requisiti hardware, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità. I componenti seguenti necessari per le conferenze telefoniche con accesso esterno dispongono anche degli stessi requisiti hardware dei Front End Server:

  - Servizio dell'applicazione

  - Applicazione Operatore Conferenza

  - Applicazione Annuncio conferenza

I requisiti hardware per Front End Server sono gli stessi di molti altri ruoli del server in Lync Server 2013 sono descritti nella tabella seguente.

</div>

<div>

## <a name="software-requirements"></a>Requisiti software

Poiché Web Conferencing e A/V Conferencing sono collocati con Front End Server, i requisiti software del server sono uguali a quelli dei Front End Server. Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Per le conferenze Web, Lync Server 2013 richiede anche Office Web Apps e il server Office Web Apps (in precedenza noto come server WAC) per gestire le presentazioni di PowerPoint. Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Per le conferenze telefoniche con accesso esterno, il servizio applicazione, l'applicazione Operatore Conferenza e l'applicazione Annuncio conferenza dispongono degli stessi requisiti del sistema operativo dei Front End Server. Per informazioni dettagliate sui requisiti software, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Applicazione Operatore Conferenza e l'applicazione Annuncio conferenza richiedono l'installazione di Windows Media Format Runtime nei Front End Server. Runtime formato Windows Media è richiesto per la riproduzione dei file audio WMA (Windows Media Audio) usati per la musica in attesa, i nomi registrati e i messaggi. Ad eccezione di Windows Server 2012 e Windows Server 2012 R2, il runtime del formato Windows Media viene installato automaticamente come parte dell'esperienza desktop di Windows durante l'esecuzione del programma di installazione, ma potrebbe essere necessario riavviare il computer. È consigliabile pertanto installare il componente come parte dell'esperienza desktop di Windows prima di eseguire il programma di installazione. Windows Server 2012 e Windows Server 2012 R2 richiedono Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Requisiti delle porte per le conferenze telefoniche con accesso esterno

Nella tabella seguente vengono descritte le porte usate per le conferenze telefoniche con accesso esterno. Se si usa un servizio di bilanciamento del carico, assicurarsi che sia configurato per le porte usate dalle applicazioni che verranno eseguite nel pool.

Tali porte vengono utilizzate per impostazione predefinita e possono essere cambiate mediante il cmdlet **Set-CsApplicationServer**. Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.

<div>


> [!NOTE]  
> Tutte le istanze della stessa applicazione in un pool usano la stessa porta di attesa SIP.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Porte usate dalle conferenze telefoniche con accesso esterno

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
<td><p>Utilizzato dall'applicazione Operatore Conferenza per le richieste di attesa SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Utilizzato dall'applicazione Annuncio di conferenza per le richieste di attesa SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Client supportati per le conferenze telefoniche con accesso esterno

È possibile usare il client seguente per pianificare conferenze locali che supportino la conferenza telefonica con accesso esterno:

  - Componente aggiuntivo per riunioni online per Lync 2013 (installato automaticamente quando si installa Lync 2013 o Attendee)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Requisiti della pagina Impostazioni conferenza telefonica con accesso esterno

La pagina Impostazioni conferenza telefonica con accesso esterno supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.

<div>


> [!NOTE]  
> Sono supportate le versioni a 32 bit e a 64 bit dei sistemi operativi.



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
<td><p>Windows Server 2008 R2</p></td>
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

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisiti dei file audio per le conferenze telefoniche con accesso esterno

Lync Server 2013 non supporta la personalizzazione di istruzioni vocali e musica per le conferenze telefoniche con accesso esterno. Tuttavia, se si ha un'esigenza aziendale complessa che richiede la modifica dei file audio predefiniti, vedere l'articolo 961177 della Microsoft Knowledge base, [come personalizzare i messaggi vocali o i file musicali per le conferenze telefoniche con accesso esterno in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

È inoltre possibile utilizzare [Microsoft Lync Server Conferencing Attendant Custom voice prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) Management Utility, che consente agli amministratori di sostituire le istruzioni vocali predefinite utilizzate quando un chiamante del telefono entra in una riunione di Lync con prompt personalizzati per fornire un'esperienza di ingresso per le riunioni diversa. Le istruzioni vocali personalizzate possono essere installate su un server che esegue Lync Server 2010 o Lync Server 2013, Enterprise o Standard Edition.

Applicazione per i servizi di conferenza e applicazione di annuncio di conferenza sono necessari i seguenti requisiti per la musica di attesa, il nome registrato e i file delle istruzioni audio:

  - Formato file WMA (Windows Media Audio)

  - Mono a 16 bit

  - CBR (Constant Bit Rate) a due passaggi 48 kbps

  - Livello parlato a -24 DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Requisiti utente per le conferenze telefoniche con accesso esterno

Gli utenti delle conferenze telefoniche con accesso esterno devono avere un numero di telefono univoco o un interno assegnato al loro account. Questo requisito supporta l'autenticazione durante l'accesso esterno. Gli utenti aziendali (ovvero gli utenti che dispongono di credenziali di servizi di dominio Active Directory e account di Lync Server all'interno dell'organizzazione) immettere il proprio numero di telefono (o estensione) e un PIN per accedere alle conferenze come un utente autenticato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

