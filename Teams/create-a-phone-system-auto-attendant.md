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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Informazioni su come configurare e testare gli operatori automatici per Microsoft Teams.
ms.openlocfilehash: 4809965eaad0f8cd81b59823d3890bd895998906
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919040"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="dde9d-103">Impostare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="dde9d-103">Set up an auto attendant</span></span>

<span data-ttu-id="dde9d-104">Gli operatori automatici consentono alle persone di chiamare l'organizzazione ed esplorare un sistema di menu per parlare al reparto, alla coda di chiamata, alla persona o a un operatore.</span><span class="sxs-lookup"><span data-stu-id="dde9d-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="dde9d-105">È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft Teams o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dde9d-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="dde9d-106">Assicurarsi di aver letto Il piano per gli operatori [](plan-auto-attendant-call-queue.md#getting-started) automatici e le code di chiamata di [Teams](plan-auto-attendant-call-queue.md) e aver seguito i passaggi introduttivi prima di seguire le procedure di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="dde9d-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="dde9d-107">Gli operatori automatici possono indirizzare le chiamate, in base all'input dei chiamanti, a una delle destinazioni seguenti: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="dde9d-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="dde9d-108">**Persona nell'organizzazione:** persona dell'organizzazione che può ricevere chiamate vocali.</span><span class="sxs-lookup"><span data-stu-id="dde9d-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="dde9d-109">Può trattarsi di un utente online o di un utente ospitato in locale con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dde9d-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="dde9d-110">**App vocale:** un altro operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="dde9d-111">Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="dde9d-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="dde9d-112">**Numero di telefono esterno:** qualsiasi numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="dde9d-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="dde9d-113">(Vedere [i dettagli tecnici sul trasferimento esterno).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="dde9d-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="dde9d-114">**Segreteria telefonica:** cassetta postale vocale associata a un gruppo di Microsoft 365 specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="dde9d-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="dde9d-115">**Operatore:** l'operatore definito per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="dde9d-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="dde9d-116">La definizione di un operatore è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="dde9d-116">Defining an operator is optional.</span></span> <span data-ttu-id="dde9d-117">L'operatore può essere definito come una qualsiasi delle altre destinazioni dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dde9d-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="dde9d-118">Ti verrà chiesto di scegliere una di queste opzioni in varie fasi durante la configurazione di un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="dde9d-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="dde9d-119">Per impostare un operatore automatico, nell'interfaccia di amministrazione di Teams espandi **Voce,** fai clic su **Operatori** automatici, quindi fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="dde9d-120">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="dde9d-120">General info</span></span>

![Schermata delle impostazioni dell'operatore automatico per nome, operatore, fuso orario, lingua e input vocali](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="dde9d-122">Digita un nome per l'operatore automatico nella casella in alto.</span><span class="sxs-lookup"><span data-stu-id="dde9d-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="dde9d-123">Se si vuole designare un operatore, specificare la destinazione delle chiamate all'operatore.</span><span class="sxs-lookup"><span data-stu-id="dde9d-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="dde9d-124">Questo passaggio è facoltativo (ma consigliato).</span><span class="sxs-lookup"><span data-stu-id="dde9d-124">This is optional (but recommended).</span></span> <span data-ttu-id="dde9d-125">È possibile impostare **l'opzione Operatore** per consentire ai chiamanti di uscire dal menu e parlare con una persona designata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="dde9d-126">Specifica il fuso orario per questo operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="dde9d-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="dde9d-127">Il fuso orario viene utilizzato per calcolare l'orario di ufficio se si crea un flusso delle [chiamate separato per l'orario di uscita.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="dde9d-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="dde9d-128">Specifica una lingua per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="dde9d-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="dde9d-129">Questa è la lingua che verrà utilizzata per i comandi vocali generati dal sistema.</span><span class="sxs-lookup"><span data-stu-id="dde9d-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="dde9d-130">Scegli se abilitare gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="dde9d-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="dde9d-131">Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="dde9d-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="dde9d-132">Ad esempio, i chiamanti possono dire "Uno" per selezionare l'opzione di menu mappata al tasto 1, oppure possono dire "Vendite" per selezionare l'opzione di menu denominata "Vendite".</span><span class="sxs-lookup"><span data-stu-id="dde9d-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="dde9d-133">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dde9d-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="dde9d-134">Flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="dde9d-134">Call flow</span></span>

![Screenshot delle impostazioni del messaggio di saluto](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="dde9d-136">Scegli se vuoi riprodurre un saluto quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="dde9d-137">Se si seleziona **Riproduci file audio,** è possibile usare il pulsante **Carica file** per caricare un messaggio di saluto registrato salvato come audio in. WAV, . MP3, o . WMA.</span><span class="sxs-lookup"><span data-stu-id="dde9d-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="dde9d-138">Le dimensioni della registrazione non possono essere superiori a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="dde9d-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="dde9d-139">Se si seleziona Digita un messaggio di saluto, il sistema leggerà il testo digitato (fino **a** 1000 caratteri) quando l'operatore automatico risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Schermata delle impostazioni di instradamento chiamate](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="dde9d-141">Scegli come instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="dde9d-142">Se si seleziona **Disconnetti,** l'operatore automatico ggancia la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-142">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="dde9d-143">Se si seleziona **Reindirizza** chiamata, è possibile scegliere una delle destinazioni di instradamento chiamate.</span><span class="sxs-lookup"><span data-stu-id="dde9d-143">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="dde9d-144">Se si seleziona **Riproduci opzioni di menu,** è possibile scegliere Riproduci **file audio** o Digitare **un** messaggio di saluto e quindi scegliere tra le opzioni del menu e la ricerca in elenco.</span><span class="sxs-lookup"><span data-stu-id="dde9d-144">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="dde9d-145">Opzioni di menu</span><span class="sxs-lookup"><span data-stu-id="dde9d-145">Menu options</span></span>

![Schermata delle opzioni dei tasti di composizione](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="dde9d-147">Per le opzioni di composizione, è possibile assegnare i tasti da 0 a 9 sulla tastiera del telefono a una delle destinazioni di instradamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="dde9d-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="dde9d-148">(I tasti \* (Ripeti) e \# (Indietro) sono riservate dal sistema e non possono essere riassegnate.</span><span class="sxs-lookup"><span data-stu-id="dde9d-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="dde9d-149">I mapping di tasti non devono essere continui.</span><span class="sxs-lookup"><span data-stu-id="dde9d-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="dde9d-150">È possibile, ad esempio, creare un menu con i tasti 0, 1 e 3 mappati alle opzioni, mentre il tasto 2 non viene usato.</span><span class="sxs-lookup"><span data-stu-id="dde9d-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="dde9d-151">Se ne è stato configurato uno, è consigliabile mappare il tasto 0 all'operatore.</span><span class="sxs-lookup"><span data-stu-id="dde9d-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="dde9d-152">Se l'operatore non è impostato su alcun tasto, viene disabilitato anche il comando vocale "Operatore".</span><span class="sxs-lookup"><span data-stu-id="dde9d-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="dde9d-153">Per ogni opzione di menu, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dde9d-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="dde9d-154">**Tasto di composizione:** il tasto sulla tastiera del telefono per accedere a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="dde9d-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="dde9d-155">Se sono disponibili input vocali, i chiamanti possono anche pronunciare questo numero per accedere all'opzione.</span><span class="sxs-lookup"><span data-stu-id="dde9d-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="dde9d-156">**Comando vocale:** definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se sono abilitati gli input vocali.</span><span class="sxs-lookup"><span data-stu-id="dde9d-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="dde9d-157">Può contenere più parole, ad esempio "Assistenza clienti" o "Operazioni e basi".</span><span class="sxs-lookup"><span data-stu-id="dde9d-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="dde9d-158">Ad esempio, il chiamante può premere 2, dire "due" o dire "Vendite" per selezionare l'opzione mappata al tasto 2.</span><span class="sxs-lookup"><span data-stu-id="dde9d-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="dde9d-159">Il testo viene visualizzato anche dal testo da sintesi vocale per la richiesta di conferma del servizio, ad esempio "Trasferimento delle chiamate alle vendite".</span><span class="sxs-lookup"><span data-stu-id="dde9d-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="dde9d-160">**Redirect to** - the call routing destination used when callers choose this option.</span><span class="sxs-lookup"><span data-stu-id="dde9d-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="dde9d-161">Se stai effettuando il reindirizzamento a un operatore automatico o a una coda di chiamata, scegli l'account della risorsa associato.</span><span class="sxs-lookup"><span data-stu-id="dde9d-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="dde9d-162">Ricerca in elenco</span><span class="sxs-lookup"><span data-stu-id="dde9d-162">Directory search</span></span>

<span data-ttu-id="dde9d-163">Se assegni i tasti di composizione alle destinazioni, ti consigliamo di scegliere **Nessuno per** la ricerca **in Elenco.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="dde9d-164">Se un chiamante prova a comporre un nome o un'estensione utilizzando tasti assegnati a destinazioni specifiche, potrebbe essere instradato in modo imprevisto a una destinazione prima di completare l'immissione del nome o dell'interno.</span><span class="sxs-lookup"><span data-stu-id="dde9d-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="dde9d-165">Ti consigliamo di creare un operatore automatico distinto per la ricerca in elenco e di impostare il collegamento dell'operatore automatico principale tramite un tasto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="dde9d-166">Se non hai assegnato i tasti di composizione, scegli un'opzione per la **ricerca in Elenco.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="dde9d-167">**Chiamata per nome:** se si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="dde9d-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="dde9d-168">Qualsiasi utente online o qualsiasi utente ospitato in locale con Skype for Business Server è un utente idoneo e può essere trovato con Chiamata per nome.</span><span class="sxs-lookup"><span data-stu-id="dde9d-168">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="dde9d-169">Puoi impostare chi è e non è incluso nella directory nella [pagina Ambito di](#dial-scope) chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="dde9d-170">**Chiamata per interno** - Se si abilita questa opzione, i chiamanti possono connettersi con gli utenti dell'organizzazione componendo l'interno del telefono.</span><span class="sxs-lookup"><span data-stu-id="dde9d-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="dde9d-171">Qualsiasi utente online o qualsiasi utente ospitato in locale con Skype for Business Server è un utente idoneo e può essere trovato con **Chiamata per interno.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-171">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="dde9d-172">Puoi impostare chi è e non è incluso nella directory nella [pagina Ambito di](#dial-scope) chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="dde9d-173">Gli utenti che si desidera rendere disponibili per Chiamata per interno devono avere un'estensione specificata come parte di uno degli attributi di telefono seguenti definiti in Active Directory o Azure Active Directory (per altre informazioni, vedere Aggiungere utenti singolarmente o [in](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) blocco).</span><span class="sxs-lookup"><span data-stu-id="dde9d-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="dde9d-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="dde9d-174">OfficePhone</span></span>
- <span data-ttu-id="dde9d-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="dde9d-175">HomePhone</span></span>
- <span data-ttu-id="dde9d-176">Cellulare/Cellulare</span><span class="sxs-lookup"><span data-stu-id="dde9d-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="dde9d-177">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="dde9d-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="dde9d-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="dde9d-178">OtherTelephone</span></span>

<span data-ttu-id="dde9d-179">Il formato richiesto per immettere l'interno nel campo del numero di telefono dell'utente è:</span><span class="sxs-lookup"><span data-stu-id="dde9d-179">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="dde9d-180">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="dde9d-180">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="dde9d-181">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="dde9d-181">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="dde9d-182">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="dde9d-182">*x\<extension>*</span></span>

- <span data-ttu-id="dde9d-183">Esempio 1: Set-MsolUser -UserPrincipalName usern@domain.com-Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="dde9d-183">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="dde9d-184">Esempio 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="dde9d-184">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="dde9d-185">Esempio 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="dde9d-185">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="dde9d-186">È possibile impostare l'estensione [nell'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) o nell'interfaccia di amministrazione di Azure Active [Directory.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="dde9d-186">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="dde9d-187">Possono essere necessarie fino a 12 ore prima che le modifiche siano disponibili per gli operatori automatici e le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-187">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="dde9d-188">Se si desidera utilizzare  sia la  funzionalità Chiamata per nome che Chiamata per interno, è possibile assegnare un tasto di chiamata sull'operatore automatico principale per raggiungere un operatore automatico abilitato per Chiamata **per nome.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-188">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="dde9d-189">All'interno di tale operatore automatico, puoi assegnare il tasto 1 (senza lettere associate) per raggiungere l'operatore automatico Chiamata per interno. </span><span class="sxs-lookup"><span data-stu-id="dde9d-189">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="dde9d-190">Dopo aver selezionato un'opzione **di ricerca nella directory,** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-190">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="dde9d-191">Flusso delle chiamate per le ore non lavorative</span><span class="sxs-lookup"><span data-stu-id="dde9d-191">Call flow for after hours</span></span>

![Screenshot delle impostazioni del giorno e dell'ora fuori orario](media/auto-attendant-business-hours.png)

<span data-ttu-id="dde9d-193">L'orario di ufficio può essere impostato per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="dde9d-193">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="dde9d-194">Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito.</span><span class="sxs-lookup"><span data-stu-id="dde9d-194">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="dde9d-195">L'orario di ufficio può essere impostato con interruzioni nel tempo durante il giorno e tutti gli orari non impostati come orario di ufficio sono considerati fuori orario.</span><span class="sxs-lookup"><span data-stu-id="dde9d-195">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="dde9d-196">Puoi impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per il dopo-orario.</span><span class="sxs-lookup"><span data-stu-id="dde9d-196">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="dde9d-197">A seconda di come hai configurato gli operatori automatici e le code di chiamata, potresti dover specificare l'instradamento delle chiamate in orario di instradamento solo per gli operatori automatici con numeri di telefono diretti.</span><span class="sxs-lookup"><span data-stu-id="dde9d-197">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="dde9d-198">Se si desidera un instradamento delle chiamate separato per i chiamanti non in orario di ufficio, specificare l'orario di ufficio per ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="dde9d-198">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="dde9d-199">Fare **clic su Aggiungi nuovo orario** per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="dde9d-199">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="dde9d-200">Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per l'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="dde9d-200">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="dde9d-201">Le stesse opzioni sono disponibili per l'instradamento delle chiamate in orario di ufficio specificato sopra.</span><span class="sxs-lookup"><span data-stu-id="dde9d-201">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="dde9d-202">Al **termine,** fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="dde9d-202">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="dde9d-203">Flussi delle chiamate durante le festività</span><span class="sxs-lookup"><span data-stu-id="dde9d-203">Call flows during holidays</span></span>

![Screenshot delle impostazioni per le festività e le festività](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="dde9d-205">L'operatore automatico può avere un flusso delle chiamate per [ogni Festività che hai impostato.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="dde9d-205">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="dde9d-206">È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="dde9d-206">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="dde9d-207">Nella pagina delle impostazioni delle chiamate per le festività fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-207">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="dde9d-208">Digitare un nome per l'impostazione delle festività.</span><span class="sxs-lookup"><span data-stu-id="dde9d-208">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="dde9d-209">**Nell'elenco** a discesa Festività scegliere la festività da usare.</span><span class="sxs-lookup"><span data-stu-id="dde9d-209">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="dde9d-210">Scegliere il tipo di messaggio di saluto da usare.</span><span class="sxs-lookup"><span data-stu-id="dde9d-210">Choose the type of greeting that you want to use.</span></span>

    ![Screenshot delle impostazioni delle azioni di chiamata per le festività](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="dde9d-212">Scegli se vuoi disconnettere **o** **reindirizzare** la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-212">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="dde9d-213">Se hai scelto di reindirizzare la chiamata, scegli la destinazione del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="dde9d-213">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="dde9d-214">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dde9d-214">Click **Save**.</span></span>

![Screenshot delle impostazioni delle festività con l'elenco delle festività](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="dde9d-216">Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="dde9d-216">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="dde9d-217">Dopo aver aggiunto tutte le festività, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-217">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="dde9d-218">Ambito di chiamata</span><span class="sxs-lookup"><span data-stu-id="dde9d-218">Dial scope</span></span>

![Schermata delle opzioni di inclusione ed esclusione dell'ambito di chiamata](media/auto-attendant-dial-scope.png)

<span data-ttu-id="dde9d-220">*L'ambito* di chiamata definisce quali utenti sono disponibili nella directory quando un chiamante usa chiamata per nome o per interno.</span><span class="sxs-lookup"><span data-stu-id="dde9d-220">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="dde9d-221">L'impostazione predefinita Di tutti gli utenti **online** include tutti gli utenti dell'organizzazione che sono utenti online o ospitati in sede con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dde9d-221">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="dde9d-222">È possibile includere o escludere utenti specifici  selezionando  Gruppo di utenti personalizzato in Includi o escludi e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza. </span><span class="sxs-lookup"><span data-stu-id="dde9d-222">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="dde9d-223">Ad esempio, è possibile escludere i dirigenti dell'organizzazione dalla directory di composizione.</span><span class="sxs-lookup"><span data-stu-id="dde9d-223">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="dde9d-224">Se un utente è presente in entrambi gli elenchi, verrà escluso dalla directory.</span><span class="sxs-lookup"><span data-stu-id="dde9d-224">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="dde9d-225">L'elenco dei nomi di un nuovo utente nella directory può richiedere fino a 36 ore.</span><span class="sxs-lookup"><span data-stu-id="dde9d-225">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="dde9d-226">Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-226">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="dde9d-227">Account delle risorse</span><span class="sxs-lookup"><span data-stu-id="dde9d-227">Resource accounts</span></span>

<span data-ttu-id="dde9d-228">Tutti gli operatori automatici devono avere un account delle risorse associato.</span><span class="sxs-lookup"><span data-stu-id="dde9d-228">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="dde9d-229">Gli operatori automatici di primo livello dovranno avere almeno un account delle risorse a cui è associato un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="dde9d-229">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="dde9d-230">Se si desidera, è possibile assegnare più account delle risorse a un operatore automatico, ognuno con un numero di servizio distinto.</span><span class="sxs-lookup"><span data-stu-id="dde9d-230">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Screenshot del riquadro Aggiungi account dell'account della risorsa](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="dde9d-232">Per aggiungere un account della risorsa, fare **clic su** Aggiungi account e cercare l'account che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="dde9d-232">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="dde9d-233">Fare **clic su** Aggiungi e quindi su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-233">Click **Add**, and then click **Add**.</span></span>

![Screenshot dell'elenco di account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="dde9d-235">Dopo aver aggiunto tutti gli account del servizio, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="dde9d-235">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="dde9d-236">La configurazione dell'operatore automatico viene completata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-236">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="dde9d-237">Trasferimenti di numeri di telefono esterni - dettagli tecnici</span><span class="sxs-lookup"><span data-stu-id="dde9d-237">External phone number transfers - technical details</span></span>

<span data-ttu-id="dde9d-238">Fai riferimento ai [prerequisiti per](plan-auto-attendant-call-queue.md#prerequisites) consentire agli operatori automatici di trasferire le chiamate esternamente.</span><span class="sxs-lookup"><span data-stu-id="dde9d-238">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="dde9d-239">Inoltre:</span><span class="sxs-lookup"><span data-stu-id="dde9d-239">In addition:</span></span>

- <span data-ttu-id="dde9d-240">Per un account [](calling-plans-for-office-365.md) risorsa con un numero di Piano per chiamate, il numero di telefono per il trasferimento esterno deve essere immesso nel formato E.164 (+[codice paese][codice area][numero di telefono]).</span><span class="sxs-lookup"><span data-stu-id="dde9d-240">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="dde9d-241">Per un account di risorsa con un numero di instradamento diretto, il formato del numero di telefono per il trasferimento esterno dipende dalle impostazioni [di Session Border Controller (SBC).](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="dde9d-241">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="dde9d-242">Il numero di telefono in uscita visualizzato viene determinato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="dde9d-242">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="dde9d-243">Per i numeri del Piano per chiamate, viene visualizzato il numero di telefono del chiamante originale.</span><span class="sxs-lookup"><span data-stu-id="dde9d-243">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="dde9d-244">Per i numeri di routing diretto, il numero inviato si basa sull'impostazione PAI (P-Asserted-Identity) nell'SBC, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dde9d-244">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="dde9d-245">Se impostato su Disabilitato, viene visualizzato il numero di telefono del chiamante originale.</span><span class="sxs-lookup"><span data-stu-id="dde9d-245">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="dde9d-246">Questa è l'impostazione predefinita e consigliata.</span><span class="sxs-lookup"><span data-stu-id="dde9d-246">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="dde9d-247">Se è impostata su Abilitato, viene visualizzato il numero di telefono dell'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="dde9d-247">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="dde9d-248">In un ambiente ibrido di Skype for Business, per trasferire una chiamata di operatore automatico alla rete PSTN, creare un nuovo utente locale con l'inoltro di chiamata impostato sul numero PSTN.</span><span class="sxs-lookup"><span data-stu-id="dde9d-248">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="dde9d-249">L'utente deve essere abilitato per VoIP aziendale e avere assegnato un criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="dde9d-249">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="dde9d-250">Per ulteriori informazioni, consulta Trasferimento di chiamata [dell'operatore automatico a PSTN.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="dde9d-250">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="dde9d-251">Creare un operatore automatico con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dde9d-251">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="dde9d-252">Puoi anche usare PowerShell per creare e configurare gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="dde9d-252">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="dde9d-253">Ecco i cmdlet necessari per gestire un operatore automatico:</span><span class="sxs-lookup"><span data-stu-id="dde9d-253">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="dde9d-254">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dde9d-254">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="dde9d-255">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dde9d-255">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="dde9d-256">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dde9d-256">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="dde9d-257">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="dde9d-257">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="dde9d-258">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dde9d-258">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="dde9d-259">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="dde9d-259">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="dde9d-260">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="dde9d-260">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="dde9d-261">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="dde9d-261">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="dde9d-262">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="dde9d-262">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="dde9d-263">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="dde9d-263">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="dde9d-264">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="dde9d-264">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="dde9d-265">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="dde9d-265">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="dde9d-266">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="dde9d-266">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="dde9d-267">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="dde9d-267">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="dde9d-268">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="dde9d-268">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="dde9d-269">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="dde9d-269">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="dde9d-270">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="dde9d-270">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="dde9d-271">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dde9d-271">Related topics</span></span>

[<span data-ttu-id="dde9d-272">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="dde9d-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

<span data-ttu-id="dde9d-273">[Recuperare numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="dde9d-273">[Getting service phone numbers](/microsoftteams/getting-service-phone-numbers)</span></span>

[<span data-ttu-id="dde9d-274">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="dde9d-274">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="dde9d-275">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="dde9d-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
