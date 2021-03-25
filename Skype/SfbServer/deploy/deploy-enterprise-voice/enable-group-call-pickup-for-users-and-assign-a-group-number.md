---
title: Abilitare la risposta alle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Abilitare gli utenti per la risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111832"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="2e862-103">Abilitare la risposta alle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2e862-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="2e862-104">Abilitare gli utenti per la risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2e862-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="2e862-105">Dopo aver aggiunto i numeri del gruppo di prelievo chiamata alla tabella orbit del parcheggio di chiamata, si utilizza lo strumento SEFAUtil per assegnare i numeri di gruppo agli utenti e abilitare la risposta alle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2e862-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="2e862-106">In una distribuzione ibrida non assegnare un gruppo di prelievo chiamata di gruppo agli utenti ospitati online.</span><span class="sxs-lookup"><span data-stu-id="2e862-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="2e862-107">Gli utenti ospitati online non possono partecipare alla risposta alle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="2e862-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="2e862-108">In altre parole, non è possibile rispondere alle chiamate di altri utenti e non possono rispondere alle chiamate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="2e862-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="2e862-109">Per assegnare un numero di gruppo e abilitare la risposta alle chiamate di gruppo per un utente</span><span class="sxs-lookup"><span data-stu-id="2e862-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="2e862-110">Accedere al computer in cui è stato installato lo strumento SEFAUtil con diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="2e862-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="2e862-111">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2e862-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="2e862-112">Ad esempio, per assegnare il numero di gruppo 199 a un utente:</span><span class="sxs-lookup"><span data-stu-id="2e862-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="2e862-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e862-113">See also</span></span>

[<span data-ttu-id="2e862-114">Disabilitare il prelievo di gruppo per gli utenti</span><span class="sxs-lookup"><span data-stu-id="2e862-114">Disable Group Pickup for Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)