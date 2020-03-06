---
title: Risorse di Microsoft Teams per l'istruzione per amministratori
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Procedure di licenza dettagliate per Microsoft Teams per l'istruzione.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b653acbe18d2247ccbf64a523fd237ca1415414
ms.sourcegitcommit: ac811017d54a55f39ecc0e3a66a883d9e027ce68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547984"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="aff0b-103">Assegnare licenze di Microsoft Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="aff0b-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="aff0b-104">Microsoft Teams è un hub digitale che raggruppa conversazioni, contenuti e app in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="aff0b-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="aff0b-105">Perché è basato su Office 365, gli istituti di istruzione traggono vantaggio dall'integrazione con le ben note app e i servizi di Office.</span><span class="sxs-lookup"><span data-stu-id="aff0b-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="aff0b-106">Gli istituti possono usare Microsoft Teams per creare classi collaborative, connettersi a comunità di formazione professionale e comunicare con il personale scolastico, tutto in un'unica posizione in Office 365 per l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="aff0b-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="aff0b-107">Per iniziare, gli amministratori IT devono usare l'interfaccia di amministrazione di Microsoft 365 per [abilitare Microsoft Teams per l'istituto di istruzione](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="aff0b-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="aff0b-108">Fatto questo, è necessario assegnare le licenze agli account utente in modo che la facoltà, il personale e gli studenti possano accedere ai servizi di Office 365, come Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aff0b-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="aff0b-109">È possibile assegnare licenze agli account utente singolarmente oppure automaticamente mediante l'appartenenza a gruppi.</span><span class="sxs-lookup"><span data-stu-id="aff0b-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="aff0b-110">Questo articolo illustra come assegnare le licenze di Office 365 a un singolo o a un piccolo set di account utente tramite l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aff0b-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="aff0b-111">Per assegnare automaticamente licenze tramite l'appartenenza a gruppi, vedere uno degli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="aff0b-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="aff0b-112">PowerShell di Office 365</span><span class="sxs-lookup"><span data-stu-id="aff0b-112">Office 365 Powershell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="aff0b-113">Licenze basate sui gruppi in Active Directory</span><span class="sxs-lookup"><span data-stu-id="aff0b-113">Group-based Licensing in Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="aff0b-114">È possibile assegnare licenze agli utenti nella pagina **Licenze** o nella pagina **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="aff0b-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="aff0b-115">Il metodo da usare varia a seconda che si vogliano assegnare licenze di prodotto a utenti specifici o assegnare licenze utente a prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="aff0b-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="aff0b-116">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="aff0b-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="aff0b-117">Assegnare licenze agli utenti nella pagina Licenze</span><span class="sxs-lookup"><span data-stu-id="aff0b-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="aff0b-118">È necessario essere un amministratore globale, un amministratore di fatturazione, un amministratore delle licenze o un amministratore di gestione degli utenti. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="aff0b-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="aff0b-119">Dalla pagina **Licenze** si assegnano licenze per un prodotto specifico per un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="aff0b-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="aff0b-120">Nella pagina **Licenze** viene visualizzato un elenco di tutti i prodotti per i quali si dispone di un abbonamento, oltre al totale di licenze per ogni prodotto, al numero di licenze assegnate e al numero di quelle disponibili.</span><span class="sxs-lookup"><span data-stu-id="aff0b-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="aff0b-121">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > [Licenze](https://go.microsoft.com/fwlink/p/?linkid=842264).</span><span class="sxs-lookup"><span data-stu-id="aff0b-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![Screenshot della finestra fatturazione e opzioni di menu.](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="aff0b-123">Selezionare un prodotto per cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="aff0b-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="aff0b-124">Microsoft Teams fa parte dello SKU gratuito di Office 365 A1 per studenti.</span><span class="sxs-lookup"><span data-stu-id="aff0b-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![Screenshot della pagina Licenze con i prodotti disponibili per l'assegnazione di licenze.](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="aff0b-126">Selezionare **Assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="aff0b-126">Select **Assign licenses**.</span></span>

   ![Schermata della sezione Utenti della pagina e dell'opzione Assegna licenze con un segno più davanti all'opzione.](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="aff0b-128">Nel riquadro **Assegna licenze agli utenti** iniziare a digitare un nome. Dovrebbe essere visualizzato un elenco di nomi.</span><span class="sxs-lookup"><span data-stu-id="aff0b-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="aff0b-129">Scegliere il nome che si sta cercando dai risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="aff0b-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="aff0b-130">È possibile aggiungere fino a 20 utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="aff0b-130">You can add up to 20 users at a time.</span></span>

   ![Screenshot della pagina Assegna licenze agli utenti, con un nome parziale digitato, che mostra i risultati della ricerca per il nome parziale.](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="aff0b-132">Selezionare **Abilita o disabilita le app e i servizi** per assegnare o rimuovere l'accesso a elementi specifici, ad esempio Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aff0b-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="aff0b-133">Verificare che **Microsoft Teams** e **Office per il Web (istruzione)** siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="aff0b-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="aff0b-134">Al termine, selezionare **Assegna**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="aff0b-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="aff0b-135">Per modificare le app e i servizi a cui un utente ha accesso:</span><span class="sxs-lookup"><span data-stu-id="aff0b-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="aff0b-136">Selezionare la riga che contiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="aff0b-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="aff0b-137">Nel riquadro destro selezionare o deselezionare le app e i servizi per i quali si vuole consentire o rimuovere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="aff0b-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="aff0b-138">Al termine, selezionare **Salva**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="aff0b-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="aff0b-139">Assegnare licenze a un singolo utente o a più utenti nella pagina Utenti attivi</span><span class="sxs-lookup"><span data-stu-id="aff0b-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="aff0b-140">Nell'interfaccia di amministrazione passare alla pagina **Utenti** > [Utenti attivi](https://go.microsoft.com/fwlink/p/?linkid=834822).</span><span class="sxs-lookup"><span data-stu-id="aff0b-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Screenshot dell'opzione di menu Utenti attivi nell'interfaccia di amministrazione di Microsoft Office 365.](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="aff0b-142">Selezionare i cerchi accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="aff0b-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![Screenshot della pagina Utenti attivi e un elenco di utenti attivi nella pagina, con alcuni utenti selezionati perché il cerchio accanto ai nomi corrispondenti è pieno.](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="aff0b-144">Nella parte superiore selezionare**Gestisci licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="aff0b-144">At the top select **Manage product licenses**.</span></span>

   ![Screenshot della scheda Gestisci licenze prodotto, con un utente indicato come senza licenza.](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="aff0b-146">Nel riquadro **Gestisci licenze prodotto** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** > **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aff0b-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![Screenshot della finestra Gestisci licenze di prodotto, con il pulsante di opzione Aggiungi ad assegnazioni licenze prodotto esistenti selezionata.](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="aff0b-148">Nel riquadro **Aggiungi a prodotti esistenti** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza che si vuole assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="aff0b-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="aff0b-149">Verificare che **Microsoft Teams** e **Office per il Web (istruzione)** siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="aff0b-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![Screenshot con Microsoft Teams e Office per il Web (istruzione), selezionati nella scheda Aggiungi a prodotti esistenti.](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="aff0b-151">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="aff0b-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="aff0b-152">È possibile limitare i servizi disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="aff0b-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="aff0b-153">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si vogliono assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="aff0b-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="aff0b-154">Nella parte inferiore del riquadro selezionare Aggiungi > Chiudi.</span><span class="sxs-lookup"><span data-stu-id="aff0b-154">At the bottom of the pane, select Add > Close.</span></span>
