---
title: Implementare Microsoft Teams First
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
description: Usare queste indicazioni per implementare Microsoft Teams come primo carico di lavoro di Microsoft 365 o Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119355"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="84450-103">Implementare Microsoft Teams First</span><span class="sxs-lookup"><span data-stu-id="84450-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="84450-104">Microsoft Teams consente ai dipendenti di rimanere in contatto e collaborare tra loro, soprattutto in un periodo senza precedenti in cui il lavoro remoto è una realtà dei dipendenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="84450-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="84450-105">La possibilità di chattare, fare video riunioni e collaborare ai documenti di Office all'interno di Teams può aiutare le aziende a rimanere produttive.</span><span class="sxs-lookup"><span data-stu-id="84450-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="84450-106">Sia che si sia una piccola azienda, un'organizzazione no profit o un'organizzazione di grandi dimensioni, è possibile iniziare a usare Teams come primo carico di lavoro all'interno della famiglia di prodotti Microsoft 365 o Office 365 prima di distribuire qualsiasi altra app o servizio di Office.</span><span class="sxs-lookup"><span data-stu-id="84450-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="84450-107">Questo articolo descrive in dettaglio le considerazioni da prendere con l'approccio "Teams First".</span><span class="sxs-lookup"><span data-stu-id="84450-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84450-108">Anche se Teams può essere il primo carico di lavoro distribuito nel cloud dell'organizzazione, la distribuzione di Teams dovrebbe far parte della strategia di distribuzione cloud generale.</span><span class="sxs-lookup"><span data-stu-id="84450-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="84450-109">Se sono già stati implementazioni altri servizi di Microsoft 365 o Office 365 e Teams è il prossimo carico di lavoro da implementare (invece del primo), iniziare con Come implementare [Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84450-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="84450-110">Iniziare da qui</span><span class="sxs-lookup"><span data-stu-id="84450-110">Start here</span></span>

<span data-ttu-id="84450-111">Per iniziare a usare la distribuzione di Teams First, è necessario soddisfare almeno alcuni prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="84450-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="84450-112">L'elenco seguente mostra ciò che è necessario avere in essere per l'organizzazione prima che Teams possa essere abilitato:</span><span class="sxs-lookup"><span data-stu-id="84450-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="84450-113">Un'organizzazione di Microsoft 365 o Office 365 configurata con il nome di dominio</span><span class="sxs-lookup"><span data-stu-id="84450-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="84450-114">Connettività di Azure Active Directory (connessione AAD) o soluzione di sincronizzazione delle identità cloud simile, con tutti gli attributi obbligatori sincronizzati con il tenant</span><span class="sxs-lookup"><span data-stu-id="84450-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="84450-115">Per comprendere gli attributi sincronizzati con la sincronizzazione AAD, vedere [Sincronizzazione di Azure AD Connect: Attributi sincronizzati con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="84450-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="84450-116">Licenze utente appropriate assegnate per Teams</span><span class="sxs-lookup"><span data-stu-id="84450-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="84450-117">Per informazioni sulle licenze di Teams, vedere [Descrizione del servizio Microsoft Teams.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="84450-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="84450-118">Rete dell'organizzazione preparata per Teams</span><span class="sxs-lookup"><span data-stu-id="84450-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="84450-119">Per informazioni sulla preparazione della rete, vedere [Preparare la rete dell'organizzazione per Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="84450-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="84450-120">Consentire l'accesso di rete a Exchange, Sharepoint e OneDrive for Business in Microsoft 365 o Office 365: URL e intervalli di indirizzi IP di [Office 365.](/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="84450-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="84450-121">Il provisioning dei tenant creati dopo l'1 settembre 2019 viene eseguito in modalità Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="84450-122">Se è stato distribuito Skype for Business Server e il provisioning del tenant è stato eseguito DOPO l'1 settembre 2019, contattare il supporto per abilitare le funzionalità di coesistenza per Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="84450-123">Prima di assegnare le licenze di Teams a <span class="underline"></span> un utente, assicurarsi che il criterio di aggiornamento a livello di organizzazione sia impostato su "Modalità isola".</span><span class="sxs-lookup"><span data-stu-id="84450-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="84450-124">Punti di partenza della migrazione</span><span class="sxs-lookup"><span data-stu-id="84450-124">Migration Starting points</span></span>

