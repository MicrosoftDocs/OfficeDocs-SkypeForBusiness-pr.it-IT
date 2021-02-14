---
title: Personalizzare l'esperienza client Mac in Skype for Business
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: Questo articolo descrive le preferenze client e le impostazioni predefinite disponibili per il client Skype for Business su Mac e come modificarle dall'esterno dell'App.
ms.openlocfilehash: cdbd1c109fffddf6d922657285f60d9b4f06924a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805756"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="38ca4-103">Personalizzare l'esperienza client Mac in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="38ca4-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="38ca4-104">Questo articolo descrive le preferenze client e le impostazioni predefinite disponibili per il client Skype for Business su Mac e come modificarle dall'esterno dell'App.</span><span class="sxs-lookup"><span data-stu-id="38ca4-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="38ca4-105">Impostazioni delle preferenze del client Skype for Business su Mac</span><span class="sxs-lookup"><span data-stu-id="38ca4-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="38ca4-106">Alcune funzionalità e comportamenti disponibili per i client Skype for Business su Mac sono determinati dalle impostazioni delle preferenze nel client.</span><span class="sxs-lookup"><span data-stu-id="38ca4-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="38ca4-107">Le preferenze di Skype for Business su Mac si trovano in un file che si trova nei Mac in cui è installato il client Skype for Business che si trova nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="38ca4-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="38ca4-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="38ca4-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="38ca4-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span><span class="sxs-lookup"><span data-stu-id="38ca4-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="38ca4-110">**Chiavi di preferenza client**</span><span class="sxs-lookup"><span data-stu-id="38ca4-110">**Client preference keys**</span></span>


