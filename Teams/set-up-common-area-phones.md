---
title: Configurare la licenza Telefono area comune
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
description: "Informazioni su come configurare i telefoni dell'area comune per lobby, aree di ricezione e sale riunioni "
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117114"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="ed531-103">Configurare la licenza dell'area Telefono per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed531-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="ed531-104">I telefoni dell'area comune non supportano la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="ed531-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="ed531-105">Un telefono di area comune è in genere posizionato in un'area come una sala d'attesa o un'altra area che è disponibile a molte persone per effettuare una chiamata; ad esempio un'area di ricezione, una sala d'attesa o un telefono per conferenze.</span><span class="sxs-lookup"><span data-stu-id="ed531-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="ed531-106">I telefoni dell'area comune sono connessi con account collegati a una licenza di area Telefono comune.</span><span class="sxs-lookup"><span data-stu-id="ed531-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="ed531-107">Anche il criterio TeamsIPPhone deve essere impostato in modo appropriato perché il telefono abbia un'esperienza utente nell'area comune.</span><span class="sxs-lookup"><span data-stu-id="ed531-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="ed531-108">Nei passaggi seguenti verrà illustrato come configurare un account per Sistema telefonico per distribuire telefoni ad area comune per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ed531-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="ed531-109">Per un'esperienza più completa nelle sale riunioni, inclusa l'audioconferenza, è consigliabile acquistare la licenza Sala riunioni con un dispositivo della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="ed531-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="ed531-110">Prima di tutto, è necessario acquistare una licenza di Common Area Telefono (CAP) e assicurarsi di avere un telefono certificato.</span><span class="sxs-lookup"><span data-stu-id="ed531-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="ed531-111">Per cercare e altre informazioni sui telefoni certificati, vai a Microsoft Teams [dispositivi.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="ed531-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="ed531-112">Passaggio 1: acquista le licenze</span><span class="sxs-lookup"><span data-stu-id="ed531-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="ed531-113">Nell'Microsoft 365 di amministrazione, passare a **Servizi** di acquisto fatturazione  >   e quindi espandere **Altri piani.**</span><span class="sxs-lookup"><span data-stu-id="ed531-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Screenshot che mostra il riquadro Telefono area comune](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="ed531-115">Selezionare **Area comune Telefono** Acquista  >  **ora**.</span><span class="sxs-lookup"><span data-stu-id="ed531-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="ed531-116">Nella pagina Checkout fare clic su **Acquista ora.**</span><span class="sxs-lookup"><span data-stu-id="ed531-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="ed531-117">Espandere **Abbonamenti ai componenti aggiuntivi e** quindi fare clic per acquistare un piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="ed531-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="ed531-118">Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.</span><span class="sxs-lookup"><span data-stu-id="ed531-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="ed531-119">Se si usa Telefono Microsoft sistema di routing diretto, non è necessaria una licenza per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ed531-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="ed531-120">Non è necessario aggiungere una licenza Sistema telefonico licenza.</span><span class="sxs-lookup"><span data-stu-id="ed531-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="ed531-121">È inclusa con la licenza per il Telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="ed531-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="ed531-122">Per altre informazioni sulle licenze, vedere Microsoft Teams [licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="ed531-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="ed531-123">La licenza common area Telefono supporta:</span><span class="sxs-lookup"><span data-stu-id="ed531-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="ed531-124">Telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="ed531-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="ed531-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ed531-125">Skype for Business</span></span> |   <span data-ttu-id="ed531-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="ed531-126">&#x2714;</span></span> |
|<span data-ttu-id="ed531-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed531-127">Microsoft Teams</span></span> |   <span data-ttu-id="ed531-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="ed531-128">&#x2714;</span></span> |
|<span data-ttu-id="ed531-129">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="ed531-129">Phone System</span></span> |    <span data-ttu-id="ed531-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="ed531-130">&#x2714;</span></span> |
|<span data-ttu-id="ed531-131">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="ed531-131">Audio Conferencing</span></span> |       <span data-ttu-id="ed531-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="ed531-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="ed531-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ed531-133">Microsoft Intune</span></span> |    <span data-ttu-id="ed531-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="ed531-134">&#x2718;</span></span> |
|<span data-ttu-id="ed531-135">Disponibilità in tutto il mondo</span><span class="sxs-lookup"><span data-stu-id="ed531-135">Worldwide Availability</span></span> |       <span data-ttu-id="ed531-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="ed531-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="ed531-137">Disponibilità del canale</span><span class="sxs-lookup"><span data-stu-id="ed531-137">Channel Availability</span></span> |    <span data-ttu-id="ed531-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="ed531-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="ed531-139">&sup1; Area comune I telefoni possono partecipare a conferenze audio tramite il numero di accesso fornito dall'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="ed531-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="ed531-140">&sup2; Non disponibile nei cloud sovrani</span><span class="sxs-lookup"><span data-stu-id="ed531-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="ed531-141">Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze</span><span class="sxs-lookup"><span data-stu-id="ed531-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="ed531-142">Nell'Microsoft 365 di amministrazione passare **a** Utenti utenti attivi  >    >  **che aggiungono un utente.**</span><span class="sxs-lookup"><span data-stu-id="ed531-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="ed531-143">Immettere un nome utente come "Principale" per il nome e "Ricezione" per il secondo nome.</span><span class="sxs-lookup"><span data-stu-id="ed531-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="ed531-144">Immettere un nome visualizzato se non lo rigenera automaticamente, ad esempio "Ricezione principale".</span><span class="sxs-lookup"><span data-stu-id="ed531-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="ed531-145">Immettere un nome utente come "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="ed531-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="ed531-146">Per i telefoni dell'area comune, è consigliabile impostare manualmente una password o avere la stessa password per tutti i telefoni dell'area comune.</span><span class="sxs-lookup"><span data-stu-id="ed531-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="ed531-147">Inoltre, è consigliabile deselezionare la casella di controllo Imposta come utente la **modifica della password** al primo accesso.</span><span class="sxs-lookup"><span data-stu-id="ed531-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="ed531-148">Assegnare le licenze all'utente.</span><span class="sxs-lookup"><span data-stu-id="ed531-148">Assign the licenses to the user.</span></span> <span data-ttu-id="ed531-149">Nella stessa pagina, fai clic per espandere **Licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="ed531-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="ed531-150">Attiva l'area comune Telefono e scegli un **piano** per chiamate nazionali o un piano per chiamate nazionali **e internazionali.**</span><span class="sxs-lookup"><span data-stu-id="ed531-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Screenshot che mostra l'assegnazione delle licenze](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="ed531-152">Se si usa il Telefono Microsoft System Direct Routing, non è necessario assegnare una licenza per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ed531-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="ed531-153">Per altre informazioni, vedere [Assegnare licenze agli utenti.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="ed531-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="ed531-154">Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="ed531-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="ed531-155">Usare l Teams di amministrazione per assegnare un numero all'utente.</span><span class="sxs-lookup"><span data-stu-id="ed531-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="ed531-156">Nell'Teams di amministrazione selezionare Numeri  >  **Telefono vocali**.</span><span class="sxs-lookup"><span data-stu-id="ed531-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="ed531-157">Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.</span><span class="sxs-lookup"><span data-stu-id="ed531-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="ed531-158">Nella **casella** Utente vocale della pagina Assegna digitare il nome dell'utente che usa il telefono e quindi selezionarlo nell'elenco **a** discesa Selezionare un utente vocale.</span><span class="sxs-lookup"><span data-stu-id="ed531-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="ed531-159">Successivamente, è necessario aggiungere un indirizzo per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ed531-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="ed531-160">Scegliere **Cerca per città,** Cerca  per descrizione o Cerca per posizione nell'elenco a discesa e quindi immettere la città, la descrizione o la posizione nella casella di testo. </span><span class="sxs-lookup"><span data-stu-id="ed531-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="ed531-161">Dopo aver cercato, cerca in **Seleziona l'indirizzo per gli interventi** di emergenza per scegliere quello giusto per te.</span><span class="sxs-lookup"><span data-stu-id="ed531-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="ed531-162">Clicca su **Salvare** e il tuo utente dovrebbe apparire così:</span><span class="sxs-lookup"><span data-stu-id="ed531-162">Click **Save** and your user should look like this:</span></span>

   ![Screenshot che mostra l'assegnazione delle licenze](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="ed531-164">Gli utenti verranno visualizzati solo se è applicata una Sistema telefonico licenza.</span><span class="sxs-lookup"><span data-stu-id="ed531-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="ed531-165">Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ed531-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="ed531-166">Per altre informazioni, vedere [Ottenere numeri di telefono per gli utenti.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="ed531-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="ed531-167">Puoi anche prendere il tuo numero di telefono che hai con un altro gestore e "porta" o trasferirlo su Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed531-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ed531-168">Vedere [Trasferire numeri di telefono Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ed531-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>