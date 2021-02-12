---
title: Autorizzazioni e considerazioni sulle app Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: L'amministratore può conoscere i dati e le autorizzazioni che le app di Microsoft Teams richiedono all'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739384"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="39317-103">Autorizzazioni e considerazioni sulle app Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="39317-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="39317-104">Le app di Microsoft Teams consentono di aggregare una o più funzionalità in un pacchetto _dell'app_ che può essere installato, aggiornato e disinstallato.</span><span class="sxs-lookup"><span data-stu-id="39317-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="39317-105">Le funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="39317-105">The capabilities include:</span></span>

- <span data-ttu-id="39317-106">Bot</span><span class="sxs-lookup"><span data-stu-id="39317-106">Bots</span></span>
- <span data-ttu-id="39317-107">Estensioni per la messaggistica</span><span class="sxs-lookup"><span data-stu-id="39317-107">Messaging extensions</span></span>
- <span data-ttu-id="39317-108">Schede</span><span class="sxs-lookup"><span data-stu-id="39317-108">Tabs</span></span>
- <span data-ttu-id="39317-109">Connettori</span><span class="sxs-lookup"><span data-stu-id="39317-109">Connectors</span></span>

<span data-ttu-id="39317-110">Le app sono autorizzate dagli utenti e gestite dal personale IT dal punto di vista dei criteri.</span><span class="sxs-lookup"><span data-stu-id="39317-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="39317-111">Nella maggior parte dei casi, tuttavia, le autorizzazioni e il profilo di rischio di un'app sono definiti dalle autorizzazioni e dai profili di rischio delle funzionalità contenute nell'app.</span><span class="sxs-lookup"><span data-stu-id="39317-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="39317-112">Di conseguenza, questo articolo è in particolare sulle autorizzazioni e considerazioni a livello di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="39317-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="39317-113">Le autorizzazioni elencate di seguito in maiuscolo, ad esempio RECEIVE_MESSAGE e REPLYTO_MESSAGE, non compaiono in nessuna parte della documentazione per sviluppatori di [Microsoft Teams](https://aka.ms/teamsdevdocs) o delle autorizzazioni per [Microsoft Graph.](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)</span><span class="sxs-lookup"><span data-stu-id="39317-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="39317-114">Si tratta semplicemente di un'abbreviazione descrittiva dello scopo di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="39317-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="39317-115">Titolo</span><span class="sxs-lookup"><span data-stu-id="39317-115">Title</span></span>   | <span data-ttu-id="39317-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39317-116">Description</span></span>    |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="39317-118">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="39317-118">Decision point</span></span>|<ul><li><span data-ttu-id="39317-119">Usare le tabelle seguenti come guida per determinare quali autorizzazioni vengono richieste dall'app che si sta esaminando.</span><span class="sxs-lookup"><span data-stu-id="39317-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Icona che descrive il passaggio successivo](media/audio_conferencing_image9.png)<br/><span data-ttu-id="39317-121">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="39317-121">Next step</span></span>|<ul><li><span data-ttu-id="39317-122">Eseguire una ricerca nell'app o nel servizio stesso per decidere se consentire l'accesso all'app o al servizio stesso all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="39317-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="39317-123">Ad esempio, i bot inviano e ricevono messaggi dagli utenti e, ad eccezione dei bot personalizzati aziendali, si trovano al di fuori del limite di conformità.</span><span class="sxs-lookup"><span data-stu-id="39317-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="39317-124">Di conseguenza, qualsiasi app che include un bot richiede tali autorizzazioni e ha almeno quel profilo di rischio.</span><span class="sxs-lookup"><span data-stu-id="39317-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="39317-125">Considerazioni e autorizzazioni per le app globali</span><span class="sxs-lookup"><span data-stu-id="39317-125">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="39317-126">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="39317-126">Required permissions</span></span>

<span data-ttu-id="39317-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="39317-127">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="39317-128">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="39317-128">Optional permissions</span></span>

<span data-ttu-id="39317-129">Nessuno</span><span class="sxs-lookup"><span data-stu-id="39317-129">None</span></span>

### <a name="considerations"></a><span data-ttu-id="39317-130">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="39317-130">Considerations</span></span>

