---
title: Impostare il PIN per il trasferimento di numeri in un nuovo provider di servizi
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: Per trasferire o delle porte numeri di telefono da Skype Business online in un altro provider di servizi telefonici o gestore di telefonia, è necessario impostare manualmente un PIN. Dopo aver impostato il PIN, è necessario includerlo nella richiesta di un numero di telefono fuori delle porte.
ms.openlocfilehash: f4ff20f4252686d047b3e9d83cf8beb4b3a9daae
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="f2bf8-104">Impostare il PIN per il trasferimento di numeri in un nuovo provider di servizi</span><span class="sxs-lookup"><span data-stu-id="f2bf8-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="f2bf8-105">Per il trasferimento o *dalla porta fuori* numeri di telefono da Skype Business online in un altro provider di servizi telefonici o gestore di telefonia, è necessario impostare manualmente un PIN.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="f2bf8-106">Dopo aver impostato il PIN, è necessario includerlo nella richiesta di un numero di telefono fuori delle porte.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f2bf8-107">Una porta fuori PIN viene utilizzata solo per le organizzazioni negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="f2bf8-108">Per ulteriori informazioni sul trasferimento e portabilità/esclusione numeri di telefono, vedere [trasferire i numeri di telefono a Office 365](transfer-phone-numbers-to-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="f2bf8-108">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="f2bf8-109">Ecco alcune informazioni specifiche sul PIN è necessario conoscere:</span><span class="sxs-lookup"><span data-stu-id="f2bf8-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="f2bf8-110">Se non viene impostato un PIN, non sarà in grado di trasferimento o dalla porta numeri telefonici da Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="f2bf8-111">Può contenere 6-10 cifre (numeri).</span><span class="sxs-lookup"><span data-stu-id="f2bf8-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="f2bf8-112">Non può contenere lettere o caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="f2bf8-113">Il PIN predefinito è vuoto, ma se vengono inseriti nel, non è possibile rimuovere o impostarla su vuoto.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="f2bf8-114">È possibile aggiornare o modificare il PIN dopo vengono inseriti.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="f2bf8-115">Configurare il PIN</span><span class="sxs-lookup"><span data-stu-id="f2bf8-115">Set up your PIN</span></span>

1. <span data-ttu-id="f2bf8-116">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f2bf8-117">Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-117">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f2bf8-118">Nel riquadro di spostamento sinistro, selezionare **segreteria** > **orders di porta**.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-118">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="f2bf8-119">Fare clic su **impostare verso l'alto e gestire il PIN** utilizzata per il trasferimento o porting numeri per portante di un altro servizio.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-119">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="f2bf8-120">Nella **impostare o modificare la porta fuori PIN** pannello, immettere il PIN e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2bf8-120">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bf8-121">Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="f2bf8-121">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f2bf8-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f2bf8-122">Related topics</span></span>
[<span data-ttu-id="f2bf8-123">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="f2bf8-123">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="f2bf8-124">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="f2bf8-124">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="f2bf8-125">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="f2bf8-125">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="f2bf8-126">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="f2bf8-126">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="f2bf8-127">Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="f2bf8-127">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 
  

