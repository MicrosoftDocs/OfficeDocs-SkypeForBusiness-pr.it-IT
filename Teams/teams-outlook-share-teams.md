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
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="12cd2-103">Condividere in Teams da Outlook</span><span class="sxs-lookup"><span data-stu-id="12cd2-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="12cd2-104">Condividi in Teams da Outlook (Condividi in Teams) consente agli utenti di condividere messaggi di posta elettronica, inclusi gli allegati, da Outlook a qualsiasi chat o canale in Teams.</span><span class="sxs-lookup"><span data-stu-id="12cd2-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="12cd2-105">Componente aggiuntivo Outlook per la condivisione in Teams</span><span class="sxs-lookup"><span data-stu-id="12cd2-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="12cd2-106">La caratteristica Condividi in Teams richiede un componente aggiuntivo per Outlook.</span><span class="sxs-lookup"><span data-stu-id="12cd2-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="12cd2-107">Questo componente aggiuntivo viene installato automaticamente ogni volta che un utente accede all'app Web teams o al client desktop di Teams.</span><span class="sxs-lookup"><span data-stu-id="12cd2-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="12cd2-108">Assicurarsi di esaminare i componenti aggiuntivi per [Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e le regole di accesso client in Exchange [Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) per assicurarsi che i componenti aggiuntivi per Outlook funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="12cd2-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="12cd2-109">Inoltre, la disabilitazione delle esperienze connesse può impedire il corretto funzionamento dei componenti aggiuntivi per Outlook.</span><span class="sxs-lookup"><span data-stu-id="12cd2-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="12cd2-110">Per [altre informazioni, vedere](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) Esperienze connesse in Office.</span><span class="sxs-lookup"><span data-stu-id="12cd2-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="12cd2-111">Condividi con Teams usa lo stesso meccanismo di trasporto utilizzato quando un utente invia un canale tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="12cd2-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="12cd2-112">Per la condivisione nelle chat, i messaggi di posta elettronica (inclusi gli allegati di posta elettronica) vengono copiati nel OneDrive del mittente.</span><span class="sxs-lookup"><span data-stu-id="12cd2-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="12cd2-113">Per la condivisione su canali, i messaggi di posta elettronica e gli allegati vengono copiati nella **cartella Messaggi di** posta elettronica in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12cd2-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="12cd2-114">Il componente aggiuntivo Outlook per la condivisione in Teams usa il set di requisiti 1.7, come descritto in dettaglio nella documentazione relativa ai componenti aggiuntivi di [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)che include dettagli sui componenti aggiuntivi di Outlook, i requisiti di ambiente per i componenti aggiuntivi di Outlook e i client di Outlook specifici supportati con il set di requisiti 1.7.</span><span class="sxs-lookup"><span data-stu-id="12cd2-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="12cd2-115">Abilitazione o disabilitazione della condivisione in Teams</span><span class="sxs-lookup"><span data-stu-id="12cd2-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="12cd2-116">Il componente aggiuntivo Outlook per la condivisione in Teams può essere disabilitato o abilitato in modo selettivo per ogni utente usando i cmdlet di PowerShell seguenti.</span><span class="sxs-lookup"><span data-stu-id="12cd2-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="12cd2-117">La disabilitazione del componente aggiuntivo è possibile solo dopo l'installazione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="12cd2-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="12cd2-118">Se si vuole applicare la disabilitazione per tutti gli utenti del tenant, eseguire periodicamente uno script.</span><span class="sxs-lookup"><span data-stu-id="12cd2-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="12cd2-119">Per disabilitare il componente aggiuntivo per Outlook usato da Condividi in Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="12cd2-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="12cd2-120">Per abilitare il componente aggiuntivo per Outlook usato da Condividi in Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="12cd2-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="12cd2-121">Browser e Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="12cd2-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="12cd2-122">La condivisione con Teams, sia nei client desktop di Outlook sul Web che nei client desktop di Outlook, si basa su un browser WebView.</span><span class="sxs-lookup"><span data-stu-id="12cd2-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="12cd2-123">Per [informazioni dettagliate](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) sui client che usano browser specifici, vedere Browser usati dai componenti aggiuntivi di Office.</span><span class="sxs-lookup"><span data-stu-id="12cd2-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="12cd2-124">La condivisione con Teams richiede che i cookie di terze parti e l'accesso all'archiviazione locale siano abilitati per i browser degli utenti.</span><span class="sxs-lookup"><span data-stu-id="12cd2-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="12cd2-125">Condividi con Teams usa Single Sign-On (SSO), il che significa che gli utenti non devono fornire le proprie credenziali quando usano il componente aggiuntivo tramite Condividi con Teams.</span><span class="sxs-lookup"><span data-stu-id="12cd2-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="12cd2-126">Per impostazione predefinita, SSO per Outlook sul Web supporta e https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx risponde agli URL.</span><span class="sxs-lookup"><span data-stu-id="12cd2-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="12cd2-127">Per i domini vanity, gli amministratori devono aggiungere l'URL di risposta di Azure Active Directory appropriato.</span><span class="sxs-lookup"><span data-stu-id="12cd2-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>