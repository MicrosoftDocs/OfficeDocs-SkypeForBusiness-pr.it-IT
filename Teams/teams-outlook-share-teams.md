---
title: Condividere con Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Informazioni sulla caratteristica Condividi in Teams, che consente agli utenti di condividere messaggi di posta elettronica e allegati di posta elettronica da Outlook a qualsiasi chat o canale in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098222"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="0f4ce-103">Condividere in Teams da Outlook</span><span class="sxs-lookup"><span data-stu-id="0f4ce-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="0f4ce-104">Condividi a Teams da Outlook (Condividi a Teams) consente agli utenti di condividere messaggi di posta elettronica, inclusi gli allegati, da Outlook a qualsiasi chat o canale in Teams.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="0f4ce-105">Outlook componente aggiuntivo per la condivisione Teams</span><span class="sxs-lookup"><span data-stu-id="0f4ce-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="0f4ce-106">La caratteristica Condividi Teams richiede un componente aggiuntivo per Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="0f4ce-107">Questo componente aggiuntivo viene installato automaticamente ogni volta che un utente accede all'app Web Teams o al client desktop Teams client desktop.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="0f4ce-108">Verificare che i componenti aggiuntivi per Outlook [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e regole di accesso client [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) per assicurarsi che i componenti aggiuntivi per Outlook funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="0f4ce-109">Inoltre, la disabilitazione delle esperienze connesse può impedire il corretto funzionamento dei componenti aggiuntivi Outlook per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="0f4ce-110">Vedere [Esperienze connesse in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="0f4ce-111">Condividi con Teams usa lo stesso meccanismo di trasporto di quando un utente invia un canale tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="0f4ce-112">Per la condivisione nelle chat, i messaggi di posta elettronica (inclusi gli allegati di posta elettronica) vengono copiati nella cartella del mittente OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="0f4ce-113">Per la condivisione su canali, i messaggi di posta elettronica e gli allegati vengono copiati nella cartella **Messaggi di** posta elettronica in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="0f4ce-114">Il componente aggiuntivo Outlook per la condivisione su Teams usa il set di requisiti 1.7, come descritto nella documentazione dei componenti aggiuntivi di [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)che include dettagli sui componenti aggiuntivi Outlook, i requisiti di ambiente per i componenti aggiuntivi Outlook e i client Outlook specifici supportati con il set di requisiti 1.7.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="0f4ce-115">Abilitazione o disabilitazione della condivisione Teams</span><span class="sxs-lookup"><span data-stu-id="0f4ce-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="0f4ce-116">Il Outlook per la condivisione a Teams può essere disabilitato o abilitato in modo selettivo in base all'utente usando i cmdlet di PowerShell seguenti.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="0f4ce-117">La disabilitazione del componente aggiuntivo è possibile solo dopo l'installazione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="0f4ce-118">Se si vuole applicare la disabilitazione per tutti gli utenti del tenant, eseguire periodicamente uno script.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="0f4ce-119">Per disabilitare il componente aggiuntivo per Outlook usato da Share to Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="0f4ce-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="0f4ce-120">Per abilitare il componente aggiuntivo per i Outlook usati da Share per Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="0f4ce-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="0f4ce-121">Browser e Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="0f4ce-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="0f4ce-122">Share to Teams, sia in Outlook web che nei client desktop Outlook desktop, si basa su un browser WebView.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="0f4ce-123">Vedere [Browser usati Office componenti aggiuntivi per](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) informazioni dettagliate sui client che usano i browser specifici.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0f4ce-124">La condivisione Teams richiede che i cookie di terze parti e l'accesso all'archiviazione locale siano abilitati per i browser degli utenti.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="0f4ce-125">Condividi con Teams usa Single Sign-On (SSO), il che significa che gli utenti non devono fornire le proprie credenziali quando usano il componente aggiuntivo tramite Condividi per Teams.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="0f4ce-126">SSO per Outlook sul Web supporta e https://outlook.office365.com/owa/extSSO.aspx risponde URL per impostazione https://outlook.office.com/owa/extSSO.aspx predefinita.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="0f4ce-127">Per i domini vanity, gli amministratori devono aggiungere l'URL Azure Active Directory risposta appropriata.</span><span class="sxs-lookup"><span data-stu-id="0f4ce-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>