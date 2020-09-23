---
title: Configurare un operatore automatico per Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Informazioni su come configurare e testare gli operatori automatici per Microsoft teams.
ms.openlocfilehash: 2cb796db37f40025dc7a78123da729fd5812bbbb
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48220376"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="66095-103">Configurare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="66095-103">Set up an auto attendant</span></span>

<span data-ttu-id="66095-104">Gli operatori automatici consentono alle persone di chiamare l'organizzazione e di spostarsi in un sistema di menu per parlare con il reparto di destra, la coda di chiamata, la persona o un operatore.</span><span class="sxs-lookup"><span data-stu-id="66095-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="66095-105">È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft teams o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66095-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="66095-106">Assicurarsi di aver letto [piano per gli operatori automatici di teams e le code di chiamata](plan-auto-attendant-call-queue.md) e aver seguito i [passaggi introduttivi](plan-auto-attendant-call-queue.md#getting-started) prima di seguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="66095-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="66095-107">Gli operatori automatici possono indirizzare le chiamate, in base all'input dei chiamanti, a una delle destinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66095-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations:</span></span>

- <span data-ttu-id="66095-108">**Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="66095-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="66095-109">Può trattarsi di un utente online o di un utente ospitato in locale con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="66095-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="66095-110">**App vocale** : un altro operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="66095-111">Scegliere l'account delle risorse associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="66095-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="66095-112">**Numero di telefono esterno** -qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="66095-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="66095-113">(Vedi [Dettagli tecnici del trasferimento esterno](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="66095-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="66095-114">**Segreteria telefonica** : casella vocale associata a un gruppo Microsoft 365 specificato.</span><span class="sxs-lookup"><span data-stu-id="66095-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="66095-115">**Operator** : l'operatore definito per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66095-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="66095-116">La definizione di un operatore è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="66095-116">Defining an operator is optional.</span></span> <span data-ttu-id="66095-117">L'operatore può essere definito come una qualsiasi delle altre destinazioni in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="66095-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="66095-118">Verrà richiesto di scegliere una di queste opzioni in varie fasi durante la configurazione di un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66095-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="66095-119">Per configurare un operatore automatico, nell'interfaccia di amministrazione Team espandere **voce**, fare clic su **operatore automatico**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="66095-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="66095-120">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="66095-120">General info</span></span>

