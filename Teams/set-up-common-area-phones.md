---
title: Configurare la licenza Common Area Phone
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Informazioni su come configurare Common Area Phones per lobbies, le aree di ricezione e le sale riunioni '
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476711"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="b9d2d-103">Configurare la licenza Common Area Phone per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9d2d-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="b9d2d-104">I telefoni nell'area comune non supportano la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="b9d2d-105">Un telefono ad area comune viene in genere inserito in un'area, ad esempio una sala d'attesa o un'altra area disponibile a molte persone per effettuare una chiamata; ad esempio un'area della reception, una sala d'attesa o un telefono da conferenza.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="b9d2d-106">I telefoni dell'area comune sono connessi con account collegati a una licenza Common Area Phone.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="b9d2d-107">Anche il criterio TeamsIPPhone deve essere impostato in modo appropriato perché il telefono abbia un'esperienza utente nell'area comune.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="b9d2d-108">Nei passaggi seguenti verrà illustrato come configurare un account per Sistema telefonico per distribuire i telefoni dell'area comune per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="b9d2d-109">Per un'esperienza di sala riunioni più completa, compresa l'audioconferenza, valutare l'acquisto della licenza dedicata per la sala riunioni con un dispositivo per la sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="b9d2d-110">Prima di tutto, è necessario acquistare una licenza Common Area Phone (CAP) e assicurarsi di avere un telefono certificato.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="b9d2d-111">Per cercare e ottenere altre informazioni sui telefoni certificati, vai ai [dispositivi Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="b9d2d-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="b9d2d-112">Passaggio 1: acquista le licenze</span><span class="sxs-lookup"><span data-stu-id="b9d2d-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="b9d2d-113">Nell'interfaccia di amministrazione di Microsoft 365 passare a **Acquisto** di fatturazione  >  **e** quindi espandere **Altri piani.**</span><span class="sxs-lookup"><span data-stu-id="b9d2d-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Screenshot che mostra il riquadro Telefono area comune](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="b9d2d-115">Seleziona **Acquista telefono area comune**  >  **ora.**</span><span class="sxs-lookup"><span data-stu-id="b9d2d-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="b9d2d-116">Nella pagina Cassa fare clic **su Acquista ora.**</span><span class="sxs-lookup"><span data-stu-id="b9d2d-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="b9d2d-117">Espandi **gli abbonamenti a componenti aggiuntivi** e quindi fai clic per acquistare un piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="b9d2d-118">Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="b9d2d-119">Se si utilizza l'instradamento diretto del Sistema telefonico Microsoft, non è necessaria una licenza per il Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="b9d2d-120">Non è necessario aggiungere una licenza Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="b9d2d-121">È inclusa con la licenza per il Telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="b9d2d-122">Per altre informazioni sulle licenze, vedere [licenze per i componenti aggiuntivi di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="b9d2d-122">For more information on licenses, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="b9d2d-123">La licenza Common Area Phone supporta:</span><span class="sxs-lookup"><span data-stu-id="b9d2d-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="b9d2d-124">Telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="b9d2d-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="b9d2d-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b9d2d-125">Skype for Business</span></span> |   <span data-ttu-id="b9d2d-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="b9d2d-126">&#x2714;</span></span> |
|<span data-ttu-id="b9d2d-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9d2d-127">Microsoft Teams</span></span> |   <span data-ttu-id="b9d2d-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="b9d2d-128">&#x2714;</span></span> |
|<span data-ttu-id="b9d2d-129">Phone System</span><span class="sxs-lookup"><span data-stu-id="b9d2d-129">Phone System</span></span> |    <span data-ttu-id="b9d2d-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="b9d2d-130">&#x2714;</span></span> |
|<span data-ttu-id="b9d2d-131">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b9d2d-131">Audio Conferencing</span></span> |       <span data-ttu-id="b9d2d-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="b9d2d-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="b9d2d-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b9d2d-133">Microsoft Intune</span></span> |    <span data-ttu-id="b9d2d-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="b9d2d-134">&#x2718;</span></span> |
|<span data-ttu-id="b9d2d-135">Disponibilità in tutto il mondo</span><span class="sxs-lookup"><span data-stu-id="b9d2d-135">Worldwide Availability</span></span> |       <span data-ttu-id="b9d2d-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="b9d2d-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="b9d2d-137">Disponibilità dei canali</span><span class="sxs-lookup"><span data-stu-id="b9d2d-137">Channel Availability</span></span> |    <span data-ttu-id="b9d2d-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="b9d2d-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="b9d2d-139">&sup1; I telefoni dell'area comune possono accedere alle audioconferezioni tramite un numero di telefono fornito dall'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="b9d2d-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="b9d2d-140">&sup2; Non disponibile nei cloud sovereign</span><span class="sxs-lookup"><span data-stu-id="b9d2d-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="b9d2d-141">Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze</span><span class="sxs-lookup"><span data-stu-id="b9d2d-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="b9d2d-142">Nell'interfaccia di amministrazione di Microsoft 365 passare **agli** utenti attivi e  >    >  **aggiungere un utente.**</span><span class="sxs-lookup"><span data-stu-id="b9d2d-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="b9d2d-143">Immettere un nome utente come "Principale" per il nome e "Ricezione" per il secondo nome.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="b9d2d-144">Immettere un nome visualizzato se non viene rigenerato automaticamente, ad esempio "Ricezione principale".</span><span class="sxs-lookup"><span data-stu-id="b9d2d-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="b9d2d-145">Immettere un nome utente, ad esempio "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="b9d2d-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="b9d2d-146">Per i telefoni dell'area comune, può essere necessario impostare manualmente una password o avere la stessa password per tutti i telefoni dell'area comune.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="b9d2d-147">È anche consigliabile deselezionare la casella di controllo Imposta questo utente per cambiare **la password** al primo accesso.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="b9d2d-148">Assegnare le licenze all'utente.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-148">Assign the licenses to the user.</span></span> <span data-ttu-id="b9d2d-149">Nella stessa pagina, fai clic per espandere **Licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="b9d2d-150">Attiva il Common Area Phone e scegli un Piano **per** chiamate nazionali o Un Piano per chiamate nazionali **e internazionali.**</span><span class="sxs-lookup"><span data-stu-id="b9d2d-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Screenshot che mostra l'assegnazione di licenze](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="b9d2d-152">Se si utilizza l'instradamento diretto del Sistema telefonico Microsoft, non è necessario assegnare una licenza per un Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="b9d2d-153">Per altre informazioni, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="b9d2d-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="b9d2d-154">Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="b9d2d-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="b9d2d-155">Usare l'interfaccia di amministrazione di Teams per assegnare un numero all'utente.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="b9d2d-156">Nell'interfaccia di amministrazione di Teams selezionare **Numeri**  >  **di telefono vocali.**</span><span class="sxs-lookup"><span data-stu-id="b9d2d-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="b9d2d-157">Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="b9d2d-158">Nella casella **Utente** vocale della pagina Assegna digita il nome dell'utente che usa il telefono e quindi seleziona l'utente nell'elenco **a** discesa Seleziona un utente vocale.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="b9d2d-159">Successivamente, è necessario aggiungere un indirizzo per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="b9d2d-160">Scegliere **Cerca per città,** Cerca  per descrizione o Cerca per località nell'elenco a discesa e quindi immettere la città, la descrizione o il luogo nella casella di testo. </span><span class="sxs-lookup"><span data-stu-id="b9d2d-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="b9d2d-161">Dopo aver cercato, cerca in **Seleziona l'indirizzo per** gli interventi di emergenza e scegli quello giusto per te.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="b9d2d-162">Clicca su **Salvare** e il tuo utente dovrebbe apparire così:</span><span class="sxs-lookup"><span data-stu-id="b9d2d-162">Click **Save** and your user should look like this:</span></span>

   ![Screenshot che mostra l'assegnazione di licenze](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="b9d2d-164">Gli utenti verranno visualizzati solo se hanno una licenza Sistema telefonico applicata.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="b9d2d-165">Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="b9d2d-166">Per ulteriori informazioni, consulta [Recupero di numeri di telefono per gli utenti.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="b9d2d-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="b9d2d-167">Puoi anche trasferire il tuo numero di telefono con un altro gestore e la "porta" oppure trasferirlo a Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9d2d-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="b9d2d-168">Vedi [Trasferire numeri di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b9d2d-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
