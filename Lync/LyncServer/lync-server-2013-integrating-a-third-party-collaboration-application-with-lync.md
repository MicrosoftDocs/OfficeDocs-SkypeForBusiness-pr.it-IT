---
title: Integrazione di un'applicazione di collaborazione di terze parti con Lync
description: Integrazione di un'applicazione di collaborazione di terze parti con Lync.
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
ms.openlocfilehash: 7adbe1abab83a569f581af034fc46abfef4cf819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552652"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="88e16-103">Integrazione di un'applicazione di collaborazione di terze parti con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88e16-103">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e16-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="88e16-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="88e16-105">È possibile integrare Lync 2013 con qualsiasi applicazione di collaborazione online di terze parti aggiungendo informazioni sull'applicazione al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="88e16-105">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="88e16-106">È possibile utilizzare Lync 2013 per avviare le sessioni di conferenza dati ospitate in un server interno, in un servizio basato su Internet o in entrambi.</span><span class="sxs-lookup"><span data-stu-id="88e16-106">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="88e16-107">La sessione di collaborazione o di conferenza dati può essere avviata dall'elenco contatti oppure da una sessione video, vocale o di messaggistica istantanea esistente.</span><span class="sxs-lookup"><span data-stu-id="88e16-107">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="88e16-108">Lync 2013 agisce solo come veicolo per l'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="88e16-108">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="88e16-109">Tutte le conversazioni di Lync 2013 esistenti rimangono attive dopo l'inizio della sessione di collaborazione online.</span><span class="sxs-lookup"><span data-stu-id="88e16-109">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="88e16-110">Nelle sezioni seguenti viene descritto come integrare Lync 2013 con le applicazioni di collaborazione basata su Internet e basate su server.</span><span class="sxs-lookup"><span data-stu-id="88e16-110">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="88e16-111">Integrazione di un'applicazione di collaborazione Internet-Based con Lync 2013</span><span class="sxs-lookup"><span data-stu-id="88e16-111">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="88e16-112">In generale, la procedura per integrare un'applicazione di collaborazione di terze parti è la seguente:</span><span class="sxs-lookup"><span data-stu-id="88e16-112">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="88e16-113">Le informazioni relative all'applicazione vengono aggiunte al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="88e16-113">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="88e16-114">L'organizzatore accede a Lync 2013 e seleziona Contatti per la condivisione e la collaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="88e16-114">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="88e16-115">È anche possibile che l'organizzatore sia già impegnato in una conversazione e decida di aggiungere la funzionalità per conferenze dati.</span><span class="sxs-lookup"><span data-stu-id="88e16-115">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="88e16-116">Lync 2013 legge il registro di sistema, avvia l'applicazione di collaborazione e quindi Invia un messaggio SIP personalizzato, ovvero un appINVITE, ai partecipanti selezionati.</span><span class="sxs-lookup"><span data-stu-id="88e16-116">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="88e16-117">I partecipanti accettano l'invito e l'applicazione di collaborazione viene avviata nel computer di ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="88e16-117">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="88e16-118">Lync 2013 utilizza il registro di sistema per determinare l'applicazione di collaborazione da utilizzare e quindi avvia l'applicazione utilizzando i parametri inclusi nel messaggio appINVITE.</span><span class="sxs-lookup"><span data-stu-id="88e16-118">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="88e16-119">Nella tabella seguente vengono descritte le voci del registro di sistema necessarie per l'integrazione di un'applicazione di collaborazione basata su Internet con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="88e16-119">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="88e16-120">Tali voci vengono inserite nel registro di sistema nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="88e16-120">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="88e16-121">HKEY \_ Local \_ Machine \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ Apps \\ Parameters</span><span class="sxs-lookup"><span data-stu-id="88e16-121">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="88e16-122">Voci del Registro di sistema per un'applicazione di collaborazione basata su Internet</span><span class="sxs-lookup"><span data-stu-id="88e16-122">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88e16-123">Nome</span><span class="sxs-lookup"><span data-stu-id="88e16-123">Name</span></span></th>
<th><span data-ttu-id="88e16-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="88e16-124">Type</span></span></th>
<th><span data-ttu-id="88e16-125">Dati</span><span class="sxs-lookup"><span data-stu-id="88e16-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88e16-126">Nome</span><span class="sxs-lookup"><span data-stu-id="88e16-126">Name</span></span></p></td>
<td><p><span data-ttu-id="88e16-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-128">Il nome dell'applicazione per i menu di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="88e16-128">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e16-129">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="88e16-129">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="88e16-130">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-130">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-131">Percorso dell'icona 16 x 16 pixel in formato BMP o PNG.</span><span class="sxs-lookup"><span data-stu-id="88e16-131">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e16-132">Percorso</span><span class="sxs-lookup"><span data-stu-id="88e16-132">Path</span></span></p></td>
<td><p><span data-ttu-id="88e16-133">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-133">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-134">Percorso dei partecipanti per l'avvio dell'applicazione di collaborazione online.</span><span class="sxs-lookup"><span data-stu-id="88e16-134">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e16-135">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="88e16-135">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="88e16-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-137">Percorso dell'organizzatore per l'avvio dell'applicazione di collaborazione online.</span><span class="sxs-lookup"><span data-stu-id="88e16-137">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="88e16-138">Questo percorso può contenere uno o più parametri personalizzati, definiti nella sottochiave Parameters.</span><span class="sxs-lookup"><span data-stu-id="88e16-138">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="88e16-139">Per esempio <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="88e16-139">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e16-140">SessionType</span><span class="sxs-lookup"><span data-stu-id="88e16-140">SessionType</span></span></p></td>
<td><p><span data-ttu-id="88e16-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="88e16-141">DWORD</span></span></p></td>
<td><p><span data-ttu-id="88e16-p106">0 = Sessione locale. L'applicazione viene avviata nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="88e16-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="88e16-144">1 = Sessione tra due parti (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="88e16-144">1 = Two-party session (default).</span></span> <span data-ttu-id="88e16-145">Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente.</span><span class="sxs-lookup"><span data-stu-id="88e16-145">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="88e16-146">L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="88e16-146">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="88e16-147">2 = Sessione tra più parti.</span><span class="sxs-lookup"><span data-stu-id="88e16-147">2 = Multiparty session.</span></span> <span data-ttu-id="88e16-148">Lync 2013 avvia l'applicazione localmente e quindi invia notifiche di sistema agli altri utenti, richiedendo loro di avviare l'applicazione specificata nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="88e16-148">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e16-149">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="88e16-149">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="88e16-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-p109">Elenco dei menu, delimitati da punto e virgola, in cui verrà visualizzato il comando. I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="88e16-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="88e16-153">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="88e16-153">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="88e16-154">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="88e16-154">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="88e16-155">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="88e16-155">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="88e16-156">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="88e16-156">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="88e16-157">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="88e16-157">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="88e16-158">Se ExtensibleMenu non è definito, vengono utilizzati i valori predefiniti MainWindowRightClick e ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="88e16-158">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88e16-159">Nella tabella riportata di seguito vengono illustrate le voci del Registro di sistema per i parametri.</span><span class="sxs-lookup"><span data-stu-id="88e16-159">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="88e16-160">Queste voci sono posizionate in HKEY i \_ \_ parametri di \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ Apps \\ .</span><span class="sxs-lookup"><span data-stu-id="88e16-160">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="88e16-161">Voci del Registro di sistema per un'applicazione di collaborazione basata su Internet</span><span class="sxs-lookup"><span data-stu-id="88e16-161">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88e16-162">Nome</span><span class="sxs-lookup"><span data-stu-id="88e16-162">Name</span></span></th>
<th><span data-ttu-id="88e16-163">Tipo</span><span class="sxs-lookup"><span data-stu-id="88e16-163">Type</span></span></th>
<th><span data-ttu-id="88e16-164">Dati</span><span class="sxs-lookup"><span data-stu-id="88e16-164">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88e16-165">Param1</span><span class="sxs-lookup"><span data-stu-id="88e16-165">Param1</span></span></p></td>
<td><p><span data-ttu-id="88e16-166">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-166">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-167">Utilizzato in formato token ( <code>%Parm1%</code> ) per aggiungere valori specifici dell'utente alla chiave del registro di sistema OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="88e16-167">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e16-168">Param2</span><span class="sxs-lookup"><span data-stu-id="88e16-168">Param2</span></span></p></td>
<td><p><span data-ttu-id="88e16-169">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-169">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-170">Vedere Param1.</span><span class="sxs-lookup"><span data-stu-id="88e16-170">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e16-171">Param3</span><span class="sxs-lookup"><span data-stu-id="88e16-171">Param3</span></span></p></td>
<td><p><span data-ttu-id="88e16-172">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-172">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-173">Vedere Param1.</span><span class="sxs-lookup"><span data-stu-id="88e16-173">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88e16-174">Nelle impostazioni del registro di sistema di esempio seguenti viene integrato il client di collaborazione ADatum con Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="88e16-174">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="88e16-175">Integrazione di un'applicazione di collaborazione Server-Based con Lync 2013</span><span class="sxs-lookup"><span data-stu-id="88e16-175">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="88e16-176">Le impostazioni per l'aggiunta di comandi per l'avvio di un'applicazione di collaborazione basata su server dall'interno di Lync 2013 sono simili a quelle descritte nella sezione precedente, in cui è stata integrata un'applicazione di collaborazione Internet-Based con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="88e16-176">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="88e16-177">La voce OriginatorPath tuttavia non è necessaria e alcuni valori sono diversi.</span><span class="sxs-lookup"><span data-stu-id="88e16-177">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="88e16-178">Le voci del registro di sistema vengono inserite nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="88e16-178">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="88e16-179">HKEY \_ Local \_ Machine \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ Apps \\ Parameters</span><span class="sxs-lookup"><span data-stu-id="88e16-179">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="88e16-180">Voci del Registro di sistema per un'applicazione di collaborazione basata su server</span><span class="sxs-lookup"><span data-stu-id="88e16-180">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88e16-181">Nome</span><span class="sxs-lookup"><span data-stu-id="88e16-181">Name</span></span></th>
<th><span data-ttu-id="88e16-182">Tipo</span><span class="sxs-lookup"><span data-stu-id="88e16-182">Type</span></span></th>
<th><span data-ttu-id="88e16-183">Dati</span><span class="sxs-lookup"><span data-stu-id="88e16-183">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88e16-184">Nome</span><span class="sxs-lookup"><span data-stu-id="88e16-184">Name</span></span></p></td>
<td><p><span data-ttu-id="88e16-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-185">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-186">Nome dell'applicazione visualizzato nel menu.</span><span class="sxs-lookup"><span data-stu-id="88e16-186">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e16-187">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="88e16-187">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="88e16-188">DWORD</span><span class="sxs-lookup"><span data-stu-id="88e16-188">DWORD</span></span></p></td>
<td><p><span data-ttu-id="88e16-189">Valore = 1.</span><span class="sxs-lookup"><span data-stu-id="88e16-189">Value = 1.</span></span> <span data-ttu-id="88e16-190">Imposta il tipo di applicazione su Protocollo.</span><span class="sxs-lookup"><span data-stu-id="88e16-190">Sets the application type to protocol.</span></span> <span data-ttu-id="88e16-191">In questo caso non si applicano gli altri valori possibili.</span><span class="sxs-lookup"><span data-stu-id="88e16-191">The other possible values do not apply in this case.</span></span> <span data-ttu-id="88e16-192">Se non è presente, ApplicationType è impostato su 0 (eseguibile).</span><span class="sxs-lookup"><span data-stu-id="88e16-192">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e16-193">Percorso</span><span class="sxs-lookup"><span data-stu-id="88e16-193">Path</span></span></p></td>
<td><p><span data-ttu-id="88e16-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-194">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-195">Protocollo utilizzato per avviare l'applicazione di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="88e16-195">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="88e16-196">Per Live Meeting 2007, il valore di path è impostato su <code>meet:%conf-uri%</code> .</span><span class="sxs-lookup"><span data-stu-id="88e16-196">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e16-197">SessionType</span><span class="sxs-lookup"><span data-stu-id="88e16-197">SessionType</span></span></p></td>
<td><p><span data-ttu-id="88e16-198">DWORD</span><span class="sxs-lookup"><span data-stu-id="88e16-198">DWORD</span></span></p></td>
<td><p><span data-ttu-id="88e16-p114">0 = Sessione locale. L'applicazione viene avviata nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="88e16-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="88e16-201">1 = Sessione tra due parti (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="88e16-201">1 = Two-party session (default).</span></span> <span data-ttu-id="88e16-202">Lync 2013 avvia l'applicazione localmente e quindi invia una notifica di sistema all'altro utente.</span><span class="sxs-lookup"><span data-stu-id="88e16-202">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="88e16-203">L'altro utente fa clic sulla notifica e avvia l'applicazione specificata nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="88e16-203">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="88e16-204">2 = Sessione tra più parti.</span><span class="sxs-lookup"><span data-stu-id="88e16-204">2 = Multiparty session.</span></span> <span data-ttu-id="88e16-205">Lync 2013 avvia l'applicazione localmente e quindi invia notifiche di sistema agli altri utenti, richiedendo loro di avviare l'applicazione specificata nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="88e16-205">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88e16-206">MCUType</span><span class="sxs-lookup"><span data-stu-id="88e16-206">MCUType</span></span></p></td>
<td><p><span data-ttu-id="88e16-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-208">DATI = Tipo di server.</span><span class="sxs-lookup"><span data-stu-id="88e16-208">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88e16-209">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="88e16-209">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="88e16-210">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="88e16-210">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="88e16-211">Elenco dei menu in cui verrà visualizzato il comando, separati da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="88e16-211">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="88e16-212">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="88e16-212">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="88e16-213">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="88e16-213">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="88e16-214">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="88e16-214">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="88e16-215">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="88e16-215">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="88e16-216">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="88e16-216">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="88e16-217">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="88e16-217">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="88e16-218">Se ExtensibleMenu non è definito, vengono utilizzati i valori predefiniti MainWindowRightClick e ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="88e16-218">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88e16-219">Nell'esempio seguente vengono aggiunti i comandi per avviare il client di collaborazione ADatum dall'interno di Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="88e16-219">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

