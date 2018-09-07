---
title: Modificare la posizione per gli interventi di emergenza per un utente
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: 'Informazioni su come modificare la posizione di emergenza per gli utenti. Con un numero illimitato di posizioni, è possibile modificare le posizioni di emergenza quando i dipendenti si spostano su altri piani o edifici. '
ms.openlocfilehash: e3805daa8248da44de84330ea5de694126e9e32c
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863274"
---
# <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="a0447-104">Modificare la posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="a0447-104">Change the emergency location for a user</span></span>

<span data-ttu-id="a0447-105">Ogni numero di telefono attivo deve avere un indirizzo di emergenza (associato quando si ricevono un numero di telefono in Office 365 o quando si trasferisce un numero di telefono) quando il numero di telefono viene assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="a0447-105">Each active phone number must have an emergency address (associated when you get a phone number in Office 365 or when you transfer a phone number) when the phone number is assigned to the user.</span></span> <span data-ttu-id="a0447-106">Quando si associa il numero a un indirizzo di emergenza, è inoltre possibile aggiungere una posizione di emergenza per fornire un luogo più preciso all'interno di una posizione fisica.</span><span class="sxs-lookup"><span data-stu-id="a0447-106">When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="a0447-107">La posizione per gli interventi di emergenza può corrispondere al piano, all'ala dell'edificio o al numero dell'ufficio in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="a0447-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="a0447-108">È possibile avere un numero illimitato di posizioni per un determinato indirizzo di emergenza ed è possibile modificare la posizione di emergenza se l'utente passa a un altro ufficio o edificio, ad esempio, se l'utente si sposta dal 34° al 35° piano.</span><span class="sxs-lookup"><span data-stu-id="a0447-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="a0447-109">Per informazioni su come ottenere Piani di chiamata in Office 365 e il relativo costo, consulta [Licenze per componenti aggiuntivi per Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a0447-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="a0447-110">Modificare la posizione di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="a0447-110">Change the emergency location for a user</span></span>

1. <span data-ttu-id="a0447-111">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="a0447-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a0447-112">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a0447-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a0447-113">Nella barra di navigazione sinistra, vai su **Voce** > **Utenti voce**.</span><span class="sxs-lookup"><span data-stu-id="a0447-113">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a0447-114">Per visualizzare l'opzione **Voce** nella barra di navigazione sinistra dell'interfaccia di amministrazione di Skype for Business, è necessario acquistare almeno una **Licenza Enterprise E5**, una licenza per il componente aggiuntivo **Sistema telefonico** o una licenza per il componente aggiuntivo **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="a0447-114">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="a0447-115">Nella pagina **Utenti voce**, individua e seleziona l'utente a cui desideri modificare l'indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="a0447-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="a0447-116">Nel riquadro Azioni, in **Posizione per gli interventi di emergenza**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a0447-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="a0447-117">Nella pagina **Assegna numero**, fai clic su **Cambia posizione**.</span><span class="sxs-lookup"><span data-stu-id="a0447-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="a0447-118">Sotto **Cambia indirizzo di emergenza**, immetti il nome della città e fai clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="a0447-118">Under **Change emergency address to** put the name of the city in the Find City box and click **Search**.</span></span>
    
8. <span data-ttu-id="a0447-119">Seleziona la posizione di emergenza dall'elenco e quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a0447-119">Select the right emergency location from the Select associated location (optional) list, then click **Save**.</span></span>
    
    <span data-ttu-id="a0447-120">Se desideri aggiungere una nuova posizione di emergenza, consulta [Aggiungere, modificare o rimuovere una posizione di emergenza per la propria organizzazione](add-change-or-remove-an-emergency-location-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="a0447-120">If you want to add a new emergency location, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a0447-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a0447-121">Related topics</span></span>
[<span data-ttu-id="a0447-122">Aggiungere o rimuovere un indirizzo di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a0447-122">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="a0447-123">Aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a0447-123">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="a0447-124">Cos'è la convalida dell'indirizzo?</span><span class="sxs-lookup"><span data-stu-id="a0447-124">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="a0447-125">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="a0447-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a0447-126">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="a0447-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a0447-127">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a0447-127">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 