<span data-ttu-id="84450-125">Il percorso verso Microsoft 365 o Office 365 e le funzionalità disponibili in Teams a seconda del punto di partenza e dell'esistenza di Skype for Business o Lync Server locale.</span><span class="sxs-lookup"><span data-stu-id="84450-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="84450-126">Le sezioni seguenti illustrano in dettaglio le funzionalità di base e le opzioni di configurazione oltre ai prerequisiti descritti sopra.</span><span class="sxs-lookup"><span data-stu-id="84450-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="84450-127">Gli scenari del punto di partenza sono stati suddivisi negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="84450-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="84450-128">**Configurazione di Tenant Teams:** le modalità tenant e utente vengono usate per controllare il comportamento del destinatario.</span><span class="sxs-lookup"><span data-stu-id="84450-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="84450-129">Queste impostazioni possono essere assegnate a livello di tenant o di utente in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84450-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="84450-130">Per altre informazioni, leggi [Coesistenza con Skype for Business.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="84450-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="84450-131">**Comunicazione chat/esterna in Teams:** i servizi chat fanno riferimento a conversazioni peer-to-peer o chat di gruppo all'interno e all'organizzazione o esternamente all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84450-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="84450-132">La comunicazione esterna è detta anche federazione in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="84450-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="84450-133">**Creare e visualizzare riunioni in Teams:** un utente può sempre creare riunioni online tramite il componente aggiuntivo Outlook Teams e l'accesso pstn è disponibile in tutti gli scenari una volta che l'utente ha una licenza.</span><span class="sxs-lookup"><span data-stu-id="84450-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="84450-134">Teams e Skype for Business archiviano le informazioni del calendario nella cassetta postale di Exchange dell'utente.</span><span class="sxs-lookup"><span data-stu-id="84450-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="84450-135">Il server Exchange locale deve essere Exchange Server 2016 CU3 o versioni successive perché il client Teams possa interagire con la cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="84450-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="84450-136">Senza l'accesso alla cassetta postale di Exchange, l'icona Calendario in Teams non viene visualizzata e l'utente non sarà in grado di visualizzare, creare o modificare riunioni nel client Di Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="84450-137">**Funzionalità di chiamata VoIP/PSTN in Teams:** le chiamate possono essere Voice over IP (VoIP) o PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="84450-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="84450-138">La connettività VoIP avviene in modo nativo tra i client di Teams, mentre la connettività PSTN avviene quando un utente compone un numero di telefono esterno.</span><span class="sxs-lookup"><span data-stu-id="84450-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="84450-139">Teams supporta due tipi di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="84450-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="84450-140">Piano per chiamate Microsoft, quando Microsoft fornisce un'infrastruttura di telefonia, incluso il numero di telefono di un utente, o la configurazione del routing diretto, in cui il cliente fornisce la connettività di telefonia tramite un Session Border Controller (SBC) per l'utente di Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="84450-141">Per saperne di più, leggi Quale piano per le chiamate [è giusto per te?](calling-plan-landing-page.md) e [Instradamento diretto del sistema telefonico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="84450-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="84450-142">Collaborazione tra team e **canali in Teams:** in Teams i team sono gruppi di persone riunite per lavoro, progetti o interessi comuni.</span><span class="sxs-lookup"><span data-stu-id="84450-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="84450-143">I team sono fatti di canali.</span><span class="sxs-lookup"><span data-stu-id="84450-143">Teams are made up of channels.</span></span> <span data-ttu-id="84450-144">Ogni canale è basato su un argomento, ad esempio "Eventi del team", un nome di reparto o solo per divertimento.</span><span class="sxs-lookup"><span data-stu-id="84450-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="84450-145">I canali sono la posizione in cui si tengono riunioni, si hanno conversazioni e si lavora insieme ai file.</span><span class="sxs-lookup"><span data-stu-id="84450-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="84450-146">Durante la collaborazione</span><span class="sxs-lookup"><span data-stu-id="84450-146">During collaboration</span></span>

