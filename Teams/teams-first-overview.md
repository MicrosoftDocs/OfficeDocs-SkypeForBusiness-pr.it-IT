---
title: Distribuire prima Microsoft Teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Usare queste linee guida per implementare Microsoft teams come primo carico di lavoro di Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 647f6879f7892c1a65599832e48deb67e183fae0
ms.sourcegitcommit: bdafa1f4146e615d325e27a50352f10c0d51ef1a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44472347"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="5d9f6-103">Distribuire prima Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="5d9f6-104">Microsoft teams può aiutare i dipendenti a rimanere connessi e collaborare tra loro, in particolare nell'attuale tempo senza precedenti in cui il lavoro remoto è una realtà dei dipendenti in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="5d9f6-105">La possibilità di chattare, eseguire riunioni video e collaborare ai documenti di Office all'interno di teams può aiutare le aziende a rimanere produttivi.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="5d9f6-106">Che tu sia una piccola impresa, un'organizzazione no profit o di grandi dimensioni, puoi iniziare a usare teams come primo carico di lavoro all'interno di Office 365 Suite prima di distribuire qualsiasi altra app o servizio di Office.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="5d9f6-107">In questo articolo vengono fornite informazioni dettagliate sulle considerazioni che è necessario apportare con l'approccio "Teams First".</span><span class="sxs-lookup"><span data-stu-id="5d9f6-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d9f6-108">Mentre i team possono essere il primo carico di lavoro distribuito nel cloud dell'organizzazione, la distribuzione dei team deve far parte della strategia globale di distribuzione del cloud.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="5d9f6-109">Se sono già stati implementati altri servizi di Office 365 e teams è il carico di lavoro successivo da implementare (invece del primo), iniziare con la [modalità di implementazione dei team](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="5d9f6-110">Iniziare da qui</span><span class="sxs-lookup"><span data-stu-id="5d9f6-110">Start here</span></span>

