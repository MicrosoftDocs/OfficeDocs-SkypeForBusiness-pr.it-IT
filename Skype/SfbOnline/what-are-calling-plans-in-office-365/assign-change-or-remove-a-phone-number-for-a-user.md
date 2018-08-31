---
title: Assegnare, modificare o rimuovere il numero di telefono di un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: Informazioni su come assegnare, modificare o rimuovere un numero di telefono per utenti di Skype for Business in modo che le aziende e i clienti esterni li possano chiamare.
ms.openlocfilehash: 8c80bf9da5471f1a7293a01ed9e2d56f6e1aa15b
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780940"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="21701-103">Assegnare, modificare o rimuovere il numero di telefono di un utente</span><span class="sxs-lookup"><span data-stu-id="21701-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="21701-104">Quando imposti i Piani di chiamata in Office 365, assegni i numeri di telefono ai tuoi utenti.</span><span class="sxs-lookup"><span data-stu-id="21701-104">When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> 

<span data-ttu-id="21701-105">Nel client di Microsoft Teams, il numero di telefono assegnato verrà elencato quando si fa clic su **Chiama**.</span><span class="sxs-lookup"><span data-stu-id="21701-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![Numero di telefono dell'utente visualizzato in Microsoft Teams.](../images/teams-phone-number.png)

<span data-ttu-id="21701-107">Nel client di Skype for Business, il numero di telefono assegnato verrà elencato nella casella **Telefono ufficio** e non può essere modificato da un utente.</span><span class="sxs-lookup"><span data-stu-id="21701-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Il numero di telefono Ufficio è ombreggiato.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="21701-109">Se un utente desidera [modificare il proprio numero di telefono per Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) e il numero di telefono nell'app Skype for Business non può essere modificato o è ombreggiato, ciò significa che gli amministratori lo hanno già impostato per l'utente e non può essere modificato da quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="21701-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="21701-110">Quando imposti la possibilità per gli utenti di effettuare e ricevere chiamate telefoniche, è necessario innanzitutto utilizzare l'interfaccia di amministrazione di Skype for Business e assegnare un numero di telefono, ma è possibile modificarlo o rimuoverlo se necessario.</span><span class="sxs-lookup"><span data-stu-id="21701-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="21701-111">Per informazioni su come ottenere Piani di chiamata in Office 365 e il relativo costo, consulta [Licenze per componenti aggiuntivi per Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="21701-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="21701-112">Un modo per verificare se un utente dispone di una licenza assegnata è andando su **Interfaccia di amministrazione di Skype for Business** > **Voce** > **Utenti Voce** e selezionare l'utente.</span><span class="sxs-lookup"><span data-stu-id="21701-112">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user.</span></span> <span data-ttu-id="21701-113">Se viene assegnata una licenza, verrà notificata in **Licenza assegnata**.</span><span class="sxs-lookup"><span data-stu-id="21701-113">If a license is assigned, it will be noted under **Assigned license**.</span></span> <span data-ttu-id="21701-114">Puoi anche utilizzare l'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="21701-114">You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="21701-115">Assegnare un numero di telefono a un utente</span><span class="sxs-lookup"><span data-stu-id="21701-115">Assign a phone number to a user.</span></span>
 
