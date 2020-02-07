---
title: Accedere a Microsoft teams con l'autenticazione moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Come accedere a Microsoft teams con l'autenticazione moderna.
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79f04161c070ff4818fdb2dfc212e5c3fc98b2b0
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845137"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="d2236-103">Accedere a Microsoft teams con l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="d2236-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="d2236-104">Microsoft teams USA l'autenticazione moderna per rendere semplice e sicura l'esperienza di accesso.</span><span class="sxs-lookup"><span data-stu-id="d2236-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="d2236-105">Per vedere come gli utenti possono accedere a teams, leggere [accedere a teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="d2236-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="d2236-106">Funzionamento dell'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="d2236-106">How modern authentication works</span></span>

<span data-ttu-id="d2236-107">L'autenticazione moderna è un processo che consente ai team di sapere che gli utenti hanno già immesso le proprie credenziali (come la posta elettronica e la password del lavoro) altrove e che non dovrebbero essere necessarie per immetterle di nuovo per avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="d2236-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="d2236-108">L'esperienza varia a seconda di un paio di fattori, ad esempio se gli utenti lavorano in Windows o in un Mac.</span><span class="sxs-lookup"><span data-stu-id="d2236-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="d2236-109">Inoltre, a seconda che l'organizzazione abbia abilitato l'autenticazione a singolo fattore o l'autenticazione a più fattori (l'autenticazione a più fattori implica in genere la verifica delle credenziali tramite un telefono, il codice univoco, l'immissione di un PIN o presentazione di un'identificazione personale).</span><span class="sxs-lookup"><span data-stu-id="d2236-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="d2236-110">Ecco una carrellata di ogni scenario di autenticazione moderno.</span><span class="sxs-lookup"><span data-stu-id="d2236-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="d2236-111">Utenti di Windows:</span><span class="sxs-lookup"><span data-stu-id="d2236-111">Windows users</span></span> 

- <span data-ttu-id="d2236-112">Se gli utenti hanno già effettuato l'accesso ad altre app di Office tramite il proprio account aziendale di Office 365, quando avviano i team vengono portati direttamente all'app.</span><span class="sxs-lookup"><span data-stu-id="d2236-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="d2236-113">Non è necessario che immettino le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="d2236-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="d2236-114">Se gli utenti non hanno eseguito l'accesso al proprio account di Office 365 Enterprise in qualsiasi altro punto, quando avviano teams, viene chiesto di specificare l'autenticazione a singolo fattore o a più fattori (SFA o AMF), a seconda di come l'organizzazione ha deciso che desidera processo da richiedere.</span><span class="sxs-lookup"><span data-stu-id="d2236-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="d2236-115">Se gli utenti hanno eseguito l'accesso a un computer collegato a un dominio, quando avviano teams, potrebbe essere richiesto di passare a un altro passaggio di autenticazione, a seconda che l'organizzazione abbia scelto di richiedere l'AMF o se il proprio computer richiede già l'accesso a Mae.</span><span class="sxs-lookup"><span data-stu-id="d2236-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="d2236-116">Se il proprio computer richiede già l'accesso a Mae, quando aprono teams, l'app viene avviata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d2236-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="d2236-117">Se gli utenti hanno eseguito l'accesso a un computer collegato a un dominio e non si vuole che il nome utente venga prepopolato nella schermata di accesso a teams, gli amministratori possono impostare il seguente registro di sistema di Windows per disattivare la prepopolazione del nome utente (UPN):</span><span class="sxs-lookup"><span data-stu-id="d2236-117">If users are signed in to a domain-joined computer and you don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="d2236-118">Computer \ HKEY_CURRENT_USER \Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="d2236-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="d2236-119">SkipUpnPrefill (REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="d2236-119">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="d2236-120">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="d2236-120">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2236-121">Per impostazione predefinita, non è necessario impostare una chiave del registro di sistema per disattivare i nomi utente che terminano con ". local" o ". Corp".</span><span class="sxs-lookup"><span data-stu-id="d2236-121">Skipping user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="d2236-122">Utenti Mac</span><span class="sxs-lookup"><span data-stu-id="d2236-122">Mac users</span></span> 

<span data-ttu-id="d2236-123">Quando gli utenti avviano teams, il loro computer non potrà tirare le proprie credenziali dall'account aziendale di Office 365 o da qualsiasi altra applicazione di Office.</span><span class="sxs-lookup"><span data-stu-id="d2236-123">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="d2236-124">Verrà invece visualizzato un messaggio che richiede l'AFS o l'AMF (a seconda delle impostazioni dell'organizzazione).</span><span class="sxs-lookup"><span data-stu-id="d2236-124">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="d2236-125">Quando gli utenti immettono le proprie credenziali, non saranno tenuti a fornire di nuovo.</span><span class="sxs-lookup"><span data-stu-id="d2236-125">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="d2236-126">Da quel momento in poi, teams avvia automaticamente ogni volta che sta lavorando nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="d2236-126">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="d2236-127">Commutazione di account dopo il completamento dell'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="d2236-127">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="d2236-128">Se gli utenti stanno lavorando a un computer collegato al dominio (ad esempio, se il tenant ha abilitato Kerberos), non possono cambiare gli account utente dopo aver completato l'autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="d2236-128">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="d2236-129">Se gli utenti non stanno lavorando a un computer collegato al dominio, possono cambiare account.</span><span class="sxs-lookup"><span data-stu-id="d2236-129">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="d2236-130">Disconnettersi da Microsoft teams dopo aver completato l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="d2236-130">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="d2236-131">Per disconnettersi da teams, gli utenti possono fare clic sull'immagine del profilo nella parte superiore dell'app e **quindi selezionare Disconnetti**. È anche possibile fare clic con il pulsante destro del mouse sull'icona dell'app nella barra delle applicazioni e quindi scegliere **Disconnetti**. Dopo aver disconnettersi da teams, è necessario immettere di nuovo le credenziali per avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="d2236-131">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="d2236-132">URL e intervalli di indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="d2236-132">URLs and IP address ranges</span></span>
<span data-ttu-id="d2236-133">I team richiedono la connettività a Internet.</span><span class="sxs-lookup"><span data-stu-id="d2236-133">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="d2236-134">Per informazioni sugli endpoint che devono essere raggiungibili per i clienti che usano team in piani di Office 365, governi e altre nubi, leggere le [indicazioni disponibili qui](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="d2236-134">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, please read the [guidance available here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="d2236-135">Oltre a questo, devi consentire anche l'accesso https://ssl.gstatic.com.</span><span class="sxs-lookup"><span data-stu-id="d2236-135">In addition to this, you'd need to also allow access to https://ssl.gstatic.com.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="d2236-136">Risoluzione dei problemi di autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="d2236-136">Troubleshooting modern authentication</span></span>

<span data-ttu-id="d2236-137">L'autenticazione moderna è disponibile per ogni organizzazione che usa teams, quindi se gli utenti non riescono a completare il processo, potrebbe esserci qualcosa che non va nel dominio o nell'account aziendale di Office 365 dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2236-137">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="d2236-138">Per altre informazioni, vedere [perché si verificano problemi di accesso a Microsoft teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="d2236-138">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

