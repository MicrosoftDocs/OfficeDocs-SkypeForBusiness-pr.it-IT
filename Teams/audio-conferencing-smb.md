---
title: Configurare audioconferenze per piccole e medie imprese
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Informazioni su come impostare i servizi di audioconferenza nelle piccole o medie imprese per le persone che devono usare un telefono per accedere alle riunioni. '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122350"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="a0801-103">Configurare audioconferenze per piccole e medie imprese</span><span class="sxs-lookup"><span data-stu-id="a0801-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="a0801-104">Con le audioconferenze, le persone possono accedere alle riunioni Teams tramite telefono invece di usare l'app Teams sul dispositivo mobile o dal computer.</span><span class="sxs-lookup"><span data-stu-id="a0801-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="a0801-105">Se si è una piccola o media azienda con un massimo di 300 utenti e attualmente non si hanno licenze di audioconferenza, è possibile ottenere servizi di audioconferenza gratuiti per un anno.</span><span class="sxs-lookup"><span data-stu-id="a0801-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="a0801-106">Questa offerta gratuita è disponibile a partire dal 1° ottobre 2020.</span><span class="sxs-lookup"><span data-stu-id="a0801-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="a0801-107">La licenza del componente aggiuntivo Audioconferenza può essere applicata agli utenti con licenze Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 o Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="a0801-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="a0801-108">Per altre informazioni, vedere Teams [licenze per i componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="a0801-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="a0801-109">Se hai Enterprise E5 o Microsoft 365 Business Voice, non potrai usare l'offerta di audioconferenza gratuita perché queste licenze includono già audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="a0801-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="a0801-110">Questo articolo illustra come configurare le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="a0801-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="a0801-111">È necessario soltanto configurare l'audioconferenza solo per gli utenti che intendono programmare o condurre riunioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="a0801-112">I partecipanti alla riunione che chiamano alle riunioni non hanno bisogno di licenze o altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="a0801-113">Per altre informazioni, vedere [Audioconferenza.](audio-conferencing-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a0801-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="a0801-114">Configurare l’audioconferenza</span><span class="sxs-lookup"><span data-stu-id="a0801-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="a0801-115">Quando si configurano le audioconferenze, al bridge di conferenza viene assegnato automaticamente un numero di telefono in modo che possa essere usato negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="a0801-116">Il numero di telefono assegnato come numero predefinito del bridge di conferenza sarà uno del paese o dell'area geografica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0801-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="a0801-117">Questo numero di telefono è un numero a pagamento, in cui possono essere applicati addebiti a lunga distanza.</span><span class="sxs-lookup"><span data-stu-id="a0801-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="a0801-118">È anche possibile usare un numero verde, che richiede alcuni passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="a0801-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="a0801-119">Per altre informazioni sui numeri di telefono per il bridge di conferenza, vedere Numeri di telefono per i servizi di [audioconferenza](#audio-conferencing-phone-numbers) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a0801-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="a0801-120">Passaggio 1: Ottenere licenze di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="a0801-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="a0801-121">Ottieni una licenza per i servizi di audioconferenza per ogni persona che condurrà le riunioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="a0801-122">Usare l'Microsoft 365 di amministrazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="a0801-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="a0801-123">Nell'Microsoft 365 di amministrazione, passare a **Servizi** di acquisto fatturazione e quindi nella parte inferiore della pagina  >  selezionare **Componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a0801-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="a0801-124">Selezionare **Microsoft 365 dettagli promozionali sull'adozione di audioconferenze** e quindi selezionare Scarica  >   **adesso.**</span><span class="sxs-lookup"><span data-stu-id="a0801-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="a0801-125">Immettere il numero di licenze necessarie per gli organizzatori della riunione e quindi completare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="a0801-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Screenshot della licenza promozionale Per l'adozione di audioconferenze":::

    > [!NOTE]
    > <span data-ttu-id="a0801-127">Deselezionare o selezionare l'opzione Assegna automaticamente a tutti gli utenti senza **licenze,** a seconda che si voglia assegnare automaticamente una licenza di audioconferenza a tutti gli utenti che non hanno questa licenza.</span><span class="sxs-lookup"><span data-stu-id="a0801-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="a0801-128">Passaggio 2: Assegnare una licenza di audioconferenza agli utenti che conducono le riunioni</span><span class="sxs-lookup"><span data-stu-id="a0801-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="a0801-129">Assegnare una licenza a ogni persona che condurrà le riunioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="a0801-130">Usare l'Microsoft 365 di amministrazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="a0801-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="a0801-131">Assegnare una licenza a un utente</span><span class="sxs-lookup"><span data-stu-id="a0801-131">Assign a license to one user</span></span>

1. <span data-ttu-id="a0801-132">Nell'Microsoft 365 di amministrazione passare a **Utenti**  >  **attivi**.</span><span class="sxs-lookup"><span data-stu-id="a0801-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="a0801-133">Selezionare la riga dell'utente a cui si vuole assegnare la licenza e quindi nel riquadro selezionare **Licenze e app.**</span><span class="sxs-lookup"><span data-stu-id="a0801-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="a0801-134">Selezionare la **Microsoft 365 audioconferenza** e quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a0801-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="a0801-135">Assegnare una licenza a più utenti</span><span class="sxs-lookup"><span data-stu-id="a0801-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="a0801-136">Nell'Microsoft 365 di amministrazione passare a **Utenti**  >  **attivi**.</span><span class="sxs-lookup"><span data-stu-id="a0801-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="a0801-137">Selezionare i cerchi accanto agli utenti a cui si vuole assegnare la licenza e quindi selezionare **Gestisci licenze prodotto.**</span><span class="sxs-lookup"><span data-stu-id="a0801-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="a0801-138">Nel riquadro **Gestisci licenze prodotto** selezionare Assegna **altro**.</span><span class="sxs-lookup"><span data-stu-id="a0801-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="a0801-139">Selezionare la **Microsoft 365 audioconferenza** e quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a0801-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="a0801-140">Pianificare Teams riunioni in Outlook</span><span class="sxs-lookup"><span data-stu-id="a0801-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="a0801-141">Gli organizzatori della riunione possono ora pianificare le riunioni in Outlook.</span><span class="sxs-lookup"><span data-stu-id="a0801-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="a0801-142">In Outlook passare a **Calendario** e quindi selezionare il **pulsante Nuovo Teams riunione.**</span><span class="sxs-lookup"><span data-stu-id="a0801-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="a0801-143">I numeri di accesso esterno della riunione e l'ID conferenza vengono aggiunti automaticamente all'invito alla riunione inviato ai partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="a0801-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="a0801-144">Per altre informazioni, vedere [Pianificare una riunione Teams in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span><span class="sxs-lookup"><span data-stu-id="a0801-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="a0801-145">Se si vuole, è possibile personalizzare gli inviti alle riunioni per aggiungere il logo della società, i collegamenti al sito Web del supporto tecnico e alla dichiarazione di non responsabilità legale e un piè di pagina di solo testo.</span><span class="sxs-lookup"><span data-stu-id="a0801-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="a0801-146">Per altre informazioni, vedere [Personalizzare gli inviti alle riunioni.](meeting-settings-in-teams.md#customize-meeting-invitations)</span><span class="sxs-lookup"><span data-stu-id="a0801-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="a0801-147">Numeri di telefono per audioconferenze</span><span class="sxs-lookup"><span data-stu-id="a0801-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="a0801-148">Per il bridge di conferenza è possibile usare due tipi di numeri.</span><span class="sxs-lookup"><span data-stu-id="a0801-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="a0801-149">È possibile usare **i numeri condivisi** (come nella sezione Configurare le audioconferenze più indietro in questo articolo) o **numeri dedicati.** [](#set-up-audio-conferencing)</span><span class="sxs-lookup"><span data-stu-id="a0801-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="a0801-150">Ecco altre informazioni su ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="a0801-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="a0801-151">Numeri condivisi</span><span class="sxs-lookup"><span data-stu-id="a0801-151">Shared numbers</span></span>

<span data-ttu-id="a0801-152">Un numero condiviso è un numero condiviso in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="a0801-153">I numeri condivisi sono numeri a pedaggio e vengono assegnati automaticamente quando si configurano le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="a0801-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="a0801-154">Per visualizzare il numero predefinito assegnato al bridge di conferenza, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Bridge di conferenza riunioni e quindi trovare il numero della posizione più  >  vicina.</span><span class="sxs-lookup"><span data-stu-id="a0801-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="a0801-155">Numeri dedicati</span><span class="sxs-lookup"><span data-stu-id="a0801-155">Dedicated numbers</span></span>

<span data-ttu-id="a0801-156">Un numero dedicato è un numero disponibile solo per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a0801-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="a0801-157">Un numero dedicato può essere un numero a pedaggio o un numero verde.</span><span class="sxs-lookup"><span data-stu-id="a0801-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="a0801-158">Per usare un numero dedicato, è necessario prima ottenere il numero, assegnarlo al bridge di conferenza e quindi assegnare il numero a ogni persona che condurrà le riunioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="a0801-159">Esistono due modi per ottenere un numero dedicato.</span><span class="sxs-lookup"><span data-stu-id="a0801-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="a0801-160">È possibile ottenere un numero da Microsoft o trasferire (porta) un numero esistente dal provider di servizi corrente a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0801-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="a0801-161">Per altre informazioni su come eseguire questa operazione, vedere Recupero [dei numeri di servizio.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="a0801-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="a0801-162">Tenere presente che se si usa un numero verde, è necessario assegnare prima una licenza Crediti comunicazioni a ogni persona che condurrà le riunioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="a0801-163">Per altre informazioni, vedere [Configurare i crediti comunicazioni per l'organizzazione.](set-up-communications-credits-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="a0801-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="a0801-164">Dopo aver assegnato il numero, assegnarlo al bridge di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a0801-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="a0801-165">Usare l'Microsoft Teams di amministrazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="a0801-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="a0801-166">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a Bridge  >  **di conferenza riunioni.**</span><span class="sxs-lookup"><span data-stu-id="a0801-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="a0801-167">Selezionare **Aggiungi** e quindi **selezionare Numero a pedaggio** o Numero **verde.**</span><span class="sxs-lookup"><span data-stu-id="a0801-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="a0801-168">Nel riquadro **Aggiungi numero di** telefono selezionare il numero e quindi scegliere **Applica**.</span><span class="sxs-lookup"><span data-stu-id="a0801-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="a0801-169">Assegnare quindi il numero a ogni persona che condurrà le riunioni.</span><span class="sxs-lookup"><span data-stu-id="a0801-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="a0801-170">Usare l'Microsoft Teams di amministrazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="a0801-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="a0801-171">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione selezionare **Utenti,** fare clic sul nome visualizzato dell'utente e selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="a0801-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="a0801-172">Selezionare **Modifica** accanto a **Audioconferenza** e quindi, nel riquadro  **Audioconferenza,** selezionare un numero negli elenchi Numero a pedaggio o Numero verde e quindi selezionare **Applica**. </span><span class="sxs-lookup"><span data-stu-id="a0801-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0801-173">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a0801-173">Related topics</span></span>

- [<span data-ttu-id="a0801-174">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="a0801-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="a0801-175">Configurare le audioconferenze per Teams</span><span class="sxs-lookup"><span data-stu-id="a0801-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="a0801-176">Numeri di telefono per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="a0801-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="a0801-177">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="a0801-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="a0801-178">Recupero dei numeri di servizio</span><span class="sxs-lookup"><span data-stu-id="a0801-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="a0801-179">Teams licenze per i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="a0801-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="a0801-180">Assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="a0801-180">Assign licenses to users</span></span>](/microsoft-365/admin/manage/assign-licenses-to-users)