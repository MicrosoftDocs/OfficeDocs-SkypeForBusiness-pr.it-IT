---
title: Guida alla sicurezza di Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Indicazioni per l'uso sicuro di Microsoft Teams con un computer condiviso sul luogo di lavoro.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45497c824cfc20644a59e35f7812b17058f61c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117054"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="1121e-103">Usare Microsoft teams in modo sicuro sui computer condivisi</span><span class="sxs-lookup"><span data-stu-id="1121e-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="1121e-104">Se possibile, *si raccomanda* alle organizzazioni di adottare un approccio Zero Trust per i dispositivi client, usando le funzionalità di gestione dei dispositivi, i controlli dell'integrità dei dispositivi, l'applicazione dei criteri, la crittografia a livello dei dispositivi e altre funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1121e-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Immagine dell'architettura Zero Trust che mostra la verifica esplicita, il principio del privilegio minimo e la presunzione della violazione, ossia i principi fondamentali dell'approccio Zero Trust, nei cerchi blu.":::

<span data-ttu-id="1121e-106">Gli amministratori possono creare ambienti molto sicuri *concentrandosi* sulla verifica, il principio del privilegio minimo e la presunzione della violazione: sono standard che comportano azioni che riducono al minimo i rischi per utenti e dati. </span><span class="sxs-lookup"><span data-stu-id="1121e-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="1121e-107">Per un'analisi più approfondita dell'architettura Zero Trust, vedere [questi video](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span><span class="sxs-lookup"><span data-stu-id="1121e-107">For a deeper examination of Zero Trust principles, see [these videos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="1121e-108">Suggerimenti per usare Microsoft Teams in modo sicuro con un computer condiviso</span><span class="sxs-lookup"><span data-stu-id="1121e-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="1121e-109">Pur riconoscendo che potrebbe non essere possibile o praticabile in tutti gli scenari, è comunque importante che gli amministratori di sicurezza seguano le indicazioni per usare Teams con un computer condiviso o un dispositivo non gestito nel migliore dei modi.</span><span class="sxs-lookup"><span data-stu-id="1121e-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="1121e-110">Si consiglia di sviluppare piani per rispettare le linee guida nel modo più rigoroso possibile.</span><span class="sxs-lookup"><span data-stu-id="1121e-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="1121e-111">Usare le funzionalità di sicurezza della piattaforma del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1121e-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="1121e-112">Assicurarsi che il sistema operativo sia configurato in modo da installare gli aggiornamenti automatici distribuiti dal provider del sistema operativo (per i sistemi Microsoft, ciò può essere fatto tramite [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span><span class="sxs-lookup"><span data-stu-id="1121e-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    1. <span data-ttu-id="1121e-113">Assicurarsi che le funzionalità crittografiche del dispositivo, come [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview), siano abilitate, e che la chiave usata per accedere al dispositivo sia protetta.</span><span class="sxs-lookup"><span data-stu-id="1121e-113">Ensure that any device encryption capabilities such as [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured.</span></span>  <span data-ttu-id="1121e-114">Si noti che la maggior parte dei [**dispositivi Windows 10 moderni supporta BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)</span><span class="sxs-lookup"><span data-stu-id="1121e-114">Note that most modern [**Windows 10 devices support bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span></span> 
    1. <span data-ttu-id="1121e-115">Usare le funzionalità antivirus, come quelle offerte da [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), sul proprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1121e-115">Use anti-virus capabilities such as those offered by [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="1121e-116">L'uso di [account utente separati](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) per ogni utente del sistema è fortemente raccomandato.</span><span class="sxs-lookup"><span data-stu-id="1121e-116">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="1121e-117">*Non* concedere né usare i privilegi di amministrazione per funzioni non amministrative (come navigare su internet, eseguire Teams, ecc.).</span><span class="sxs-lookup"><span data-stu-id="1121e-117">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

<span data-ttu-id="1121e-118">Se non è possibile soddisfare le indicazioni precedenti, è consigliabile usare altre procedure consigliate per la sicurezza del browser:</span><span class="sxs-lookup"><span data-stu-id="1121e-118">If the above guidance cannot be met, we recommend making use of additional browser security best practices:</span></span>

1. <span data-ttu-id="1121e-119">Sfruttare le funzionalità di sicurezza del browser.</span><span class="sxs-lookup"><span data-stu-id="1121e-119">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="1121e-120">Usare le sessioni di navigazione privata per minimizzare i dati e la cronologia che persistono sul disco.</span><span class="sxs-lookup"><span data-stu-id="1121e-120">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="1121e-121">Per esempio, usare la [navigazione inPrivate di Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [la navigazione in incognito di Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), o le funzionalità di navigazione privata del browser in uso.</span><span class="sxs-lookup"><span data-stu-id="1121e-121">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="1121e-122">Si raccomanda di modificare il sistema in modo che la navigazione privata sia attivata per *impostazione predefinita*.</span><span class="sxs-lookup"><span data-stu-id="1121e-122">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

2. <span data-ttu-id="1121e-123">Individuare e usare [l'app web di Teams](https://teams.microsoft.com) (indicata a volte come il *client web*), invece del client scaricabile di Teams.</span><span class="sxs-lookup"><span data-stu-id="1121e-123">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

3. <span data-ttu-id="1121e-124">Dopo aver finito di usare il sistema condiviso, è necessario:</span><span class="sxs-lookup"><span data-stu-id="1121e-124">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="1121e-125">[Disconnettersi da Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span><span class="sxs-lookup"><span data-stu-id="1121e-125">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="1121e-126">Chiudere tutte le schede e le finestre del browser.</span><span class="sxs-lookup"><span data-stu-id="1121e-126">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="1121e-127">Disconnettersi dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1121e-127">Sign out of the device.</span></span>

<span data-ttu-id="1121e-128">Gli elementi precedenti non sono un elenco completo delle migliori pratiche o dei controlli di sicurezza relativi a tutti i casi, e potrebbe essere possibile compiere altre azioni nel proprio ambiente (ad esempio, gli amministratori di sicurezza possono scegliere di usare i collegamenti e gli allegati sicuri di Teams se usano [Office 365 ATP piano 1 o 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span><span class="sxs-lookup"><span data-stu-id="1121e-128">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="1121e-129">Tuttavia, questi passaggi sono un punto di partenza per creare indicazioni per l'uso di Teams con dispositivi condivisi.</span><span class="sxs-lookup"><span data-stu-id="1121e-129">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="1121e-130">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="1121e-130">More Information</span></span>

[<span data-ttu-id="1121e-131">Bitlocker in Gestione configurazione</span><span class="sxs-lookup"><span data-stu-id="1121e-131">Bitlocker in Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="1121e-132">BitLocker per Windows 10 in Intune</span><span class="sxs-lookup"><span data-stu-id="1121e-132">Bitlocker for Windows 10 in Intune</span></span>](/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="1121e-133">Sicurezza degli endpoint in Intune</span><span class="sxs-lookup"><span data-stu-id="1121e-133">Endpoint security in Intune</span></span>](/mem/intune/protect/endpoint-security)

<span data-ttu-id="1121e-134">[Abilitare](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender in Sicurezza di Windows ed [eseguire le scansioni](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="1121e-134">[Enable](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="1121e-135">Articolo su Centro sicurezza di Microsoft Defender </span><span class="sxs-lookup"><span data-stu-id="1121e-135">Microsoft Defender security center article</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="1121e-136">Client web e app web di Teams</span><span class="sxs-lookup"><span data-stu-id="1121e-136">Teams web client/teams web app</span></span>](./get-clients.md#web-client)

[<span data-ttu-id="1121e-137">Sicurezza e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1121e-137">Security and Microsoft Teams</span></span>](./teams-security-guide.md)