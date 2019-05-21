---
title: Configurare il PIN per il trasferimento numeri a un nuovo provider di servizi
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: To transfer or port out phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN. After you set the PIN, you need to include it when you request to port a phone number out.
ms.openlocfilehash: 64eaa010939c10a25e7c1fb4c53672a27296ebe1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290854"
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="c9489-104">Configurare il PIN per il trasferimento numeri a un nuovo provider di servizi</span><span class="sxs-lookup"><span data-stu-id="c9489-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="c9489-p102">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN. After you set the PIN, you need to include it when you request to port a phone number out.</span><span class="sxs-lookup"><span data-stu-id="c9489-p102">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN. After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c9489-107">Un PIN esportato viene utilizzato solo per le organizzazioni negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="c9489-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="c9489-108">Per ulteriori informazioni sul trasferimento e la portabilità/esclusione di numeri di telefono, consultare [Trasferire i numeri di telefono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="c9489-108">See [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="c9489-109">Ecco alcune informazioni specifiche sul PIN che è necessario conoscere:</span><span class="sxs-lookup"><span data-stu-id="c9489-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="c9489-110">Se non viene impostato un PIN, non sarà possibile o il trasferimento o la portabilità di numeri telefonici da Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="c9489-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="c9489-111">Può contenere 6-10 cifre (numeri).</span><span class="sxs-lookup"><span data-stu-id="c9489-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="c9489-112">Non può contenere lettere o caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="c9489-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="c9489-113">Il PIN predefinito è vuoto, ma se viene inserito, non è possibile rimuoverlo o reimpostarlo a vuoto.</span><span class="sxs-lookup"><span data-stu-id="c9489-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="c9489-114">È possibile aggiornare o modificare il PIN dopo che ne viene inserito uno.</span><span class="sxs-lookup"><span data-stu-id="c9489-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="c9489-115">Configurare il PIN</span><span class="sxs-lookup"><span data-stu-id="c9489-115">Set up your PIN</span></span>

<span data-ttu-id="c9489-116">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con l'interfaccia di amministrazione di Skype for business**</span><span class="sxs-lookup"><span data-stu-id="c9489-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="c9489-117">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c9489-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c9489-118">Accedere al**portale legacy**dell'interfaccia di **Amministrazione** > di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c9489-118">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c9489-119">Nel riquadro di spostamento sinistro, seleziona **Voce** > **Ordini di portabilità**.</span><span class="sxs-lookup"><span data-stu-id="c9489-119">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="c9489-120">Fai cli su **Imposta e gestisci il PIN** utilizzato per il trasferimento o la portabilità dei numeri ad un altro gestore di telefonia.</span><span class="sxs-lookup"><span data-stu-id="c9489-120">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="c9489-121">Nel pannello **Imposta o modifica il PIN di portabilità**, immettere il PIN e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c9489-121">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c9489-122">Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="c9489-122">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c9489-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c9489-123">Related topics</span></span>
[<span data-ttu-id="c9489-124">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="c9489-124">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="c9489-125">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="c9489-125">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="c9489-126">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c9489-126">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c9489-127">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="c9489-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c9489-128">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c9489-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
  

