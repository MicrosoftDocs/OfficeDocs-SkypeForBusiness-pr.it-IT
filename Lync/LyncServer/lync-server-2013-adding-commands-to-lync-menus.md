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
ms.openlocfilehash: b1cbce99116159d119eaa604b7000764913b3cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="be43a-102">Aggiunta di comandi ai menu di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be43a-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be43a-103">_**Argomento Ultima modifica:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="be43a-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="be43a-104">È possibile aggiungere comandi personalizzati ai menu di Lync 2013 e passare l'URI (Uniform Resource Identifier) SIP dell'utente corrente e i contatti selezionati all'applicazione avviata dal comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be43a-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="be43a-105">I comandi personalizzati aggiunti possono essere visualizzati in uno o più dei menu seguenti:</span><span class="sxs-lookup"><span data-stu-id="be43a-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="be43a-106">Menu strumenti nella barra dei menu della finestra principale di Lync</span><span class="sxs-lookup"><span data-stu-id="be43a-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="be43a-107">Menu di scelta rapida per i contatti nell'elenco contatti</span><span class="sxs-lookup"><span data-stu-id="be43a-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="be43a-108">Menu altre opzioni nella finestra di conversazione</span><span class="sxs-lookup"><span data-stu-id="be43a-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="be43a-109">Menu di scelta rapida per gli utenti elencati nell'elenco dei partecipanti della finestra di conversazione</span><span class="sxs-lookup"><span data-stu-id="be43a-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="be43a-110">Menu opzioni in una scheda contatto</span><span class="sxs-lookup"><span data-stu-id="be43a-110">The options menu in a contact card</span></span>

<span data-ttu-id="be43a-111">Puoi definire comandi personalizzati per due tipi di applicazioni, ovvero applicazioni che eseguono una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="be43a-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="be43a-112">Si applicano solo all'utente corrente e vengono avviati nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="be43a-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="be43a-113">Coinvolgere altri utenti, ad esempio un programma di collaborazione online, e deve essere avviato nel computer di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="be43a-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="be43a-114">Il comando personalizzato può essere richiamato nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="be43a-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="be43a-115">Selezionare uno o più utenti e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be43a-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="be43a-116">Avviare una conversazione con due o più parti e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be43a-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="be43a-117">Per aggiungere un comando personalizzato</span><span class="sxs-lookup"><span data-stu-id="be43a-117">To add a custom command</span></span>

