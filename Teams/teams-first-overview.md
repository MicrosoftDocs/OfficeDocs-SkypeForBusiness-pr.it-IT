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
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909480"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="e9647-103">Implementare Microsoft Teams First</span><span class="sxs-lookup"><span data-stu-id="e9647-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="e9647-104">Microsoft Teams può aiutare i dipendenti a rimanere in contatto e a collaborare tra loro, soprattutto nel tempo attuale in cui il lavoro remoto è una realtà di dipendenti in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="e9647-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="e9647-105">La possibilità di chattare, fare video riunioni e collaborare ai documenti di Office all'interno di Teams può aiutare le aziende a rimanere produttivi.</span><span class="sxs-lookup"><span data-stu-id="e9647-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="e9647-106">Sia che si sia una piccola azienda, una no profit o una grande organizzazione, è possibile iniziare a usare Teams come primo carico di lavoro all'interno della famiglia di prodotti Microsoft 365 o Office 365 prima di distribuire qualsiasi altra app o servizio di Office.</span><span class="sxs-lookup"><span data-stu-id="e9647-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="e9647-107">Questo articolo illustra nel dettaglio le considerazioni da tenere in considerazione per l'approccio "Teams First".</span><span class="sxs-lookup"><span data-stu-id="e9647-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9647-108">Anche se Teams può essere il primo carico di lavoro distribuito nel cloud dell'organizzazione, la distribuzione di Teams dovrebbe fare parte della strategia di distribuzione cloud complessiva.</span><span class="sxs-lookup"><span data-stu-id="e9647-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="e9647-109">Se sono già stati implementazioni altri servizi di Microsoft 365 o Office 365 e Teams rappresenta il prossimo carico di lavoro da implementare (invece del primo), iniziare da [Come implementare Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="e9647-110">Iniziare da qui</span><span class="sxs-lookup"><span data-stu-id="e9647-110">Start here</span></span>

