---
title: Preparare la rete dell'organizzazione per Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Informazioni sulla preparazione della rete delL’organizzazione per Microsoft Teams, tra cui requisiti di rete, ottimizzazione della rete e requisiti di larghezza di banda.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420831"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="ff254-103">Preparare la rete dell'organizzazione per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff254-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="ff254-104">Requisiti di rete</span><span class="sxs-lookup"><span data-stu-id="ff254-104">Network requirements</span></span>

<span data-ttu-id="ff254-105">Se la rete è già [ottimizzata per Microsoft 365 o Office 365](/Office365/Enterprise/assessing-network-connectivity), è probabile che sia pronta per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff254-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="ff254-106">In ogni caso, e soprattutto se stai implementando rapidamente Teams come primo carico di lavoro di Microsoft 365 o Office 365 per supportare i **lavoratori remoti**, verifica quanto segue prima di iniziare a implementare Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="ff254-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="ff254-107">Le sedi della tua organizzazione hanno accesso a Internet (in modo che possano connettersi a Microsoft 365 o Office 365)?</span><span class="sxs-lookup"><span data-stu-id="ff254-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="ff254-108">Oltre al normale traffico Web, verifica di aver aperto le porte TCP e gli indirizzi IP elencati per Teams negli [gli URL e gli intervalli di indirizzi IP di Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="ff254-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ff254-109">Se è necessario attuare la federazione con Skype for Business, sia locale che online, è necessario configurare un record DNS aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="ff254-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="ff254-110">Record DNS</span><span class="sxs-lookup"><span data-stu-id="ff254-110">DNS record</span></span>  |<span data-ttu-id="ff254-111">Servizio</span><span class="sxs-lookup"><span data-stu-id="ff254-111">Service</span></span>  |<span data-ttu-id="ff254-112">Protocol</span><span class="sxs-lookup"><span data-stu-id="ff254-112">Protocol</span></span>  |<span data-ttu-id="ff254-113">Priority</span><span class="sxs-lookup"><span data-stu-id="ff254-113">Priority</span></span>  |<span data-ttu-id="ff254-114">Peso</span><span class="sxs-lookup"><span data-stu-id="ff254-114">Weight</span></span>  |<span data-ttu-id="ff254-115">Port</span><span class="sxs-lookup"><span data-stu-id="ff254-115">Port</span></span>  |<span data-ttu-id="ff254-116">Target</span><span class="sxs-lookup"><span data-stu-id="ff254-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="ff254-117">SRV</span><span class="sxs-lookup"><span data-stu-id="ff254-117">SRV</span></span>     |<span data-ttu-id="ff254-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ff254-118">sipfederationtls</span></span>     |<span data-ttu-id="ff254-119">TCP</span><span class="sxs-lookup"><span data-stu-id="ff254-119">TCP</span></span>     |<span data-ttu-id="ff254-120">100</span><span class="sxs-lookup"><span data-stu-id="ff254-120">100</span></span>     |<span data-ttu-id="ff254-121">1</span><span class="sxs-lookup"><span data-stu-id="ff254-121">1</span></span>     |<span data-ttu-id="ff254-122">5061</span><span class="sxs-lookup"><span data-stu-id="ff254-122">5061</span></span>     |<span data-ttu-id="ff254-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff254-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="ff254-124">Si dispone di un dominio verificato per Microsoft 365 o Office 365 (ad esempio, contoso.com)?</span><span class="sxs-lookup"><span data-stu-id="ff254-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="ff254-125">Se l’organizzazione non ha implementato Microsoft 365 o Office 365, consulta la [Guida introduttiva](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="ff254-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="ff254-126">Se l’organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, consulta le [Domande frequenti sui domini](/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="ff254-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="ff254-127">L’organizzazione ha implementato Exchange Online e Microsoft SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="ff254-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="ff254-128">Se l’organizzazione non ha implementato Exchange Online, vedi [Informazioni su come interagiscono Exchange e Microsoft Teams](exchange-teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="ff254-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="ff254-129">Se l’organizzazione non ha implementato SharePoint Online, vedi [Informazioni su come Microsoft SharePoint Online e Microsoft OneDrive for Business interagiscono con Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="ff254-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="ff254-130">Dopo aver verificato che i requisiti di rete siano soddisfatti, è possibile [implementare Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ff254-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="ff254-131">Nel caso di una grande azienda multinazionale o se si riscontrano limitazioni di rete, leggere le informazioni su come valutare e ottimizzare la rete per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff254-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff254-132">**Per gli istituti di istruzione**: se l’organizzazione è un istituto di istruzione e si utilizza un sistema informativo degli studenti (SIS), [implementare School Data Sync](/schooldatasync/) prima di implementare Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff254-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="ff254-133">**Esecuzione in locale di Skype for Business Server**: se l'organizzazione esegue Skype for Business Server (o Lync Server) in locale, è necessario [configurare Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) per sincronizzare la directory locale con Microsoft 365 o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff254-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="ff254-134">Procedura consigliata: monitorare la rete utilizzando Dashboard Qualità della chiamata e Analisi delle chiamate</span><span class="sxs-lookup"><span data-stu-id="ff254-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="ff254-135">Utilizzare [Dashboard Qualità della chiamata (DQC)](turning-on-and-using-call-quality-dashboard.md) per ottenere informazioni dettagliate sulla qualità delle chiamate e delle riunioni in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff254-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="ff254-136">DQC consente di ottimizzare la rete mantenendo sotto controllo la qualità, l’affidabilità e l’esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="ff254-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="ff254-137">DQC esamina la telemetria aggregata per un’intera organizzazione nella quale è possibile rilevare modelli generali che consentono di identificare i problemi e pianificare le correzioni.</span><span class="sxs-lookup"><span data-stu-id="ff254-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="ff254-138">Inoltre, DQC fornisce report dettagliati sulle metriche per informazioni dettagliate sulla qualità, l’affidabilità e l’esperienza utente complessive.</span><span class="sxs-lookup"><span data-stu-id="ff254-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="ff254-139">[Analisi delle chiamate](set-up-call-analytics.md) consente di indagare i problemi relativi alle chiamate e alle riunioni per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="ff254-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="ff254-140">Ottimizzazione della rete</span><span class="sxs-lookup"><span data-stu-id="ff254-140">Network optimization</span></span>

<span data-ttu-id="ff254-141">Le attività seguenti sono facoltative e non sono necessarie per l’implementazione di Microsoft Teams, specialmente nel caso di una piccola azienda che ha già implementato Microsoft 365 o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff254-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ff254-142">Attenersi a queste indicazioni per ottimizzare le prestazioni della rete e di Microsoft Teams o in caso di limitazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="ff254-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="ff254-143">È consigliabile eseguire un’ulteriore ottimizzazione della rete se:</span><span class="sxs-lookup"><span data-stu-id="ff254-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="ff254-144">L’esecuzione di Microsoft Teams è lenta (ad esempio la larghezza di banda è insufficiente)</span><span class="sxs-lookup"><span data-stu-id="ff254-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="ff254-145">Le chiamate si interrompono (probabilmente a causa di blocchi del firewall o del proxy)</span><span class="sxs-lookup"><span data-stu-id="ff254-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="ff254-146">Si riscontrano interferenze o distorsioni durante le chiamate oppure riproduzioni audio robotiche (a causa di instabilità o perdita di pacchetti)</span><span class="sxs-lookup"><span data-stu-id="ff254-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="ff254-147">Per informazioni dettagliate sull’ottimizzazione della rete, incluse indicazioni per l’identificazione e la correzione di eventuali problemi di rete, consulta [Principi di connettività di rete di Microsoft 365 e Microsoft Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span><span class="sxs-lookup"><span data-stu-id="ff254-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ff254-148">Attività di ottimizzazione della rete</span><span class="sxs-lookup"><span data-stu-id="ff254-148">Network optimization task</span></span></th>
<th><span data-ttu-id="ff254-149">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ff254-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ff254-150">Network Planner</span><span class="sxs-lookup"><span data-stu-id="ff254-150">Network planner</span></span></td>
<td><p><span data-ttu-id="ff254-151">Per ricevere assistenza nella valutazione della rete, nonché nei calcoli della larghezza di banda e nei requisiti di rete per le varie sedi dell’organizzazione, consulta lo strumento <a href="/microsoftteams/network-planner">Network Planner</a> nelll’<a href="https://admin.teams.microsoft.com">Interfaccia di amministrazione di Microsoft Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ff254-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="ff254-152">Quando si specificano i dettagli della rete e l'uso di Teams, Network Planner calcola i requisiti di rete per la distribuzione di Teams e Cloud Voice nei luoghi fisici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ff254-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="ff254-153">Per uno scenario di esempio, vedere <a href="/microsoftteams/tutorial-network-planner-example">Utilizzo di Network Planner, scenario di esempio</a>.</span><span class="sxs-lookup"><span data-stu-id="ff254-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ff254-154">Assistente per Teams</span><span class="sxs-lookup"><span data-stu-id="ff254-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="ff254-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor per Teams</a> fa parte dell’<a href="https://admin.teams.microsoft.com">interfaccia di amministrazione di Microsoft Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ff254-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="ff254-156">Valuta l'ambiente di Microsoft 365 o Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams.</span><span class="sxs-lookup"><span data-stu-id="ff254-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ff254-157">Risoluzione del nome esterno</span><span class="sxs-lookup"><span data-stu-id="ff254-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="ff254-158">Assicurarsi che tutti i computer che eseguono il client Teams possano risolvere query DNS esterne per rilevare i servizi forniti da Microsoft 365 o Microsoft Office 365 e che il firewall non impedisca l’accesso.</span><span class="sxs-lookup"><span data-stu-id="ff254-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="ff254-159">Per informazioni sulla configurazione delle porte del firewall, vai a <a href="/microsoftteams/office-365-urls-ip-address-ranges">URL e intervalli IP di Microsoft 365 e Microsoft Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="ff254-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ff254-160">Salvataggio permanente della sessione</span><span class="sxs-lookup"><span data-stu-id="ff254-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="ff254-161">Verificare che il firewall non modifichi gli indirizzi NAT (Network Address Translation) o le porte mappate per UDP.</span><span class="sxs-lookup"><span data-stu-id="ff254-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="ff254-162">Convalidare le dimensioni del pool NAT</span><span class="sxs-lookup"><span data-stu-id="ff254-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="ff254-163">Convalidare le dimensioni del pool NAT necessarie per la connettività utente.</span><span class="sxs-lookup"><span data-stu-id="ff254-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="ff254-164">Quando più utenti e dispositivi accedono a Microsoft 365 o Microsoft Office 365 utilizzando <a href="/office365/enterprise/nat-support-with-office-365">NAT (Network Address Translation) o PAT (Port Address Translation)</a>, è necessario assicurarsi che i dispositivi nascosti dietro ogni indirizzo IP instradabile pubblicamente non superino il numero supportato.</span><span class="sxs-lookup"><span data-stu-id="ff254-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="ff254-165">Assicurarsi che ai pool NAT siano assegnati indirizzi IP pubblici adeguati per prevenire l'esaurimento della porta.</span><span class="sxs-lookup"><span data-stu-id="ff254-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="ff254-166">L’esaurimento delle porte non consente agli utenti interni e ai dispositivi di connettersi al servizio Microsoft 365 o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff254-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ff254-167">Routing ai data center Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff254-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="ff254-168"><a href="/office365/enterprise/client-connectivity">Implementare il routing ottimizzato ai data center Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="ff254-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="ff254-169">Identificare le posizioni che possono utilizzare i punti di uscita locali per connettersi alla rete Microsoft nel modo più efficiente possibile.</span><span class="sxs-lookup"><span data-stu-id="ff254-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ff254-170">Indicazioni per il rilevamento e la prevenzione delle intrusioni</span><span class="sxs-lookup"><span data-stu-id="ff254-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="ff254-171">Se l’ambiente ha implementato un <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Rilevamento intrusioni</a> o un sistema di prevenzione (IDS/IPS) per un livello di sicurezza supplementare per le connessioni in uscita, assicurarsi di autorizzare tutti gli URL di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff254-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ff254-172">Configurare split tunneling per VPN</span><span class="sxs-lookup"><span data-stu-id="ff254-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="ff254-173">È consigliabile specificare un percorso alternativo per il traffico di Microsoft Teams che ignori la rete privata virtuale (VPN), comunemente nota come <a href="/windows/security/identity-protection/vpn/vpn-routing">Split tunnelling per VPN</a>.</span><span class="sxs-lookup"><span data-stu-id="ff254-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="ff254-174">Lo split tunnelling per VPN consente di inviare il traffico di Microsoft 365 o Office 365 non alla VPN ma direttamente a Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff254-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ff254-175">Ignorare la VPN influisce positivamente sulla qualità di Microsoft Teams e riduce il carico nei dispositivi VPN e nella rete dell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ff254-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="ff254-176">Per implementare lo split tunneling per VPN, contatta il fornitore VPN.</span><span class="sxs-lookup"><span data-stu-id="ff254-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="ff254-177">Altri motivi per cui è consigliabile ignorare la VPN:</span><span class="sxs-lookup"><span data-stu-id="ff254-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="ff254-178">Le VPN in genere non sono progettate o configurate per supportare il traffico multimediale in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ff254-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="ff254-179">È inoltre possibile che alcune VPN non supportino l’UDP (necessario per Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="ff254-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="ff254-180">Le VPN introducono anche un livello di crittografia aggiuntivo al traffico multimediale già crittografato.</span><span class="sxs-lookup"><span data-stu-id="ff254-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="ff254-181">La connettività a Microsoft Teams potrebbe non essere efficiente a causa dell’hairpinning del traffico tramite un dispositivo VPN.</span><span class="sxs-lookup"><span data-stu-id="ff254-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ff254-182">Implementare QoS</span><span class="sxs-lookup"><span data-stu-id="ff254-182">Implement QoS</span></span></td>
<td><span data-ttu-id="ff254-183"><a href="/microsoftteams/qos-in-teams">Utilizzare il servizio QoS (Quality of Service)</a> per configurare la priorità dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="ff254-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="ff254-184">In tal modo è possibile migliorare la qualità delle chiamate in Microsoft Teams nonché monitorare e risolvere i problemi relativi alla qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="ff254-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="ff254-185">È necessario implementare QoS in tutti i segmenti di una rete gestita.</span><span class="sxs-lookup"><span data-stu-id="ff254-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="ff254-186">Anche se per la larghezza di banda è stato eseguito un adeguato provisioning della rete, QoS consente la mitigazione dei rischi in caso di eventi di rete imprevisti.</span><span class="sxs-lookup"><span data-stu-id="ff254-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="ff254-187">QoS assegna la priorità al traffico vocale in modo da impedire che eventi imprevisti influiscano negativamente sulla qualità.</span><span class="sxs-lookup"><span data-stu-id="ff254-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ff254-188">Ottimizzazione WiFi</span><span class="sxs-lookup"><span data-stu-id="ff254-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="ff254-189">Proprio come la VPN, le reti WiFi non sono necessariamente progettate o configurate per supportare il traffico multimediale in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ff254-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="ff254-190">La pianificazione o l'ottimizzazione di una rete WiFi per supportare Microsoft Teams è una considerazione importante per una distribuzione di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="ff254-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="ff254-191">Prendere in considerazione questi fattori:</span><span class="sxs-lookup"><span data-stu-id="ff254-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff254-192">Implementare QoS o Wi-Fi Multimedia (WMM) per garantire che il traffico multimediale abbia la priorità appropriata sulle reti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ff254-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="ff254-193">Pianificare e ottimizzare le bande Wi-Fi e il posizionamento del punto di accesso.</span><span class="sxs-lookup"><span data-stu-id="ff254-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="ff254-194">L’intervallo a 2,4 GHz potrebbe offrire un’esperienza adeguata a seconda del posizionamento del punto di accesso. Tuttavia, i punti di accesso sono spesso influenzati da altri dispositivi di consumo che operano nell’intervallo.</span><span class="sxs-lookup"><span data-stu-id="ff254-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="ff254-195">L'intervallo a 5 GHz è più adatto al traffico multimediale in tempo reale grazie al fitto intervallo ma richiede più punti di accesso per ottenere una copertura sufficiente.</span><span class="sxs-lookup"><span data-stu-id="ff254-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="ff254-196">Gli endpoint devono inoltre supportare tale intervallo ed essere configurati per sfruttare tali bande di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="ff254-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="ff254-197">Se si utilizzano reti WiFi dual band, prendere in considerazione l’implementazione del band steering.</span><span class="sxs-lookup"><span data-stu-id="ff254-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="ff254-198"><em>Il band steering</em> è una tecnica implementata dai fornitori di reti WiFi per influenzare i client dual band a utilizzare l'intervallo a 5 GHz.</span><span class="sxs-lookup"><span data-stu-id="ff254-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="ff254-199">Quando i punti di accesso dello stesso canale sono troppo vicini tra loro, possono causare la sovrapposizione del segnale e competere involontariamente, causando una brutta esperienza per l'utente.</span><span class="sxs-lookup"><span data-stu-id="ff254-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="ff254-200">Assicurarsi che i punti di accesso che si trovano uno accanto all'altro siano su canali che non si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="ff254-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="ff254-201">Ogni fornitore wireless ha le proprie raccomandazioni per l'implementazione della propria soluzione wireless.</span><span class="sxs-lookup"><span data-stu-id="ff254-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="ff254-202">Per indicazioni specifiche, contattare il fornitore della rete WiFi.</span><span class="sxs-lookup"><span data-stu-id="ff254-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="ff254-203">Requisiti relativi alla larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="ff254-203">Bandwidth requirements</span></span>

<span data-ttu-id="ff254-204">Microsoft Teams è progettato per offrire esperienze audio, video e di condivisione contenuti eccezionali, a prescindere dalle condizioni di rete.</span><span class="sxs-lookup"><span data-stu-id="ff254-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="ff254-205">Tuttavia, se la larghezza di banda è insufficiente, Microsoft Teams assegna la priorità alla qualità audio sulla qualità video.</span><span class="sxs-lookup"><span data-stu-id="ff254-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="ff254-206">Se la larghezza di banda non è limitata, Microsoft Teams ottimizza la qualità multimediale, audio di alta fedeltà, inclusa una risoluzione video massima di 1080p, fino a 30fps (fotogrammi al secondo) per video e contenuto.</span><span class="sxs-lookup"><span data-stu-id="ff254-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="ff254-207">Questa tabella descrive le modalità di utilizzo della larghezza di banda da parte di Teams.</span><span class="sxs-lookup"><span data-stu-id="ff254-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="ff254-208">Teams fa un utilizzo moderato della larghezza di banda ed è in grado di garantire una qualità video ad alta definizione in meno di 1,5 Mbps.</span><span class="sxs-lookup"><span data-stu-id="ff254-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="ff254-209">Il consumo effettivo della larghezza di banda in ogni chiamata audio/video o riunione varia in base a diversi fattori, ad esempio il layout video, la risoluzione video e i fotogrammi video al secondo.</span><span class="sxs-lookup"><span data-stu-id="ff254-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="ff254-210">Quando sarà disponibile una maggiore larghezza di banda, la qualità e l'utilizzo aumenteranno per offrire la migliore esperienza.</span><span class="sxs-lookup"><span data-stu-id="ff254-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="ff254-211">**Modalità**</span><span class="sxs-lookup"><span data-stu-id="ff254-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="ff254-212">**Requisiti di larghezza di banda (bitrate KB/s su/giù)**</span><span class="sxs-lookup"><span data-stu-id="ff254-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ff254-213">**Minimo**</span><span class="sxs-lookup"><span data-stu-id="ff254-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ff254-214">**Consigliata**</span><span class="sxs-lookup"><span data-stu-id="ff254-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ff254-215">**Prestazioni ottimali**</span><span class="sxs-lookup"><span data-stu-id="ff254-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="ff254-216">**Audio**</span><span class="sxs-lookup"><span data-stu-id="ff254-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-217">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="ff254-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-218">10/10</span><span class="sxs-lookup"><span data-stu-id="ff254-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-219">58/58</span><span class="sxs-lookup"><span data-stu-id="ff254-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-220">76/76</span><span class="sxs-lookup"><span data-stu-id="ff254-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-221">Riunioni</span><span class="sxs-lookup"><span data-stu-id="ff254-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-222">10/10</span><span class="sxs-lookup"><span data-stu-id="ff254-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-223">58/58</span><span class="sxs-lookup"><span data-stu-id="ff254-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-224">76/76</span><span class="sxs-lookup"><span data-stu-id="ff254-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="ff254-225">**Video**</span><span class="sxs-lookup"><span data-stu-id="ff254-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-226">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="ff254-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-227">150/150</span><span class="sxs-lookup"><span data-stu-id="ff254-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-228">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="ff254-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-229">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="ff254-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-230">Riunioni</span><span class="sxs-lookup"><span data-stu-id="ff254-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-231">150/200</span><span class="sxs-lookup"><span data-stu-id="ff254-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-232">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="ff254-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-233">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="ff254-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="ff254-234">**Condivisione dello schermo.**</span><span class="sxs-lookup"><span data-stu-id="ff254-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-235">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="ff254-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-236">200/200</span><span class="sxs-lookup"><span data-stu-id="ff254-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-237">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="ff254-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-238">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="ff254-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-239">Riunioni</span><span class="sxs-lookup"><span data-stu-id="ff254-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-240">250/250</span><span class="sxs-lookup"><span data-stu-id="ff254-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-241">2,500/2,500</span><span class="sxs-lookup"><span data-stu-id="ff254-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-242">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="ff254-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="ff254-243">**Modalità Insieme**</span><span class="sxs-lookup"><span data-stu-id="ff254-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-244">Uno a uno</span><span class="sxs-lookup"><span data-stu-id="ff254-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-245">N/D</span><span class="sxs-lookup"><span data-stu-id="ff254-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-246">N/D</span><span class="sxs-lookup"><span data-stu-id="ff254-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-247">N/D</span><span class="sxs-lookup"><span data-stu-id="ff254-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="ff254-248">Riunioni</span><span class="sxs-lookup"><span data-stu-id="ff254-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-249">1,000/1,500</span><span class="sxs-lookup"><span data-stu-id="ff254-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-250">1,500/2,500</span><span class="sxs-lookup"><span data-stu-id="ff254-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="ff254-251">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="ff254-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="ff254-252">I requisiti **minimi**, **consigliati** e **le prestazioni migliori** della larghezza di banda sono basati sull'utilizzo per endpoint.</span><span class="sxs-lookup"><span data-stu-id="ff254-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="ff254-253">In genere, è presente un endpoint per utente, come un computer o un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="ff254-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="ff254-254">Tuttavia, se un utente partecipa a una riunione di Teams in *sia* un computer *che* un dispositivo mobile, a tale utente vengono associati due endpoint.</span><span class="sxs-lookup"><span data-stu-id="ff254-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="ff254-255">I requisiti **minimi** della larghezza di banda per le videochiamate sono fino a una risoluzione di 240p, la frequenza dei fotogrammi del contenuto di condivisione dello schermo adattiva da 1,875 a 7,5 fps e i video in modalità Insieme/Raccolta grande fino a una risoluzione di 540p.</span><span class="sxs-lookup"><span data-stu-id="ff254-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="ff254-256">I requisiti **consigliati** per la larghezza di banda per le videochiamate sono fino a 1080p di risoluzione<sup>\*</sup>, frequenza dei fotogrammi del contenuto di condivisione dello schermo adattivi da 7,5 a 30 fps e video in modalità Insieme/Raccolta grande fino a una risoluzione di 1080p<sup>\*</sup>.</span><span class="sxs-lookup"><span data-stu-id="ff254-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="ff254-257">**Prestazioni ottimali** Guidance consente una maggiore fedeltà di video per riunioni con partecipanti di grandi dimensioni, ambienti con perdita elevata e contenuti di movimento più elevati con frequenze dei fotogrammi del contenuto di condivisione dello schermo adattive da 15 a 30 fps.</span><span class="sxs-lookup"><span data-stu-id="ff254-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="ff254-258"><sup>\*</sup>È prevista una qualità fino a 1080p, ma a seconda delle condizioni della rete, la risoluzione e la qualità del video verranno ottimizzate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="ff254-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="ff254-259">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ff254-259">Related Topics</span></span>

[<span data-ttu-id="ff254-260">Principi di connettività di rete di Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="ff254-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="ff254-261">Endpoint in tutto il mondo: Skype for Business Online e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff254-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="ff254-262">Server proxy per Teams</span><span class="sxs-lookup"><span data-stu-id="ff254-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="ff254-263">Elementi multimediali di Teams: ciò che rende le riunioni così semplici</span><span class="sxs-lookup"><span data-stu-id="ff254-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="ff254-264">Elementi multimediali di Teams: un approfondimento sui flussi multimediali</span><span class="sxs-lookup"><span data-stu-id="ff254-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="ff254-265">Modelli di identità e autenticazione in Teams</span><span class="sxs-lookup"><span data-stu-id="ff254-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="ff254-266">Come implementare Teams</span><span class="sxs-lookup"><span data-stu-id="ff254-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="ff254-267">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="ff254-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
