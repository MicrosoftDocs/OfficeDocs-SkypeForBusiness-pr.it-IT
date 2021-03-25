---
title: Considerazioni e autorizzazioni per le app di Microsoft Teams
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
description: L'amministratore può scoprire quali dati e autorizzazioni le app di Microsoft Teams richiedono all'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120858"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="92f7c-103">Considerazioni e autorizzazioni per le app di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92f7c-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="92f7c-104">Le app di Microsoft Teams consentono di aggregare una o più funzionalità in un pacchetto di _app_ che può essere installato, aggiornato e disinstallato.</span><span class="sxs-lookup"><span data-stu-id="92f7c-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="92f7c-105">Le funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="92f7c-105">The capabilities include:</span></span>

- <span data-ttu-id="92f7c-106">Bot</span><span class="sxs-lookup"><span data-stu-id="92f7c-106">Bots</span></span>
- <span data-ttu-id="92f7c-107">Estensioni di messaggistica</span><span class="sxs-lookup"><span data-stu-id="92f7c-107">Messaging extensions</span></span>
- <span data-ttu-id="92f7c-108">Schede</span><span class="sxs-lookup"><span data-stu-id="92f7c-108">Tabs</span></span>
- <span data-ttu-id="92f7c-109">Connettori</span><span class="sxs-lookup"><span data-stu-id="92f7c-109">Connectors</span></span>

<span data-ttu-id="92f7c-110">Le app sono autorizzate dagli utenti e gestite dall'IT dal punto di vista dei criteri.</span><span class="sxs-lookup"><span data-stu-id="92f7c-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="92f7c-111">Tuttavia, per la maggior parte, le autorizzazioni e il profilo di rischio di un'app sono definiti dalle autorizzazioni e dai profili di rischio delle funzionalità contenute nell'app.</span><span class="sxs-lookup"><span data-stu-id="92f7c-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="92f7c-112">Di conseguenza, questo articolo si concentra sulle autorizzazioni e sulle considerazioni a livello di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="92f7c-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="92f7c-113">Le autorizzazioni elencate di seguito in lettere maiuscole, ad esempio RECEIVE_MESSAGE e REPLYTO_MESSAGE, non vengono visualizzate nella documentazione per sviluppatori di [Microsoft Teams](/microsoftteams/platform/overview) o nelle autorizzazioni per [Microsoft Graph.](/graph/permissions-reference)</span><span class="sxs-lookup"><span data-stu-id="92f7c-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](/microsoftteams/platform/overview) or the [permissions for Microsoft Graph](/graph/permissions-reference).</span></span> <span data-ttu-id="92f7c-114">Si tratta semplicemente di una abbreviazione descrittiva ai fini di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="92f7c-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="92f7c-115">Titolo</span><span class="sxs-lookup"><span data-stu-id="92f7c-115">Title</span></span>   | <span data-ttu-id="92f7c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92f7c-116">Description</span></span>    |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/><span data-ttu-id="92f7c-118">Punto di decisione</span><span class="sxs-lookup"><span data-stu-id="92f7c-118">Decision point</span></span>|<ul><li><span data-ttu-id="92f7c-119">Usare le tabelle seguenti come guida per comprendere le autorizzazioni richieste dall'app che si sta esaminando.</span><span class="sxs-lookup"><span data-stu-id="92f7c-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Icona che descrive il passaggio successivo](media/audio_conferencing_image9.png)<br/><span data-ttu-id="92f7c-121">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="92f7c-121">Next step</span></span>|<ul><li><span data-ttu-id="92f7c-122">Eseguire ricerche nell'app o nel servizio stesso per decidere se consentire l'accesso all'app o al servizio stesso all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="92f7c-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="92f7c-123">Ad esempio, i bot inviano e ricevono messaggi dagli utenti e, ad eccezione dei bot personalizzati aziendali, si trovano all'esterno del limite di conformità.</span><span class="sxs-lookup"><span data-stu-id="92f7c-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="92f7c-124">Pertanto, qualsiasi app che include un bot richiede queste autorizzazioni e ha almeno quel profilo di rischio.</span><span class="sxs-lookup"><span data-stu-id="92f7c-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="92f7c-125">Vedere anche [Richiedere autorizzazioni per i dispositivi per la scheda Microsoft Teams.](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)</span><span class="sxs-lookup"><span data-stu-id="92f7c-125">See also [Request device permissions for your Microsoft Teams tab](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="92f7c-126">Considerazioni e autorizzazioni per le app globali</span><span class="sxs-lookup"><span data-stu-id="92f7c-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="92f7c-127">Autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="92f7c-127">Required permissions</span></span>