- <span data-ttu-id="39317-131">Un'app deve divulgare i dati usati e i relativi dati nelle relative condizioni d'uso e nei collegamenti all'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="39317-131">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="39317-132">[Il consenso specifico delle](resource-specific-consent.md) risorse fornisce un set di autorizzazioni che le app possono richiedere, che viene visualizzato nella schermata di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="39317-132">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="39317-133">Per altre informazioni sulle autorizzazioni specifiche della risorsa, vedere Informazioni di riferimento [sulle autorizzazioni di Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="39317-133">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="39317-134">Le app possono anche avere bisogno di autorizzazioni diverse da quelle specifiche per le risorse.</span><span class="sxs-lookup"><span data-stu-id="39317-134">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="39317-135">Dopo l'installazione di un'app, l'app può richiedere le autorizzazioni di Graph tramite una richiesta di consenso.</span><span class="sxs-lookup"><span data-stu-id="39317-135">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="39317-136">Per altre informazioni, vedere Informazioni sulle esperienze di [consenso dell'applicazione Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)</span><span class="sxs-lookup"><span data-stu-id="39317-136">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="39317-137">Puoi configurare le autorizzazioni API e il consenso nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="39317-137">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="39317-138">Per altre informazioni, vedere Il framework di consenso [di Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="39317-138">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="39317-139">Bot ed estensioni di messaggistica</span><span class="sxs-lookup"><span data-stu-id="39317-139">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="39317-140">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="39317-140">Required permissions</span></span>

- <span data-ttu-id="39317-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="39317-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="39317-142">Il bot può ricevere messaggi dagli utenti e rispondere. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="39317-142">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="39317-143">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="39317-143">POST_MESSAGE_USER.</span></span> <span data-ttu-id="39317-144">Dopo che un utente ha inviato un messaggio a un bot, il bot può inviare all'utente messaggi diretti (detti anche messaggi *proattivi* in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="39317-144">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="39317-145">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="39317-145">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="39317-146">I bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali di un team.</span><span class="sxs-lookup"><span data-stu-id="39317-146">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="39317-147">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="39317-147">Optional permissions</span></span>

- <span data-ttu-id="39317-148">IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="39317-148">IDENTITY.</span></span> <span data-ttu-id="39317-149">Quando viene usato in un canale, i bot dell'app possono accedere alle informazioni di identità di base dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica); quando viene usato in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="39317-149">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="39317-150">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="39317-150">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="39317-151">Consente ai bot di un'app di inviare messaggi diretti (proattivi) a qualsiasi membro del team in qualsiasi momento, anche se l'utente non ha mai parlato con il bot prima d'ora.</span><span class="sxs-lookup"><span data-stu-id="39317-151">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="39317-152">Le autorizzazioni seguenti non sono esplicite, ma sono implicite da RECEIVE_MESSAGE e REPLYTO_MESSAGE e dagli ambiti in cui i bot possono essere usati, dichiarati nel manifesto:</span><span class="sxs-lookup"><span data-stu-id="39317-152">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="39317-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="39317-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="39317-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="39317-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="39317-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="39317-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="39317-156">SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controlla se un bot può inviare e ricevere file in una chat personale (non ancora supportato per chat di gruppo o canali).</span><span class="sxs-lookup"><span data-stu-id="39317-156">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="39317-157">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="39317-157">Considerations</span></span>

- <span data-ttu-id="39317-158">I bot hanno accesso solo ai team a cui sono stati aggiunti o agli utenti che li hanno installati.</span><span class="sxs-lookup"><span data-stu-id="39317-158">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="39317-159">I bot ricevono solo i messaggi in cui sono esplicitamente menzionati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="39317-159">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="39317-160">Questi dati lasciano la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="39317-160">This data leaves the corporate network.</span></span>

- <span data-ttu-id="39317-161">I bot possono rispondere solo alle conversazioni in cui sono menzionati.</span><span class="sxs-lookup"><span data-stu-id="39317-161">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="39317-162">Dopo che un utente ha inversato con un bot, se il bot archivia l'ID di quell'utente, può inviare all'utente messaggi diretti in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="39317-162">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="39317-163">In teoria, i messaggi bot potrebbero contenere collegamenti a siti di phishing o malware, ma i bot possono essere bloccati dall'utente, dall'amministratore del tenant o globalmente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39317-163">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="39317-164">Un bot può recuperare (e potrebbe archiviare) informazioni di identità molto di base per i membri del team a cui è stata aggiunta l'app o per singoli utenti in chat personali o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="39317-164">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="39317-165">Per ottenere altre informazioni su questi utenti, il bot deve richiedere loro di accedere ad Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="39317-165">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="39317-166">I bot possono recuperare (e archiviare) l'elenco dei canali di un team; questi dati lasciano la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="39317-166">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="39317-167">Quando un file viene inviato a un bot, lascia la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="39317-167">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="39317-168">L'invio e la ricezione di file richiede l'approvazione dell'utente per ogni file.</span><span class="sxs-lookup"><span data-stu-id="39317-168">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="39317-169">Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma possono chiedere agli utenti di accedere; Non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="39317-169">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="39317-170">La descrizione esatta di questi elementi aggiuntivi dipende dal bot e da dove l'utente accede: un bot è un'app di Azure AD registrata e può avere un https://apps.dev.microsoft.com/ proprio set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="39317-170">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="39317-171">I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.</span><span class="sxs-lookup"><span data-stu-id="39317-171">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="39317-172">I bot non vedono gli indirizzi IP degli utenti o altre informazioni referenziante.</span><span class="sxs-lookup"><span data-stu-id="39317-172">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="39317-173">Tutte le informazioni provengono da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39317-173">All information comes from Microsoft.</span></span> <span data-ttu-id="39317-174">Esiste un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso visualizza gli indirizzi IP degli utenti e le informazioni di riferimento.</span><span class="sxs-lookup"><span data-stu-id="39317-174">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="39317-175">Le estensioni per la messaggistica, al contrario, visualizzano gli indirizzi IP degli utenti e le informazioni di riferimento.</span><span class="sxs-lookup"><span data-stu-id="39317-175">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="39317-176">Le linee guida per le app (e il processo di revisione di AppSource) richiedono la pubblicazione di messaggi di chat personali agli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi.</span><span class="sxs-lookup"><span data-stu-id="39317-176">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="39317-177">In caso di abuso, gli utenti possono bloccare il bot, gli amministratori del tenant possono bloccare l'app e Microsoft può bloccare i bot a livello centrale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="39317-177">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="39317-178"><sup>1</sup> Alcuni bot inviano solo messaggi (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="39317-178"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="39317-179">Si tratta di bot "solo notifiche", ma il termine non fa riferimento a ciò che un bot è autorizzato a fare, significa che il bot non vuole esporre un'esperienza di conversazione.</span><span class="sxs-lookup"><span data-stu-id="39317-179">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="39317-180">Teams utilizza questo campo per disabilitare nell'interfaccia utente funzionalità che normalmente verrebbero abilitate; il bot non si limita a ciò che è consentito fare rispetto ai bot che espongono un'esperienza di conversazione.</span><span class="sxs-lookup"><span data-stu-id="39317-180">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="39317-181"><sup>2</sup> Disciplinato dalla proprietà booleana supportsFiles dell'oggetto bot nell'manifest.jsfile per l'app.</span><span class="sxs-lookup"><span data-stu-id="39317-181"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="39317-182">Se un bot ha un proprio accesso, c'è un secondo, diverso, esperienza del consenso la prima volta che l'utente accede.</span><span class="sxs-lookup"><span data-stu-id="39317-182">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="39317-183">Attualmente, le autorizzazioni di Azure AD associate a qualsiasi funzionalità all'interno di un'app Teams (bot, scheda, connettore o estensione di messaggistica) sono completamente separate dalle autorizzazioni di Teams elencate qui.</span><span class="sxs-lookup"><span data-stu-id="39317-183">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="39317-184">Schede</span><span class="sxs-lookup"><span data-stu-id="39317-184">Tabs</span></span>

<span data-ttu-id="39317-185">Una scheda è un sito Web in esecuzione all'interno di Teams.</span><span class="sxs-lookup"><span data-stu-id="39317-185">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="39317-186">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="39317-186">Required permissions</span></span>

<span data-ttu-id="39317-187">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="39317-187">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="39317-188">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="39317-188">Optional permissions</span></span>

<span data-ttu-id="39317-189">Nessuno (attualmente)</span><span class="sxs-lookup"><span data-stu-id="39317-189">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="39317-190">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="39317-190">Considerations</span></span>

- <span data-ttu-id="39317-191">Il profilo di rischio per una scheda è quasi identico allo stesso sito Web in esecuzione in una scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="39317-191">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="39317-192">Una scheda ottiene anche il contesto in cui è in esecuzione, inclusi il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto di Azure ACTIVE per l'utente corrente, l'ID del gruppo di Microsoft 365 in cui si trova (se si tratta di un team), l'ID tenant e le impostazioni locali correnti dell'utente.</span><span class="sxs-lookup"><span data-stu-id="39317-192">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="39317-193">Tuttavia, per mappare questi ID alle informazioni di un utente, la scheda deve fare in modo che l'utente abbia accesso ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="39317-193">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="39317-194">Connettori</span><span class="sxs-lookup"><span data-stu-id="39317-194">Connectors</span></span>

<span data-ttu-id="39317-195">Un connettore pubblica messaggi in un canale quando si verificano eventi in un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="39317-195">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="39317-196">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="39317-196">Required permissions</span></span>

<span data-ttu-id="39317-197">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="39317-197">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="39317-198">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="39317-198">Optional permissions</span></span>

<span data-ttu-id="39317-199">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="39317-199">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="39317-200">Alcuni connettori supportano messaggi su cui è possibile eseguire azioni, che consentono agli utenti di pubblicare risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda di Trello.</span><span class="sxs-lookup"><span data-stu-id="39317-200">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="39317-201">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="39317-201">Considerations</span></span>

- <span data-ttu-id="39317-202">Il sistema in cui vengono pubblicati i messaggi dei connettori non sa chi pubblica o chi riceve i messaggi: non vengono divulgate informazioni sul destinatario.</span><span class="sxs-lookup"><span data-stu-id="39317-202">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="39317-203">(Microsoft è il destinatario effettivo, non il tenant; Microsoft pubblica effettivamente il post sul canale.</span><span class="sxs-lookup"><span data-stu-id="39317-203">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="39317-204">Nessun dato lascia la rete aziendale quando i messaggi dei connettori vengono pubblicati su un canale.</span><span class="sxs-lookup"><span data-stu-id="39317-204">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="39317-205">Anche i connettori che supportano messaggi che REPLYTO_CONNECTOR_MESSAGE autorizzazioni di riferimento non vedono l'indirizzo IP e le informazioni sul referenziante; queste informazioni vengono inviate a Microsoft e quindi indirizzate agli endpoint HTTP precedentemente registrati con Microsoft nel portale dei connettori.</span><span class="sxs-lookup"><span data-stu-id="39317-205">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="39317-206">Ogni volta che si configura un connettore per un canale, viene creato un URL univoco per l'istanza del connettore.</span><span class="sxs-lookup"><span data-stu-id="39317-206">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="39317-207">Se l'istanza del connettore viene eliminata, l'URL non può più essere usato.</span><span class="sxs-lookup"><span data-stu-id="39317-207">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="39317-208">I messaggi del connettore non possono contenere file allegati.</span><span class="sxs-lookup"><span data-stu-id="39317-208">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="39317-209">L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque abbia tale URL può inserire un post, ad esempio un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39317-209">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="39317-210">Di conseguenza, esiste un rischio di posta indesiderata o collegamenti a siti di phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="39317-210">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="39317-211">In questo caso, i proprietari del team possono eliminare l'istanza del connettore.</span><span class="sxs-lookup"><span data-stu-id="39317-211">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="39317-212">Se il servizio che invia messaggi del connettore viene compromesso e inizia a inviare collegamenti a posta indesiderata/phishing/malware, un amministratore del tenant può impedire la creazione di nuove istanze del connettore e Microsoft può bloccarle centralmente.</span><span class="sxs-lookup"><span data-stu-id="39317-212">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="39317-213">Attualmente non è possibile sapere quali connettori supportano i messaggi su cui è possibile eseguire azioni (REPLYTO_CONNECTOR_MESSAGE autorizzazioni).</span><span class="sxs-lookup"><span data-stu-id="39317-213">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="39317-214">Webhook in uscita</span><span class="sxs-lookup"><span data-stu-id="39317-214">Outgoing webhooks</span></span>

<span data-ttu-id="39317-215">*I webhook in uscita* vengono creati al volo dai proprietari del team o dai membri del team.</span><span class="sxs-lookup"><span data-stu-id="39317-215">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="39317-216">Non sono funzionalità delle app di Teams; queste informazioni sono incluse per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="39317-216">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="39317-217">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="39317-217">Required permissions</span></span>

<span data-ttu-id="39317-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="39317-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="39317-219">Può ricevere messaggi dagli utenti e rispondere.</span><span class="sxs-lookup"><span data-stu-id="39317-219">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="39317-220">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="39317-220">Optional permissions</span></span>

<span data-ttu-id="39317-221">Nessuno</span><span class="sxs-lookup"><span data-stu-id="39317-221">None</span></span>

### <a name="considerations"></a><span data-ttu-id="39317-222">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="39317-222">Considerations</span></span>

- <span data-ttu-id="39317-223">I webhook in uscita sono simili ai bot, ma hanno un numero inferiore di privilegi.</span><span class="sxs-lookup"><span data-stu-id="39317-223">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="39317-224">Devono essere menzionati esplicitamente, proprio come i bot.</span><span class="sxs-lookup"><span data-stu-id="39317-224">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="39317-225">Quando viene registrato un webhook in uscita, viene generato un segreto, che consente al webhook in uscita di verificare che il mittente sia Microsoft Teams invece di un utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="39317-225">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="39317-226">Questo segreto deve rimanere un segreto; chiunque vi abbia accesso può impersonare Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39317-226">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="39317-227">Se il segreto viene compromesso, il Webhook in uscita può essere eliminato e ri creato di nuovo e verrà generato un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="39317-227">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="39317-228">Anche se è possibile creare un webhook in uscita che non convalida il segreto, è consigliabile usare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="39317-228">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="39317-229">Oltre a ricevere e rispondere ai messaggi, gli webhook in uscita non possono fare molto: non possono inviare proattivamente messaggi, non possono inviare o ricevere file, non possono fare altro che ricevere e rispondere ai messaggi.</span><span class="sxs-lookup"><span data-stu-id="39317-229">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
