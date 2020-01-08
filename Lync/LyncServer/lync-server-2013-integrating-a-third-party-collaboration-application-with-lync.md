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

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="18cf7-102">Integrazione di un'applicazione di collaborazione di terze parti con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18cf7-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18cf7-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="18cf7-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="18cf7-104">È possibile integrare Lync 2013 con un'applicazione di collaborazione online di terze parti aggiungendo informazioni sull'applicazione al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="18cf7-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="18cf7-105">È possibile usare Lync 2013 per avviare sessioni di conferenza dati ospitate in un server interno, un servizio basato su Internet o entrambi.</span><span class="sxs-lookup"><span data-stu-id="18cf7-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="18cf7-106">La sessione di collaborazione o conferenza dati può essere avviata dall'elenco contatti o da una sessione di messaggistica istantanea, vocale o video esistente.</span><span class="sxs-lookup"><span data-stu-id="18cf7-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="18cf7-107">Lync 2013 agisce solo come veicolo per l'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18cf7-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="18cf7-108">Le conversazioni di Lync 2013 esistenti rimangono attive dopo l'inizio della sessione di collaborazione online.</span><span class="sxs-lookup"><span data-stu-id="18cf7-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="18cf7-109">Nelle sezioni seguenti viene descritto come integrare Lync 2013 con le applicazioni di collaborazione basate su Internet e basate su server.</span><span class="sxs-lookup"><span data-stu-id="18cf7-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="18cf7-110">Integrazione di un'applicazione di collaborazione basata su Internet con Lync 2013</span><span class="sxs-lookup"><span data-stu-id="18cf7-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="18cf7-111">In generale, i passaggi necessari per l'integrazione di un'applicazione di collaborazione di terze parti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="18cf7-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="18cf7-112">Le informazioni sull'applicazione vengono aggiunte al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="18cf7-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="18cf7-113">L'organizzatore accede a Lync 2013 e seleziona i contatti per la condivisione e la collaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="18cf7-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="18cf7-114">In alternativa, l'organizzatore può già partecipare a una conversazione e decidere di aggiungere servizi di conferenza dati.</span><span class="sxs-lookup"><span data-stu-id="18cf7-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="18cf7-115">Lync 2013 legge il registro di sistema, avvia l'applicazione di collaborazione e quindi Invia un messaggio SIP personalizzato, ovvero un appINVITE, ai partecipanti selezionati.</span><span class="sxs-lookup"><span data-stu-id="18cf7-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="18cf7-116">I partecipanti accettano l'invito e l'applicazione di collaborazione viene avviata nel computer di ogni persona.</span><span class="sxs-lookup"><span data-stu-id="18cf7-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="18cf7-117">Lync 2013 usa il registro di sistema per determinare l'applicazione di collaborazione da usare e quindi avvia l'applicazione usando i parametri inclusi nel messaggio di appINVITE.</span><span class="sxs-lookup"><span data-stu-id="18cf7-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="18cf7-118">La tabella seguente descrive le voci del registro di sistema necessarie per integrare un'applicazione di collaborazione basata su Internet con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="18cf7-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="18cf7-119">Queste voci vengono inserite nel registro di sistema nella posizione seguente:</span><span class="sxs-lookup"><span data-stu-id="18cf7-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="18cf7-120">HKEY\_Local\_computer\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\parametri\\delle app</span><span class="sxs-lookup"><span data-stu-id="18cf7-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="18cf7-121">Voci del registro di sistema per un'applicazione di collaborazione basata su Internet</span><span class="sxs-lookup"><span data-stu-id="18cf7-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18cf7-122">Nome</span><span class="sxs-lookup"><span data-stu-id="18cf7-122">Name</span></span></th>
<th><span data-ttu-id="18cf7-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="18cf7-123">Type</span></span></th>
<th><span data-ttu-id="18cf7-124">Dati</span><span class="sxs-lookup"><span data-stu-id="18cf7-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-125">Nome</span><span class="sxs-lookup"><span data-stu-id="18cf7-125">Name</span></span></p></td>
<td><p><span data-ttu-id="18cf7-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-127">Nome dell'applicazione per i menu di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="18cf7-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18cf7-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="18cf7-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="18cf7-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-130">Percorso dell'icona di 16 pixel x 16 pixel, BMP o PNG.</span><span class="sxs-lookup"><span data-stu-id="18cf7-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-131">Percorso</span><span class="sxs-lookup"><span data-stu-id="18cf7-131">Path</span></span></p></td>
<td><p><span data-ttu-id="18cf7-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-133">Percorso partecipante per l'avvio dell'applicazione di collaborazione online.</span><span class="sxs-lookup"><span data-stu-id="18cf7-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18cf7-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="18cf7-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="18cf7-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-136">Percorso dell'organizzatore per l'avvio dell'applicazione di collaborazione online.</span><span class="sxs-lookup"><span data-stu-id="18cf7-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="18cf7-137">Questo percorso può contenere uno o più parametri personalizzati definiti nella sottochiave Parameters.</span><span class="sxs-lookup"><span data-stu-id="18cf7-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="18cf7-138">Per esempio<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="18cf7-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="18cf7-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="18cf7-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="18cf7-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="18cf7-141">0 = sessione locale.</span><span class="sxs-lookup"><span data-stu-id="18cf7-141">0 = Local session.</span></span> <span data-ttu-id="18cf7-142">L'applicazione viene avviata nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="18cf7-142">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="18cf7-143">1 = sessione a due parti (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="18cf7-143">1 = Two-party session (default).</span></span> <span data-ttu-id="18cf7-144">Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente.</span><span class="sxs-lookup"><span data-stu-id="18cf7-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="18cf7-145">L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="18cf7-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="18cf7-146">2 = sessione in più parti.</span><span class="sxs-lookup"><span data-stu-id="18cf7-146">2 = Multiparty session.</span></span> <span data-ttu-id="18cf7-147">Lync 2013 avvia l'applicazione localmente e quindi invia le notifiche di sistema agli altri utenti, chiedendo loro di avviare l'applicazione specificata nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="18cf7-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18cf7-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="18cf7-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="18cf7-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-150">Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="18cf7-150">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="18cf7-151">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="18cf7-151">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="18cf7-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="18cf7-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="18cf7-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="18cf7-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="18cf7-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="18cf7-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="18cf7-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="18cf7-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="18cf7-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="18cf7-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="18cf7-157">Se ExtensibleMenu non è definito, vengono usati i valori predefiniti di MainWindowRightClick e ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="18cf7-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18cf7-158">La tabella seguente descrive le voci del registro di sistema per i parametri.</span><span class="sxs-lookup"><span data-stu-id="18cf7-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="18cf7-159">Queste voci sono inserite in HKEY\_\_\\i parametri delle\\app\\\\di\\Microsoft\\Office\\15,0\\Lync sessionmanager.</span><span class="sxs-lookup"><span data-stu-id="18cf7-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="18cf7-160">Voci del registro di sistema per un'applicazione di collaborazione basata su Internet</span><span class="sxs-lookup"><span data-stu-id="18cf7-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18cf7-161">Nome</span><span class="sxs-lookup"><span data-stu-id="18cf7-161">Name</span></span></th>
<th><span data-ttu-id="18cf7-162">Tipo</span><span class="sxs-lookup"><span data-stu-id="18cf7-162">Type</span></span></th>
<th><span data-ttu-id="18cf7-163">Dati</span><span class="sxs-lookup"><span data-stu-id="18cf7-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-164">Param1</span><span class="sxs-lookup"><span data-stu-id="18cf7-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="18cf7-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-166">Usato in formato token (<code>%Parm1%</code>) per aggiungere valori specifici dell'utente alla chiave del registro di sistema OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="18cf7-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18cf7-167">Param2</span><span class="sxs-lookup"><span data-stu-id="18cf7-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="18cf7-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-169">Vedere param1.</span><span class="sxs-lookup"><span data-stu-id="18cf7-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-170">Param3</span><span class="sxs-lookup"><span data-stu-id="18cf7-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="18cf7-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-172">Vedere param1.</span><span class="sxs-lookup"><span data-stu-id="18cf7-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18cf7-173">Le impostazioni del registro di sistema di esempio seguenti integrano client di collaborazione ADatum con Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="18cf7-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="18cf7-174">Integrazione di un'applicazione di collaborazione basata su server con Lync 2013</span><span class="sxs-lookup"><span data-stu-id="18cf7-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="18cf7-175">Le impostazioni per l'aggiunta di comandi per l'avvio di un'applicazione di collaborazione basata su server dall'interno di Lync 2013 sono simili a quelle descritte nella sezione precedente, che integrano un'applicazione di collaborazione basata su Internet con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="18cf7-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="18cf7-176">Tuttavia, OriginatorPath non è obbligatorio e alcuni valori vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="18cf7-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="18cf7-177">Le voci del registro di sistema vengono inserite nella posizione seguente:</span><span class="sxs-lookup"><span data-stu-id="18cf7-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="18cf7-178">HKEY\_Local\_computer\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\parametri\\delle app</span><span class="sxs-lookup"><span data-stu-id="18cf7-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="18cf7-179">Voci del registro di sistema per un'applicazione di collaborazione basata su server</span><span class="sxs-lookup"><span data-stu-id="18cf7-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18cf7-180">Nome</span><span class="sxs-lookup"><span data-stu-id="18cf7-180">Name</span></span></th>
<th><span data-ttu-id="18cf7-181">Tipo</span><span class="sxs-lookup"><span data-stu-id="18cf7-181">Type</span></span></th>
<th><span data-ttu-id="18cf7-182">Dati</span><span class="sxs-lookup"><span data-stu-id="18cf7-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-183">Nome</span><span class="sxs-lookup"><span data-stu-id="18cf7-183">Name</span></span></p></td>
<td><p><span data-ttu-id="18cf7-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-185">Nome dell'applicazione come viene visualizzato nel menu.</span><span class="sxs-lookup"><span data-stu-id="18cf7-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18cf7-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="18cf7-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="18cf7-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="18cf7-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="18cf7-188">Valore = 1.</span><span class="sxs-lookup"><span data-stu-id="18cf7-188">Value = 1.</span></span> <span data-ttu-id="18cf7-189">Imposta il tipo di applicazione su Protocol.</span><span class="sxs-lookup"><span data-stu-id="18cf7-189">Sets the application type to protocol.</span></span> <span data-ttu-id="18cf7-190">Gli altri valori possibili non si applicano in questo caso.</span><span class="sxs-lookup"><span data-stu-id="18cf7-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="18cf7-191">Se non è presente, ApplicationType è impostato su 0 (eseguibile).</span><span class="sxs-lookup"><span data-stu-id="18cf7-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-192">Percorso</span><span class="sxs-lookup"><span data-stu-id="18cf7-192">Path</span></span></p></td>
<td><p><span data-ttu-id="18cf7-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-194">Protocollo usato per avviare l'applicazione di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="18cf7-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="18cf7-195">Per Live Meeting 2007, il valore di path è impostato su <code>meet:%conf-uri%</code>.</span><span class="sxs-lookup"><span data-stu-id="18cf7-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18cf7-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="18cf7-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="18cf7-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="18cf7-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="18cf7-198">0 = sessione locale.</span><span class="sxs-lookup"><span data-stu-id="18cf7-198">0 = Local session.</span></span> <span data-ttu-id="18cf7-199">L'applicazione viene avviata nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="18cf7-199">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="18cf7-200">1 = sessione a due parti (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="18cf7-200">1 = Two-party session (default).</span></span> <span data-ttu-id="18cf7-201">Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente.</span><span class="sxs-lookup"><span data-stu-id="18cf7-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="18cf7-202">L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="18cf7-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="18cf7-203">2 = sessione in più parti.</span><span class="sxs-lookup"><span data-stu-id="18cf7-203">2 = Multiparty session.</span></span> <span data-ttu-id="18cf7-204">Lync 2013 avvia l'applicazione localmente e quindi invia le notifiche di sistema agli altri utenti, chiedendo loro di avviare l'applicazione specificata nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="18cf7-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18cf7-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="18cf7-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="18cf7-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-207">DATA = tipo di server.</span><span class="sxs-lookup"><span data-stu-id="18cf7-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18cf7-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="18cf7-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="18cf7-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="18cf7-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="18cf7-210">Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="18cf7-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="18cf7-211">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="18cf7-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="18cf7-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="18cf7-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="18cf7-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="18cf7-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="18cf7-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="18cf7-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="18cf7-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="18cf7-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="18cf7-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="18cf7-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="18cf7-217">Se ExtensibleMenu non è definito, vengono usati i valori predefiniti di MainWindowRightClick e ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="18cf7-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18cf7-218">L'esempio seguente aggiunge i comandi per avviare ADatum Collaboration client dall'interno di Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="18cf7-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