| <span data-ttu-id="38ca4-111">Chiave</span><span class="sxs-lookup"><span data-stu-id="38ca4-111">Key</span></span> | <span data-ttu-id="38ca4-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="38ca4-112">Type</span></span> | <span data-ttu-id="38ca4-113">Valore</span><span class="sxs-lookup"><span data-stu-id="38ca4-113">Value</span></span> | <span data-ttu-id="38ca4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38ca4-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38ca4-115">autoDetectAutoDicoveryURLs</span><span class="sxs-lookup"><span data-stu-id="38ca4-115">autoDetectAutoDicoveryURLs</span></span>    |<span data-ttu-id="38ca4-116">Bool</span><span class="sxs-lookup"><span data-stu-id="38ca4-116">Bool</span></span>    |<span data-ttu-id="38ca4-117">0 = configurazione manuale del server</span><span class="sxs-lookup"><span data-stu-id="38ca4-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="38ca4-118">1 = rilevamento automatico del server (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="38ca4-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="38ca4-119">Specificare in che modo Skype for Business identifica il trasporto e il server da usare durante l'accesso.</span><span class="sxs-lookup"><span data-stu-id="38ca4-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="38ca4-120">Se si abilita questa impostazione di criteri, è necessario specificare **internalAutoDiscoveryURL** e **externalAutoDiscoveryURL.**</span><span class="sxs-lookup"><span data-stu-id="38ca4-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="38ca4-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="38ca4-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="38ca4-122">Stringa</span><span class="sxs-lookup"><span data-stu-id="38ca4-122">String</span></span>    |<span data-ttu-id="38ca4-123">URL di individuazione automatica completo</span><span class="sxs-lookup"><span data-stu-id="38ca4-123">Full autodiscover URL</span></span>    |<span data-ttu-id="38ca4-124">URL di individuazione automatica interno</span><span class="sxs-lookup"><span data-stu-id="38ca4-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="38ca4-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="38ca4-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="38ca4-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="38ca4-126">String</span></span>    |<span data-ttu-id="38ca4-127">URL di individuazione automatica completo</span><span class="sxs-lookup"><span data-stu-id="38ca4-127">Full autodiscover URL</span></span>    |<span data-ttu-id="38ca4-128">URL di individuazione automatica esterno</span><span class="sxs-lookup"><span data-stu-id="38ca4-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="38ca4-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="38ca4-129">httpProxyDomain</span></span>    |<span data-ttu-id="38ca4-130">Stringa</span><span class="sxs-lookup"><span data-stu-id="38ca4-130">String</span></span>    ||<span data-ttu-id="38ca4-131">Dominio proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="38ca4-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="38ca4-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="38ca4-132">httpProxyUserName</span></span>    |<span data-ttu-id="38ca4-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="38ca4-133">String</span></span>    ||<span data-ttu-id="38ca4-134">Nome utente proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="38ca4-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="38ca4-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="38ca4-135">httpProxyPassword</span></span>    |<span data-ttu-id="38ca4-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="38ca4-136">String</span></span>    ||<span data-ttu-id="38ca4-137">HTTP Proxy Password</span><span class="sxs-lookup"><span data-stu-id="38ca4-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="38ca4-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="38ca4-138">trustedDomainList</span></span>    |<span data-ttu-id="38ca4-139">Matrice</span><span class="sxs-lookup"><span data-stu-id="38ca4-139">Array</span></span>    ||<span data-ttu-id="38ca4-140">Elenco dei domini attendibili per i reindirizzamenti HTTP.</span><span class="sxs-lookup"><span data-stu-id="38ca4-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="38ca4-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="38ca4-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="38ca4-142">Numero</span><span class="sxs-lookup"><span data-stu-id="38ca4-142">Number</span></span>    |<span data-ttu-id="38ca4-143">300 (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="38ca4-143">300 (default)</span></span>    |<span data-ttu-id="38ca4-144">Timeout di accettazione automatica per gli utenti senza Cronologia conversazioni sul lato server.</span><span class="sxs-lookup"><span data-stu-id="38ca4-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="38ca4-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="38ca4-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="38ca4-146">Bool</span><span class="sxs-lookup"><span data-stu-id="38ca4-146">Bool</span></span>    |<span data-ttu-id="38ca4-147">0 = Disabilitato</span><span class="sxs-lookup"><span data-stu-id="38ca4-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="38ca4-148">1 = Abilitato</span><span class="sxs-lookup"><span data-stu-id="38ca4-148">1 = Enabled</span></span>    |<span data-ttu-id="38ca4-149">Avvisa l'utente quando compone un numero di emergenza da una posizione sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="38ca4-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="38ca4-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="38ca4-150">sipAddress</span></span>    |<span data-ttu-id="38ca4-151">Stringa</span><span class="sxs-lookup"><span data-stu-id="38ca4-151">String</span></span>    ||<span data-ttu-id="38ca4-152">L'indirizzo SIP (e-mail) usato per accedere a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="38ca4-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="38ca4-153">userName</span><span class="sxs-lookup"><span data-stu-id="38ca4-153">userName</span></span>    |<span data-ttu-id="38ca4-154">Stringa</span><span class="sxs-lookup"><span data-stu-id="38ca4-154">String</span></span>    ||<span data-ttu-id="38ca4-155">UPN (UserName) usato per accedere a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="38ca4-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="38ca4-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="38ca4-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="38ca4-157">Bool</span><span class="sxs-lookup"><span data-stu-id="38ca4-157">Bool</span></span>    |<span data-ttu-id="38ca4-158">0 = visualizzare il campo Nome utente nella schermata di accesso principale e nella finestra di dialogo Proprietà avanzate</span><span class="sxs-lookup"><span data-stu-id="38ca4-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="38ca4-159">1 = visualizzare il campo Nome utente solo nella finestra di dialogo Proprietà avanzate (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="38ca4-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="38ca4-160">Specificare dove viene visualizzato il campo Nome utente durante l'accesso.</span><span class="sxs-lookup"><span data-stu-id="38ca4-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="38ca4-161">Esempi di utilizzo</span><span class="sxs-lookup"><span data-stu-id="38ca4-161">Usage examples</span></span>

<span data-ttu-id="38ca4-162">Per aggiungere un singolo dominio (Contoso.com) all'elenco di domini trusted, utilizzare la chiave trustedDomainList come illustrato:</span><span class="sxs-lookup"><span data-stu-id="38ca4-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="38ca4-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="38ca4-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="38ca4-164">Per aggiungere diversi domini all'elenco di domini trusted, utilizzare la chiave trustedDomainList come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="38ca4-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="38ca4-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span><span class="sxs-lookup"><span data-stu-id="38ca4-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="38ca4-166">Esempio di impostazioni non modificate</span><span class="sxs-lookup"><span data-stu-id="38ca4-166">Sample unedited settings</span></span>

<span data-ttu-id="38ca4-167">Per riferimento, ecco un file di impostazioni di esempio che usa solo le impostazioni predefinite:</span><span class="sxs-lookup"><span data-stu-id="38ca4-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```console
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
