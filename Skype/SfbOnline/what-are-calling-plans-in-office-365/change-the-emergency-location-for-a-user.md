---
title: Assegnare o modificare il percorso di emergenza per un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 'Learn how to change the emergency location for your users. With an unlimited number of locations, you can change emergency locations as employees move floors or buildings. '
ms.openlocfilehash: fc128a8de266bbf5ed6804ea07cc73bb2287a6e5
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754843"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a><span data-ttu-id="c1caa-104">Assegnare o modificare il percorso di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="c1caa-104">Assign or change the emergency location for a user</span></span>

<span data-ttu-id="c1caa-105">Ogni numero di telefono attivo deve avere un indirizzo di emergenza associato quando si assegna il numero di telefono a un utente.</span><span class="sxs-lookup"><span data-stu-id="c1caa-105">Each active phone number must have an associated emergency address when you assign the phone number to a user.</span></span> <span data-ttu-id="c1caa-106">(Viene associato all'indirizzo quando si ricevono un numero di telefono in Office 365 o quando si trasferisce un numero di telefono). Quando si associa il numero a un indirizzo di emergenza, è inoltre possibile aggiungere un percorso di emergenza per fornire una posizione più preciso all'interno di una posizione fisica.</span><span class="sxs-lookup"><span data-stu-id="c1caa-106">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="c1caa-107">La posizione per gli interventi di emergenza può corrispondere al piano, all'ala dell'edificio o al numero dell'ufficio in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="c1caa-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="c1caa-108">È possibile avere un numero illimitato di posizioni per un determinato indirizzo di emergenza ed è possibile modificare la posizione di emergenza se l'utente passa a un altro ufficio o edificio, ad esempio, se l'utente si sposta dal 34° al 35° piano.</span><span class="sxs-lookup"><span data-stu-id="c1caa-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="c1caa-109">Per informazioni su come ottenere Piani di chiamata in Office 365 e il relativo costo, consulta [Licenze per componenti aggiuntivi per Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c1caa-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="assign-or-change-the-emergency-location"></a><span data-ttu-id="c1caa-110">Assegnare o modificare il percorso di emergenza</span><span class="sxs-lookup"><span data-stu-id="c1caa-110">Assign or change the emergency location</span></span>

1. <span data-ttu-id="c1caa-111">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="c1caa-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c1caa-112">Vai al **Centro di amministrazione di team Microsoft che** > **portale Legacy**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-112">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c1caa-113">Nel riquadro sinistro passare a **Voice** > **agli utenti di VoIP**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-113">In the left navigation go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c1caa-114">Per poter visualizzare l'opzione **vocale** nel riquadro di spostamento sinistra in Skype per interfaccia di amministrazione di Business, è necessario acquistare una licenza di componente aggiuntivo **Per conferenze Audio** , una licenza di componente aggiuntivo di **Sistema telefonico** o almeno una **licenza Enterprise E5**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="c1caa-115">Nella pagina **Utenti voce**, individua e seleziona l'utente a cui desideri modificare l'indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c1caa-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="c1caa-116">Nel riquadro Azioni, in **Posizione per gli interventi di emergenza**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="c1caa-117">Nella pagina **Assegna numero**, fai clic su **Cambia posizione**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="c1caa-118">**Cambia indirizzo di emergenza per**immettere il nome della città nella casella e fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-118">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>

8. <span data-ttu-id="c1caa-119">Selezionare **ricerca dalla posizione** nell'elenco a discesa, immettere una parte del nome del percorso (ad esempio, immettere **la base**), quindi fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-119">Select **Search by location** from the drop-down list, enter a partial name for the location (for example, enter **floor**), and then click **Search**.</span></span> 
    
8. <span data-ttu-id="c1caa-120">Selezionare il percorso di emergenza nell'elenco e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c1caa-120">Select the emergency location from the list, and then click **Save**.</span></span>
    
    <span data-ttu-id="c1caa-121">Se si desidera aggiungere un nuovo percorso di emergenza che verrà visualizzato nell'elenco, vedere [aggiungere, modificare o rimuovere un percorso di emergenza per l'organizzazione](add-change-or-remove-an-emergency-location-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c1caa-121">If you want to add a new emergency location that will appear on the list, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c1caa-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c1caa-122">Related topics</span></span>
[<span data-ttu-id="c1caa-123">Aggiungere o rimuovere un indirizzo di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c1caa-123">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="c1caa-124">Aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c1caa-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="c1caa-125">Cos'è la convalida dell'indirizzo?</span><span class="sxs-lookup"><span data-stu-id="c1caa-125">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="c1caa-126">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c1caa-126">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c1caa-127">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="c1caa-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c1caa-128">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c1caa-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 