<span data-ttu-id="21701-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="21701-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="21701-117">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="21701-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="21701-118">Vai su **Vai su Interfaccia di amministrazione di Office 365** > **Interfacce amministratore** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="21701-118">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="21701-119">Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.** **  >  ** **</span><span class="sxs-lookup"><span data-stu-id="21701-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
 <span data-ttu-id="21701-120">Per visualizzare l'opzione **Voce** nella barra di navigazione sinistra dell'interfaccia di amministrazione di Skype for Business, è necessario acquistare almeno una **licenza Enterprise E5**, una licenza per il componente aggiuntivo **Sistema telefonico** o una licenza per il componente aggiuntivo **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="21701-120">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="21701-121">Nella pagina **Utenti voce**, individua e seleziona l'utente o gli utenti a cui vuoi assegnare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="21701-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="21701-122">Nel riquadro Azione, seleziona **Assegna numero**.</span><span class="sxs-lookup"><span data-stu-id="21701-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="21701-123">Nella pagina **Assegna numero** nel menu a discesa **Seleziona il numero da assegnare**, scegli il numero di telefono per l'utente.</span><span class="sxs-lookup"><span data-stu-id="21701-123">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="21701-124">Se non riesci a visualizzare nessun numero di telefono nell'elenco, devi prima [Ottenere numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="21701-124">If you don't see any phone numbers listed, you need to [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md) first.</span></span> <span data-ttu-id="21701-125">Oppure, utilizzando la pagina **Interfaccia di amminstrazione Skype per Business** > **Voce** > **Numeri di telefono**, fai clic su **Aggiungi** e quindi fai clic su **Nuovi numeri utente**.</span><span class="sxs-lookup"><span data-stu-id="21701-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="21701-126">Per assegnare o modificare l'indirizzo di emergenza associato, vai su **Selezionare luogo di emergenza approvato**, seleziona il luogo dall'elenco oppure, se hai molti luoghi definiti, immetti il nome della città nella casella di ricerca e fai clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="21701-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="21701-127">Una volta selezionato il numero di telefono e il luogo di emergenza, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="21701-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="21701-128">A causa della latenza tra Office 365 e Skype for Business online, talvolta sono necessarie fino a 24 ore per abilitare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="21701-128">Latency after assigning licenses: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="21701-129">Se dopo 24 ore il numero di telefono non è assegnato correttamente, per favore [Contatta il supporto per i prodotti per aziende - Guida amministratore](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="21701-129">If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="21701-130">Siamo qui per aiutarti!</span><span class="sxs-lookup"><span data-stu-id="21701-130">We're here to help</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="21701-131">Modificare un numero di telefono di un utente</span><span class="sxs-lookup"><span data-stu-id="21701-131">Assign, change, or remove a phone number for a user</span></span>
 
<span data-ttu-id="21701-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="21701-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="21701-133">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="21701-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="21701-134">Vai su **Vai su Interfaccia di amministrazione di Office 365** > **Interfacce amministratore** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="21701-134">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="21701-135">Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.** **  >  ** **</span><span class="sxs-lookup"><span data-stu-id="21701-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="21701-136">Nella pagina Utenti voce, individua e seleziona l'utente o gli utenti a cui vuoi assegnare un numero di telefono.** **</span><span class="sxs-lookup"><span data-stu-id="21701-136">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="21701-137">Nel riquadro Azioni, su **Numero assegnato**, fai clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="21701-137">In the Action pane under **Assigned license**, click **Edit**.</span></span> 
    
6. <span data-ttu-id="21701-138">Nella pagina **Assegna numero**, fai clic su **Modifica numero**.</span><span class="sxs-lookup"><span data-stu-id="21701-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="21701-139">Nella pagina **Assegna numero** su **Seleziona numero da assegnare**, utilizza l'elenco per selezionare il nuovo numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="21701-139">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span> 
    
8. <span data-ttu-id="21701-140">Per modificare l'indirizzo di emergenza associato, fai clic su **Modifica luogo**e quindi su **Modifica l'indirizzo di emergenza**, selezionando il percorso dall'elenco oppure, se hai molti luoghi definiti, immetti il nome della città nella casella di ricerca e fai clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="21701-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="21701-141">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="21701-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="21701-142">Rimozione di un numero di telefono da un utente</span><span class="sxs-lookup"><span data-stu-id="21701-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="21701-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="21701-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="21701-144">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="21701-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="21701-145">Vai su **Interfaccia di amministrazione di Office 365** > **Interfacce amministratore** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="21701-145">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="21701-146">Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.** **  >  ** **</span><span class="sxs-lookup"><span data-stu-id="21701-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="21701-147">Nella pagina **Utenti voce**, individua e seleziona l'utente o gli utenti a cui vuoi assegnare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="21701-147">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="21701-148">Nel riquadro Azioni, su **Numero assegnato**, fai clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="21701-148">In the Action pane under **Assigned license**, click **Edit**.</span></span> 
    
6. <span data-ttu-id="21701-149">Nella pagina **Vuoi rimuovere il numero assegnato selezionato?** fai clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="21701-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="21701-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="21701-150">Related topics</span></span>
[<span data-ttu-id="21701-151">Cos'è la convalida dell'indirizzo?</span><span class="sxs-lookup"><span data-stu-id="21701-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="21701-152">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="21701-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="21701-153">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="21701-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="21701-154">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="21701-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 