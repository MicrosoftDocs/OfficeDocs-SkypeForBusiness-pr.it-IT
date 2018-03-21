---
title: Spostamento di provider di servizi di conferenza audio di un utente a Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
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
f1keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Modificare il Skype per gli utenti aziendali dal provider di terze parti audioconferenza (ACP) a un provider di conferenze telefoniche con Microsoft. '
ms.openlocfilehash: e28fb11d757265aa74eb559a9d9f4c26661ac26c
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="5d8f5-103">Spostamento di provider di servizi di conferenza audio di un utente a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d8f5-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="5d8f5-104">Per utilizzare audioconferenze con accesso esterno in Office 365 con Skype per le aziende e Teams Microsoft, è necessario impostare gli utenti dell'organizzazione necessita di una licenza di **Audioconferenza** assegnata a loro e i provider di servizi di conferenza audio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft.</span></span> <span data-ttu-id="5d8f5-105">Per ulteriori informazioni sulla gestione delle licenze e sul costo, vedere [prova o acquisto audioconferenza in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="5d8f5-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="5d8f5-106">Per spostare il provider di conferenza audio di un utente a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d8f5-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="5d8f5-107">Se una licenza di **Accesso esterno alle audioconferenze** è assegnata a un utente che non dispone di un provider, provider dell'utente viene automaticamente impostato su Microsoft e non è necessario eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-107">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else.</span></span> <span data-ttu-id="5d8f5-108">Se l'utente dispone già di un provider di servizi di conferenza audio, è necessario modificare provider dell'utente a Microsoft dopo l'assegnazione di una licenza di **Audioconferenza** .</span><span class="sxs-lookup"><span data-stu-id="5d8f5-108">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="5d8f5-109">Per configurare Microsoft come provider di audioconferenza per un utente che dispone di una licenza di **Audioconferenza** assegnati ma utilizza un altro provider di servizi di conferenza audio, eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="5d8f5-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="5d8f5-110">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5d8f5-111">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5d8f5-112">In **Skype per interfaccia di amministrazione di Business**, passare a **conferenze Audio**.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="5d8f5-113">Se viene visualizzata un'intestazione di notifica che indica che non vi sono utenti che dispongono di un' **Audioconferenza** licenza assegnata ma non dispone di Microsoft impostato come i provider di servizi di conferenza audio sono ancora stati, fare clic **qui per spostarli**.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="5d8f5-114">Se non viene visualizzata l'intestazione, in **Skype per Business admin center** fare clic su **utenti**e quindi selezionare il filtro **utenti pronti a conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="5d8f5-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="5d8f5-115">Selezionare gli utenti da spostare e quindi nel riquadro azioni fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="5d8f5-116">Selezionare **Microsoft** nell'elenco **nome del Provider** .</span><span class="sxs-lookup"><span data-stu-id="5d8f5-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d8f5-117">Quando il provider di servizi di conferenza audio di un utente viene modificato in Microsoft, le informazioni di accesso esterno alle audioconferenze dell'utente verranno modificato.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-117">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change.</span></span> <span data-ttu-id="5d8f5-118">Se è necessario conservare tali informazioni, visitare registrarlo in un punto qualsiasi prima di modificare il provider di uno degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-118">If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="5d8f5-119">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="5d8f5-120">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="5d8f5-120">What else should I know?</span></span>

- <span data-ttu-id="5d8f5-121">Se si seleziona l'utente nell'elenco, è possibile visualizzare le informazioni di audioconferenza predefinito dell'utente, ma non sarà in grado di visualizzare il PIN per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-121">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN.</span></span> <span data-ttu-id="5d8f5-122">È possibile reimpostare il PIN di un utente per conferenze audio facendo clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="5d8f5-122">You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="5d8f5-123">Se si desidera modificare le impostazioni di conferenza audio di un utente, si può selezionare l'utente dall'elenco e quindi fare clic su **Modifica** e apportare le modifiche desiderate nella pagina delle **proprietà** .</span><span class="sxs-lookup"><span data-stu-id="5d8f5-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="5d8f5-124">See also</span><span class="sxs-lookup"><span data-stu-id="5d8f5-124">Related topics</span></span>

[<span data-ttu-id="5d8f5-125">Servizi di conferenza telefonica con accesso esterno in Office 365</span><span class="sxs-lookup"><span data-stu-id="5d8f5-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

