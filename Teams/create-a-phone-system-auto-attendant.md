---
title: Configurare un operatore automatico cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Informazioni su come configurare e testare gli operatori automatici di cloud per Microsoft teams.
ms.openlocfilehash: 6ac4ccea48e70a8bba5e11511379fef5c5a2a861
ms.sourcegitcommit: e89c2234fc5aa8f7eeef66ba1ae093a0f7beda85
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "37349250"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="9d065-103">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="9d065-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="9d065-104">Gli operatori automatici consentono agli utenti che chiamano l'organizzazione e spostano un sistema di menu per accedervi al reparto di destra, alla coda di chiamata, alla persona o all'operatore.</span><span class="sxs-lookup"><span data-stu-id="9d065-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="9d065-105">Puoi creare un operatore automatico per l'organizzazione usando l'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="9d065-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="9d065-106">Per creare un nuovo operatore automatico, passa a **voce** nella barra di spostamento sinistra e quindi seleziona **operatori** > automatici**Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="9d065-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="9d065-107">Per altre informazioni sugli operatori automatici, vedere [che cosa sono gli operatori automatici di cloud?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="9d065-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="9d065-108">Questo articolo si applica sia a Microsoft teams che a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="9d065-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="9d065-109">Passaggio 1: iniziare</span><span class="sxs-lookup"><span data-stu-id="9d065-109">Step 1 — Get started</span></span>

- <span data-ttu-id="9d065-110">Per avere un account di risorse associato, è necessario un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="9d065-111">Vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) per informazioni dettagliate sugli account delle risorse e tutte le licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="9d065-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="9d065-112">Per reindirizzare le chiamate a un operatore o a un'opzione di menu che è un utente online con una licenza di **sistema telefonico** , sarà necessario abilitarle per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9d065-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="9d065-113">Vedere [assegnare licenze di Skype for business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [assegnare licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="9d065-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="9d065-114">Puoi anche utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d065-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="9d065-115">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="9d065-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="9d065-116">Passaggio 2: creare un nuovo operatore automatico</span><span class="sxs-lookup"><span data-stu-id="9d065-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d065-117">Ogni operatore automatico è necessario per avere un [account di risorse](manage-resource-accounts.md)associato.</span><span class="sxs-lookup"><span data-stu-id="9d065-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="9d065-118">Devi prima creare l'account della risorsa, quindi puoi associarlo all'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9d065-119">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d065-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9d065-120">Nell'interfaccia di **amministrazione di Microsoft teams**fare clic su**operatore automatico** **vocale** > , quindi fare clic su **+ nuovo**:</span><span class="sxs-lookup"><span data-stu-id="9d065-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="9d065-121">Pagina informazioni generali</span><span class="sxs-lookup"><span data-stu-id="9d065-121">General info page</span></span>

![Screenshot della pagina My Auto Attendant](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="9d065-124">**Nome** Immettere un nome visualizzato descrittivo per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="9d065-125">Il nome è obbligatorio e può contenere fino a 64 caratteri, inclusi gli spazi.</span><span class="sxs-lookup"><span data-stu-id="9d065-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="9d065-126">È elencata nella colonna **nome** della scheda **operatori automatici** .</span><span class="sxs-lookup"><span data-stu-id="9d065-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="9d065-128"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="9d065-128"></span></span>

<span data-ttu-id="9d065-129">**Account risorse** Fare clic su questo pulsante per selezionare uno o più account risorse per connettersi al nuovo operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-129">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="9d065-130">Tutti gli operatori automatici devono avere un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="9d065-130">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="9d065-131">Un account di risorse può avere un numero di telefono associato all'account, ma un numero di telefono non è un requisito.</span><span class="sxs-lookup"><span data-stu-id="9d065-131">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="9d065-132">Un operatore automatico di primo livello ha in genere un account di risorse con un numero di telefono assegnato, ma l'operatore automatico annidato (usato come menu di livello 2 a cui si connette l'operatore automatico di prima livello) potrebbe non avere un numero di telefono assegnato al proprio account di risorse.</span><span class="sxs-lookup"><span data-stu-id="9d065-132">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

<span data-ttu-id="9d065-133">![Icona del numero 3, che fa riferimento a un callout nella schermata](media/sfbcallout3.png)
 <a name="timezone"> </a> precedente</span><span class="sxs-lookup"><span data-stu-id="9d065-133">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png)
<a name="timezone"> </a></span></span>

