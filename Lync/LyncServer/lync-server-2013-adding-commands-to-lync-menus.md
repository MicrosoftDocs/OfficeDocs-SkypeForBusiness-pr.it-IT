---
title: 'Lync Server 2013: aggiunta di comandi ai menu di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96a0df07a44392857f4384a1285245229874cdaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Aggiunta di comandi ai menu di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-04-11_

È possibile aggiungere comandi personalizzati ai menu di Lync 2013 e passare l'URI (Uniform Resource Identifier) SIP dell'utente corrente e i contatti selezionati all'applicazione che viene avviata dal comando personalizzato.

È possibile visualizzare i comandi personalizzati aggiunti all'interno di uno o più dei menu seguenti:

  - Menu Strumenti, sulla barra dei menu della finestra principale di Lync

  - Menu di scelta rapida per i contatti nell'elenco Contatti

  - Il menu altre opzioni, nella finestra di conversazione

  - Menu di scelta rapida per gli utenti elencati nell'elenco dei partecipanti della finestra Conversazione

  - Menu Opzioni in una scheda contatto

È possibile definire comandi personalizzati per due tipi di applicazioni, ovvero per le applicazioni con una delle caratteristiche seguenti:

  - Si applicano solo all'utente corrente e vengono avviate nel computer locale.

  - Coinvolgono altri utenti, come avviene con i programmi di collaborazione online, e devono essere avviate nel computer di ogni utente.

È possibile richiamare il comando personalizzato nei modi seguenti:

  - Selezionare uno o più utenti e quindi scegliere il comando personalizzato.

  - Avviare una conversazione con due o più partecipanti e quindi scegliere il comando personalizzato.

<div>

## <a name="to-add-a-custom-command"></a>Per aggiungere un comando personalizzato

Utilizzare le impostazioni del registro di sistema nella tabella seguente per aggiungere un comando ai menu. Tali voci vengono inserite nel registro di sistema in una delle posizioni seguenti:

  - Per il sistema operativo a\_32bit\_:\\HKEY\\Local\\Machine\\software\\Microsoft\\Office\\15,0 Lync SessionManager Apps

  - Per il sistema operativo a\_64bit\_:\\HKEY\\Local\\Machine\\software\\Wow6432Node\\Microsoft\\Office\\15,0 Lync SessionManager Apps

### <a name="custom-command-registry-entries"></a>Voci del Registro di sistema dei comandi personalizzati

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
<td><p>0 = Eseguibile (impostazione predefinita)</p>
<div>

> [!NOTE]  
> Richiede ApplicationInstallPath.


</div>
<p>1 = Protocollo</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso completo dell'eseguibile.</p>
<div>

> [!NOTE]  
> Deve essere specificato se ApplicationType è 0 (Eseguibile).


</div></td>
</tr>
<tr class="even">
<td><p>Percorso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso completo di avvio con eventuali parametri, compresi i parametri predefiniti<em>%user-id%</em> e <em>%contact-id%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Sessione locale. L'applicazione viene avviata nel computer locale.</p>
<p>1 = Sessione tra due parti (impostazione predefinita). Lync 2013 avvia l'applicazione localmente e quindi invia una notifica desktop all'altro utente. L'altro utente fa clic sulla notifica per avviare l'applicazione nel computer in uso.</p>
<p>2 = Sessione tra più parti. Lync 2013 avvia l'applicazione localmente e quindi invia notifiche desktop agli altri utenti. L'altro utente fa clic sulla notifica per avviare l'applicazione specificata nel computer in uso.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola. I valori possibili sono:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Se ExtensibleMenu non è definito, vengono utilizzati i valori predefiniti MainWindowRightClick e ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


Ad esempio, nel file dell'editor del Registro di sistema (con estensione REG) seguente sono illustrati i risultati dell'aggiunta della voce di menu Contoso Sales Contact Manager al menu Azioni nella finestra Conversazione:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>Per accedere a un comando personalizzato

Per accedere a un comando personalizzato dopo che è stato aggiunto, eseguire una delle operazioni seguenti, a seconda dei valori di ExtensibleMenu definiti:

  - **MainWindowActions**   nella finestra principale di Lync, fare clic su **strumenti**, quindi fare clic sul comando personalizzato.

  - **MainWindowRightClick**   nella finestra principale di Lync, fare clic con il pulsante destro del mouse su un contatto e quindi scegliere il comando personalizzato.

  - **ConversationWindowActions**   nella finestra conversazione, fare clic sull'icona **altre opzioni** , quindi fare clic sul comando personalizzato.

  - **ConversationWindowRightClick**   nella finestra conversazione, fare clic con il pulsante destro del mouse su un nome di contatto e quindi scegliere il comando personalizzato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