<span data-ttu-id="e9647-111">Per iniziare con la distribuzione Teams First, è necessario soddisfare almeno alcuni prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="e9647-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="e9647-112">L'elenco seguente mostra cosa è necessario avere in posizione per l'organizzazione prima che Teams possa essere abilitato:</span><span class="sxs-lookup"><span data-stu-id="e9647-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="e9647-113">Un'organizzazione di Microsoft 365 o Office 365 configurata con il nome di dominio</span><span class="sxs-lookup"><span data-stu-id="e9647-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="e9647-114">Connettività di Azure Active Directory (connessione AAD) o soluzione di sincronizzazione delle identità cloud simile, con tutti gli attributi obbligatori sincronizzati con il tenant</span><span class="sxs-lookup"><span data-stu-id="e9647-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="e9647-115">Per informazioni sugli attributi sincronizzati con la sincronizzazione AAD, leggere la sincronizzazione [di Azure AD Connect: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="e9647-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="e9647-116">Licenze utente appropriate assegnate a Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="e9647-117">Per informazioni sulle licenze di Teams, leggere la [descrizione del servizio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="e9647-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="e9647-118">Rete dell'organizzazione preparata per Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="e9647-119">Per informazioni sulla preparazione della rete, vedere [Preparare la rete dell'organizzazione per Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="e9647-120">Consentire l'accesso di rete a Exchange, Sharepoint e OneDrive for Business in Microsoft 365 o Office 365: URL e intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="e9647-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="e9647-121">I tenant creati dopo il 1° settembre 2019 sono disponibili solo in modalità Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="e9647-122">Se è stato distribuito Skype for Business Server ed è stato eseguito il provisioning del tenant DOPO il 1° settembre 2019, contattare il supporto per abilitare le funzionalità di coesistenza per Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="e9647-123">Assicurati che il "criterio di aggiornamento a livello di organizzazione" sia impostato sulla "modalità <span class="underline">Isola"</span> prima di assegnare le licenze di Teams a un utente.</span><span class="sxs-lookup"><span data-stu-id="e9647-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="e9647-124">Punti di partenza della migrazione</span><span class="sxs-lookup"><span data-stu-id="e9647-124">Migration Starting points</span></span>

<span data-ttu-id="e9647-125">Il viaggio in Microsoft 365 o Office 365 e le funzionalità disponibili in Teams dipendono dal punto di partenza e dalla presenza di Skype for Business o Lync Server locale.</span><span class="sxs-lookup"><span data-stu-id="e9647-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="e9647-126">Le sezioni seguenti illustrano in dettaglio le funzionalità e le opzioni di configurazione di base oltre ai prerequisiti descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e9647-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="e9647-127">Gli scenari di partenza sono stati suddivisi negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9647-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="e9647-128">**Configurazione di Tenant Teams:** le modalità tenant e utente vengono usate per controllare il comportamento del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e9647-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="e9647-129">Queste impostazioni possono essere assegnate a livello di tenant o di utente in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9647-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="e9647-130">Per ulteriori informazioni, vedere [Coesistenza con Skype for Business.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="e9647-131">**Comunicazione tramite chat o esterna in Teams:** i servizi di chat fanno riferimento a conversazioni peer-to-peer o di chat di gruppo all'interno e all'organizzazione o esternamente all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9647-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="e9647-132">La comunicazione esterna è detta anche federazione in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e9647-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="e9647-133">**Creare e visualizzare riunioni in Teams:** un utente può sempre creare riunioni online tramite il componente aggiuntivo Outlook Teams e l'accesso con accesso remoto PSTN è disponibile in tutti gli scenari una volta che l'utente ha una licenza.</span><span class="sxs-lookup"><span data-stu-id="e9647-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="e9647-134">Teams e Skype for Business archiviano le informazioni del calendario nella cassetta postale di Exchange dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e9647-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="e9647-135">Il server Exchange locale deve Exchange Server 2016 CU3 o versione precedente perché il client Teams possa interagire con la cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e9647-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="e9647-136">Senza accesso alla cassetta postale di Exchange, l'icona calendario in Teams non verrà visualizzata e l'utente non sarà in grado di visualizzare, creare o modificare riunioni nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="e9647-137">**Funzionalità di chiamata VoIP/PSTN in Teams:** le chiamate possono essere Voice over IP (VoIP) o PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="e9647-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="e9647-138">La connettività VoIP avviene a livello nativo tra i client di Teams, mentre la connettività PSTN avviene quando un utente compone un numero di telefono esterno.</span><span class="sxs-lookup"><span data-stu-id="e9647-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="e9647-139">Teams supporta due tipi di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="e9647-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="e9647-140">Piano per chiamate Microsoft, quando Microsoft fornisce un'infrastruttura telefonica comprensiva del numero di telefono di un utente o della configurazione di instradamento diretto, in cui il cliente fornisce la connettività telefonica su un Session Border Controller (SBC) per l'utente di Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="e9647-141">Per saperne di più, leggi Quale piano per chiamate è la scelta giusta [per te?](calling-plan-landing-page.md) [e Instradamento diretto del Sistema telefonico.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="e9647-142">**Collaborazione tra team e canali in Teams:** In Teams, i team sono gruppi di persone che si riuniranno per lavoro, progetti o interessi comuni.</span><span class="sxs-lookup"><span data-stu-id="e9647-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="e9647-143">I team sono fatti di canali.</span><span class="sxs-lookup"><span data-stu-id="e9647-143">Teams are made up of channels.</span></span> <span data-ttu-id="e9647-144">Ogni canale è basato su un argomento, ad esempio "Eventi del team", il nome di un reparto o solo per divertimento.</span><span class="sxs-lookup"><span data-stu-id="e9647-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="e9647-145">Nei canali puoi tenere riunioni, tenere conversazioni e lavorare insieme ai file.</span><span class="sxs-lookup"><span data-stu-id="e9647-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="e9647-146">Durante la collaborazione</span><span class="sxs-lookup"><span data-stu-id="e9647-146">During collaboration</span></span>

<span data-ttu-id="e9647-147">**OneDrive for Business (condivisione di file P2P) in Teams:** All'esterno di Teams e canali, gli utenti di Teams possono condividere file peer-to-peer utilizzando OneDrive for Business o altri programmi di file di condivisione P2P come File Citrix, DropBox, Box e Google Drive.</span><span class="sxs-lookup"><span data-stu-id="e9647-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="e9647-148">Per OneDrive for Business, è necessario che a un utente sia assegnata una licenza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e9647-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="e9647-149">**Piattaforma** dell'applicazione: le app forniscono strumenti avanzati per l'organizzazione per ottenere il maggior numero di informazioni da Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="e9647-150">Queste app combinano le funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9647-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="e9647-151">**Caratteristiche di sicurezza e conformità:** Teams include un'ampia gamma di informazioni utili per le aree di conformità, tra cui criteri di conservazione, prevenzione della perdita dei dati (DLP), eDiscovery e blocco a livello legale per canali, chat e file, ricerca nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="e9647-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="e9647-152">Per saperne di più, [leggi Sicurezza e conformità in Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="e9647-153">Le caratteristiche di Advance eDiscovery richiedono una licenza E5.</span><span class="sxs-lookup"><span data-stu-id="e9647-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="e9647-154">[Confrontare le opzioni di licenza.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="e9647-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="e9647-155">Leggere [come interagiscono Exchange e Microsoft Teams](exchange-teams-interact.md) per sapere quali funzionalità di conformità sono disponibili nello scenario.</span><span class="sxs-lookup"><span data-stu-id="e9647-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="e9647-156">Organizzazioni **<span class="underline">senza</span>** Skype for Business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="e9647-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="e9647-157">Questo punto di partenza presuppone che l'organizzazione non utilizzi attualmente Skype for Business o Lync Server e Teams sarà la prima applicazione in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9647-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e9647-158">La tabella seguente dettaglia la configurazione di alto livello e le funzionalità per gli utenti finali di Teams per i servizi di base.</span><span class="sxs-lookup"><span data-stu-id="e9647-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e9647-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9647-159">Item</span></span></th>
<th><span data-ttu-id="e9647-160">Note</span><span class="sxs-lookup"><span data-stu-id="e9647-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e9647-161">Configurazione di Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="e9647-162">Modalità Solo Teams, tutte le funzionalità di chat e chiamate sono disponibili solo in Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-163">Chat/Comunicazione esterna in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="e9647-164">Comunicazioni interne (interne a Microsoft 365 o Office 365) e chat esterne da Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="e9647-165"><em>Nota: le voci DNS devono essere configurate per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="e9647-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="e9647-166">I record DNS di Skype for Business sono necessari anche se skype for Business non è installato in locale o in Microsoft 365 o Office 365, per consentire la federazione con ambienti Lync e Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="e9647-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="e9647-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Record DNS (Domain Name System) esterni</a></em></span><span class="sxs-lookup"><span data-stu-id="e9647-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9647-168">Creare e visualizzare riunioni in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="e9647-169">Possibilità di creare riunioni interne ed esterne tramite il componente aggiuntivo Outlook.</span><span class="sxs-lookup"><span data-stu-id="e9647-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="e9647-170">Con le licenze di Audioconferenza è disponibile la funzionalità Chiamata in ingresso e uscita PSTN.</span><span class="sxs-lookup"><span data-stu-id="e9647-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="e9647-171">L'accesso al calendario di Teams richiede Exchange 2016 CU3+ locale distribuito con Exchange ibrido stabilito: creare una distribuzione ibrida con <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">la procedura guidata Configurazione ibrida.</a> </span><span class="sxs-lookup"><span data-stu-id="e9647-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="e9647-172">Oltre alla configurazione ibrida di Exchange, stabilire l'autenticazione OAuth di Exchange: configurare l'autenticazione OAuth tra le organizzazioni di Exchange ed <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="e9647-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-173">Funzionalità di chiamata</span><span class="sxs-lookup"><span data-stu-id="e9647-173">Calling Features</span></span><br />
<span data-ttu-id="e9647-174">VoIP/PSTN in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="e9647-175">VoIP sia all'interno che all'esterno del tenant è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e9647-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="e9647-176">I servizi PSTN possono essere configurati tramite il Sistema telefonico Microsoft, oltre all'aggiunta di un piano per chiamate Microsoft o di instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="e9647-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9647-177">Collaborazione tra team e canali in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="e9647-178">Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare una licenza di SharePoint Online all'utente.</span><span class="sxs-lookup"><span data-stu-id="e9647-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="e9647-179">Non è richiesta la migrazione di siti di SharePoint locali esistenti.</span><span class="sxs-lookup"><span data-stu-id="e9647-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-180">OneDrive for Business (condivisione di file P2P)</span><span class="sxs-lookup"><span data-stu-id="e9647-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="e9647-181">OneDrive for Business richiede l'assegnazione di una licenza di SharePoint Online a un utente.</span><span class="sxs-lookup"><span data-stu-id="e9647-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="e9647-182">Senza questa licenza non sarà possibile condividere i file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="e9647-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9647-183">Piattaforma dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="e9647-183">Application platform</span></span></td>
<td><span data-ttu-id="e9647-184">Gli utenti potranno usare le app designate per loro disponibili in base ai criteri della società.</span><span class="sxs-lookup"><span data-stu-id="e9647-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="e9647-185">Altre informazioni qui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Impostazioni di amministratore per le app in Teams</a></span><span class="sxs-lookup"><span data-stu-id="e9647-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-186">Caratteristiche di sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="e9647-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e9647-187">Sono disponibili criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="e9647-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="e9647-188">Sono supportati eDiscovery e blocco a livello legale per la conformità ai messaggi di canale.</span><span class="sxs-lookup"><span data-stu-id="e9647-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="e9647-189">Sono disponibili criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="e9647-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="e9647-190">Set di caratteristiche completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="e9647-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="e9647-191">Per un elenco completo, vedere come <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">interagiscono Exchange e Teams.</a></span><span class="sxs-lookup"><span data-stu-id="e9647-191">For a full list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="e9647-192">Procedura di abilitazione per le organizzazioni senza Skype for Business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="e9647-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="e9647-193">Ecco i prerequisiti dettagliati nella sezione Iniziare qui sopra</span><span class="sxs-lookup"><span data-stu-id="e9647-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="e9647-194">Passa il tenant in modalità Solo Teams (solo per i tenant esistenti): [Impostazione delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="e9647-195">Configurare il tenant in base ai criteri aziendali: gestire le impostazioni di [Microsoft Teams per l'organizzazione.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="e9647-196">Distribuire il client teams agli utenti: [Ottenere i client per Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="e9647-197">Guidare il programma di adozione</span><span class="sxs-lookup"><span data-stu-id="e9647-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="e9647-198">Adottare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="e9647-199">Elenco di controllo introduttivo per l'adozione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="e9647-200">Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="e9647-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="e9647-201">Organizzazioni **<span class="underline">con</span>** Skype for Business o Lync Server</span><span class="sxs-lookup"><span data-stu-id="e9647-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="e9647-202">Da questo punto di partenza si presuppone che l'organizzazione utilizzi il server Skype for Business 2019 o 2015+ o Lync 2013+ locale.</span><span class="sxs-lookup"><span data-stu-id="e9647-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="e9647-203">Sono già disponibili indicazioni per le organizzazioni che ese stanno eseguendo la migrazione da server locali a Teams e devono essere seguite per questi scenari.</span><span class="sxs-lookup"><span data-stu-id="e9647-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="e9647-204">Queste indicazioni sono specifiche per lo scenario che Teams è la prima applicazione utilizzata in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9647-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e9647-205">La tabella seguente dettaglia la configurazione di alto livello e le funzionalità per gli utenti finali di Teams per i servizi di base.</span><span class="sxs-lookup"><span data-stu-id="e9647-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e9647-206">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9647-206">Item</span></span></th>
<th><span data-ttu-id="e9647-207">Note</span><span class="sxs-lookup"><span data-stu-id="e9647-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e9647-208">Configurazione di Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="e9647-209">Modalità Isole.</span><span class="sxs-lookup"><span data-stu-id="e9647-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-210">Chat/Comunicazione esterna in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="e9647-211">Interna solo all'interno del proprio tenant, la comunicazione esterna (federazione) avviene tramite la distribuzione di Skype for Business o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9647-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9647-212">Creare e visualizzare riunioni in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="e9647-213">Possibilità di creare riunioni interne ed esterne tramite il componente aggiuntivo Outlook.</span><span class="sxs-lookup"><span data-stu-id="e9647-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="e9647-214">Con le licenze di Audioconferenza è disponibile la funzionalità Chiamata in ingresso e uscita PSTN.</span><span class="sxs-lookup"><span data-stu-id="e9647-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="e9647-215">L'accesso al calendario di Teams richiede Exchange 2016 CU3+ locale distribuito con Exchange ibrido stabilito:</span><span class="sxs-lookup"><span data-stu-id="e9647-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="e9647-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la procedura guidata Configurazione ibrida.</a></span><span class="sxs-lookup"><span data-stu-id="e9647-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="e9647-217">L'amministratore può controllare il componente aggiuntivo Outlook di Skype for Business tramite l'attributo PreferredMeetingProviderForIslandsMode dei criteri riunione di Teams:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></span><span class="sxs-lookup"><span data-stu-id="e9647-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-218">Funzionalità di chiamata</span><span class="sxs-lookup"><span data-stu-id="e9647-218">Calling Features</span></span><br />
<span data-ttu-id="e9647-219">VoIP/PSTN in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="e9647-220">VoIP internamente al tenant è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e9647-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="e9647-221">I servizi PSTN o Piani per chiamate non sono disponibili finché l'utente non passa all'esperienza Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9647-222">Collaborazione tra team e canali in Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="e9647-223">Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare una licenza di SharePoint Online all'utente.</span><span class="sxs-lookup"><span data-stu-id="e9647-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="e9647-224">Non è richiesta la migrazione di siti di SharePoint locali esistenti.</span><span class="sxs-lookup"><span data-stu-id="e9647-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-225">OneDrive for Business (condivisione di file P2P)</span><span class="sxs-lookup"><span data-stu-id="e9647-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="e9647-226">OneDrive for Business richiede l'assegnazione di una licenza di SharePoint Online a un utente.</span><span class="sxs-lookup"><span data-stu-id="e9647-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="e9647-227">Senza questa licenza non sarà possibile condividere i file per peer.</span><span class="sxs-lookup"><span data-stu-id="e9647-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9647-228">Piattaforma dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="e9647-228">Application platform</span></span></td>
<td><span data-ttu-id="e9647-229">Gli utenti potranno usare le app designate per loro disponibili in base ai criteri della società.</span><span class="sxs-lookup"><span data-stu-id="e9647-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="e9647-230">Altre informazioni qui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Impostazioni di amministratore per le app in Teams</a></span><span class="sxs-lookup"><span data-stu-id="e9647-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9647-231">Caratteristiche di sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="e9647-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="e9647-232">Sono disponibili criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="e9647-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="e9647-233">Sono supportati eDiscovery e blocco a livello legale per la conformità ai messaggi di canale.</span><span class="sxs-lookup"><span data-stu-id="e9647-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="e9647-234">Sono disponibili criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="e9647-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="e9647-235">Set di caratteristiche completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="e9647-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="e9647-236">Per un elenco completo, vedere <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">l'interazione tra Exchange e Teams.</a></span><span class="sxs-lookup"><span data-stu-id="e9647-236">For a complete list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="e9647-237">Procedura di abilitazione per le organizzazioni con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e9647-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="e9647-238">Ecco i prerequisiti dettagliati nella sezione Iniziare qui sopra.</span><span class="sxs-lookup"><span data-stu-id="e9647-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="e9647-239">Passare alla modalità Isole (per i tenant di cui è stato effettuato il provisioning DOPO l'1/9/2019, contatta il supporto tecnico per apportare questa modifica)</span><span class="sxs-lookup"><span data-stu-id="e9647-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="e9647-240">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e9647-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="e9647-241">Configurare il tenant in base ai criteri aziendali e aziendali</span><span class="sxs-lookup"><span data-stu-id="e9647-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="e9647-242">Gestire le impostazioni di Microsoft Teams per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e9647-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="e9647-243">Distribuire il client di Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="e9647-244">Ottenere client per Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="e9647-245">Guidare il programma di adozione</span><span class="sxs-lookup"><span data-stu-id="e9647-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="e9647-246">Adottare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="e9647-247">Elenco di controllo introduttivo per l'adozione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="e9647-248">Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="e9647-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="e9647-249">Stabilire una distribuzione ibrida di Skype for Business e seguire i percorsi di aggiornamento consigliati per i server Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="e9647-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="e9647-250">Eseguire l'aggiornamento da Skype for Business locale a Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="e9647-251">Istruzione di chiusura</span><span class="sxs-lookup"><span data-stu-id="e9647-251">Closing statement</span></span>

<span data-ttu-id="e9647-252">Microsoft Teams può essere un abilitazione per l'organizzazione a riunire tutti i dipendenti, information worker e frontline worker su un'unica piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e9647-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="e9647-253">È possibile [iniziare oggi](https://products.office.com/microsoft-teams/group-chat-software) stesso.</span><span class="sxs-lookup"><span data-stu-id="e9647-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="e9647-254">Puoi rimanere in contatto con tutti gli ultimi annunci e gli aggiornamenti mensili dei [prodotti qui.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="e9647-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="e9647-255">Inoltre, poiché le aziende di tutto il mondo gestiscono l'attuale situazione di COVID-19, abbiamo creato una serie di contenuti che ti aiuteranno a utilizzare Teams per il massimo impatto nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9647-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="e9647-256">Il [nostro impegno verso i clienti durante IL COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="e9647-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="e9647-257">2 settimane in: ciò che abbiamo appreso sul lavoro remoto</span><span class="sxs-lookup"><span data-stu-id="e9647-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="e9647-258">Fornire riunioni ed eventi online</span><span class="sxs-lookup"><span data-stu-id="e9647-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="e9647-259">Aiutare le piccole e medie imprese a lavorare in remoto con Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="e9647-260">Trasformazione digitale degli eventi live: osservazioni di Bob Bejan dal fronte</span><span class="sxs-lookup"><span data-stu-id="e9647-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="e9647-261">I principali 9 modi in cui Microsoft IT sta abilitando il lavoro remoto per i suoi dipendenti</span><span class="sxs-lookup"><span data-stu-id="e9647-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="e9647-262">Lavorare in remoto e restare al sicuro, suggerimenti per CISO</span><span class="sxs-lookup"><span data-stu-id="e9647-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="e9647-263">Aiutare insegnanti e studenti a passare all'apprendimento remoto</span><span class="sxs-lookup"><span data-stu-id="e9647-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="e9647-264">Rimanere produttivi mentre si lavora in remoto con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="e9647-265">Informazioni di riferimento per i Servizi di supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="e9647-265">Support Services reference</span></span>

<span data-ttu-id="e9647-266">Teams si basa su Exchange Online, SharePoint Online, OneDrive for Business e Gruppi di Microsoft 365 per offrire agli utenti un'esperienza microsoft 365 o Office 365 completamente integrata.</span><span class="sxs-lookup"><span data-stu-id="e9647-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="e9647-267">Come descritto in precedenza, Teams funzionerà senza la distribuzione completa di questi servizi, con funzionalità limitate.</span><span class="sxs-lookup"><span data-stu-id="e9647-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="e9647-268">Per saperne di più su Teams e sui prerequisiti, vedere: [Benvenuto in Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="e9647-269">Per informazioni specifiche su ognuno dei servizi elencati sopra, seguire i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9647-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="e9647-270">Exchange Online viene usato per le funzionalità di calendario e per l'archiviazione di messaggi peer-to-peer in Teams.</span><span class="sxs-lookup"><span data-stu-id="e9647-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="e9647-271">Per altre informazioni, vedere [Come interagiscono Exchange e Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9647-272">Per l'interoperabilità di Teams con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange come descritto in Configurare l'autenticazione OAuth tra le organizzazioni di Exchange ed [Exchange Online.](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="e9647-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="e9647-273">SharePoint viene usato per la condivisione di file nei canali, mentre /OneDrive for Business viene usato per la condivisione di file in una chat 1:1 o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e9647-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="e9647-274">Per altre informazioni, vedere [Come interagiscono SharePoint Online e OneDrive for Business con Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="e9647-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="e9647-275">[I gruppi di Microsoft 365 vengono](office-365-groups.md) usati per la creazione/gestione di team e canali.</span><span class="sxs-lookup"><span data-stu-id="e9647-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e9647-276">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e9647-276">Related topics</span></span>

[<span data-ttu-id="e9647-277">Poster di soluzioni di telefonia e architettura IT di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="e9647-278">Pianificare la connettività ibrida tra Skype for Business Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="e9647-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="e9647-279">Supportare lavoratori remoti con Teams</span><span class="sxs-lookup"><span data-stu-id="e9647-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="e9647-280">Lavorare in remoto con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9647-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
