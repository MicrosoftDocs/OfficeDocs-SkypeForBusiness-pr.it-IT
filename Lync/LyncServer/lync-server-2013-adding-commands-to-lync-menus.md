---
title: 'Lync Server 2013: aggiunta di comandi ai menu di Lync'
description: 'Lync Server 2013: aggiunta di comandi ai menu di Lync.'
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
ms.openlocfilehash: ed4d62d085eaf115d107244ae50a7cc69e0aacd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558232"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="e6a50-103">Aggiunta di comandi ai menu di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a50-103">Adding commands to Lync menus in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6a50-104">_**Ultimo argomento modificato:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="e6a50-104">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="e6a50-105">È possibile aggiungere comandi personalizzati ai menu di Lync 2013 e passare l'URI (Uniform Resource Identifier) SIP dell'utente corrente e i contatti selezionati all'applicazione che viene avviata dal comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6a50-105">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="e6a50-106">È possibile visualizzare i comandi personalizzati aggiunti all'interno di uno o più dei menu seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6a50-106">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="e6a50-107">Menu Strumenti, sulla barra dei menu della finestra principale di Lync</span><span class="sxs-lookup"><span data-stu-id="e6a50-107">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="e6a50-108">Menu di scelta rapida per i contatti nell'elenco Contatti</span><span class="sxs-lookup"><span data-stu-id="e6a50-108">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="e6a50-109">Il menu altre opzioni, nella finestra di conversazione</span><span class="sxs-lookup"><span data-stu-id="e6a50-109">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="e6a50-110">Menu di scelta rapida per gli utenti elencati nell'elenco dei partecipanti della finestra Conversazione</span><span class="sxs-lookup"><span data-stu-id="e6a50-110">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="e6a50-111">Menu Opzioni in una scheda contatto</span><span class="sxs-lookup"><span data-stu-id="e6a50-111">The options menu in a contact card</span></span>

<span data-ttu-id="e6a50-112">È possibile definire comandi personalizzati per due tipi di applicazioni, ovvero per le applicazioni con una delle caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6a50-112">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="e6a50-113">Si applicano solo all'utente corrente e vengono avviate nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="e6a50-113">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="e6a50-114">Coinvolgono altri utenti, come avviene con i programmi di collaborazione online, e devono essere avviate nel computer di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="e6a50-114">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="e6a50-115">È possibile richiamare il comando personalizzato nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6a50-115">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="e6a50-116">Selezionare uno o più utenti e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6a50-116">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="e6a50-117">Avviare una conversazione con due o più partecipanti e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6a50-117">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="e6a50-118">Per aggiungere un comando personalizzato</span><span class="sxs-lookup"><span data-stu-id="e6a50-118">To add a custom command</span></span>