<span data-ttu-id="5d9f6-111">Per iniziare a usare la prima distribuzione di teams, è necessario soddisfare almeno alcuni requisiti preliminari.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="5d9f6-112">L'elenco seguente mostra le informazioni che è necessario avere sul posto per l'organizzazione prima che i team possano essere abilitati:</span><span class="sxs-lookup"><span data-stu-id="5d9f6-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="5d9f6-113">Un'organizzazione di Office 365 configurata con il nome di dominio</span><span class="sxs-lookup"><span data-stu-id="5d9f6-113">An Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="5d9f6-114">Azure Active Directory Connectivity (AAD Connect) o una simile soluzione di sincronizzazione delle identità cloud, con tutti gli attributi necessari sincronizzati con il tenant</span><span class="sxs-lookup"><span data-stu-id="5d9f6-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="5d9f6-115">Per comprendere gli attributi sincronizzati con la sincronizzazione AAD, leggere [Azure ad Connect Sync: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="5d9f6-116">Licenze utente appropriate assegnate per i team</span><span class="sxs-lookup"><span data-stu-id="5d9f6-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="5d9f6-117">Per informazioni sulle licenze di teams, leggere la [Descrizione del servizio Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="5d9f6-118">Rete dell'organizzazione predisposta per i team</span><span class="sxs-lookup"><span data-stu-id="5d9f6-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="5d9f6-119">Per informazioni sulla preparazione della rete, leggere [preparare la rete dell'organizzazione per i team](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="5d9f6-120">Consentire l'accesso di rete a Exchange, SharePoint e OneDrive for business in Office 365: [URL e intervalli di indirizzi IP di office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="5d9f6-121">I tenant creati dopo il 1 ° settembre 2019 vengono provisionati in modalità solo teams.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="5d9f6-122">Se si è distribuito Skype for Business Server e il tenant è stato effettuato il provisioning dopo il 2019 settembre, contattare il supporto tecnico per abilitare le funzionalità di coesistenza per i team.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="5d9f6-123">Verificare che il criterio "organizzazione Wide Upgrade policy" sia impostato su "modalità Isola" <span class="underline">prima</span> di assegnare le licenze per i team a un utente.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="5d9f6-124">Punti di partenza della migrazione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-124">Migration Starting points</span></span>

<span data-ttu-id="5d9f6-125">Il viaggio in Office 365 e le caratteristiche disponibili in teams a seconda del punto di partenza e dell'esistenza dei locali Skype for business o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="5d9f6-126">Le sezioni seguenti illustrano in dettaglio le funzionalità di base e le opzioni di configurazione oltre ai prerequisiti precedenti.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="5d9f6-127">Sono stati suddivisi gli scenari del punto di partenza per gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d9f6-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="5d9f6-128">**Configurazione del tenant teams**: le modalità tenant e User vengono usate per controllare il comportamento del destinatario.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="5d9f6-129">Queste impostazioni possono essere assegnate a livello di tenant o a livello di utente in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="5d9f6-130">Per altre informazioni, leggi [la coesistenza con Skype for business](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="5d9f6-131">**Chat/comunicazioni esterne in teams**: i servizi di chat fanno riferimento alle conversazioni peer-to-peer o di chat di gruppo all'interno e all'organizzazione o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="5d9f6-132">La comunicazione esterna viene definita anche federazione in Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="5d9f6-133">**Creare e visualizzare riunioni in teams**: un utente può sempre creare riunioni online tramite il componente aggiuntivo di Outlook teams e il dial-in PSTN è disponibile in tutti gli scenari una volta che l'utente ha una licenza.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="5d9f6-134">Teams e Skype for business memorizzano le informazioni del calendario nella cassetta postale di Exchange dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="5d9f6-135">In locale Exchange Server deve essere Exchange Server 2016 CU3 o versioni successive per consentire al client teams di interagire con la cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="5d9f6-136">Senza accesso alle cassette postali di Exchange l'icona del calendario in teams non verrà visualizzata e l'utente non sarà in grado di visualizzare, creare o modificare riunioni nel client teams.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="5d9f6-137">**Chiamata di funzionalità VoIP/PSTN in teams**: la chiamata può essere VoIP (Voice over IP) o PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="5d9f6-138">La connettività VoIP avviene a livello nativo tra i client dei team, mentre la connettività PSTN si verifica quando un utente compone un numero di telefono esterno.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="5d9f6-139">I team supportano due tipi di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="5d9f6-140">Piano di chiamate Microsoft, quando Microsoft fornisce l'infrastruttura per la telefonia, incluso il numero di telefono di un utente o la configurazione del routing diretto, in cui il cliente fornisce la connettività telefonica su un SBC (Session Border Controller) per l'utente di teams.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="5d9f6-141">Per altre informazioni, leggere [quale piano per le chiamate è giusto per l'utente?](calling-plan-landing-page.md) e [sistema telefonico Direct routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="5d9f6-142">**Collaborazione di team e canali in**teams: in teams, teams sono gruppi di persone riunite per lavoro, progetti o interessi comuni.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="5d9f6-143">I team sono costituiti da canali.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-143">Teams are made up of channels.</span></span> <span data-ttu-id="5d9f6-144">Ogni canale è costruito attorno a un argomento, ad esempio "eventi del team", un nome di reparto o solo per divertimento.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="5d9f6-145">I canali sono il luogo in cui si organizzano riunioni, si hanno conversazioni e si lavora insieme ai file.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="5d9f6-146">Durante la collaborazione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-146">During collaboration</span></span>

<span data-ttu-id="5d9f6-147">**OneDrive for business (P2P file sharing) in teams: al**di fuori di team e canali, gli utenti del team possono condividere file peer-to-peer usando OneDrive for business o altri programmi di condivisione di file P2P, come file Citrix, Dropbox, box e Google Drive.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="5d9f6-148">Per OneDrive for business un utente deve avere la licenza di SharePoint Online assegnata.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="5d9f6-149">**Piattaforma applicativa**: le app contengono strumenti fuori sede per l'organizzazione per ottenere un numero maggiore di team.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="5d9f6-150">Queste app combinano la funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="5d9f6-151">**Caratteristiche di sicurezza e conformità:** Teams offre una vasta gamma di informazioni per aiutarti con le aree di conformità, inclusi i criteri di conservazione, la protezione dalla perdita dei dati (DLP), eDiscovery e il blocco legale per canali, chat e file, ricerca nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="5d9f6-152">Per altre informazioni, leggere [sicurezza e conformità in Microsoft teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="5d9f6-153">Advance eDiscovery caratteristiche richiedono licenze E5.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="5d9f6-154">[Confrontare le opzioni di licenza](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="5d9f6-155">Leggere [come interagiscono Exchange e Microsoft teams](exchange-teams-interact.md) per scoprire quali funzionalità di conformità sono disponibili nello scenario.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="5d9f6-156">Organizzazioni **<span class="underline">senza</span>** Skype for business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="5d9f6-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="5d9f6-157">Questo punto di partenza presuppone che l'organizzazione non utilizzi Skype for business o Lync Server attualmente e i team saranno la prima applicazione in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="5d9f6-158">La tabella seguente descrive in dettaglio la configurazione ad alto livello e le funzionalità degli utenti finali per i team per i servizi principali.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5d9f6-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d9f6-159">Item</span></span></th>
<th><span data-ttu-id="5d9f6-160">Note</span><span class="sxs-lookup"><span data-stu-id="5d9f6-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5d9f6-161">Configurazione di Team tenant</span><span class="sxs-lookup"><span data-stu-id="5d9f6-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="5d9f6-162">Modalità solo teams, tutte le funzionalità di chat e chiamate sono solo in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-163">Chat/comunicazioni esterne in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="5d9f6-164">Comunicazioni interne (intra Office 365 Organization) e chat esterna possibili da teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-164">Internal (intra Office 365 organization) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="5d9f6-165"><em>Nota: le voci DNS devono essere configurate per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="5d9f6-166">I record DNS Skype for business sono necessari anche se non si dispone di Skype for business locale o in Office 365 per consentire la Federazione con gli ambienti Lync e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="5d9f6-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Record di sistema dei nomi di dominio esterni per Office 365</a></em></span><span class="sxs-lookup"><span data-stu-id="5d9f6-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5d9f6-168"><em>Creare e visualizzare riunioni in teams</em></span><span class="sxs-lookup"><span data-stu-id="5d9f6-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="5d9f6-169"><em>In grado di creare riunioni tramite il componente aggiuntivo per Outlook</em></span><span class="sxs-lookup"><span data-stu-id="5d9f6-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="5d9f6-170"><em>La funzionalità di accesso esterno e chiamata PSTN è disponibile con le licenze per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="5d9f6-171">Nota: l'accesso al calendario di team richiede Exchange 2016 CU3 + locale distribuito con Exchange Hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">creare una distribuzione ibrida con la configurazione guidata ibrida</a></span><span class="sxs-lookup"><span data-stu-id="5d9f6-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="5d9f6-172">Oltre alla configurazione ibrida di Exchange, stabilire l'autenticazione OAuth di Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online</a></em></span><span class="sxs-lookup"><span data-stu-id="5d9f6-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-173">Funzionalità di chiamata</span><span class="sxs-lookup"><span data-stu-id="5d9f6-173">Calling Features</span></span><br />
<span data-ttu-id="5d9f6-174">VoIP/PSTN in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="5d9f6-175">Il VoIP internamente ed esternamente al tenant è disponibile</span><span class="sxs-lookup"><span data-stu-id="5d9f6-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="5d9f6-176">I servizi PSTN possono essere configurati tramite il sistema telefonico Microsoft, oltre ad aggiungere un piano di chiamata Microsoft o un routing diretto.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5d9f6-177">Collaborazione di team e canali in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="5d9f6-178">Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="5d9f6-179">La migrazione dei siti di SharePoint locali esistenti non è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-180">OneDrive for business (condivisione di file P2P)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="5d9f6-181">OneDrive for business richiede a un utente di assegnare una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="5d9f6-182">Senza la condivisione di file peer-to-peer della licenza non sarà possibile.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5d9f6-183">Piattaforma dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-183">Application platform</span></span></td>
<td><span data-ttu-id="5d9f6-184">Gli utenti potranno usare le app designate a loro disposizione in base ai criteri aziendali.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="5d9f6-185">Altre informazioni: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">impostazioni di amministrazione per le app in teams</a></span><span class="sxs-lookup"><span data-stu-id="5d9f6-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-186">Caratteristiche di sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="5d9f6-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="5d9f6-187">Sono disponibili criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="5d9f6-188">eDiscovery e Legal detiene per la conformità ai messaggi di canale è supportato</span><span class="sxs-lookup"><span data-stu-id="5d9f6-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="5d9f6-189">Sono disponibili i criteri di prevenzione della perdita dei dati (DLP)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="5d9f6-190">Set di caratteristiche completo disponibile con Exchange Online, Exchange locale supporta la maggior parte di queste funzionalità, vedere <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">modalità di interazione tra Exchange e teams</a> per l'elenco completo.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a> for full list.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="5d9f6-191">Procedura di attivazione per le organizzazioni senza Skype for business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="5d9f6-191">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="5d9f6-192">Soddisfare i requisiti preliminari descritti nella sezione inizio qui sopra</span><span class="sxs-lookup"><span data-stu-id="5d9f6-192">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="5d9f6-193">Cambiare il tenant in modalità solo Teams (solo per i tenant esistenti): [impostare le impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-193">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="5d9f6-194">Configurare il tenant conformemente ai criteri aziendali/commerciali della società: [gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-194">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="5d9f6-195">Distribuire il client teams agli utenti: [ottenere clienti per Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-195">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="5d9f6-196">Guidare il programma di adozione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-196">Drive your adoption program</span></span>  
    [<span data-ttu-id="5d9f6-197">Adottare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-197">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="5d9f6-198">Elenco di controllo introduttivo di Microsoft teams adoption</span><span class="sxs-lookup"><span data-stu-id="5d9f6-198">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="5d9f6-199">Iniziare a pianificare lo spostamento di altri carichi di lavoro in Office 365</span><span class="sxs-lookup"><span data-stu-id="5d9f6-199">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="5d9f6-200">Organizzazioni **<span class="underline">con</span>** Skype for business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="5d9f6-200">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="5d9f6-201">Questo punto di partenza presuppone che l'organizzazione utilizzi Skype for business 2019 o 2015 + o Lync 2013 + server in locale.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-201">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="5d9f6-202">Esistono già linee guida estese per le organizzazioni che migrano dai server locali ai team e che dovrebbero essere seguite per questi scenari.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-202">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="5d9f6-203">Questa guida è specifica dello scenario in cui teams è la prima applicazione che si usa in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-203">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="5d9f6-204">La tabella seguente descrive in dettaglio la configurazione ad alto livello e le funzionalità degli utenti finali per i team per i servizi principali.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-204">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5d9f6-205">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d9f6-205">Item</span></span></th>
<th><span data-ttu-id="5d9f6-206">Note</span><span class="sxs-lookup"><span data-stu-id="5d9f6-206">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5d9f6-207">Configurazione di Team tenant</span><span class="sxs-lookup"><span data-stu-id="5d9f6-207">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="5d9f6-208">Modalità Isole</span><span class="sxs-lookup"><span data-stu-id="5d9f6-208">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-209">Chat/comunicazioni esterne in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-209">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="5d9f6-210">Interno solo all'interno del proprio tenant, la comunicazione esterna (Federazione) è tramite la distribuzione di Skype for business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="5d9f6-210">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5d9f6-211">Creare e visualizzare riunioni in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-211">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="5d9f6-212">In grado di creare riunioni tramite il componente aggiuntivo per Outlook</span><span class="sxs-lookup"><span data-stu-id="5d9f6-212">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="5d9f6-213">La funzionalità di accesso esterno e chiamata PSTN è disponibile con le licenze per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-213">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="5d9f6-214">L'accesso al calendario teams richiede Exchange 2016 CU3 + locale distribuito con Exchange Hybrid established:</span><span class="sxs-lookup"><span data-stu-id="5d9f6-214">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="5d9f6-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la configurazione guidata ibrida</a></span><span class="sxs-lookup"><span data-stu-id="5d9f6-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-216">Funzionalità di chiamata</span><span class="sxs-lookup"><span data-stu-id="5d9f6-216">Calling Features</span></span><br />
<span data-ttu-id="5d9f6-217">VoIP/PSTN in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-217">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="5d9f6-218">Il VoIP internamente al tenant è disponibile</span><span class="sxs-lookup"><span data-stu-id="5d9f6-218">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="5d9f6-219">I servizi PSTN o per i piani di chiamata non sono disponibili finché l'utente non viene spostato nell'esperienza solo Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-219">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5d9f6-220">Collaborazione di team e canali in teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-220">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="5d9f6-221">Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-221">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="5d9f6-222">La migrazione dei siti di SharePoint locali esistenti non è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-222">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-223">OneDrive for business (condivisione di file P2P)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-223">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="5d9f6-224">OneDrive for business richiede a un utente di assegnare una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-224">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="5d9f6-225">Senza la condivisione di file della licenza per-to-peer non sarà possibile.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-225">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5d9f6-226">Piattaforma dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-226">Application platform</span></span></td>
<td><span data-ttu-id="5d9f6-227">Gli utenti potranno usare le app designate a loro disposizione in base ai criteri aziendali.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-227">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="5d9f6-228">Altre informazioni: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">impostazioni di amministrazione per le app in teams</a></span><span class="sxs-lookup"><span data-stu-id="5d9f6-228">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5d9f6-229">Caratteristiche di sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="5d9f6-229">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="5d9f6-230">Sono disponibili criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-230">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="5d9f6-231">eDiscovery e Legal detiene per la conformità ai messaggi di canale è supportato</span><span class="sxs-lookup"><span data-stu-id="5d9f6-231">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="5d9f6-232">Sono disponibili i criteri di prevenzione della perdita dei dati (DLP)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-232">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="5d9f6-233">Set di caratteristiche completo disponibile con Exchange Online, Exchange locale supporta la maggior parte di queste funzionalità, vedere</span><span class="sxs-lookup"><span data-stu-id="5d9f6-233">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="5d9f6-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Modalità di interazione tra Exchange e Teams</a></span><span class="sxs-lookup"><span data-stu-id="5d9f6-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="5d9f6-235">per l'elenco completo</span><span class="sxs-lookup"><span data-stu-id="5d9f6-235">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="5d9f6-236">Procedura di attivazione per le organizzazioni con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5d9f6-236">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="5d9f6-237">Soddisfare i requisiti preliminari descritti nella sezione inizio qui sopra.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-237">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="5d9f6-238">Cambiare il tenant in modalità isole (per i tenant con provisioning dopo 9/1/2019, contattare il supporto tecnico per apportare questa modifica)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-238">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="5d9f6-239">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5d9f6-239">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="5d9f6-240">Configurare il tenant in conformità con le politiche aziendali/aziendali</span><span class="sxs-lookup"><span data-stu-id="5d9f6-240">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="5d9f6-241">Gestire le impostazioni di Microsoft Teams per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-241">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="5d9f6-242">Distribuire il client Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-242">Deploy the Teams client</span></span>  
    [<span data-ttu-id="5d9f6-243">Ottenere client per Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-243">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="5d9f6-244">Guidare il programma di adozione</span><span class="sxs-lookup"><span data-stu-id="5d9f6-244">Drive your adoption program</span></span>  
    [<span data-ttu-id="5d9f6-245">Adottare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-245">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="5d9f6-246">Elenco di controllo introduttivo di Microsoft teams adoption</span><span class="sxs-lookup"><span data-stu-id="5d9f6-246">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="5d9f6-247">Iniziare a pianificare lo spostamento di altri carichi di lavoro in Office 365</span><span class="sxs-lookup"><span data-stu-id="5d9f6-247">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="5d9f6-248">Creare Skype for business Hybrid e seguire i percorsi di aggiornamento consigliati per Skype for business e i server Lync</span><span class="sxs-lookup"><span data-stu-id="5d9f6-248">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="5d9f6-249">Eseguire l'aggiornamento da Skype for business locale a teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-249">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="5d9f6-250">Istruzione Closing</span><span class="sxs-lookup"><span data-stu-id="5d9f6-250">Closing statement</span></span>

<span data-ttu-id="5d9f6-251">Microsoft teams può essere un attivatore per consentire all'organizzazione di riunire tutti i dipendenti, gli Information Worker e i lavoratori I FIRSTLINE su una singola piattaforma.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-251">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="5d9f6-252">[Puoi iniziare oggi stesso](https://products.office.com/microsoft-teams/group-chat-software) .</span><span class="sxs-lookup"><span data-stu-id="5d9f6-252">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="5d9f6-253">[Qui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)è possibile rimanere in contatto con tutti gli annunci più recenti e gli aggiornamenti mensili del prodotto.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-253">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="5d9f6-254">Inoltre, dato che le aziende di tutto il mondo stanno gestendo l'attuale situazione COVID-19, abbiamo creato una serie di contenuti che ti aiuteranno a usare team per ottenere il massimo impatto nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-254">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="5d9f6-255">Il nostro [impegno per i clienti durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-255">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="5d9f6-256">2 settimane in: cosa abbiamo imparato sul lavoro remoto</span><span class="sxs-lookup"><span data-stu-id="5d9f6-256">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="5d9f6-257">Distribuzione di riunioni ed eventi online</span><span class="sxs-lookup"><span data-stu-id="5d9f6-257">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="5d9f6-258">Aiutare le piccole e medie imprese a lavorare in remoto con Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-258">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="5d9f6-259">Trasformazione digitale di eventi Live: osservazioni di Bob Bejan dal Frontline</span><span class="sxs-lookup"><span data-stu-id="5d9f6-259">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="5d9f6-260">I principali 9 modi in cui Microsoft IT sta abilitando il lavoro remoto per i suoi dipendenti</span><span class="sxs-lookup"><span data-stu-id="5d9f6-260">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="5d9f6-261">Lavorare in remoto, rimanere al sicuro: suggerimenti per CISOs</span><span class="sxs-lookup"><span data-stu-id="5d9f6-261">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="5d9f6-262">Aiutare gli insegnanti e gli studenti a passare all'apprendimento remoto</span><span class="sxs-lookup"><span data-stu-id="5d9f6-262">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="5d9f6-263">Rimanere produttivi mentre si lavora in remoto con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-263">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="5d9f6-264">Informazioni di riferimento sui servizi di supporto</span><span class="sxs-lookup"><span data-stu-id="5d9f6-264">Support Services reference</span></span>

<span data-ttu-id="5d9f6-265">Teams si basa sui gruppi di Exchange Online, SharePoint Online, OneDrive for business e Microsoft 365 per dare agli utenti un'esperienza di Office 365 completamente integrata.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-265">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="5d9f6-266">Come indicato in precedenza, le squadre lavoreranno senza la distribuzione completa di questi servizi, con funzionalità limitate.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-266">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="5d9f6-267">Per altre informazioni sui team e i suoi requisiti preliminari, vedere il sito: [Benvenuti in teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-267">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="5d9f6-268">Per informazioni specifiche su ognuno dei servizi elencati sopra, seguire i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d9f6-268">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="5d9f6-269">Exchange Online viene usato per le funzionalità di calendario e per l'archiviazione dei messaggi peer-to-peer in teams.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-269">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="5d9f6-270">Per altre informazioni, vedere [come interagiscono Exchange e teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="5d9f6-270">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d9f6-271">Per l'interoperabilità teams con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange come descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-271">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="5d9f6-272">SharePoint viene usato per la condivisione di file nei canali, mentre/OneDrive for business viene usato per la condivisione di file in 1:1 o in chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-272">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="5d9f6-273">Per altre informazioni, vedere [come interagire con SharePoint Online e OneDrive for business con Microsoft teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f6-273">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="5d9f6-274">I [gruppi Microsoft 365](office-365-groups.md) vengono usati per la creazione e la gestione di team e canali.</span><span class="sxs-lookup"><span data-stu-id="5d9f6-274">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5d9f6-275">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5d9f6-275">Related topics</span></span>

[<span data-ttu-id="5d9f6-276">Poster di soluzioni di telefonia e architettura IT di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-276">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="5d9f6-277">Pianificare la connettività ibrida tra Skype for Business Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="5d9f6-277">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="5d9f6-278">Supportare i dipendenti remoti tramite Teams</span><span class="sxs-lookup"><span data-stu-id="5d9f6-278">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="5d9f6-279">Lavorare in remoto con Office 365</span><span class="sxs-lookup"><span data-stu-id="5d9f6-279">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)