<span data-ttu-id="92f7c-128">Nessuno</span><span class="sxs-lookup"><span data-stu-id="92f7c-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="92f7c-129">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="92f7c-129">Optional permissions</span></span>

<span data-ttu-id="92f7c-130">Nessuno</span><span class="sxs-lookup"><span data-stu-id="92f7c-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="92f7c-131">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="92f7c-131">Considerations</span></span>

- <span data-ttu-id="92f7c-132">Un'app deve divulgare i dati usati e i relativi collegamenti alle condizioni d'uso e all'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="92f7c-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="92f7c-133">[Il consenso specifico delle](resource-specific-consent.md) risorse fornisce un set di autorizzazioni che le app possono richiedere, che vengono visualizzate nella schermata di installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="92f7c-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="92f7c-134">Per altre informazioni sulle autorizzazioni di consenso specifiche delle risorse, vedere Informazioni [di riferimento sulle autorizzazioni del grafico.](/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="92f7c-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="92f7c-135">Le app potrebbero anche avere bisogno di autorizzazioni diverse da quelle specifiche per le risorse.</span><span class="sxs-lookup"><span data-stu-id="92f7c-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="92f7c-136">Dopo l'installazione di un'app, l'app può richiedere le autorizzazioni di Graph tramite una richiesta di consenso.</span><span class="sxs-lookup"><span data-stu-id="92f7c-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="92f7c-137">Per altre informazioni, vedere Informazioni sulle esperienze [di consenso delle applicazioni di Azure AD.](/azure/active-directory/develop/application-consent-experience)</span><span class="sxs-lookup"><span data-stu-id="92f7c-137">To learn more, see [Understanding Azure AD application consent experiences](/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="92f7c-138">È possibile configurare le autorizzazioni API e il consenso nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="92f7c-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="92f7c-139">Per altre informazioni, vedere Framework di consenso [di Azure Active Directory.](/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="92f7c-139">To learn more, see [Azure Active Directory consent framework](/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="92f7c-140">Bot ed estensioni di messaggistica</span><span class="sxs-lookup"><span data-stu-id="92f7c-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="92f7c-141">Autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="92f7c-141">Required permissions</span></span>

- <span data-ttu-id="92f7c-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="92f7c-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="92f7c-143">Il bot può ricevere messaggi dagli utenti e rispondere. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92f7c-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="92f7c-144">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="92f7c-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="92f7c-145">Dopo che un utente ha inviato un messaggio a un bot, il bot può inviare messaggi diretti all'utente , detti anche *messaggi proattivi* in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="92f7c-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="92f7c-146">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="92f7c-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="92f7c-147">I bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali in un team.</span><span class="sxs-lookup"><span data-stu-id="92f7c-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="92f7c-148">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="92f7c-148">Optional permissions</span></span>

- <span data-ttu-id="92f7c-149">IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="92f7c-149">IDENTITY.</span></span> <span data-ttu-id="92f7c-150">Quando viene usato in un canale, i bot dell'app possono accedere alle informazioni di identità di base dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica); quando viene usato in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="92f7c-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="92f7c-151">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="92f7c-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="92f7c-152">Consente ai bot di un'app di inviare messaggi diretti (proattivi) a qualsiasi membro del team in qualsiasi momento, anche se l'utente non ha mai parlato con il bot prima.</span><span class="sxs-lookup"><span data-stu-id="92f7c-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="92f7c-153">Le autorizzazioni seguenti non sono esplicite, ma sono implicite da RECEIVE_MESSAGE e REPLYTO_MESSAGE e dagli ambiti in cui è possibile usare i bot, dichiarati nel manifesto:</span><span class="sxs-lookup"><span data-stu-id="92f7c-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="92f7c-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="92f7c-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="92f7c-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="92f7c-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="92f7c-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="92f7c-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="92f7c-157">SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controlla se un bot può inviare e ricevere file nella chat personale (non ancora supportata per la chat di gruppo o i canali).</span><span class="sxs-lookup"><span data-stu-id="92f7c-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="92f7c-158">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="92f7c-158">Considerations</span></span>

- <span data-ttu-id="92f7c-159">I bot hanno accesso solo ai team a cui sono stati aggiunti o agli utenti che li hanno installati.</span><span class="sxs-lookup"><span data-stu-id="92f7c-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="92f7c-160">I bot ricevono solo messaggi in cui vengono menzionati esplicitamente dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="92f7c-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="92f7c-161">Questi dati lasciano la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="92f7c-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="92f7c-162">I bot possono rispondere solo alle conversazioni in cui sono menzionati.</span><span class="sxs-lookup"><span data-stu-id="92f7c-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="92f7c-163">Dopo che un utente ha conversato con un bot, se il bot archivia l'ID dell'utente, può inviare messaggi diretti all'utente in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="92f7c-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="92f7c-164">È in teoria possibile che i messaggi bot contengano collegamenti a siti di phishing o malware, ma i bot possono essere bloccati dall'utente, dall'amministratore del tenant o globalmente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92f7c-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="92f7c-165">Un bot può recuperare (e archiviare) informazioni di identità molto di base per i membri del team a cui è stata aggiunta l'app o per i singoli utenti nelle chat personali o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="92f7c-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="92f7c-166">Per ottenere altre informazioni su questi utenti, il bot deve richiedere l'accesso ad Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="92f7c-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="92f7c-167">I bot possono recuperare (e archiviare) l'elenco dei canali in un team; questi dati lasciano la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="92f7c-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="92f7c-168">Quando un file viene inviato a un bot, il file lascia la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="92f7c-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="92f7c-169">L'invio e la ricezione di file richiede l'approvazione dell'utente per ogni file.</span><span class="sxs-lookup"><span data-stu-id="92f7c-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="92f7c-170">Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma i bot possono chiedere agli utenti di accedere. Non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="92f7c-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="92f7c-171">Esattamente quali sono questi elementi aggiuntivi dipendono dal bot e dalla posizione in cui l'utente accede: un bot è un'app Azure AD registrata in e può avere un https://apps.dev.microsoft.com/ proprio set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="92f7c-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="92f7c-172">I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.</span><span class="sxs-lookup"><span data-stu-id="92f7c-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="92f7c-173">I bot non vedono gli indirizzi IP degli utenti o altre informazioni di riferimento.</span><span class="sxs-lookup"><span data-stu-id="92f7c-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="92f7c-174">Tutte le informazioni provengono da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92f7c-174">All information comes from Microsoft.</span></span> <span data-ttu-id="92f7c-175">Esiste un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso visualizza gli indirizzi IP degli utenti e le informazioni sul referrer.</span><span class="sxs-lookup"><span data-stu-id="92f7c-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="92f7c-176">Le estensioni di messaggistica, invece, visualizzano gli indirizzi IP degli utenti e le informazioni sul referrer.</span><span class="sxs-lookup"><span data-stu-id="92f7c-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="92f7c-177">Le linee guida per le app (e il processo di revisione di AppSource) richiedono la discrezione di pubblicare messaggi di chat personali agli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi.</span><span class="sxs-lookup"><span data-stu-id="92f7c-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="92f7c-178">In caso di abuso, gli utenti possono bloccare il bot, gli amministratori del tenant possono bloccare l'app e Microsoft può bloccare i bot centralmente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="92f7c-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="92f7c-179"><sup>1</sup> Alcuni bot inviano solo messaggi (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="92f7c-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="92f7c-180">Si chiamano bot "solo notifiche", ma il termine non fa riferimento a ciò che un bot è consentito o non può eseguire, significa che il bot non vuole esporre un'esperienza di conversazione.</span><span class="sxs-lookup"><span data-stu-id="92f7c-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="92f7c-181">Teams usa questo campo per disabilitare nell'interfaccia utente la funzionalità che normalmente verrebbe abilitata; il bot non è limitato alle attività consentite rispetto ai bot che espongono un'esperienza di conversazione.</span><span class="sxs-lookup"><span data-stu-id="92f7c-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="92f7c-182"><sup>2</sup> Regolato dalla proprietà booleana supportsFiles sull'oggetto bot nell'manifest.jsfile per l'app.</span><span class="sxs-lookup"><span data-stu-id="92f7c-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="92f7c-183">Se un bot ha un proprio accesso, la prima volta che l'utente effettua l'accesso esiste un'esperienza di consenso diversa.</span><span class="sxs-lookup"><span data-stu-id="92f7c-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="92f7c-184">Attualmente, le autorizzazioni di Azure AD associate a qualsiasi funzionalità all'interno di un'app Teams (bot, scheda, connettore o estensione di messaggistica) sono completamente separate dalle autorizzazioni di Teams elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="92f7c-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="92f7c-185">Schede</span><span class="sxs-lookup"><span data-stu-id="92f7c-185">Tabs</span></span>

<span data-ttu-id="92f7c-186">Una scheda è un sito Web in esecuzione all'interno di Teams.</span><span class="sxs-lookup"><span data-stu-id="92f7c-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="92f7c-187">Autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="92f7c-187">Required permissions</span></span>

<span data-ttu-id="92f7c-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="92f7c-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="92f7c-189">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="92f7c-189">Optional permissions</span></span>

<span data-ttu-id="92f7c-190">Nessuno (attualmente)</span><span class="sxs-lookup"><span data-stu-id="92f7c-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="92f7c-191">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="92f7c-191">Considerations</span></span>

- <span data-ttu-id="92f7c-192">Il profilo di rischio per una scheda è quasi identico allo stesso sito Web in esecuzione in una scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="92f7c-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="92f7c-193">Una scheda ottiene anche il contesto in cui è in esecuzione, inclusi il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto di Azure AD per l'utente corrente, l'ID del gruppo di Microsoft 365 in cui si trova (se si tratta di un team), l'ID tenant e le impostazioni locali correnti dell'utente.</span><span class="sxs-lookup"><span data-stu-id="92f7c-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="92f7c-194">Tuttavia, per mappare questi ID alle informazioni di un utente, la scheda deve rendere l'utente connesso ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="92f7c-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="92f7c-195">Connettori</span><span class="sxs-lookup"><span data-stu-id="92f7c-195">Connectors</span></span>

<span data-ttu-id="92f7c-196">Un connettore invia messaggi a un canale quando si verificano eventi in un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="92f7c-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="92f7c-197">Autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="92f7c-197">Required permissions</span></span>

<span data-ttu-id="92f7c-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="92f7c-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="92f7c-199">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="92f7c-199">Optional permissions</span></span>

<span data-ttu-id="92f7c-200">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="92f7c-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="92f7c-201">Alcuni connettori supportano messaggi utilizzabili, che consentono agli utenti di pubblicare risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda Trello.</span><span class="sxs-lookup"><span data-stu-id="92f7c-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="92f7c-202">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="92f7c-202">Considerations</span></span>

- <span data-ttu-id="92f7c-203">Il sistema che pubblica i messaggi del connettore non sa chi pubblica o chi riceve i messaggi: nessuna informazione sul destinatario viene divulgata.</span><span class="sxs-lookup"><span data-stu-id="92f7c-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="92f7c-204">Microsoft è il destinatario effettivo, non il tenant. Microsoft esegue il post effettivo nel canale.</span><span class="sxs-lookup"><span data-stu-id="92f7c-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="92f7c-205">Nessun dato lascia la rete aziendale quando i messaggi del connettore vengono pubblicati in un canale.</span><span class="sxs-lookup"><span data-stu-id="92f7c-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="92f7c-206">Anche i connettori che supportano i messaggi REPLYTO_CONNECTOR_MESSAGE non visualizzano le informazioni sull'indirizzo IP e sul referrer. queste informazioni vengono inviate a Microsoft e quindi indirizzate agli endpoint HTTP precedentemente registrati con Microsoft nel portale connettori.</span><span class="sxs-lookup"><span data-stu-id="92f7c-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="92f7c-207">Ogni volta che un connettore viene configurato per un canale, viene creato un URL univoco per l'istanza del connettore.</span><span class="sxs-lookup"><span data-stu-id="92f7c-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="92f7c-208">Se l'istanza del connettore viene eliminata, l'URL non può più essere usato.</span><span class="sxs-lookup"><span data-stu-id="92f7c-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="92f7c-209">I messaggi del connettore non possono contenere file allegati.</span><span class="sxs-lookup"><span data-stu-id="92f7c-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="92f7c-210">L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque abbia tale URL può pubblicarlo, ad esempio un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="92f7c-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="92f7c-211">Di conseguenza, esiste un rischio di posta indesiderata o collegamenti a siti di phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="92f7c-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="92f7c-212">In questo caso, i proprietari del team possono eliminare l'istanza del connettore.</span><span class="sxs-lookup"><span data-stu-id="92f7c-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="92f7c-213">Se il servizio che invia i messaggi del connettore viene compromesso e inizia a inviare collegamenti di posta indesiderata/phishing/malware, un amministratore del tenant può impedire la creazione di nuove istanze del connettore e Microsoft può bloccarle centralmente.</span><span class="sxs-lookup"><span data-stu-id="92f7c-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="92f7c-214">Al momento non è possibile sapere quali connettori supportano i messaggi REPLYTO_CONNECTOR_MESSAGE messaggi.</span><span class="sxs-lookup"><span data-stu-id="92f7c-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="92f7c-215">Webhook in uscita</span><span class="sxs-lookup"><span data-stu-id="92f7c-215">Outgoing webhooks</span></span>

<span data-ttu-id="92f7c-216">*I webhook in uscita* vengono creati al volo dai proprietari del team o dai membri del team.</span><span class="sxs-lookup"><span data-stu-id="92f7c-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="92f7c-217">Non sono funzionalità delle app di Teams. queste informazioni sono incluse per completezza.</span><span class="sxs-lookup"><span data-stu-id="92f7c-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="92f7c-218">Autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="92f7c-218">Required permissions</span></span>

<span data-ttu-id="92f7c-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="92f7c-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="92f7c-220">Può ricevere messaggi dagli utenti e rispondere.</span><span class="sxs-lookup"><span data-stu-id="92f7c-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="92f7c-221">Autorizzazioni facoltative</span><span class="sxs-lookup"><span data-stu-id="92f7c-221">Optional permissions</span></span>

<span data-ttu-id="92f7c-222">Nessuno</span><span class="sxs-lookup"><span data-stu-id="92f7c-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="92f7c-223">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="92f7c-223">Considerations</span></span>

- <span data-ttu-id="92f7c-224">I webhook in uscita sono simili ai bot, ma hanno meno privilegi.</span><span class="sxs-lookup"><span data-stu-id="92f7c-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="92f7c-225">Devono essere menzionati esplicitamente, proprio come i bot.</span><span class="sxs-lookup"><span data-stu-id="92f7c-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="92f7c-226">Quando viene registrato un webhook in uscita, viene generato un segreto, che consente al webhook in uscita di verificare che il mittente sia Microsoft Teams anziché un utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="92f7c-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="92f7c-227">Questo segreto deve rimanere segreto; Chiunque abbia accesso ad essa può impersonare Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="92f7c-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="92f7c-228">Se il segreto viene compromesso, il webhook in uscita può essere eliminato e ri-creato e verrà generato un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="92f7c-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="92f7c-229">Anche se è possibile creare un webhook in uscita che non convalida il segreto, è consigliabile non farlo.</span><span class="sxs-lookup"><span data-stu-id="92f7c-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="92f7c-230">Oltre a ricevere e rispondere ai messaggi, i webhook in uscita non possono fare molto: non possono inviare messaggi in modo proattivo, non possono inviare o ricevere file, non possono fare altro che ricevere e rispondere ai messaggi.</span><span class="sxs-lookup"><span data-stu-id="92f7c-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>