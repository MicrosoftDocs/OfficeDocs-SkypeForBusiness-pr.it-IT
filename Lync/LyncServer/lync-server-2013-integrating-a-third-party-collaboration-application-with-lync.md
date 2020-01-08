---
title: Integrazione di un'applicazione di collaborazione di terze parti con Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Integrazione di un'applicazione di collaborazione di terze parti con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

È possibile integrare Lync 2013 con un'applicazione di collaborazione online di terze parti aggiungendo informazioni sull'applicazione al registro di sistema. È possibile usare Lync 2013 per avviare sessioni di conferenza dati ospitate in un server interno, un servizio basato su Internet o entrambi. La sessione di collaborazione o conferenza dati può essere avviata dall'elenco contatti o da una sessione di messaggistica istantanea, vocale o video esistente. Lync 2013 agisce solo come veicolo per l'avvio dell'applicazione. Le conversazioni di Lync 2013 esistenti rimangono attive dopo l'inizio della sessione di collaborazione online.

Nelle sezioni seguenti viene descritto come integrare Lync 2013 con le applicazioni di collaborazione basate su Internet e basate su server.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Integrazione di un'applicazione di collaborazione basata su Internet con Lync 2013

In generale, i passaggi necessari per l'integrazione di un'applicazione di collaborazione di terze parti sono i seguenti:

1.  Le informazioni sull'applicazione vengono aggiunte al registro di sistema.

2.  L'organizzatore accede a Lync 2013 e seleziona i contatti per la condivisione e la collaborazione dei dati. In alternativa, l'organizzatore può già partecipare a una conversazione e decidere di aggiungere servizi di conferenza dati.

3.  Lync 2013 legge il registro di sistema, avvia l'applicazione di collaborazione e quindi Invia un messaggio SIP personalizzato, ovvero un appINVITE, ai partecipanti selezionati.

4.  I partecipanti accettano l'invito e l'applicazione di collaborazione viene avviata nel computer di ogni persona. Lync 2013 usa il registro di sistema per determinare l'applicazione di collaborazione da usare e quindi avvia l'applicazione usando i parametri inclusi nel messaggio di appINVITE.

La tabella seguente descrive le voci del registro di sistema necessarie per integrare un'applicazione di collaborazione basata su Internet con Lync 2013. Queste voci vengono inserite nel registro di sistema nella posizione seguente:

  - HKEY\_Local\_computer\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\parametri\\delle app

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Voci del registro di sistema per un'applicazione di collaborazione basata su Internet

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
<td><p>Nome</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nome dell'applicazione per i menu di Lync 2013.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso dell'icona di 16 pixel x 16 pixel, BMP o PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Percorso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso partecipante per l'avvio dell'applicazione di collaborazione online.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso dell'organizzatore per l'avvio dell'applicazione di collaborazione online. Questo percorso può contenere uno o più parametri personalizzati definiti nella sottochiave Parameters. Per esempio<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = sessione locale. L'applicazione viene avviata nel computer locale.</p>
<p>1 = sessione a due parti (impostazione predefinita). Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente. L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel computer in uso.</p>
<p>2 = sessione in più parti. Lync 2013 avvia l'applicazione localmente e quindi invia le notifiche di sistema agli altri utenti, chiedendo loro di avviare l'applicazione specificata nel proprio computer.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola. I valori possibili sono:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Se ExtensibleMenu non è definito, vengono usati i valori predefiniti di MainWindowRightClick e ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


La tabella seguente descrive le voci del registro di sistema per i parametri. Queste voci sono inserite in HKEY\_\_\\i parametri delle\\app\\\\di\\Microsoft\\Office\\15,0\\Lync sessionmanager.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Voci del registro di sistema per un'applicazione di collaborazione basata su Internet

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
<td><p>Usato in formato token (<code>%Parm1%</code>) per aggiungere valori specifici dell'utente alla chiave del registro di sistema OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vedere param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vedere param1.</p></td>
</tr>
</tbody>
</table>


Le impostazioni del registro di sistema di esempio seguenti integrano client di collaborazione ADatum con Lync 2013:

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

Le impostazioni per l'aggiunta di comandi per l'avvio di un'applicazione di collaborazione basata su server dall'interno di Lync 2013 sono simili a quelle descritte nella sezione precedente, che integrano un'applicazione di collaborazione basata su Internet con Lync 2013. Tuttavia, OriginatorPath non è obbligatorio e alcuni valori vengono modificati. Le voci del registro di sistema vengono inserite nella posizione seguente:

  - HKEY\_Local\_computer\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\parametri\\delle app

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Voci del registro di sistema per un'applicazione di collaborazione basata su server

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
<td><p>Nome</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nome dell'applicazione come viene visualizzato nel menu.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>Valore = 1. Imposta il tipo di applicazione su Protocol. Gli altri valori possibili non si applicano in questo caso. Se non è presente, ApplicationType è impostato su 0 (eseguibile).</p></td>
</tr>
<tr class="odd">
<td><p>Percorso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocollo usato per avviare l'applicazione di collaborazione. Per Live Meeting 2007, il valore di path è impostato su <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = sessione locale. L'applicazione viene avviata nel computer locale.</p>
<p>1 = sessione a due parti (impostazione predefinita). Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente. L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel computer in uso.</p>
<p>2 = sessione in più parti. Lync 2013 avvia l'applicazione localmente e quindi invia le notifiche di sistema agli altri utenti, chiedendo loro di avviare l'applicazione specificata nel proprio computer.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = tipo di server.</p></td>
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
<p>Se ExtensibleMenu non è definito, vengono usati i valori predefiniti di MainWindowRightClick e ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


L'esempio seguente aggiunge i comandi per avviare ADatum Collaboration client dall'interno di Lync 2013:

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

