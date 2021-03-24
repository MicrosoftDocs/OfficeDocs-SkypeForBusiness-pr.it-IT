---
title: Selezionare i membri consentiti
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
ROBOTS: NOINDEX, NOFOLLOW
description: La creazione e la gestione delle chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire AllowedMembers e Creators per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il pannello di controllo o Windows PowerShell cmdlet.
ms.openlocfilehash: 809426e7a8c52c51e6793690886decce58f8edcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109122"
---
# <a name="select-allowed-members"></a><span data-ttu-id="a8749-105">Selezionare membri consentiti</span><span class="sxs-lookup"><span data-stu-id="a8749-105">Select Allowed Members</span></span>

> [!NOTE] 
> <span data-ttu-id="a8749-106">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8749-106">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a8749-107">La stessa funzionalità è disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="a8749-107">The same functionality is available in Teams.</span></span> <span data-ttu-id="a8749-108">Per ulteriori informazioni, vedere [Aggiornamento da Skype for Business a Microsoft Teams.](/MicrosoftTeams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="a8749-108">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="a8749-109">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a8749-109">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>