<span data-ttu-id="9d065-134">**Fuso orario** È necessario impostare il fuso orario per l'operatore automatico, che non deve necessariamente corrispondere al fuso orario dell'indirizzo principale indicato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d065-134">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="9d065-135">Ogni operatore automatico può avere un fuso orario diverso e gli orari di ufficio impostati per l'operatore automatico vengono impostati in base al fuso orario selezionato qui.</span><span class="sxs-lookup"><span data-stu-id="9d065-135">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![Icona del numero 4, che fa riferimento a un callout nella schermata precedente](media/sfbcallout4.png)

<span data-ttu-id="9d065-137"><a name="language"> </a></span><span class="sxs-lookup"><span data-stu-id="9d065-137"></span></span>

<span data-ttu-id="9d065-138">**Lingua** Seleziona la lingua che vuoi utilizzare per l'operatore automatico tra una delle lingue disponibili elencate.</span><span class="sxs-lookup"><span data-stu-id="9d065-138">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="9d065-139">La lingua impostata qui è la lingua usata dall'operatore automatico per interagire con le persone che chiamano l'operatore automatico e tutte le richieste di sistema vengono riprodotte in questa lingua.</span><span class="sxs-lookup"><span data-stu-id="9d065-139">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![Icona del numero 5, che fa riferimento a un callout nella schermata precedente](media/sfbcallout5.png)

<span data-ttu-id="9d065-141"><a name="operator"> </a></span><span class="sxs-lookup"><span data-stu-id="9d065-141"></span></span>

<span data-ttu-id="9d065-142">**Operatore** È facoltativo, ma puoi impostare l'opzione **operator** per consentire ai chiamanti di uscire dai menu e parlare con una persona.</span><span class="sxs-lookup"><span data-stu-id="9d065-142">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="9d065-143">Per impostazione predefinita, il tasto 0 viene assegnato all'operatore.</span><span class="sxs-lookup"><span data-stu-id="9d065-143">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="9d065-144">Se si imposta un operatore, sarà anche necessario indicare agli utenti che chiamano l'opzione nelle **Opzioni del menu modifica** nella pagina **Gestione chiamate orari di ufficio** .</span><span class="sxs-lookup"><span data-stu-id="9d065-144">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="9d065-145">Se si imposta un operatore nell'operatore automatico, è necessario immettere il testo del prompt corrispondente nei **chiamanti si sente** la casella o si modifica il file audio per includere questa opzione.</span><span class="sxs-lookup"><span data-stu-id="9d065-145">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="9d065-146">Ad esempio: "Per contattare un operatore, premere zero".</span><span class="sxs-lookup"><span data-stu-id="9d065-146">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="9d065-147">Sono disponibili diversi modi per impostare l'operatore:</span><span class="sxs-lookup"><span data-stu-id="9d065-147">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="9d065-148">**Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati.</span><span class="sxs-lookup"><span data-stu-id="9d065-148">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="9d065-149">Una **Persona nell'azienda** può essere un utente in linea o un utente ospitato in locale con Skype per Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d065-149">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="9d065-150">**Applicazione vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="9d065-150">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="9d065-151">È possibile configurarlo in modo che la persona che chiama venga inviata alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-151">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="9d065-152">A questo scopo, seleziona **persona nella tua azienda** e imposta le chiamate di questa persona da inoltrare direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-152">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Icona del numero 6, che fa riferimento a un callout nella schermata precedente](media/sfbcallout6.png)

<span data-ttu-id="9d065-154">**Abilitare gli input vocali** Il riconoscimento vocale è disponibile se questa opzione è selezionata.</span><span class="sxs-lookup"><span data-stu-id="9d065-154">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="9d065-155">Le persone che chiamano in grado di usare l'input vocale nella [lingua impostata](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9d065-155">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="9d065-156">Se si vuole consentire solo agli utenti di usare la tastiera del telefono, è possibile disabilitare il riconoscimento vocale impostandolo su disattivato.</span><span class="sxs-lookup"><span data-stu-id="9d065-156">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="9d065-157">Dopo aver completato le selezioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9d065-157">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="9d065-158">Pagina orari di ufficio</span><span class="sxs-lookup"><span data-stu-id="9d065-158">Business hours page</span></span>

