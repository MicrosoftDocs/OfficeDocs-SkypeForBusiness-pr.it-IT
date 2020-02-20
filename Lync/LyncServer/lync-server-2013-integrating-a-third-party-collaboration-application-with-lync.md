---
title: Integrazione di un'applicazione di collaborazione di terze parti con Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Integrazione di un'applicazione di collaborazione di terze parti con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

È possibile integrare Lync 2013 con qualsiasi applicazione di collaborazione online di terze parti aggiungendo informazioni sull'applicazione al registro di sistema. È possibile utilizzare Lync 2013 per avviare le sessioni di conferenza dati ospitate in un server interno, in un servizio basato su Internet o in entrambi. La sessione di collaborazione o di conferenza dati può essere avviata dall'elenco contatti oppure da una sessione video, vocale o di messaggistica istantanea esistente. Lync 2013 agisce solo come veicolo per l'avvio dell'applicazione. Tutte le conversazioni di Lync 2013 esistenti rimangono attive dopo l'inizio della sessione di collaborazione online.

Nelle sezioni seguenti viene descritto come integrare Lync 2013 con le applicazioni di collaborazione basata su Internet e basate su server.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Integrazione di un'applicazione di collaborazione basata su Internet con Lync 2013

In generale, la procedura per integrare un'applicazione di collaborazione di terze parti è la seguente:

1.  Le informazioni relative all'applicazione vengono aggiunte al Registro di sistema.

2.  L'organizzatore accede a Lync 2013 e seleziona Contatti per la condivisione e la collaborazione dei dati. È anche possibile che l'organizzatore sia già impegnato in una conversazione e decida di aggiungere la funzionalità per conferenze dati.

3.  Lync 2013 legge il registro di sistema, avvia l'applicazione di collaborazione e quindi Invia un messaggio SIP personalizzato, ovvero un appINVITE, ai partecipanti selezionati.

4.  I partecipanti accettano l'invito e l'applicazione di collaborazione viene avviata nel computer di ognuno di essi. Lync 2013 utilizza il registro di sistema per determinare l'applicazione di collaborazione da utilizzare e quindi avvia l'applicazione utilizzando i parametri inclusi nel messaggio appINVITE.

Nella tabella seguente vengono descritte le voci del registro di sistema necessarie per l'integrazione di un'applicazione di collaborazione basata su Internet con Lync 2013. Tali voci vengono inserite nel registro di sistema nel percorso seguente:

  - HKEY\_Local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\Apps\\Parameters

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Voci del Registro di sistema per un'applicazione di collaborazione basata su Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Dati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>Il nome dell'applicazione per i menu di Lync 2013.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso dell'icona 16 x 16 pixel in formato BMP o PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Percorso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso dei partecipanti per l'avvio dell'applicazione di collaborazione online.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso dell'organizzatore per l'avvio dell'applicazione di collaborazione online. Questo percorso può contenere uno o più parametri personalizzati, definiti nella sottochiave Parameters. Per esempio<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Sessione locale. L'applicazione viene avviata nel computer locale.</p>
<p>1 = Sessione tra due parti (impostazione predefinita). Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente. L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel proprio computer.</p>
<p>2 = Sessione tra più parti. Lync 2013 avvia l'applicazione localmente e quindi invia notifiche di sistema agli altri utenti, richiedendo loro di avviare l'applicazione specificata nel proprio computer.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Elenco dei menu, delimitati da punto e virgola, in cui verrà visualizzato il comando. I valori possibili sono:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Se ExtensibleMenu non è definito, vengono utilizzati i valori predefiniti MainWindowRightClick e ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


Nella tabella riportata di seguito vengono illustrate le voci del Registro di sistema per i parametri. Queste voci sono posizionate in\_HKEY\_\\i parametri\\di\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\Apps.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Voci del Registro di sistema per un'applicazione di collaborazione basata su Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Dati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Utilizzato in formato token (<code>%Parm1%</code>) per aggiungere valori specifici dell'utente alla chiave del registro di sistema OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vedere Param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vedere Param1.</p></td>
</tr>
</tbody>
</table>


Nelle impostazioni del registro di sistema di esempio seguenti viene integrato il client di collaborazione ADatum con Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Integrazione di un'applicazione di collaborazione basata su server con Lync 2013

Le impostazioni per l'aggiunta di comandi per l'avvio di un'applicazione di collaborazione basata su server dall'interno di Lync 2013 sono simili a quelle descritte nella sezione precedente, in cui è stata integrata un'applicazione di collaborazione basata su Internet con Lync 2013. La voce OriginatorPath tuttavia non è necessaria e alcuni valori sono diversi. Le voci del registro di sistema vengono inserite nel percorso seguente:

  - HKEY\_Local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\Apps\\Parameters

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Voci del Registro di sistema per un'applicazione di collaborazione basata su server

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Dati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nome dell'applicazione visualizzato nel menu.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>Valore = 1. Imposta il tipo di applicazione su Protocollo. In questo caso non si applicano gli altri valori possibili. Se non è presente, ApplicationType è impostato su 0 (eseguibile).</p></td>
</tr>
<tr class="odd">
<td><p>Percorso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocollo utilizzato per avviare l'applicazione di collaborazione. Per Live Meeting 2007, il valore di path è impostato su <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Sessione locale. L'applicazione viene avviata nel computer locale.</p>
<p>1 = Sessione tra due parti (impostazione predefinita). Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente. L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel proprio computer.</p>
<p>2 = Sessione tra più parti. Lync 2013 avvia l'applicazione localmente e quindi invia notifiche di sistema agli altri utenti, richiedendo loro di avviare l'applicazione specificata nel computer in uso.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATI = Tipo di server.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola. I valori possibili sono:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Se ExtensibleMenu non è definito, vengono utilizzati i valori predefiniti MainWindowRightClick e ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


Nell'esempio seguente vengono aggiunti i comandi per avviare il client di collaborazione ADatum dall'interno di Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

