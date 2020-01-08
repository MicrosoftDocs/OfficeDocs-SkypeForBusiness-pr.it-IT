---
title: 'Lync Server 2013: aggiunta di comandi ai menu di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Aggiunta di comandi ai menu di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-04-11_

È possibile aggiungere comandi personalizzati ai menu di Lync 2013 e passare l'URI (Uniform Resource Identifier) SIP dell'utente corrente e i contatti selezionati all'applicazione avviata dal comando personalizzato.

I comandi personalizzati aggiunti possono essere visualizzati in uno o più dei menu seguenti:

  - Menu strumenti nella barra dei menu della finestra principale di Lync

  - Menu di scelta rapida per i contatti nell'elenco contatti

  - Menu altre opzioni nella finestra di conversazione

  - Menu di scelta rapida per gli utenti elencati nell'elenco dei partecipanti della finestra di conversazione

  - Menu opzioni in una scheda contatto

Puoi definire comandi personalizzati per due tipi di applicazioni, ovvero applicazioni che eseguono una delle operazioni seguenti:

  - Si applicano solo all'utente corrente e vengono avviati nel computer locale.

  - Coinvolgere altri utenti, ad esempio un programma di collaborazione online, e deve essere avviato nel computer di ogni utente.

Il comando personalizzato può essere richiamato nei modi seguenti:

  - Selezionare uno o più utenti e quindi scegliere il comando personalizzato.

  - Avviare una conversazione con due o più parti e quindi scegliere il comando personalizzato.

<div>

## <a name="to-add-a-custom-command"></a>Per aggiungere un comando personalizzato

Usare le impostazioni del registro di sistema nella tabella seguente per aggiungere un comando ai menu. Queste voci vengono inserite nel registro di sistema in una delle posizioni seguenti:

  - Per il sistema operativo a\_32\_bit\\:\\HKEY\\Local\\computer\\software\\Microsoft\\Office 15,0 Lync SessionManager app

  - Per il sistema operativo 64bit\_:\_HKEY\\LOCAL\\Machine\\software\\Wow6432Node\\Microsoft\\Office\\15,0\\Lync SessionManager Apps

### <a name="custom-command-registry-entries"></a>Voci del registro di sistema dei comandi personalizzati

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
<td><p>0 = eseguibile (impostazione predefinita)</p>
<div>

> [!NOTE]  
> Richiede ApplicationInstallPath.


</div>
<p>1 = protocollo</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso completo dell'eseguibile.</p>
<div>

> [!NOTE]  
> Deve essere specificato se ApplicationType è 0 (eseguibile).


</div></td>
</tr>
<tr class="even">
<td><p>Percorso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Percorso completo da avviare insieme a tutti i parametri, inclusi i parametri predefiniti% <em>User-ID%</em> e <em>% Contact-ID</em>%.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = sessione locale. L'applicazione viene avviata nel computer locale.</p>
<p>1 = sessione a due parti (impostazione predefinita). Lync 2013 avvia l'applicazione localmente e quindi invia una notifica desktop per l'altro utente. L'altro utente fa clic sulla notifica per avviare l'applicazione nel computer in uso.</p>
<p>2 = sessione in più parti. Lync 2013 avvia l'applicazione localmente e quindi invia notifiche desktop agli altri utenti. L'altro utente fa clic sulla notifica per avviare l'applicazione specificata nel computer in uso.</p></td>
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
<p>Se ExtensibleMenu non è definito, vengono usati i valori predefiniti di MainWindowRightClick e ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


Ad esempio, l'editor del registro di sistema seguente (. REG) Mostra i risultati dell'aggiunta di una voce di menu di Contoso Sales Contact Manager al menu azioni nella finestra di conversazione:

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

Per accedere a un comando personalizzato dopo l'aggiunta, eseguire una delle operazioni seguenti, a seconda dei valori di ExtensibleMenu definiti:

  - **MainWindowActions**   nella finestra principale di Lync, fare clic su **strumenti**e quindi su comando personalizzato.

  - **MainWindowRightClick**   nella finestra principale di Lync, fare clic con il pulsante destro del mouse su un contatto e quindi scegliere il comando personalizzato.

  - **ConversationWindowActions**   nella finestra di conversazione, fare clic sull'icona **altre opzioni** e quindi fare clic sul comando personalizzato.

  - **ConversationWindowRightClick**   nella finestra di conversazione fare clic con il pulsante destro del mouse su un nome di contatto e quindi scegliere il comando personalizzato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

