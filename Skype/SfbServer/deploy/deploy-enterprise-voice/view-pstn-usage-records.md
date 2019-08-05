---
title: Visualizzare i record di utilizzo PSTN in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Riepilogo: informazioni su come visualizzare i record di utilizzo PSTN usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.'
ms.openlocfilehash: d00fcab8c7f5ad9b8f47d5aecb6c6169e8d43574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195205"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="ffb1f-103">Visualizzare i record di utilizzo PSTN in Skype for business</span><span class="sxs-lookup"><span data-stu-id="ffb1f-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="ffb1f-104">**Riepilogo:** Informazioni su come visualizzare i record di utilizzo PSTN usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="ffb1f-105">Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere eseguita da vari utenti o gruppi di utenti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="ffb1f-106">Per informazioni dettagliate, vedere [record sull'utilizzo PSTN](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ffb1f-107">Per visualizzare un record di utilizzo PSTN tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ffb1f-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ffb1f-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ffb1f-109">Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="ffb1f-110">Nella pagina **uso PSTN** evidenziare il record di utilizzo PSTN che si vuole visualizzare, fare clic su **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ffb1f-111">Una pagina di sola lettura del record di utilizzo PSTN selezionato Mostra le route associate e i criteri vocali associati.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="ffb1f-112">Per visualizzare le informazioni sull'utilizzo PSTN usando i cmdlet di Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ffb1f-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="ffb1f-113">Per visualizzare informazioni su tutti gli usi PSTN, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="ffb1f-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="ffb1f-114">Questo comando restituisce informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="ffb1f-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="ffb1f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffb1f-115">See also</span></span>

[<span data-ttu-id="ffb1f-116">Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business</span><span class="sxs-lookup"><span data-stu-id="ffb1f-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