<span data-ttu-id="84450-147">**OneDrive for Business (condivisione di file P2P) in Teams:** all'esterno di Teams e canali, gli utenti di Teams possono condividere file peer-to-peer usando OneDrive for Business o altri programmi di file di condivisione P2P come Citrix Files, DropBox, Box e Google Drive.</span><span class="sxs-lookup"><span data-stu-id="84450-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="84450-148">Per OneDrive for Business un utente deve avere una licenza di SharePoint Online assegnata.</span><span class="sxs-lookup"><span data-stu-id="84450-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="84450-149">**Piattaforma applicativa:** le app forniscono strumenti avanzati per l'organizzazione per ottenere di più da Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="84450-150">Queste app combinano le funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84450-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="84450-151">**Caratteristiche di sicurezza e conformità:** Teams include un'ampia gamma di informazioni utili per le aree di conformità, inclusi i criteri di conservazione, la prevenzione della perdita dei dati (DLP), eDiscovery e il blocco legale per canali, chat e file, ricerca nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="84450-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="84450-152">Per altre informazioni, vedere [Sicurezza e conformità in Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84450-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="84450-153">Le funzionalità avanzate di eDiscovery richiedono la licenza E5.</span><span class="sxs-lookup"><span data-stu-id="84450-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="84450-154">[Confrontare le opzioni di licenza](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="84450-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="84450-155">Per informazioni sulle caratteristiche di conformità disponibili nello scenario, vedere Come interagiscono Exchange e [Microsoft Teams.](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="84450-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="84450-156">Organizzazioni **<span class="underline">senza</span>** Skype for Business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="84450-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="84450-157">Questo punto di partenza presuppone che l'organizzazione non usa attualmente Skype for Business o Lync Server e Teams sarà la prima applicazione in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="84450-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="84450-158">La tabella seguente contiene informazioni dettagliate sulla configurazione di alto livello e sulle funzionalità degli utenti finali per Teams per i servizi di base.</span><span class="sxs-lookup"><span data-stu-id="84450-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="84450-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="84450-159">Item</span></span></th>
<th><span data-ttu-id="84450-160">Note</span><span class="sxs-lookup"><span data-stu-id="84450-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="84450-161">Configurazione di Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="84450-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="84450-162">Modalità Solo Teams, tutte le funzionalità di chat e chiamate sono disponibili solo in Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-163">Chat /Comunicazione esterna in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="84450-164">Comunicazioni interne (all'interno di Microsoft 365 o Office 365) e comunicazioni di chat esterne da Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="84450-165"><em>Nota: le voci DNS devono essere configurate per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="84450-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="84450-166">I record DNS di Skype for Business sono necessari anche se non si dispone di Skype for Business locale o in Microsoft 365 o Office 365, per consentire la federazione con gli ambienti Lync e Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="84450-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="84450-167">
<a href="/office365/enterprise/external-domain-name-system-records">Record domain name system esterni</a></em></span><span class="sxs-lookup"><span data-stu-id="84450-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84450-168">Creare e visualizzare riunioni in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="84450-169">Possibilità di creare riunioni interne ed esterne tramite il componente aggiuntivo Outlook.</span><span class="sxs-lookup"><span data-stu-id="84450-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="84450-170">Con le licenze di audioconferenza è disponibile la funzionalità Di accesso esterno e Chiamata in uscita PSTN.</span><span class="sxs-lookup"><span data-stu-id="84450-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="84450-171">Per l'accesso al calendario di Teams è necessario che Exchange 2016 CU3+ sia distribuito in locale con exchange ibrido stabilito: Creare una distribuzione ibrida con <a href="/exchange/hybrid-deployment/deploy-hybrid">la procedura guidata Configurazione ibrida.</a> </span><span class="sxs-lookup"><span data-stu-id="84450-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="84450-172">Oltre alla configurazione ibrida di Exchange, stabilire l'autenticazione OAuth di Exchange: Configurare l'autenticazione OAuth tra le organizzazioni di <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange ed Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="84450-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-173">Funzionalità di chiamata</span><span class="sxs-lookup"><span data-stu-id="84450-173">Calling Features</span></span><br />
<span data-ttu-id="84450-174">VoIP/PSTN in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="84450-175">VoIP internamente ed esternamente al tenant è disponibile.</span><span class="sxs-lookup"><span data-stu-id="84450-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="84450-176">I servizi PSTN possono essere configurati tramite Microsoft Phone System, oltre ad aggiungere un piano per chiamate Microsoft o un routing diretto.</span><span class="sxs-lookup"><span data-stu-id="84450-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84450-177">Collaborazione di Teams e Canali in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="84450-178">Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84450-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="84450-179">La migrazione dei siti di SharePoint locali esistenti non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="84450-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-180">OneDrive for Business (condivisione di file P2P)</span><span class="sxs-lookup"><span data-stu-id="84450-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="84450-181">OneDrive for Business richiede che a un utente sia assegnata una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84450-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="84450-182">Senza questa licenza, la condivisione di file peer-to-peer non sarà possibile.</span><span class="sxs-lookup"><span data-stu-id="84450-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84450-183">Piattaforma dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="84450-183">Application platform</span></span></td>
<td><span data-ttu-id="84450-184">Gli utenti potranno usare le app designate per loro in base ai criteri aziendali.</span><span class="sxs-lookup"><span data-stu-id="84450-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="84450-185">Altre informazioni qui: <a href="/microsoftteams/admin-settings">Impostazioni di amministrazione per le app in Teams</a></span><span class="sxs-lookup"><span data-stu-id="84450-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-186">Caratteristiche di sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="84450-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="84450-187">Sono disponibili criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="84450-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="84450-188">Sono supportati eDiscovery e blocco legale per la conformità ai messaggi del canale.</span><span class="sxs-lookup"><span data-stu-id="84450-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="84450-189">Sono disponibili i criteri di prevenzione della perdita dei dati.Data Loss Prevention policies (DLP) are available.</span><span class="sxs-lookup"><span data-stu-id="84450-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="84450-190">Set di funzionalità completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="84450-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="84450-191">Per un elenco completo, vedere <a href="/MicrosoftTeams/exchange-teams-interact">Interazione tra Exchange e Teams.</a></span><span class="sxs-lookup"><span data-stu-id="84450-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="84450-192">Procedura di abilitazione per le organizzazioni senza Skype for Business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="84450-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="84450-193">Ecco i prerequisiti descritti in dettaglio nella sezione Iniziare qui riportata sopra</span><span class="sxs-lookup"><span data-stu-id="84450-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="84450-194">Passare alla modalità Solo teams (solo per i tenant esistenti): Impostazione [delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="84450-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="84450-195">Configurare il tenant in base ai criteri aziendali/aziendali dell'azienda: [Gestire le impostazioni di Microsoft Teams per l'organizzazione.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="84450-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="84450-196">Distribuire il client Teams agli utenti: [Ottenere i client per Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="84450-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="84450-197">Guida il tuo programma di adozione</span><span class="sxs-lookup"><span data-stu-id="84450-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="84450-198">Adottare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84450-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="84450-199">Elenco di controllo introduttivo sull'adozione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84450-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="84450-200">Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="84450-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="84450-201">Organizzazioni **<span class="underline">con</span>** Skype for Business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="84450-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="84450-202">Questo punto di partenza presuppone che l'organizzazione usa il server Skype for Business 2019 o 2015+ o Lync 2013+ locale.</span><span class="sxs-lookup"><span data-stu-id="84450-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="84450-203">Sono già disponibili indicazioni approfondite per le organizzazioni che esevranno eseguire la migrazione da server locali a Teams e dovrebbero essere seguite per questi scenari.</span><span class="sxs-lookup"><span data-stu-id="84450-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="84450-204">Queste indicazioni sono specifiche dello scenario in cui Teams è la prima applicazione utilizzata in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="84450-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="84450-205">La tabella seguente contiene informazioni dettagliate sulla configurazione di alto livello e sulle funzionalità degli utenti finali per Teams per i servizi di base.</span><span class="sxs-lookup"><span data-stu-id="84450-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="84450-206">Elemento</span><span class="sxs-lookup"><span data-stu-id="84450-206">Item</span></span></th>
<th><span data-ttu-id="84450-207">Note</span><span class="sxs-lookup"><span data-stu-id="84450-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="84450-208">Configurazione di Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="84450-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="84450-209">Modalità Isole.</span><span class="sxs-lookup"><span data-stu-id="84450-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-210">Chat /Comunicazione esterna in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="84450-211">Interno solo all'interno del proprio tenant, la comunicazione esterna (federazione) avviene tramite la distribuzione di Skype for Business o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84450-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84450-212">Creare e visualizzare riunioni in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="84450-213">Possibilità di creare riunioni interne ed esterne tramite il componente aggiuntivo Outlook.</span><span class="sxs-lookup"><span data-stu-id="84450-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="84450-214">Con le licenze di audioconferenza è disponibile la funzionalità Di accesso esterno e Chiamata in uscita PSTN.</span><span class="sxs-lookup"><span data-stu-id="84450-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="84450-215">L'accesso al calendario di Teams richiede Exchange 2016 CU3+ locale distribuito con exchange ibrido stabilito:</span><span class="sxs-lookup"><span data-stu-id="84450-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="84450-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la procedura guidata Configurazione ibrida.</a></span><span class="sxs-lookup"><span data-stu-id="84450-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="84450-217">L'amministratore può controllare il componente aggiuntivo Outlook di Skype for Business tramite l'attributo PreferredMeetingProviderForIslandsMode dei criteri di riunione di Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></span><span class="sxs-lookup"><span data-stu-id="84450-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-218">Funzionalità di chiamata</span><span class="sxs-lookup"><span data-stu-id="84450-218">Calling Features</span></span><br />
<span data-ttu-id="84450-219">VoIP/PSTN in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="84450-220">VoIP internamente al tenant è disponibile.</span><span class="sxs-lookup"><span data-stu-id="84450-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="84450-221">I servizi PSTN o Piano chiamate non sono disponibili finché l'utente non viene spostato nell'esperienza Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84450-222">Collaborazione di Teams e Canali in Teams</span><span class="sxs-lookup"><span data-stu-id="84450-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="84450-223">Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84450-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="84450-224">La migrazione dei siti di SharePoint locali esistenti non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="84450-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-225">OneDrive for Business (condivisione di file P2P)</span><span class="sxs-lookup"><span data-stu-id="84450-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="84450-226">OneDrive for Business richiede che a un utente sia assegnata una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84450-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="84450-227">Senza questa licenza non sarà possibile condividere file per peer.</span><span class="sxs-lookup"><span data-stu-id="84450-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84450-228">Piattaforma dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="84450-228">Application platform</span></span></td>
<td><span data-ttu-id="84450-229">Gli utenti potranno usare le app designate per loro in base ai criteri aziendali.</span><span class="sxs-lookup"><span data-stu-id="84450-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="84450-230">Altre informazioni qui: <a href="/microsoftteams/admin-settings">Impostazioni di amministrazione per le app in Teams</a></span><span class="sxs-lookup"><span data-stu-id="84450-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84450-231">Caratteristiche di sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="84450-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="84450-232">Sono disponibili criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="84450-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="84450-233">Sono supportati eDiscovery e blocco legale per la conformità ai messaggi del canale.</span><span class="sxs-lookup"><span data-stu-id="84450-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="84450-234">Sono disponibili i criteri di prevenzione della perdita dei dati.Data Loss Prevention policies (DLP) are available.</span><span class="sxs-lookup"><span data-stu-id="84450-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="84450-235">Set di funzionalità completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="84450-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="84450-236">Per un elenco completo, vedere <a href="/MicrosoftTeams/exchange-teams-interact">Interazione tra Exchange e Teams.</a></span><span class="sxs-lookup"><span data-stu-id="84450-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="84450-237">Passaggi di abilitazione per le organizzazioni con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="84450-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="84450-238">Ecco i prerequisiti descritti in dettaglio nella sezione Iniziare qui sopra.</span><span class="sxs-lookup"><span data-stu-id="84450-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="84450-239">Impostare il tenant in modalità Isole (per i tenant di cui è stato eseguito il provisioning DOPO l'1/9/2019, contattare il supporto tecnico per apportare questa modifica)</span><span class="sxs-lookup"><span data-stu-id="84450-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="84450-240">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="84450-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="84450-241">Configurare il tenant in base ai criteri aziendali/aziendali dell'azienda</span><span class="sxs-lookup"><span data-stu-id="84450-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="84450-242">Gestire le impostazioni di Microsoft Teams per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="84450-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="84450-243">Distribuire il client Teams</span><span class="sxs-lookup"><span data-stu-id="84450-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="84450-244">Ottenere client per Teams</span><span class="sxs-lookup"><span data-stu-id="84450-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="84450-245">Guida il tuo programma di adozione</span><span class="sxs-lookup"><span data-stu-id="84450-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="84450-246">Adottare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84450-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="84450-247">Elenco di controllo introduttivo sull'adozione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84450-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="84450-248">Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="84450-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="84450-249">Stabilire la distribuzione ibrida di Skype for Business e seguire i percorsi di aggiornamento consigliati per i server Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="84450-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="84450-250">Eseguire l'aggiornamento da Skype for Business locale a Teams</span><span class="sxs-lookup"><span data-stu-id="84450-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="84450-251">Istruzione di chiusura</span><span class="sxs-lookup"><span data-stu-id="84450-251">Closing statement</span></span>

