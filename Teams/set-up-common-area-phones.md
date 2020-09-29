---
title: Configurare la licenza telefonica per l'area comune
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
description: "Informazioni su come configurare i telefoni per l'area comune per atri, aree di ricezione e sale conferenze "
ms.openlocfilehash: dfde8c601c0a52dc56a3d76903b788400a5b299a
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294462"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="fd2c3-103">Configurare la licenza telefonica per l'area comune per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd2c3-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="fd2c3-104">I telefoni delle aree comuni non supportano la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="fd2c3-105">Un telefono con area comune viene in genere posizionato in un'area come una sala d'attesa o in un'altra area disponibile per molti utenti per effettuare una chiamata; ad esempio, un'area di ricezione, una sala d'attesa o un telefono per conferenze.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="fd2c3-106">I telefoni delle aree comuni sono connessi con gli account collegati a una licenza telefonica per l'area comune.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="fd2c3-107">Anche il criterio TeamsIPPhone deve essere impostato in modo appropriato per consentire al telefono di avere un'esperienza utente nell'area comune.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="fd2c3-108">Nei passaggi seguenti ti aiuteremo a configurare un account per il sistema telefonico per la distribuzione dei telefoni delle aree comuni per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="fd2c3-109">Per un'esperienza di sala riunioni più completa, inclusi i servizi di audioconferenza, valutare l'acquisto della licenza dedicata sala riunioni con un dispositivo della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="fd2c3-110">Prima di tutto, è necessario acquistare una licenza per un telefono con area comune (CAP) e assicurarsi di avere un telefono certificato.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="fd2c3-111">Per cercare e ottenere ulteriori informazioni sui telefoni certificati, vedere [dispositivi Microsoft teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="fd2c3-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="fd2c3-112">Passaggio 1: acquista le licenze</span><span class="sxs-lookup"><span data-stu-id="fd2c3-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="fd2c3-113">Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Billing**  >  **servizi di acquisto** fatturazione e quindi espandere **altri piani**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Screenshot che mostra il riquadro Telefono area comune](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="fd2c3-115">Selezionare Acquista **telefono area comune**  >  **ora**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="fd2c3-116">Nella pagina estrazione fare clic su **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="fd2c3-117">Espandere **abbonamenti a componenti aggiuntivi** e quindi fare clic per acquistare un piano per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="fd2c3-118">Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="fd2c3-119">Se si usa il routing diretto di Microsoft Phone System, non è necessaria una licenza per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="fd2c3-120">Non è necessario aggiungere una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="fd2c3-121">È inclusa con la licenza per il Telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="fd2c3-122">Per altre informazioni sulle licenze, vedere [licenze per i componenti aggiuntivi Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="fd2c3-122">For more information on licenses, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="fd2c3-123">La licenza telefonica per l'area comune supporta:</span><span class="sxs-lookup"><span data-stu-id="fd2c3-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="fd2c3-124">Telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="fd2c3-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="fd2c3-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd2c3-125">Skype for Business</span></span> |   <span data-ttu-id="fd2c3-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fd2c3-126">&#x2714;</span></span> |
|<span data-ttu-id="fd2c3-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd2c3-127">Microsoft Teams</span></span> |   <span data-ttu-id="fd2c3-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fd2c3-128">&#x2714;</span></span> |
|<span data-ttu-id="fd2c3-129">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="fd2c3-129">Phone System</span></span> |    <span data-ttu-id="fd2c3-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fd2c3-130">&#x2714;</span></span> |
|<span data-ttu-id="fd2c3-131">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="fd2c3-131">Audio Conferencing</span></span> |       <span data-ttu-id="fd2c3-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="fd2c3-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="fd2c3-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fd2c3-133">Microsoft Intune</span></span> |    <span data-ttu-id="fd2c3-134">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fd2c3-134">&#x2714;</span></span> |
|<span data-ttu-id="fd2c3-135">Disponibilità mondiale</span><span class="sxs-lookup"><span data-stu-id="fd2c3-135">Worldwide Availability</span></span> |       <span data-ttu-id="fd2c3-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="fd2c3-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="fd2c3-137">Disponibilità del canale</span><span class="sxs-lookup"><span data-stu-id="fd2c3-137">Channel Availability</span></span> |    <span data-ttu-id="fd2c3-138">EA, EAS, CSP, GCC, SEO, Web Direct</span><span class="sxs-lookup"><span data-stu-id="fd2c3-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="fd2c3-139">&sup1; I telefoni per l'area comune possono partecipare a conferenze audio tramite il numero di accesso esterno fornito dall'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="fd2c3-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="fd2c3-140">&sup2; Non disponibile in nubi sovrane</span><span class="sxs-lookup"><span data-stu-id="fd2c3-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="fd2c3-141">Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze</span><span class="sxs-lookup"><span data-stu-id="fd2c3-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="fd2c3-142">Nell'interfaccia di amministrazione di Microsoft 365, passa **a utenti**attivi gli utenti che  >  **active users**  >  **aggiungono un utente**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="fd2c3-143">Immettere un nome utente come "Main" per il nome e la "ricezione" per il secondo nome.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="fd2c3-144">Immettere un nome visualizzato se non genera automaticamente uno come "ricezione principale".</span><span class="sxs-lookup"><span data-stu-id="fd2c3-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="fd2c3-145">Immettere un nome utente come "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="fd2c3-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="fd2c3-146">Per i telefoni delle aree comuni, è possibile impostare una password manualmente o avere la stessa password per tutti i telefoni delle aree comuni.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="fd2c3-147">Inoltre, potresti pensare di deselezionare la casella di controllo **imposta l'utente come modificarne la password al primo accesso** .</span><span class="sxs-lookup"><span data-stu-id="fd2c3-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="fd2c3-148">Assegnare le licenze all'utente.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-148">Assign the licenses to the user.</span></span> <span data-ttu-id="fd2c3-149">Nella stessa pagina, fai clic per espandere **Licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="fd2c3-150">Attivare il telefono per l'area comune e selezionare un **piano per chiamate nazionali** o un **piano per chiamate nazionali e internazionali**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Schermata che mostra l'assegnazione delle licenze](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="fd2c3-152">Se si usa il routing diretto di Microsoft Phone System, non è necessario assegnare una licenza per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="fd2c3-153">Per altre informazioni, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="fd2c3-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="fd2c3-154">Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="fd2c3-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="fd2c3-155">Usare l'interfaccia di amministrazione di teams per assegnare un numero all'utente.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="fd2c3-156">Nell'interfaccia di amministrazione di teams **Voice**selezionare  >  **numeri di telefono**vocali.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="fd2c3-157">Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="fd2c3-158">Nella casella utente vocale della pagina **assegna** Digitare il nome dell'utente che utilizzerà il telefono e quindi selezionare l'utente nell'elenco a discesa **selezionare un utente vocale** .</span><span class="sxs-lookup"><span data-stu-id="fd2c3-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="fd2c3-159">Devi quindi aggiungere un indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="fd2c3-160">Scegliere **Cerca**in base alla città, **ricerca per Descrizione**o **Cerca in base alla posizione** dall'elenco a discesa e quindi immettere la città, la descrizione o la posizione nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="fd2c3-161">Una volta eseguita la ricerca, Cerca in **selezionare l'indirizzo di emergenza per selezionarne** uno giusto.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="fd2c3-162">Clicca su **Salvare** e il tuo utente dovrebbe apparire così:</span><span class="sxs-lookup"><span data-stu-id="fd2c3-162">Click **Save** and your user should look like this:</span></span>

   ![Schermata che mostra l'assegnazione delle licenze](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="fd2c3-164">Gli utenti verranno visualizzati solo se è stata applicata una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="fd2c3-165">Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="fd2c3-166">Per altre informazioni, vedere [recupero di numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c3-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="fd2c3-167">È anche possibile prendere il numero di telefono che si ha con un altro vettore e "porta" oppure trasferirlo in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="fd2c3-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="fd2c3-168">Vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fd2c3-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
