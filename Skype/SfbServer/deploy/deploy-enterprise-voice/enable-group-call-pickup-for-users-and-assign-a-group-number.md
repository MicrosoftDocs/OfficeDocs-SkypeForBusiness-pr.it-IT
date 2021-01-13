---
title: Abilitazione del prelievo delle chiamate di gruppo per gli utenti e assegnazione di un numero di gruppo in Skype for business
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
description: Abilitare gli utenti per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830966"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="5fd4a-103">Abilitazione del prelievo delle chiamate di gruppo per gli utenti e assegnazione di un numero di gruppo in Skype for business</span><span class="sxs-lookup"><span data-stu-id="5fd4a-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="5fd4a-104">Abilitare gli utenti per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.</span><span class="sxs-lookup"><span data-stu-id="5fd4a-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="5fd4a-105">Dopo aver aggiunto i numeri del gruppo di prelievo delle chiamate alla tabella orbit del parcheggio di chiamata, è possibile utilizzare lo strumento SEFAUtil per assegnare i numeri di gruppo agli utenti e abilitare il prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="5fd4a-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="5fd4a-106">In una distribuzione ibrida, non assegnare un gruppo di prelievo di chiamata di gruppo agli utenti ospitati online.</span><span class="sxs-lookup"><span data-stu-id="5fd4a-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="5fd4a-107">Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="5fd4a-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="5fd4a-108">Vale a fare che le chiamate non possono rispondere ad altri utenti e che non rispondono alle chiamate ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="5fd4a-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="5fd4a-109">Per assegnare un numero di gruppo e abilitare il prelievo delle chiamate di gruppo per un utente</span><span class="sxs-lookup"><span data-stu-id="5fd4a-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="5fd4a-110">Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="5fd4a-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="5fd4a-111">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5fd4a-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="5fd4a-112">Ad esempio, per assegnare il numero di gruppo 199 a un utente:</span><span class="sxs-lookup"><span data-stu-id="5fd4a-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="5fd4a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fd4a-113">See also</span></span>

[<span data-ttu-id="5fd4a-114">Disattiva raccolta gruppi per gli utenti</span><span class="sxs-lookup"><span data-stu-id="5fd4a-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

