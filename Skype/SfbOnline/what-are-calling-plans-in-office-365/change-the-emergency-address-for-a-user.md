---
title: Modificare l’indirizzo per gli interventi di emergenza per un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
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
description: "Procedura per cambiare l'indirizzo di emergenza per un utente per l'utilizzo con la Rete telefonica pubblica commutata (PSTN) negli Stati Uniti e in Europe. "
ms.openlocfilehash: dad05a0ea42e6007e96b34ce5e0881fa6b427b8f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881900"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="94c0b-103">Modificare l’indirizzo per gli interventi di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="94c0b-103">Change the emergency address for a user</span></span>

<span data-ttu-id="94c0b-104">Durante la configurazione dei Piani di chiamata in Office 365, devi assegnare un indirizzo di emergenza a ciascun numero di telefono o utente.</span><span class="sxs-lookup"><span data-stu-id="94c0b-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="94c0b-105">Nei paesi europei, l'indirizzo di emergenza è associato al numero di telefono quando lo si ottiene da Office 365 o quando si trasferisce un numero di telefono in Office 365.</span><span class="sxs-lookup"><span data-stu-id="94c0b-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="94c0b-106">Negli Stati Uniti, l'indirizzo di emergenza è associato al numero di telefono quando viene assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="94c0b-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="94c0b-107">È possibile cambiare l'indirizzo di emergenza se l'utente a cui è assegnato si sposta in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="94c0b-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="94c0b-108">Per ulteriori informazioni sugli indirizzi di emergenza e posizioni, vedere [quali sono posizioni di emergenza, indirizzi e il routing delle chiamate?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="94c0b-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span></span>
  
<span data-ttu-id="94c0b-109">Per informazioni su come ottenere Piani di chiamata in Office 365 e il relativo costo, consulta [Licenze per componenti aggiuntivi per Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="94c0b-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="94c0b-110">Modificare l’indirizzo per gli interventi di emergenza per un utente</span><span class="sxs-lookup"><span data-stu-id="94c0b-110">Change the emergency address for a user</span></span>

<span data-ttu-id="94c0b-111">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="94c0b-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="94c0b-112">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="94c0b-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="94c0b-113">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="94c0b-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="94c0b-114">Nel riquadro di spostamento sinistro, passare a **Voice** > **agli utenti di VoIP**.</span><span class="sxs-lookup"><span data-stu-id="94c0b-114">In the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94c0b-115">Per poter visualizzare l'opzione **vocale** nel riquadro di spostamento sinistra in Skype per interfaccia di amministrazione di Business, è necessario acquistare una licenza di componente aggiuntivo **Per conferenze Audio** , una licenza di componente aggiuntivo di **Sistema telefonico** o almeno una **licenza Enterprise E5**.</span><span class="sxs-lookup"><span data-stu-id="94c0b-115">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="94c0b-116">Nella pagina **Utenti voce**, individua e seleziona l'utente a cui desideri cambiare l'indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="94c0b-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="94c0b-117">Nel riquadro Azioni, in **Posizione per gli interventi di emergenza**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="94c0b-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="94c0b-118">Nella pagina **Assegna numero**, fai clic su **Cambia posizione**.</span><span class="sxs-lookup"><span data-stu-id="94c0b-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="94c0b-119">**Cambia indirizzo di emergenza per**immettere il nome della città nella casella e fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="94c0b-119">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94c0b-120">È possibile cambiare solo un indirizzo di emergenza che è già stato convalidato.</span><span class="sxs-lookup"><span data-stu-id="94c0b-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="94c0b-121">Per cambiare un indirizzo di emergenza che non è stato convalidato, elimina quell'indirizzo e creane un altro.</span><span class="sxs-lookup"><span data-stu-id="94c0b-121">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
8. <span data-ttu-id="94c0b-122">Seleziona un nuovo indirizzo di emergenza dall'elenco e fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94c0b-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="94c0b-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="94c0b-123">Related topics</span></span>
[<span data-ttu-id="94c0b-124">Aggiungere o rimuovere un indirizzo di emergenza per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="94c0b-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="94c0b-125">Aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="94c0b-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="94c0b-126">Cos'è la convalida dell'indirizzo?</span><span class="sxs-lookup"><span data-stu-id="94c0b-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="94c0b-127">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="94c0b-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="94c0b-128">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="94c0b-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="94c0b-129">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="94c0b-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 