<span data-ttu-id="84450-252">Microsoft Teams può essere un'opzione che consente all'organizzazione di riunire tutti i dipendenti, gli information worker e i frontline worker su un'unica piattaforma.</span><span class="sxs-lookup"><span data-stu-id="84450-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="84450-253">È possibile [iniziare oggi](https://products.office.com/microsoft-teams/group-chat-software) stesso.</span><span class="sxs-lookup"><span data-stu-id="84450-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="84450-254">È possibile rimanere in contatto con tutti gli annunci più recenti e gli aggiornamenti mensili dei prodotti [qui.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="84450-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="84450-255">Inoltre, poiché le aziende di tutto il mondo gestiscono l'attuale situazione di COVID-19, abbiamo creato una serie di contenuti che ti aiuteranno a usare Teams per il massimo impatto nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84450-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="84450-256">Il [nostro impegno per i clienti durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="84450-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="84450-257">2 settimane in: ciò che abbiamo imparato sul lavoro remoto</span><span class="sxs-lookup"><span data-stu-id="84450-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="84450-258">Distribuzione di riunioni ed eventi online</span><span class="sxs-lookup"><span data-stu-id="84450-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="84450-259">Aiutare le piccole e medie imprese a lavorare in remoto con Teams</span><span class="sxs-lookup"><span data-stu-id="84450-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="84450-260">Trasformazione digitale degli eventi live: le osservazioni di Bob Bejan dalla prima linea</span><span class="sxs-lookup"><span data-stu-id="84450-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="84450-261">I principali 9 modi in cui Microsoft IT sta abilitando il lavoro remoto per i suoi dipendenti</span><span class="sxs-lookup"><span data-stu-id="84450-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="84450-262">Lavorare in remoto, rimanere al sicuro: suggerimenti per i CISO</span><span class="sxs-lookup"><span data-stu-id="84450-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="84450-263">Aiutare insegnanti e studenti a passare all'apprendimento remoto</span><span class="sxs-lookup"><span data-stu-id="84450-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="84450-264">Rimanere produttivi mentre si lavora in remoto con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84450-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="84450-265">Informazioni di riferimento su Servizi di supporto</span><span class="sxs-lookup"><span data-stu-id="84450-265">Support Services reference</span></span>

<span data-ttu-id="84450-266">Teams si basa su Exchange Online, SharePoint Online, OneDrive for Business e Gruppi di Microsoft 365 per offrire agli utenti un'esperienza completamente integrata in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="84450-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="84450-267">Come indicato in precedenza, Teams funzionerà senza distribuire completamente questi servizi, con funzionalità limitate.</span><span class="sxs-lookup"><span data-stu-id="84450-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="84450-268">Per altre informazioni su Teams e sui relativi prerequisiti, vedere: [Benvenuto in Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84450-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="84450-269">Per informazioni specifiche su ognuno dei servizi elencati sopra, seguire i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="84450-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="84450-270">Exchange Online viene usato per le funzionalità di calendario e per l'archiviazione di messaggi peer-to-peer in Teams.</span><span class="sxs-lookup"><span data-stu-id="84450-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="84450-271">Per altre informazioni, vedere [Interazione tra Exchange e Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="84450-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84450-272">Per l'interoperabilità di Teams con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange come descritto in Configurare l'autenticazione OAuth tra le organizzazioni di [Exchange ed Exchange Online.](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="84450-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="84450-273">SharePoint viene usato per la condivisione di file nei canali, mentre /OneDrive for Business viene usato per la condivisione di file in 1:1 o in una chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="84450-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="84450-274">Per altre informazioni, vedere [Come SharePoint Online e OneDrive for Business interagiscono con Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="84450-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="84450-275">[I gruppi di Microsoft 365 vengono](office-365-groups.md) usati per la creazione/gestione di team e canali.</span><span class="sxs-lookup"><span data-stu-id="84450-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="84450-276">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="84450-276">Related topics</span></span>

[<span data-ttu-id="84450-277">Poster di soluzioni di telefonia e architettura IT di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84450-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="84450-278">Pianificare la connettività ibrida tra Skype for Business Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="84450-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="84450-279">Supportare i lavoratori remoti con Teams</span><span class="sxs-lookup"><span data-stu-id="84450-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="84450-280">Lavorare in remoto con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="84450-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)