<span data-ttu-id="be43a-118">Usare le impostazioni del registro di sistema nella tabella seguente per aggiungere un comando ai menu.</span><span class="sxs-lookup"><span data-stu-id="be43a-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="be43a-119">Queste voci vengono inserite nel registro di sistema in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="be43a-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="be43a-120">Per il sistema operativo a\_32\_bit\\:\\HKEY\\Local\\computer\\software\\Microsoft\\Office 15,0 Lync SessionManager app</span><span class="sxs-lookup"><span data-stu-id="be43a-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="be43a-121">Per il sistema operativo 64bit\_:\_HKEY\\LOCAL\\Machine\\software\\Wow6432Node\\Microsoft\\Office\\15,0\\Lync SessionManager Apps</span><span class="sxs-lookup"><span data-stu-id="be43a-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="be43a-122">Voci del registro di sistema dei comandi personalizzati</span><span class="sxs-lookup"><span data-stu-id="be43a-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be43a-123">Nome</span><span class="sxs-lookup"><span data-stu-id="be43a-123">Name</span></span></th>
<th><span data-ttu-id="be43a-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="be43a-124">Type</span></span></th>
<th><span data-ttu-id="be43a-125">Dati</span><span class="sxs-lookup"><span data-stu-id="be43a-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be43a-126">Nome</span><span class="sxs-lookup"><span data-stu-id="be43a-126">Name</span></span></p></td>
<td><p><span data-ttu-id="be43a-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="be43a-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="be43a-128">Nome dell'applicazione come viene visualizzato nel menu.</span><span class="sxs-lookup"><span data-stu-id="be43a-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be43a-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="be43a-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="be43a-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="be43a-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="be43a-131">0 = eseguibile (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="be43a-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="be43a-132">Richiede ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="be43a-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="be43a-133">1 = protocollo</span><span class="sxs-lookup"><span data-stu-id="be43a-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be43a-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="be43a-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="be43a-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="be43a-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="be43a-136">Percorso completo dell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="be43a-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="be43a-137">Deve essere specificato se ApplicationType è 0 (eseguibile).</span><span class="sxs-lookup"><span data-stu-id="be43a-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be43a-138">Percorso</span><span class="sxs-lookup"><span data-stu-id="be43a-138">Path</span></span></p></td>
<td><p><span data-ttu-id="be43a-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="be43a-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="be43a-140">Percorso completo da avviare insieme a tutti i parametri, inclusi i parametri predefiniti% <em>User-ID%</em> e <em>% Contact-ID</em>%.</span><span class="sxs-lookup"><span data-stu-id="be43a-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be43a-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="be43a-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="be43a-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="be43a-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="be43a-143">0 = sessione locale.</span><span class="sxs-lookup"><span data-stu-id="be43a-143">0 = Local session.</span></span> <span data-ttu-id="be43a-144">L'applicazione viene avviata nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="be43a-144">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="be43a-145">1 = sessione a due parti (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="be43a-145">1 = Two-party session (default).</span></span> <span data-ttu-id="be43a-146">Lync 2013 avvia l'applicazione localmente e quindi invia una notifica desktop per l'altro utente.</span><span class="sxs-lookup"><span data-stu-id="be43a-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="be43a-147">L'altro utente fa clic sulla notifica per avviare l'applicazione nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="be43a-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="be43a-148">2 = sessione in più parti.</span><span class="sxs-lookup"><span data-stu-id="be43a-148">2 = Multiparty session.</span></span> <span data-ttu-id="be43a-149">Lync 2013 avvia l'applicazione localmente e quindi invia notifiche desktop agli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="be43a-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="be43a-150">L'altro utente fa clic sulla notifica per avviare l'applicazione specificata nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="be43a-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be43a-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="be43a-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="be43a-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="be43a-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="be43a-153">Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="be43a-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="be43a-154">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="be43a-154">Possible values are:</span></span></p>
<p><span data-ttu-id="be43a-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="be43a-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="be43a-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="be43a-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="be43a-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="be43a-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="be43a-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="be43a-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="be43a-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="be43a-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="be43a-160">Se ExtensibleMenu non è definito, vengono usati i valori predefiniti di MainWindowRightClick e ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="be43a-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be43a-161">Ad esempio, l'editor del registro di sistema seguente (. REG) Mostra i risultati dell'aggiunta di una voce di menu di Contoso Sales Contact Manager al menu azioni nella finestra di conversazione:</span><span class="sxs-lookup"><span data-stu-id="be43a-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="be43a-162">Per accedere a un comando personalizzato</span><span class="sxs-lookup"><span data-stu-id="be43a-162">To access a custom command</span></span>

<span data-ttu-id="be43a-163">Per accedere a un comando personalizzato dopo l'aggiunta, eseguire una delle operazioni seguenti, a seconda dei valori di ExtensibleMenu definiti:</span><span class="sxs-lookup"><span data-stu-id="be43a-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="be43a-164">**MainWindowActions**   nella finestra principale di Lync, fare clic su **strumenti**e quindi su comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be43a-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="be43a-165">**MainWindowRightClick**   nella finestra principale di Lync, fare clic con il pulsante destro del mouse su un contatto e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be43a-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="be43a-166">**ConversationWindowActions**   nella finestra di conversazione, fare clic sull'icona **altre opzioni** e quindi fare clic sul comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be43a-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="be43a-167">**ConversationWindowRightClick**   nella finestra di conversazione fare clic con il pulsante destro del mouse su un nome di contatto e quindi scegliere il comando personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be43a-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