<span data-ttu-id="e6a50-119">Utilizzare le impostazioni del registro di sistema nella tabella seguente per aggiungere un comando ai menu.</span><span class="sxs-lookup"><span data-stu-id="e6a50-119">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="e6a50-120">Tali voci vengono inserite nel registro di sistema in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6a50-120">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="e6a50-121">Per il sistema operativo a 32bit: HKEY \_ Local \_ Machine \\ SOFTWARE \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ Apps</span><span class="sxs-lookup"><span data-stu-id="e6a50-121">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="e6a50-122">Per il sistema operativo a 64bit: HKEY \_ Local \_ Machine \\ software \\ Wow6432Node \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ Apps</span><span class="sxs-lookup"><span data-stu-id="e6a50-122">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="e6a50-123">Voci del Registro di sistema dei comandi personalizzati</span><span class="sxs-lookup"><span data-stu-id="e6a50-123">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6a50-124">Nome</span><span class="sxs-lookup"><span data-stu-id="e6a50-124">Name</span></span></th>
<th><span data-ttu-id="e6a50-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6a50-125">Type</span></span></th>
<th><span data-ttu-id="e6a50-126">Dati</span><span class="sxs-lookup"><span data-stu-id="e6a50-126">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6a50-127">Nome</span><span class="sxs-lookup"><span data-stu-id="e6a50-127">Name</span></span></p></td>
<td><p><span data-ttu-id="e6a50-128">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e6a50-128">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="e6a50-129">Nome dell'applicazione visualizzato nel menu.</span><span class="sxs-lookup"><span data-stu-id="e6a50-129">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a50-130">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="e6a50-130">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="e6a50-131">DWORD</span><span class="sxs-lookup"><span data-stu-id="e6a50-131">DWORD</span></span></p></td>
<td><p><span data-ttu-id="e6a50-132">0 = Eseguibile (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e6a50-132">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e6a50-133">Richiede ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="e6a50-133">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="e6a50-134">1 = Protocollo</span><span class="sxs-lookup"><span data-stu-id="e6a50-134">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a50-135">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="e6a50-135">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="e6a50-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e6a50-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="e6a50-137">Percorso completo dell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e6a50-137">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e6a50-138">Deve essere specificato se ApplicationType è 0 (Eseguibile).</span><span class="sxs-lookup"><span data-stu-id="e6a50-138">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a50-139">Percorso</span><span class="sxs-lookup"><span data-stu-id="e6a50-139">Path</span></span></p></td>
<td><p><span data-ttu-id="e6a50-140">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e6a50-140">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="e6a50-141">Percorso completo di avvio con eventuali parametri, compresi i parametri predefiniti<em>%user-id%</em> e <em>%contact-id%</em>.</span><span class="sxs-lookup"><span data-stu-id="e6a50-141">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a50-142">SessionType</span><span class="sxs-lookup"><span data-stu-id="e6a50-142">SessionType</span></span></p></td>
<td><p><span data-ttu-id="e6a50-143">DWORD</span><span class="sxs-lookup"><span data-stu-id="e6a50-143">DWORD</span></span></p></td>
<td><p><span data-ttu-id="e6a50-p102">0 = Sessione locale. L'applicazione viene avviata nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="e6a50-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="e6a50-146">1 = Sessione tra due parti (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="e6a50-146">1 = Two-party session (default).</span></span> <span data-ttu-id="e6a50-147">Lync 2013 avvia l'applicazione localmente e quindi invia una notifica desktop all'altro utente.</span><span class="sxs-lookup"><span data-stu-id="e6a50-147">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="e6a50-148">L'altro utente fa clic sulla notifica per avviare l'applicazione nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="e6a50-148">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="e6a50-149">2 = Sessione tra più parti.</span><span class="sxs-lookup"><span data-stu-id="e6a50-149">2 = Multiparty session.</span></span> <span data-ttu-id="e6a50-150">Lync 2013 avvia l'applicazione localmente e quindi invia notifiche desktop agli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="e6a50-150">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="e6a50-151">L'altro utente fa clic sulla notifica per avviare l'applicazione specificata nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="e6a50-151">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a50-152">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="e6a50-152">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="e6a50-153">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e6a50-153">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="e6a50-154">Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="e6a50-154">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="e6a50-155">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e6a50-155">Possible values are:</span></span></p>
<p><span data-ttu-id="e6a50-156">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="e6a50-156">MainWindowActions</span></span></p>
<p><span data-ttu-id="e6a50-157">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="e6a50-157">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="e6a50-158">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="e6a50-158">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="e6a50-159">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="e6a50-159">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="e6a50-160">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="e6a50-160">ContactCardMenu</span></span></p>
<p><span data-ttu-id="e6a50-161">Se ExtensibleMenu non è definito, vengono utilizzati i valori predefiniti MainWindowRightClick e ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="e6a50-161">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e6a50-162">Ad esempio, nel file dell'editor del Registro di sistema (con estensione REG) seguente sono illustrati i risultati dell'aggiunta della voce di menu Contoso Sales Contact Manager al menu Azioni nella finestra Conversazione:</span><span class="sxs-lookup"><span data-stu-id="e6a50-162">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="e6a50-163">Per accedere a un comando personalizzato</span><span class="sxs-lookup"><span data-stu-id="e6a50-163">To access a custom command</span></span>

<span data-ttu-id="e6a50-164">Per accedere a un comando personalizzato dopo che è stato aggiunto, eseguire una delle operazioni seguenti, a seconda dei valori di ExtensibleMenu definiti:</span><span class="sxs-lookup"><span data-stu-id="e6a50-164">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="e6a50-165">**MainWindowActions**     Nella finestra principale di Lync, fare clic su **strumenti**, quindi fare clic sul comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6a50-165">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="e6a50-166">**MainWindowRightClick**     Nella finestra principale di Lync fare clic con il pulsante destro del mouse su un contatto e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6a50-166">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="e6a50-167">**ConversationWindowActions**     Nella finestra di conversazione, fare clic sull'icona **altre opzioni** , quindi fare clic sul comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6a50-167">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="e6a50-168">**ConversationWindowRightClick**     Nella finestra di conversazione fare clic con il pulsante destro del mouse su un nome di contatto e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e6a50-168">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

