---
title: Modificare le impostazioni degli utenti di Microsoft teams in blocco
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come gestire le impostazioni utente di Microsoft teams in blocco nell'interfaccia di amministrazione di Microsoft teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c57ae4978e0cfacf69c9e68fb47d3f28ad5c4f4d
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483749"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="a85ad-103">Modificare le impostazioni degli utenti di Microsoft teams in blocco</span><span class="sxs-lookup"><span data-stu-id="a85ad-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="a85ad-104">Come amministratore, puoi gestire le impostazioni degli utenti dei team nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="a85ad-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a85ad-105">Nella pagina **utenti** è possibile visualizzare informazioni come account e dettagli sulle licenze e modificare i criteri e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a85ad-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="a85ad-106">È possibile modificare le impostazioni per gli utenti singolarmente o per più utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a85ad-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="a85ad-107">Modificare le impostazioni utente in blocco</span><span class="sxs-lookup"><span data-stu-id="a85ad-107">Edit user settings in bulk</span></span>

<span data-ttu-id="a85ad-108">Usare l'interfaccia di amministrazione di Microsoft teams per modificare le impostazioni per più utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="a85ad-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="a85ad-109">Ti consigliamo di modificare le impostazioni per 20 utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="a85ad-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="a85ad-110">Per modificare le impostazioni per un numero elevato di utenti, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a85ad-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="a85ad-111">Per altre informazioni, Vedi [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a85ad-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="a85ad-112">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**.</span><span class="sxs-lookup"><span data-stu-id="a85ad-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="a85ad-113">Cercare gli utenti da modificare o filtrare la visualizzazione per mostrare gli utenti che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="a85ad-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="a85ad-114">Nella colonna **&#x2713;** (segno di spunta) selezionare utenti eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a85ad-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="a85ad-115">Selezionare gli utenti uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="a85ad-115">Select users one at a time.</span></span> <span data-ttu-id="a85ad-116">Accanto a ogni utente selezionato viene visualizzato un **&#x2713;** .</span><span class="sxs-lookup"><span data-stu-id="a85ad-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="a85ad-117">Se si selezionano più di 20 utenti, non verranno bloccati, ma si terrà presente che più utenti si selezionano, più lungo sarà il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="a85ad-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![Screenshot della pagina utenti che mostra la selezione dell'utente](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="a85ad-119">Fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella per selezionare tutti gli utenti (fino a un massimo di 20 utenti), quindi nella finestra di dialogo **limite selezione** fare clic su **continua selezionare tutto** per completare la selezione.</span><span class="sxs-lookup"><span data-stu-id="a85ad-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="a85ad-120">![Screenshot della pagina utenti che mostra il limite di selezione](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="a85ad-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="a85ad-121">Accanto agli utenti selezionati viene visualizzata una **&#x2713;** .</span><span class="sxs-lookup"><span data-stu-id="a85ad-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Screenshot della pagina utenti che Mostra 20 utenti selezionati](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="a85ad-123">Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a85ad-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Screenshot del riquadro Modifica impostazioni](media/bulk-edit-user-settings-edit-settings.png)
