---
title: Visualizzare i record di utilizzo PSTN in Skype for Business
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Riepilogo: informazioni su come visualizzare i record di utilizzo PSTN utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.'
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830536"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="9b751-103">Visualizzare i record di utilizzo PSTN in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9b751-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="9b751-104">**Riepilogo:** Informazioni su come visualizzare i record di utilizzo PSTN utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9b751-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="9b751-105">Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata, ad esempio interna, locale o interurbana, che può essere effettuata da vari utenti o gruppi di utenti in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9b751-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="9b751-106">Per informazioni dettagliate, vedere [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9b751-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9b751-107">Per visualizzare un record di utilizzo PSTN tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9b751-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9b751-108">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9b751-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="9b751-109">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="9b751-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="9b751-110">Nella pagina **Utilizzo PSTN** evidenziare i record di utilizzo PSTN che si desidera visualizzare, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9b751-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9b751-111">In una pagina di sola lettura per il record di utilizzo PSTN selezionato vengono visualizzati le route e i criteri vocali associati.</span><span class="sxs-lookup"><span data-stu-id="9b751-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="9b751-112">Per visualizzare le informazioni sull'utilizzo PSTN utilizzando i cmdlet di Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9b751-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="9b751-113">Per visualizzare informazioni su tutti gli utilizzi PSTN, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9b751-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="9b751-114">Il comando restituisce informazioni simili a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="9b751-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="9b751-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b751-115">See also</span></span>

[<span data-ttu-id="9b751-116">Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9b751-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

