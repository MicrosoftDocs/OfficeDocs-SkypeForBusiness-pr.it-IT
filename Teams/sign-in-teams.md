---
title: Accedere a Microsoft Teams con l'autenticazione moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Come accedere a Microsoft Teams usando l'autenticazione moderna. Include come ignorare l'aggiunta automatica del nome utente UPN quando gli utenti accedono.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c541371b78bcd9119abe7a11523d0d2f7b5eda7c
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978368"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="2e3cf-104">Accedere a Microsoft Teams con l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="2e3cf-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="2e3cf-105">Microsoft Teams usa l'autenticazione moderna per mantenere l'esperienza di accesso più semplice e sicura.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-105">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="2e3cf-106">Per scoprire in che modo gli utenti accedono a Teams, leggere [Accedere a Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="2e3cf-106">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="2e3cf-107">Funzionamento dell'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="2e3cf-107">How modern authentication works</span></span>

<span data-ttu-id="2e3cf-108">L'autenticazione moderna è un processo che informa Teams che gli utenti hanno già immesso le loro credenziali, come l'indirizzo di posta elettronica aziendale e la password, e che non è necessario immetterle di nuovo per avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-108">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="2e3cf-109">L'esperienza varia in base a un paio di fattori, ad esempio se gli utenti lavorano in Windows o in Mac.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-109">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="2e3cf-110">Inoltre, varia a seconda che l'organizzazione abbia abilitato l'autenticazione a un fattore o l'autenticazione a più fattori. L'autenticazione a più fattori implica in genere la verifica delle credenziali tramite un telefono, l'inserimento di un codice univoco, l'immissione di un PIN o la presentazione di un'identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-110">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="2e3cf-111">Ecco una panoramica di ogni scenario di autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-111">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="2e3cf-112">Utenti di Windows</span><span class="sxs-lookup"><span data-stu-id="2e3cf-112">Windows users</span></span> 

- <span data-ttu-id="2e3cf-113">Se gli utenti hanno già eseguito l'accesso ad altre app di Office tramite il loro account di Office 365 Enterprise, all'avvio di Teams vengono portati direttamente all'app.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-113">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="2e3cf-114">Non è necessario immettere le credenziali.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-114">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="2e3cf-115">Se gli utenti non hanno eseguito l'accesso al proprio account di Office 365 Enterprise, all'avvio di Teams viene loro chiesto di fornire l'autenticazione a uno o a più fattori (SFA o MFA), in base alla scelta dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-115">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="2e3cf-116">Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio, all'avvio di Teams potrebbero dover eseguire un ulteriore passaggio di autenticazione, a seconda che l'organizzazione abbia scelto di richiedere l'autenticazione MFA o che il computer in uso richieda già l'autenticazione MFA per accedere.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-116">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="2e3cf-117">Se il computer in uso richiede già l'autenticazione MFA per accedere, aprendo Teams l'app viene avviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-117">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="2e3cf-118">Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio e non si vuole che il nome utente sia precompilato nella schermata di accesso a Teams, gli amministratori possono impostare la chiave seguente del Registro di sistema di Windows per disattivare il prepopolamento del nome utente (UPN):</span><span class="sxs-lookup"><span data-stu-id="2e3cf-118">If users are signed in to a domain-joined computer and you don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="2e3cf-119">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="2e3cf-119">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="2e3cf-120">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="2e3cf-120">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="2e3cf-121">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="2e3cf-121">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e3cf-122">La precompilazione del nome utente per i nomi che terminano in ".local" o ".corp" è disattivata per impostazione predefinita, non è necessario impostare una chiave del Registro di sistema allo scopo.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-122">Skipping user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="2e3cf-123">Utenti Mac</span><span class="sxs-lookup"><span data-stu-id="2e3cf-123">Mac users</span></span> 

<span data-ttu-id="2e3cf-124">Quando gli utenti avviano Teams, il computer non sarà in grado di recuperare le credenziali dall'account di Office 365 Enterprise o da qualsiasi altra applicazione di Office.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-124">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="2e3cf-125">Verrà visualizzato un messaggio che chiede l'autenticazione SFA o MFA, in base alle impostazioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-125">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="2e3cf-126">Una volta immesse le credenziali, gli utenti non dovranno fornirle di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-126">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="2e3cf-127">Da quel momento in poi, Teams si avvierà automaticamente ogni volta che lavorano con lo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-127">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="2e3cf-128">Cambiare account dopo aver completato l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="2e3cf-128">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="2e3cf-129">Se gli utenti stanno lavorando su un computer aggiunto a un dominio, ad esempio se il tenant ha abilitato Kerberos, non possono cambiare account utente dopo aver completato l'autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-129">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="2e3cf-130">Se gli utenti non stanno lavorando su un computer aggiunto a un dominio, possono cambiare account.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-130">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="2e3cf-131">Disconnessione da Teams dopo aver completato l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="2e3cf-131">Signing out of Teams after completing modern authentication</span></span>
<span data-ttu-id="2e3cf-132">Per disconnettersi da Teams, gli utenti possono fare clic sull'immagine del profilo nella parte superiore dell'app e quindi selezionare **Disconnetti**. Possono anche fare clic con il pulsante destro del mouse sull'icona dell'app nella barra delle applicazioni e scegliere **Disconnetti**. Dopo la disconnessione da Teams, per avviare l'app è necessario immettere di nuovo le credenziali.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-132">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="2e3cf-133">URL e intervalli di indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="2e3cf-133">URLs and IP address ranges</span></span>
<span data-ttu-id="2e3cf-134">Teams richiede la connettività a Internet.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-134">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="2e3cf-135">Per informazioni sugli endpoint che devono essere raggiungibili per i clienti che usano Teams nei piani di Office 365, nel cloud per enti pubblici e in altri cloud, vedere [URL e intervalli di indirizzi IP per Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="2e3cf-135">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2e3cf-136">Attualmente Teams richiede l'accesso sulla porta TCP 443 al servizio Google ssl.gstatic.com (https://ssl.gstatic.com) per tutti gli utenti. Questo avviene anche se non si usa Gstatic.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-136">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (https://ssl.gstatic.com) for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="2e3cf-137">Teams rimuoverà il requisito presto (all'inizio del 2020) e questo articolo verrà aggiornato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-137">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="2e3cf-138">Risoluzione dei problemi relativi all'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="2e3cf-138">Troubleshooting modern authentication</span></span>

<span data-ttu-id="2e3cf-139">L'autenticazione moderna è disponibile per tutte le organizzazioni che usano Teams, quindi se gli utenti non riescono a completare il processo potrebbe esserci un problema con il dominio o con l'account di Office 365 Enterprise dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2e3cf-139">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="2e3cf-140">Per altre informazioni, vedere [Perché non riesco ad accedere a Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="2e3cf-140">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