<span data-ttu-id="9d065-159">Per impostazione predefinita, le ore lavorative sono impostate su 9:00 AM 5:00 PM, dal lunedì al venerdì.</span><span class="sxs-lookup"><span data-stu-id="9d065-159">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="9d065-160">Tutte le ore che non sono incluse in orari di ufficio vengono considerate dopo l'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="9d065-160">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="9d065-161">È possibile fare clic su **seleziona 24/7** per impostare tutte le ore lavorative.</span><span class="sxs-lookup"><span data-stu-id="9d065-161">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="9d065-162">A meno che non si selezioni l'opzione **seleziona 24/7** , verrà usata la pagina **Impostazioni chiamate dopo ora** per configurare le regole di gestione delle chiamate per gli orari di ufficio per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-162">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![Screenshot della pagina orari di ufficio](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="9d065-165">Per impostazione predefinita, le ore lavorative sono impostate su lunedì a venerdì, 9:00 AM-5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="9d065-165">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="9d065-166">Selezionare **Cancella tutte le ore per deselezionare** tutte le ore nella programmazione.</span><span class="sxs-lookup"><span data-stu-id="9d065-166">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="9d065-167">Quando si seleziona **Reimposta per impostazione predefinita**, le ore lavorative vengono reimpostate dal lunedì al venerdì, 9:00 am-5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="9d065-167">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="9d065-169">Per modificare le ore lavorative, evidenziare gli orari di ufficio che si desidera impostare nel calendario.</span><span class="sxs-lookup"><span data-stu-id="9d065-169">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="9d065-170">Il calendario consente di selezionare gli orari di ufficio in intervalli di 30 minuti e gli orari di ufficio selezionati sono basati sul fuso orario impostato nella pagina **informazioni generali** .</span><span class="sxs-lookup"><span data-stu-id="9d065-170">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="9d065-171">Per impostare una pausa (ad esempio la pausa pranzo), deseleziona o trascina per deselezionare l'orario in questione sul calendario.</span><span class="sxs-lookup"><span data-stu-id="9d065-171">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="9d065-172">È possibile impostare più interruzioni in orari di ufficio.</span><span class="sxs-lookup"><span data-stu-id="9d065-172">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="9d065-173">Dopo aver completato le selezioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9d065-173">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="9d065-174">Impostazioni delle chiamate in orario di ufficio</span><span class="sxs-lookup"><span data-stu-id="9d065-174">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="9d065-175">Se si usa una programmazione per orari di ufficio personalizzati, è anche necessario configurare la consegna delle chiamate dopo l'orario di ufficio con la pagina **after hours handling** , che fornisce le stesse opzioni **delle impostazioni delle chiamate in orario di ufficio**.</span><span class="sxs-lookup"><span data-stu-id="9d065-175">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="9d065-176">È possibile configurare i messaggi di saluto, le richieste e i menu che gli utenti sentono quando chiamano il numero di telefono collegato all'operatore automatico dell'organizzazione durante l'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="9d065-176">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="9d065-177">![Screenshot della sezione relativa](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![alla gestione delle chiamate in orario di ufficio per l'apertura della pagina nella sezione delle azioni della pagina Gestione delle chiamate in orario di ufficio](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="9d065-177">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="9d065-179"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="9d065-179"></span></span>

<span data-ttu-id="9d065-180">**Messaggio di saluto** Un saluto per le ore lavorative è facoltativo e può essere impostato su **Nessun saluto**.</span><span class="sxs-lookup"><span data-stu-id="9d065-180">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="9d065-181">In questo caso, il chiamante non sente un messaggio o un saluto prima che la chiamata venga gestita da una delle azioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="9d065-181">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="9d065-182">È possibile caricare un file audio (nel formato con estensione wav, mp3 o .wma) o creare un messaggio di saluto personalizzato utilizzando la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="9d065-182">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="9d065-183">**Caricare un file audio** Se si sceglie questo record, registrare il messaggio di saluto e quindi caricare il file audio (in formato WAV, MP3 o WMA).</span><span class="sxs-lookup"><span data-stu-id="9d065-183">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="9d065-184">**Digitare un messaggio di saluto** Se si sceglie questa opzione, immettere il testo da leggere per il sistema (fino a 1000 caratteri).</span><span class="sxs-lookup"><span data-stu-id="9d065-184">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="9d065-185">Ad esempio, è possibile immettere "Benvenuti alla Contoso.</span><span class="sxs-lookup"><span data-stu-id="9d065-185">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="9d065-186">La tua chiamata è importante per noi."</span><span class="sxs-lookup"><span data-stu-id="9d065-186">Your call is important to us."</span></span> <span data-ttu-id="9d065-187">nella casella **I chiamanti udiranno**.</span><span class="sxs-lookup"><span data-stu-id="9d065-187">in the **Callers will hear** box.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="9d065-189">È possibile selezionare cosa avviene alle chiamate in arrivo durante l'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="9d065-189">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="9d065-190">È possibile scegliere tra le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d065-190">You can chose from the following actions:</span></span>

<span data-ttu-id="9d065-191"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="9d065-191"></span></span>

- <span data-ttu-id="9d065-192">**Disconnettere** Se selezionata, la persona che chiama verrà disconnessa dopo aver ascoltato una saluto di orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="9d065-192">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="9d065-193">**Reindirizzare una chiamata** Ciò consente di inviare automaticamente la chiamata a:</span><span class="sxs-lookup"><span data-stu-id="9d065-193">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="9d065-194">**Persona in società** con una licenza di **sistema telefonico** abilitata per i piani VoIP aziendale o per le chiamate assegnate in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d065-194">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="9d065-195">Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-195">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="9d065-196">A questo scopo, seleziona **persona in società** e imposta questa persona per inoltrare le chiamate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-196">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="9d065-197">La **persona in società** può essere un utente online o un utente ospitato in locale con Skype for Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d065-197">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="9d065-198">Un altro **operatore automatico**</span><span class="sxs-lookup"><span data-stu-id="9d065-198">Another **Auto attendant**</span></span>

   <span data-ttu-id="9d065-199">Puoi usare un operatore automatico esistente per creare un secondo livello di opzioni di menu che contiene un sottomenu.</span><span class="sxs-lookup"><span data-stu-id="9d065-199">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="9d065-200">Questi sono denominati operatori automatici innestati.</span><span class="sxs-lookup"><span data-stu-id="9d065-200">These are called nested auto attendants.</span></span> <span data-ttu-id="9d065-201">Per inviare la chiamata a un operatore automatico annidato, selezionare **persona in società** e assegnare un account di risorse, uno che ha già un operatore automatico associato o uno che verrà associato a un operatore automatico dopo aver creato questo operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-201">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="9d065-202">Le **Opzioni del menu Riproduci** possono essere usate anche per configurare un prompt che si vuole riprodurre.</span><span class="sxs-lookup"><span data-stu-id="9d065-202">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Icona del numero 3, che fa riferimento a un callout nella schermata precedente](media/sfbcallout3.png)

<span data-ttu-id="9d065-204">**Messaggio del menu** Per creare il messaggio del menu principale, puoi utilizzare il sintetizzatore vocale o caricare un file audio (.wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="9d065-204">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="9d065-205">È possibile digitare il messaggio nella casella **imposta il menu di spostamento per i chiamanti** o registrare un file audio e dire, ad esempio: "per le vendite, dire o premere o dire 1.</span><span class="sxs-lookup"><span data-stu-id="9d065-205">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="9d065-206">Per i servizi, premere o pronunciare 2.</span><span class="sxs-lookup"><span data-stu-id="9d065-206">For Services, press or say 2.</span></span> <span data-ttu-id="9d065-207">Per l'assistenza clienti, premere o pronunciare 3.</span><span class="sxs-lookup"><span data-stu-id="9d065-207">For Customer Support, press or say 3.</span></span> <span data-ttu-id="9d065-208">Per contattare un operatore, premere o pronunciare 0.</span><span class="sxs-lookup"><span data-stu-id="9d065-208">For the operator, press or say 0.</span></span> <span data-ttu-id="9d065-209">Per ascoltare di nuovo questo menu, premere il tasto asterisco o pronunciare Ripeti".</span><span class="sxs-lookup"><span data-stu-id="9d065-209">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="9d065-210">**Digitare un messaggio di saluto** Se si è scelto questo articolo, è necessario immettere il testo che si vuole leggere dal sistema (fino a 1000 caratteri).</span><span class="sxs-lookup"><span data-stu-id="9d065-210">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="9d065-211">**Carica un file audio** Se scegli questa opzione, dovrai registrare il messaggio di saluto e poi caricare il file audio (in formato .wav, .mp3 o .wma).</span><span class="sxs-lookup"><span data-stu-id="9d065-211">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Icona del numero 4, che fa riferimento a un callout nella schermata precedente](media/sfbcallout4.png)

<span data-ttu-id="9d065-213">**Configurazione delle opzioni del menu** Le opzioni di menu che usano i pulsanti chiave sulla tastiera possono essere aggiunte o rimosse.</span><span class="sxs-lookup"><span data-stu-id="9d065-213">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="9d065-214">Per aggiungere un'opzione di menu, premere **+ assegnazione di un tasto**di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9d065-214">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="9d065-215">Di seguito viene visualizzata una riga di opzioni corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9d065-215">A corresponding row of options will appear below.</span></span> <span data-ttu-id="9d065-216">Per eliminare un'opzione di menu, fare semplicemente clic a sinistra del tasto corrispondente sul controllo tastiera e fare clic sull'icona Elimina sopra.</span><span class="sxs-lookup"><span data-stu-id="9d065-216">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="9d065-217">La riga di mapping dei tasti verrà rimossa.</span><span class="sxs-lookup"><span data-stu-id="9d065-217">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="9d065-218">Sarà necessario aggiornare il menu richieste di testo o registrare di nuovo l'audio separatamente quando si aggiungono le opzioni di rimozione perché non verranno eseguite automaticamente per il prompt dei menu esistente.</span><span class="sxs-lookup"><span data-stu-id="9d065-218">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="9d065-219">Qualsiasi opzione di menu può essere aggiunta e rimossa in qualsiasi ordine e i mapping delle chiavi non devono essere continui.</span><span class="sxs-lookup"><span data-stu-id="9d065-219">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="9d065-220">È possibile, ad esempio, creare un menu con i tasti 0, 1 e 3 mappato alle opzioni, mentre il tasto 2 non viene usato.</span><span class="sxs-lookup"><span data-stu-id="9d065-220">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="9d065-221">I tasti \* (Repeat) e \# (back) sono riservati dal sistema e non possono essere riassegnati.</span><span class="sxs-lookup"><span data-stu-id="9d065-221">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="9d065-222">Se il riconoscimento vocale è abilitato, premendo \* corrisponderà a "REPEAT" e # corrisponderà ai comandi vocali "back".</span><span class="sxs-lookup"><span data-stu-id="9d065-222">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="9d065-223">Per configurare le opzioni di menu, dopo aver selezionato il tasto o i tasti di scelta rapida, sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="9d065-223">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="9d065-224">Immettere il **comando vocale** dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="9d065-224">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="9d065-225">Questo può contenere fino a 64 caratteri e può includere più parole come "Customer Service" o "Operations and grounds".</span><span class="sxs-lookup"><span data-stu-id="9d065-225">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="9d065-226">Se è abilitato il riconoscimento vocale, verrà riconosciuto automaticamente il nome e la persona chiamata sarà in grado di premere 3, dire "tre" oppure "Servizio clienti" per selezionare l'opzione mappata al tasto 3.</span><span class="sxs-lookup"><span data-stu-id="9d065-226">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="9d065-227">Selezionare la posizione in cui deve essere inviata la chiamata se viene premuto il tasto corrispondente oppure l'opzione è selezionata tramite riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="9d065-227">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="9d065-228">La chiamata può essere inviata a:</span><span class="sxs-lookup"><span data-stu-id="9d065-228">The call can be sent to:</span></span>

  - <span data-ttu-id="9d065-229">**Operatore** Se l'operatore è già stato configurato, viene automaticamente mappato al tasto 0, ma può anche essere eliminato o riassegnato a un tasto diverso.</span><span class="sxs-lookup"><span data-stu-id="9d065-229">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="9d065-230">Se l'operatore non è impostato su nessun tasto, anche il comando vocale "Operatore" verrà disabilitato.</span><span class="sxs-lookup"><span data-stu-id="9d065-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="9d065-231">Una **Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati.</span><span class="sxs-lookup"><span data-stu-id="9d065-231">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="9d065-232">Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-232">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="9d065-233">A questo scopo, seleziona **persona nella tua azienda** e imposta questa persona per inoltrare le chiamate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-233">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="9d065-234">**La persona della società** può essere un utente online o un utente ospitato in locale con Skype for Business Server o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d065-234">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>
    - <span data-ttu-id="9d065-235">Un altro **operatore automatico**</span><span class="sxs-lookup"><span data-stu-id="9d065-235">Another **Auto attendant**</span></span>

       <span data-ttu-id="9d065-236">Puoi usare un operatore automatico esistente per creare un secondo livello di opzioni di menu che contiene un sottomenu.</span><span class="sxs-lookup"><span data-stu-id="9d065-236">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="9d065-237">Questi sono denominati operatori automatici innestati.</span><span class="sxs-lookup"><span data-stu-id="9d065-237">These are called nested auto attendants.</span></span> <span data-ttu-id="9d065-238">Per inviare la chiamata a un operatore automatico annidato, selezionare **persona in società** e assegnare un account di risorse, uno che ha già un operatore automatico associato o uno che verrà associato a un operatore automatico dopo aver creato questo operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-238">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="9d065-239">Gli **Orari d'ufficio** degli operatori automatici innestati (o di secondo livello) verranno inoltre utilizzate, incluso per le chiamate inviate da altri operatori automatici che sono stati configurati.</span><span class="sxs-lookup"><span data-stu-id="9d065-239">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

       - <span data-ttu-id="9d065-240">**Applicazione vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="9d065-240">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icona del numero 5, che fa riferimento a un callout nella schermata precedente](media/sfbcallout5.png)

<span data-ttu-id="9d065-242">**Chiamata per nome** Se scegli questa opzione, consentirà agli utenti che accedono alla ricerca di persone nell'organizzazione tramite la ricerca nella directory.</span><span class="sxs-lookup"><span data-stu-id="9d065-242">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="9d065-243">Puoi selezionare quali persone saranno elencate come disponibili o non disponibili per Chiamata per nome definendo queste opzioni nella pagina **Ambito chiamata**.</span><span class="sxs-lookup"><span data-stu-id="9d065-243">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="9d065-244">Tutti gli utenti online con una licenza di **sistema telefonico** o qualsiasi utente ospitato in locale con Skype for Business Server o Lync Server 2013 possono essere trovati con la chiamata per nome.</span><span class="sxs-lookup"><span data-stu-id="9d065-244">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="9d065-245">Dopo aver completato le selezioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9d065-245">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="9d065-246">Impostazioni delle chiamate per le festività</span><span class="sxs-lookup"><span data-stu-id="9d065-246">Holiday call settings</span></span>

<span data-ttu-id="9d065-247">È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-247">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="9d065-248">Per creare festività, è possibile visualizzare le **Impostazioni** > **a** livello di organizzazione, oppure crearle come parte della creazione di un nuovo gestore chiamate.</span><span class="sxs-lookup"><span data-stu-id="9d065-248">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Screenshot della pagina delle impostazioni delle chiamate festive](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="9d065-251">Se sono già stati creati altri operatori automatici, è possibile che venga visualizzata un'opzione che consente di usare o modificare le informazioni necessarie in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="9d065-251">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="9d065-252">In caso contrario, devi creare un nuovo gestore chiamate.</span><span class="sxs-lookup"><span data-stu-id="9d065-252">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="9d065-253">Per aggiungere un nuovo gestore chiamate, fare clic su **+ nuovo gestore chiamate**.</span><span class="sxs-lookup"><span data-stu-id="9d065-253">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Screenshot che mostra l'aggiunta di un nuovo gestore chiamate](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="9d065-256">Nella nuova finestra immettere un nome per il gestore della nuova chiamata nella parte superiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="9d065-256">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="9d065-258">Se il nome della tua vacanza esiste già nell'elenco a discesa **festività** , puoi usarlo.</span><span class="sxs-lookup"><span data-stu-id="9d065-258">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="9d065-259">Se il nome di festività necessario non esiste già, selezionare **Crea nuova festività** nell'elenco a discesa e assegnare un nome e una data per la nuova festività nella nuova schermata visualizzata.</span><span class="sxs-lookup"><span data-stu-id="9d065-259">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="9d065-260">Fare clic su **Salva** quando si è pronti.</span><span class="sxs-lookup"><span data-stu-id="9d065-260">Click on **Save** when ready.</span></span>

<span data-ttu-id="9d065-261">I nomi delle festività possono essere formati da un massimo di 64 caratteri e devono essere univoci per l'operatore automatico stesso.</span><span class="sxs-lookup"><span data-stu-id="9d065-261">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="9d065-262">Ad esempio, è possibile avere due festività denominate "Giorno del ringraziamento" nello stesso operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-262">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Icona del numero 3, che fa riferimento a un callout nella schermata precedente](media/sfbcallout3.png)

<span data-ttu-id="9d065-264">**Messaggio di saluto** Il messaggio di saluto è facoltativo e può essere impostato su **Nessun saluto**.</span><span class="sxs-lookup"><span data-stu-id="9d065-264">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="9d065-265">In questo caso, il chiamante non udirà alcun messaggio o saluto prima che la chiamata venga gestita da una delle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="9d065-265">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="9d065-266">È possibile caricare un file audio (nel formato con estensione wav, mp3 o .wma) o creare un messaggio di saluto personalizzato utilizzando la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="9d065-266">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="9d065-267">**Nessun saluto** Nessun messaggio di saluto verrà riprodotto quando gli utenti chiamano il numero di telefono dell'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9d065-267">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="9d065-268">**Caricare un file audio** Se si sceglie questo documento, registrare il messaggio di saluto e quindi caricare il file audio (in formato. wav,. mp3 o. WMA)</span><span class="sxs-lookup"><span data-stu-id="9d065-268">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="9d065-269">**Digitare un messaggio di saluto** Se si sceglie questa opzione, immettere il testo da leggere per il sistema (fino a 1000 caratteri).</span><span class="sxs-lookup"><span data-stu-id="9d065-269">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="9d065-270">Ad esempio, è possibile immettere "Buon anno!</span><span class="sxs-lookup"><span data-stu-id="9d065-270">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="9d065-271">I nostri uffici sono chiusi."</span><span class="sxs-lookup"><span data-stu-id="9d065-271">Our offices are currently closed."</span></span> <span data-ttu-id="9d065-272">nella casella **digitare un messaggio di saluto** .</span><span class="sxs-lookup"><span data-stu-id="9d065-272">in the **Type a greeting message** box.</span></span>

![Icona del numero 4, che fa riferimento a un callout nella schermata precedente](media/sfbcallout4.png)

<span data-ttu-id="9d065-274">**Azioni** È possibile selezionare cosa succede alle chiamate che arrivano durante questa festività.</span><span class="sxs-lookup"><span data-stu-id="9d065-274">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="9d065-275">È possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d065-275">You can chose from the following options:</span></span>

- <span data-ttu-id="9d065-276">**Disconnettere**  La persona chiamata verrà disconnessa dopo aver ascoltato il messaggio di saluto di festività.</span><span class="sxs-lookup"><span data-stu-id="9d065-276">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="9d065-277">**Reindirizzare una chiamata** Ciò consente di inviare automaticamente la chiamata a:</span><span class="sxs-lookup"><span data-stu-id="9d065-277">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="9d065-278">Una **Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati.</span><span class="sxs-lookup"><span data-stu-id="9d065-278">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="9d065-279">Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-279">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="9d065-280">A questo scopo, seleziona **persona nella tua azienda**e imposta questa persona per inoltrare le chiamate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9d065-280">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="9d065-281">Una **Persona nell'azienda** può essere un utente in linea o un utente ospitato in locale con Skype per Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d065-281">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="9d065-282">**Applicazione vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="9d065-282">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="9d065-283">Per impostazione predefinita, per tutte le chiamate in arrivo per un periodo di festività impostate per essere disconnesse dopo il messaggio di saluto (se esistenti), è necessario specificare un reindirizzamento se non si desidera un comportamento diverso.</span><span class="sxs-lookup"><span data-stu-id="9d065-283">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="9d065-284">Pagina Seleziona ambito di chiamata</span><span class="sxs-lookup"><span data-stu-id="9d065-284">Select dial scope page</span></span>

<span data-ttu-id="9d065-285">In questa pagina è possibile configurare gli utenti dell'organizzazione che verranno elencati nella directory e disponibili per il nome della chiamata per ogni persona che chiama l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d065-285">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Schermata che mostra la pagina dell'ambito di chiamata](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="9d065-287">![Icona del numero 1, facendo riferimento a un callout nello screenshot](media/sfbcallout1.png) precedente con l'opzione **Includi** , sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="9d065-287">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="9d065-288">**Tutti gli utenti online** Questa opzione permette di includere tutte le persone dell'organizzazione nella ricerca in elenco.</span><span class="sxs-lookup"><span data-stu-id="9d065-288">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="9d065-289">Tutti gli utenti online con una licenza di **sistema telefonico** , nonché gli utenti ospitati in locale con Skype for Business Server o Lync Server 2013 che hanno piani di chiamata in Office 365, verranno elencati.</span><span class="sxs-lookup"><span data-stu-id="9d065-289">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="9d065-290">**Gruppo utenti personalizzato** Se si usa questa opzione, è possibile cercare un gruppo, una lista di distribuzione o un gruppo di sicurezza di Office 365 creato nell'organizzazione e le persone aggiunte al gruppo di Office 365, alla lista di distribuzione o al gruppo di sicurezza che sono **utenti online con un Licenza di sistema telefonico** o ospitata in locale con Skype for Business Server 2015 o Lync server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d065-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="9d065-291">È possibile aggiungere più gruppi di Office 365, liste di distribuzione e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9d065-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="9d065-293">Con l'opzione **Escludi** sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="9d065-293">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="9d065-294">**Nessuno** Questa opzione indica che nessun utente online sarà escluso dalla ricerca in elenco.</span><span class="sxs-lookup"><span data-stu-id="9d065-294">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="9d065-295">**Gruppo utenti personalizzato** Se si usa questa opzione, è possibile cercare un gruppo, una lista di distribuzione o un gruppo di sicurezza di Office 365 creato nell'organizzazione e tutti gli utenti aggiunti a questo gruppo di Office 365, a una lista di distribuzione o a gruppi di sicurezza verranno esclusi dalla ricerca nella directory.</span><span class="sxs-lookup"><span data-stu-id="9d065-295">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="9d065-296">È possibile aggiungere più gruppi di Office 365, liste di distribuzione e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9d065-296">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="9d065-297">Il nome di un nuovo utente può richiedere fino a 36 ore nella directory quando qualcuno usa la chiamata per nome con il riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="9d065-297">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="9d065-298">Dopo aver immesso tutti i campi obbligatori e configurato i menu e le opzioni di gestione delle chiamate, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="9d065-298">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="9d065-299">Modifica e test degli operatori automatici</span><span class="sxs-lookup"><span data-stu-id="9d065-299">Editing and testing auto attendants</span></span>

<span data-ttu-id="9d065-300">Dopo aver salvato il tuo operatore automatico, verrà elencato nella pagina **Operatori automatici**.</span><span class="sxs-lookup"><span data-stu-id="9d065-300">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="9d065-301">In questo modo è possibile visualizzare rapidamente alcune delle opzioni configurate, ad esempio il nome, il numero di telefono, la lingua e lo stato.</span><span class="sxs-lookup"><span data-stu-id="9d065-301">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="9d065-302">Se si vogliono apportare modifiche a un operatore automatico, selezionare l'operatore automatico e quindi nel riquadro azioni fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="9d065-302">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="9d065-303">È anche possibile inserire rapidamente una chiamata di test all'operatore automatico usando il pulsante **test** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="9d065-303">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="9d065-304">Cmdlet dell'operatore automatico</span><span class="sxs-lookup"><span data-stu-id="9d065-304">Auto attendant cmdlets</span></span>

<span data-ttu-id="9d065-305">Puoi anche utilizzare Windows PowerShell per creare e configurare gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="9d065-305">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="9d065-306">Ecco i cmdlet necessari per gestire un operatore automatico:</span><span class="sxs-lookup"><span data-stu-id="9d065-306">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="9d065-307">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="9d065-307">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="9d065-308">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="9d065-308">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9d065-309">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="9d065-309">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9d065-310">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="9d065-310">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9d065-311">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="9d065-311">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9d065-312">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="9d065-312">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="9d065-313">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="9d065-313">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="9d065-314">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="9d065-314">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="9d065-315">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="9d065-315">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9d065-316">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="9d065-316">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="9d065-317">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="9d065-317">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="9d065-318">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="9d065-318">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="9d065-319">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="9d065-319">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="9d065-320">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="9d065-320">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="9d065-321">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="9d065-321">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="9d065-322">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="9d065-322">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9d065-323">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="9d065-323">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="9d065-324">Altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d065-324">More about Windows PowerShell</span></span>

- <span data-ttu-id="9d065-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9d065-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9d065-326">Con Windows PowerShell è possibile gestire Office 365 e Microsoft teams usando un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9d065-326">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9d065-327">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="9d065-327">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9d065-328">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d065-328">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="9d065-329">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="9d065-329">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="9d065-330">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9d065-330">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9d065-331">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9d065-331">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="9d065-332">Gestire Office 365 con Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d065-332">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="9d065-333">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9d065-333">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="9d065-334">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9d065-334">Related topics</span></span>

[<span data-ttu-id="9d065-335">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="9d065-335">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="9d065-336">Recupero di numeri di telefono del servizio</span><span class="sxs-lookup"><span data-stu-id="9d065-336">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="9d065-337">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="9d065-337">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="9d065-338">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="9d065-338">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="9d065-339">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="9d065-339">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="9d065-340">Esempio per piccole imprese - Impostare un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="9d065-340">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