![](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="66095-121">Digitare un nome per l'operatore automatico nella casella nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="66095-121">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="66095-122">Se si vuole designare un operatore, specificare la destinazione per le chiamate all'operatore.</span><span class="sxs-lookup"><span data-stu-id="66095-122">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="66095-123">Questa opzione è facoltativa (ma consigliata).</span><span class="sxs-lookup"><span data-stu-id="66095-123">This is optional (but recommended).</span></span> <span data-ttu-id="66095-124">Puoi impostare l'opzione **operator** per consentire ai chiamanti di uscire dai menu e parlare con una persona designata.</span><span class="sxs-lookup"><span data-stu-id="66095-124">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="66095-125">Specificare il fuso orario per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66095-125">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="66095-126">Il fuso orario viene usato per calcolare le ore lavorative se si [Crea un flusso di chiamata separato per le ore successive](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="66095-126">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="66095-127">Specificare una lingua per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66095-127">Specify a language for this auto attendant.</span></span> <span data-ttu-id="66095-128">Questa è la lingua che verrà usata per le istruzioni vocali generate dal sistema.</span><span class="sxs-lookup"><span data-stu-id="66095-128">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="66095-129">Scegliere se si desidera abilitare gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="66095-129">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="66095-130">Quando è abilitata, il nome di ogni opzione del menu diventa una parola chiave per il riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="66095-130">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="66095-131">Ad esempio, i chiamanti possono pronunciare "uno" per selezionare l'opzione di menu mappata con il tasto 1 oppure possono dire "vendite" per selezionare l'opzione di menu denominata "Sales".</span><span class="sxs-lookup"><span data-stu-id="66095-131">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="66095-132">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66095-132">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="66095-133">Flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="66095-133">Call flow</span></span>

![](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="66095-134">Scegliere se si vuole riprodurre un saluto quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-134">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="66095-135">Se si seleziona **Riproduci un file audio** , è possibile usare il pulsante **Carica file** per caricare un messaggio di saluto registrato salvato come audio. WAV,. MP3 o. Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="66095-135">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="66095-136">La registrazione non può essere superiore a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="66095-136">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="66095-137">Se si seleziona **digita un messaggio di saluto** , il sistema leggerà il testo del testo digitato (fino a 1000 caratteri) quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-137">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="66095-138">Scegliere come si vuole instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-138">Choose how you want to route the call.</span></span>

<span data-ttu-id="66095-139">Se si seleziona **Disconnetti**, l'operatore automatico bloccherà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-139">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="66095-140">Se si seleziona **reindirizza chiamata**, è possibile scegliere una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="66095-140">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="66095-141">Se si seleziona **Opzioni di menu Riproduci**, è possibile scegliere di **riprodurre un file audio** o **digitare un messaggio di saluto** e quindi scegliere tra le opzioni del menu e la ricerca nella directory.</span><span class="sxs-lookup"><span data-stu-id="66095-141">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="66095-142">Opzioni di menu</span><span class="sxs-lookup"><span data-stu-id="66095-142">Menu options</span></span>

![](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="66095-143">Per le opzioni di chiamata, è possibile assegnare le chiavi di 0-9 sul tastierino telefonico a una delle destinazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="66095-143">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="66095-144">(I tasti \* (Repeat) e \# (back) sono riservati dal sistema e non possono essere riassegnati.</span><span class="sxs-lookup"><span data-stu-id="66095-144">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="66095-145">I mapping dei tasti non devono essere continui.</span><span class="sxs-lookup"><span data-stu-id="66095-145">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="66095-146">È possibile, ad esempio, creare un menu con i tasti 0, 1 e 3 mappato alle opzioni, mentre il tasto 2 non viene usato.</span><span class="sxs-lookup"><span data-stu-id="66095-146">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="66095-147">È consigliabile eseguire il mapping della chiave 0 all'operatore se è stata configurata una.</span><span class="sxs-lookup"><span data-stu-id="66095-147">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="66095-148">Se l'operatore non è impostato su un tasto qualsiasi, anche il comando vocale "operator" è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="66095-148">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="66095-149">Per ogni opzione di menu, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="66095-149">For each menu option, specify the following:</span></span>

- <span data-ttu-id="66095-150">**Tasto** di scelta rapida: il tasto sulla tastiera del telefono per accedere a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="66095-150">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="66095-151">Se sono disponibili input vocali, i chiamanti possono anche pronunciare questo numero per accedere all'opzione.</span><span class="sxs-lookup"><span data-stu-id="66095-151">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="66095-152">**Comando vocale** : definisce il comando vocale che può essere dato da un chiamante per accedere a questa opzione, se gli input vocali sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="66095-152">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="66095-153">Può contenere più parole come "Customer Service" o "Operations and grounds".</span><span class="sxs-lookup"><span data-stu-id="66095-153">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="66095-154">Ad esempio, il chiamante può premere 2, dire "due" oppure dire "vendite" per selezionare l'opzione mappata al tasto 2.</span><span class="sxs-lookup"><span data-stu-id="66095-154">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="66095-155">Questo testo viene inoltre eseguito tramite testo in sintesi vocale per la richiesta di conferma del servizio, che potrebbe essere simile a "trasferimento di una chiamata alle vendite".</span><span class="sxs-lookup"><span data-stu-id="66095-155">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="66095-156">**Reindirizza a** -la destinazione di routing delle chiamate usata quando i chiamanti scelgono questa opzione.</span><span class="sxs-lookup"><span data-stu-id="66095-156">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="66095-157">Se si reindirizza a un operatore automatico o a una coda di chiamata, scegliere l'account delle risorse associato.</span><span class="sxs-lookup"><span data-stu-id="66095-157">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="66095-158">Ricerca directory</span><span class="sxs-lookup"><span data-stu-id="66095-158">Directory search</span></span>

<span data-ttu-id="66095-159">Se si assegnano i tasti di scelta alle destinazioni, è consigliabile scegliere **nessuno** per la **ricerca nella directory**.</span><span class="sxs-lookup"><span data-stu-id="66095-159">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="66095-160">Se un chiamante tenta di chiamare un nome o un'estensione usando le chiavi assegnate a destinazioni specifiche, potrebbe essere instradato in modo imprevisto verso una destinazione prima di completare l'immissione del nome o dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="66095-160">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="66095-161">È consigliabile creare un operatore automatico distinto per la ricerca nella directory e avere il collegamento dell'operatore automatico principale tramite un tasto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-161">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="66095-162">Se non si assegnano i tasti di scelta rapida, scegliere un'opzione per la **ricerca nella directory**.</span><span class="sxs-lookup"><span data-stu-id="66095-162">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="66095-163">Chiamata **per nome** : se si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="66095-163">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="66095-164">Qualsiasi utente online con una licenza di sistema telefonico o qualsiasi utente ospitato in locale con Skype for Business Server è un utente idoneo e può essere trovato con chiamata per nome.</span><span class="sxs-lookup"><span data-stu-id="66095-164">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="66095-165">Puoi impostare chi è e non è incluso nella directory nella pagina dell'ambito di [chiamata](#dial-scope) .</span><span class="sxs-lookup"><span data-stu-id="66095-165">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="66095-166">**Dial by Extension** : se si abilita questa opzione, i chiamanti possono connettersi con gli utenti dell'organizzazione componendo l'estensione del telefono.</span><span class="sxs-lookup"><span data-stu-id="66095-166">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="66095-167">Qualsiasi utente online con una licenza di sistema telefonico o qualsiasi utente ospitato in locale con Skype for Business Server è un utente idoneo e può essere trovato con l' **estensione dial by**.</span><span class="sxs-lookup"><span data-stu-id="66095-167">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="66095-168">Puoi impostare chi è e non è incluso nella directory nella pagina dell'ambito di [chiamata](#dial-scope) .</span><span class="sxs-lookup"><span data-stu-id="66095-168">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="66095-169">Gli utenti che si desidera rendere disponibili per la chiamata tramite estensione devono avere un'estensione specificata come parte di uno degli attributi di telefono seguenti definiti in Active Directory o in Azure Active Directory (vedere [aggiungere utenti singolarmente o in blocco](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="66095-169">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="66095-170">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="66095-170">OfficePhone</span></span>
- <span data-ttu-id="66095-171">HomePhone</span><span class="sxs-lookup"><span data-stu-id="66095-171">HomePhone</span></span>
- <span data-ttu-id="66095-172">Dispositivi mobili/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="66095-172">Mobile/MobilePhone</span></span>
- <span data-ttu-id="66095-173">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="66095-173">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="66095-174">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="66095-174">OtherTelephone</span></span>

<span data-ttu-id="66095-175">Il formato obbligatorio per immettere l'estensione nel campo numero di telefono dell'utente è \* + <phone number> ext = <extension> \* o \* + <phone number> x <extension> \*.</span><span class="sxs-lookup"><span data-stu-id="66095-175">The required format to enter the extension in the user phone number field is either *+<phone number>ext=<extension>* or *+<phone number>x<extension>*.</span></span>

<span data-ttu-id="66095-176">È possibile impostare l'estensione nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/) o nell'interfaccia di [amministrazione di Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="66095-176">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="66095-177">Possono essere necessarie fino a 12 ore prima che le modifiche siano disponibili per gli operatori automatici e le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-177">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="66095-178">Se si vogliono usare sia le funzionalità **di chiamata per nome** che per l' **estensione dial by** , è possibile assegnare un tasto di chiamata nell'operatore automatico principale per raggiungere un operatore automatico abilitato per il **nome della chiamata**.</span><span class="sxs-lookup"><span data-stu-id="66095-178">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="66095-179">All'interno di tale operatore automatico è possibile assegnare il tasto 1 (senza lettere associate) per raggiungere la chiamata tramite l'operatore automatico **di estensione** .</span><span class="sxs-lookup"><span data-stu-id="66095-179">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="66095-180">Dopo aver selezionato un'opzione di **ricerca della directory** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66095-180">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="66095-181">Flusso delle chiamate per le ore successive</span><span class="sxs-lookup"><span data-stu-id="66095-181">Call flow for after hours</span></span>

![](media/auto-attendant-business-hours.png)

<span data-ttu-id="66095-182">Gli orari di ufficio possono essere impostati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66095-182">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="66095-183">Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="66095-183">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="66095-184">Gli orari di ufficio possono essere impostati con interruzioni nel tempo durante il giorno e tutte le ore che non sono impostate come orari di ufficio sono considerate after-hours.</span><span class="sxs-lookup"><span data-stu-id="66095-184">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="66095-185">È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e i messaggi di saluto per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="66095-185">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="66095-186">A seconda di come sono stati configurati gli operatori automatici e le code di chiamata, è possibile che sia necessario specificare il routing delle chiamate after-hours per gli operatori automatici con numeri di telefono diretti.</span><span class="sxs-lookup"><span data-stu-id="66095-186">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="66095-187">Se si vuole eseguire il routing delle chiamate separate per i chiamanti dopo le ore, specificare gli orari di ufficio per ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="66095-187">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="66095-188">Fare clic su **Aggiungi nuovo orario** per specificare più set di ore per un giorno specifico, ad esempio per specificare una pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="66095-188">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="66095-189">Dopo aver specificato gli orari di ufficio, scegliere le opzioni di routing delle chiamate per le ore successive.</span><span class="sxs-lookup"><span data-stu-id="66095-189">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="66095-190">Le stesse opzioni sono disponibili per il routing delle chiamate in orario di ufficio specificato sopra.</span><span class="sxs-lookup"><span data-stu-id="66095-190">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="66095-191">Al termine, fare clic su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="66095-191">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="66095-192">Flussi delle chiamate durante le festività</span><span class="sxs-lookup"><span data-stu-id="66095-192">Call flows during holidays</span></span>

![](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="66095-193">L'operatore automatico può avere un flusso di chiamata per ogni [festività configurata](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="66095-193">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="66095-194">È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66095-194">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="66095-195">Nella pagina delle impostazioni delle chiamate festive fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="66095-195">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="66095-196">Digitare un nome per l'impostazione festività.</span><span class="sxs-lookup"><span data-stu-id="66095-196">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="66095-197">Nell'elenco a discesa **festività** scegliere la festività che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="66095-197">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="66095-198">Scegliere il tipo di saluto che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="66095-198">Choose the type of greeting that you want to use.</span></span>

    ![](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="66095-199">Scegliere se si vuole **disconnettere** o **reindirizzare** la chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-199">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="66095-200">Se si è scelto di reindirizzare, scegliere la destinazione di routing delle chiamate per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-200">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="66095-201">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="66095-201">Click **Save**.</span></span>

![](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="66095-202">Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="66095-202">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="66095-203">Dopo aver aggiunto tutte le festività, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66095-203">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="66095-204">Ambito di chiamata</span><span class="sxs-lookup"><span data-stu-id="66095-204">Dial scope</span></span>

![](media/auto-attendant-dial-scope.png)

<span data-ttu-id="66095-205">L' *ambito di chiamata* definisce gli utenti disponibili nella directory quando un chiamante usa la chiamata per nome o il dial-by-Extension.</span><span class="sxs-lookup"><span data-stu-id="66095-205">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="66095-206">Il valore predefinito di **tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online con una licenza di sistema telefonico o ospitati in locale con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="66095-206">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="66095-207">È possibile includere o escludere utenti specifici selezionando un **gruppo di utenti personalizzato** in **Includi** o **Escludi** e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="66095-207">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="66095-208">Ad esempio, potresti voler escludere i dirigenti dell'organizzazione dalla directory di chiamata.</span><span class="sxs-lookup"><span data-stu-id="66095-208">For example, you might want to exclude executives in your organization from the dialing directory.</span></span>

> [!NOTE]
> <span data-ttu-id="66095-209">Per un nuovo utente potrebbe essere necessario un massimo di 36 ore per avere il nome elencato nella directory.</span><span class="sxs-lookup"><span data-stu-id="66095-209">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="66095-210">Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66095-210">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="66095-211">Account risorse</span><span class="sxs-lookup"><span data-stu-id="66095-211">Resource accounts</span></span>

<span data-ttu-id="66095-212">Tutti gli operatori automatici devono avere un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="66095-212">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="66095-213">Per gli operatori automatici di primo livello sarà necessario almeno un account delle risorse con un numero di servizio associato.</span><span class="sxs-lookup"><span data-stu-id="66095-213">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="66095-214">Se lo si desidera, è possibile assegnare più account di risorse a un operatore automatico, ognuno con un numero di servizio distinto.</span><span class="sxs-lookup"><span data-stu-id="66095-214">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="66095-215">Per aggiungere un account di risorse, fare clic su **Aggiungi account** e cercare l'account che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="66095-215">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="66095-216">Fare clic su **Aggiungi**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="66095-216">Click **Add**, and then click **Add**.</span></span>

![](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="66095-217">Dopo aver aggiunto gli account del servizio, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="66095-217">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="66095-218">Viene completata la configurazione dell'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="66095-218">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="66095-219">Trasferimenti di numeri di telefono esterni-dettagli tecnici</span><span class="sxs-lookup"><span data-stu-id="66095-219">External phone number transfers - technical details</span></span>

<span data-ttu-id="66095-220">Quando si trasferiscono le chiamate a un numero di telefono esterno, l'account delle risorse associato all'operatore automatico o alla coda di chiamata deve avere un numero di telefono e un sistema telefonico Microsoft 365-licenza utente virtuale.</span><span class="sxs-lookup"><span data-stu-id="66095-220">When transferring calls to an external phone number, the resource account associated with the auto attendant or call queue must have a phone number and a Microsoft 365 Phone System - Virtual User license.</span></span> <span data-ttu-id="66095-221">Inoltre</span><span class="sxs-lookup"><span data-stu-id="66095-221">Additionally:</span></span>

- <span data-ttu-id="66095-222">Per un account delle risorse con un numero di piano chiamante, assegnare una licenza per il [piano di chiamata](calling-plans-for-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="66095-222">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="66095-223">Per un account delle risorse con un numero di routing diretto, assegnare un [criterio di routing vocale online](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="66095-223">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

<span data-ttu-id="66095-224">Il numero di telefono in uscita visualizzato è determinato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="66095-224">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="66095-225">Per chiamare i numeri del piano, viene visualizzato il numero di telefono del chiamante originale.</span><span class="sxs-lookup"><span data-stu-id="66095-225">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="66095-226">Per i numeri di routing diretti, il numero inviato si basa sull'impostazione P-Asserted-Identity (PAI) nell'SBC, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="66095-226">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="66095-227">Se impostato su disabilitato, viene visualizzato il numero di telefono del chiamante originale.</span><span class="sxs-lookup"><span data-stu-id="66095-227">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="66095-228">Questa è l'impostazione predefinita e consigliata.</span><span class="sxs-lookup"><span data-stu-id="66095-228">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="66095-229">Se impostato su abilitato, viene visualizzato il numero di telefono dell'account risorse.</span><span class="sxs-lookup"><span data-stu-id="66095-229">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="66095-230">I trasferimenti tra Trunks del piano chiamante e trunk di routing diretto non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="66095-230">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

<span data-ttu-id="66095-231">In un ambiente ibrido, per trasferire una chiamata di operatore automatico alla rete PSTN tramite l'integrazione PSTN di Skype for business, creare un nuovo utente locale con l'opzione inoltro di chiamata impostata sul numero PSTN.</span><span class="sxs-lookup"><span data-stu-id="66095-231">In a hybrid environment, to transfer an auto attendant call to the PSTN via Skype for Business PSTN integration, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="66095-232">L'utente deve essere abilitato per VoIP aziendale e avere un criterio vocale assegnato.</span><span class="sxs-lookup"><span data-stu-id="66095-232">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="66095-233">Per altre informazioni, vedere [trasferimento automatico delle chiamate di operatore in PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="66095-233">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="66095-234">Creare un operatore automatico con PowerShell</span><span class="sxs-lookup"><span data-stu-id="66095-234">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="66095-235">È anche possibile usare PowerShell per creare e configurare gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="66095-235">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="66095-236">Ecco i cmdlet necessari per gestire un operatore automatico:</span><span class="sxs-lookup"><span data-stu-id="66095-236">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="66095-237">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="66095-237">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="66095-238">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="66095-238">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="66095-239">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="66095-239">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [<span data-ttu-id="66095-240">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="66095-240">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="66095-241">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="66095-241">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="66095-242">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="66095-242">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="66095-243">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="66095-243">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="66095-244">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="66095-244">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="66095-245">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="66095-245">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="66095-246">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="66095-246">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="66095-247">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="66095-247">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="66095-248">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="66095-248">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="66095-249">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="66095-249">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="66095-250">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="66095-250">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="66095-251">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="66095-251">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="66095-252">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="66095-252">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="66095-253">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="66095-253">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)


## <a name="related-topics"></a><span data-ttu-id="66095-254">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="66095-254">Related topics</span></span>

[<span data-ttu-id="66095-255">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="66095-255">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

<span data-ttu-id="66095-256">[Recuperare numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="66095-256">[Getting service phone numbers](/microsoftteams/getting-service-phone-numbers)</span></span>

[<span data-ttu-id="66095-257">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="66095-257">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="66095-258">Esempio di piccola impresa: configurare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="66095-258">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="66095-259">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="66095-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
