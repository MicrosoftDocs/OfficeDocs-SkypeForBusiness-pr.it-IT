---
title: Usare la procedura guidata Attività iniziali per configurare Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
- m365initiative-voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a3a5162f46631e00e6ffc22c19654908b4cb78b
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726237"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a><span data-ttu-id="69be9-102">Usare la procedura guidata Attività iniziali per configurare Business Voice</span><span class="sxs-lookup"><span data-stu-id="69be9-102">Use the Getting Started wizard to set up Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69be9-103">Le informazioni contenute in questo articolo sono applicabili solo a Business Voice **senza** Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="69be9-103">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="69be9-104">Business Voice con Piano per chiamate è disponibile solo in determinati paesi e regioni.</span><span class="sxs-lookup"><span data-stu-id="69be9-104">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="69be9-105">Prima di leggere questo articolo, controllare la [disponibilità di Business Voice per paesi e aree geografiche](country-region-availability.md) per verificare se il proprio paese o area geografica supporta Business Voice con Piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="69be9-105">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="69be9-106">Se il tenant si trova in un paese o un'area geografica che non supporta Business Voice con Piano per chiamate, vedere [Ottenere assistenza da parte di un rivenditore o un partner Microsoft](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="69be9-106">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="69be9-107">La procedura guidata Attività iniziali per configurare rapidamente Microsoft 365 Business Voice consente di effettuare e ricevere chiamate telefoniche in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="69be9-107">The Getting Started wizard for Microsoft 365 Business Voice gets you set up quickly to make and receive phone calls in Microsoft Teams.</span></span> <span data-ttu-id="69be9-108">Per le aziende di piccole dimensioni che partono da zero, la procedura guidata consente di iniziare a usare il sistema in pochi minuti con numeri di telefono, menu di chiamata, messaggi di saluto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="69be9-108">If you're a small business just starting out, the wizard can get you up and running in a few minutes with phone numbers, call menus, greetings, and more.</span></span> <span data-ttu-id="69be9-109">Per le aziende più grandi con una soluzione di telefonia consolidata, la procedura guidata consente di configurare una distribuzione pilota di Business Voice, in modo da poterlo usare con pochi utenti prima di configurarlo per tutti.</span><span class="sxs-lookup"><span data-stu-id="69be9-109">If you're a larger business with an established telephony solution, the wizard can help you set up a pilot so a few users can try Business Voice before you roll it out for everyone.</span></span> <span data-ttu-id="69be9-110">In entrambi i casi, si può iniziare a usare Business Voice appena terminata la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="69be9-110">Either way, you can start using Business Voice as soon as the wizard is finished!</span></span>

<span data-ttu-id="69be9-111">È consigliabile leggere questo articolo prima di avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="69be9-111">It's a good idea to read this article before you start the wizard.</span></span> <span data-ttu-id="69be9-112">Quando si è pronti a eseguire la procedura guidata, selezionare **Inizia** nella pagina [Introduzione a Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice).</span><span class="sxs-lookup"><span data-stu-id="69be9-112">When you're ready to run the wizard, select **Get started** on the [Get started with Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice) page.</span></span> <span data-ttu-id="69be9-113">Accedere con l'account usato per creare l'abbonamento o un altro account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="69be9-113">Sign in by using the account you used to create your subscription or another account that's a Global Administrator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69be9-114">Microsoft Teams e Business Voice funzionano solo quando le cassette postali degli utenti si trovano in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69be9-114">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="69be9-115">Le cassette postali in Exchange Server locale non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="69be9-115">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="69be9-116">Attività iniziali guidate non supporta le distribuzioni ibride di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="69be9-116">The Getting Started Wizard doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="69be9-117">Se si usa una distribuzione ibrida di Skype for Business e si vuole configurare VoIP aziendale, vedere [Configurare il Sistema telefonico nell'organizzazione](../setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="69be9-117">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

<span data-ttu-id="69be9-118">Se non si vuole personalizzare subito nulla, l'operazione è completata.</span><span class="sxs-lookup"><span data-stu-id="69be9-118">If you don't want to customize anything immediately, you're done!</span></span> <span data-ttu-id="69be9-119">È possibile iniziare subito a usare Business Voice.</span><span class="sxs-lookup"><span data-stu-id="69be9-119">You can start using Business Voice right away.</span></span>

## <a name="emergency-services-location"></a><span data-ttu-id="69be9-120">Ubicazione dei servizi di emergenza</span><span class="sxs-lookup"><span data-stu-id="69be9-120">Emergency services location</span></span>

<table>
    <tr>
        <td><span data-ttu-id="69be9-121">Se si desidera modificare l'indirizzo di emergenza, fare clic su <b>Modifica</b> e immettere un nuovo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="69be9-121">If you want to change the emergency address, click <b>Edit</b>, and then enter a new address.</span></span> <span data-ttu-id="69be9-122">L'indirizzo specificato viene convalidato per verificare che sia legittimo e formattato correttamente per i servizi di risposta alle emergenze.</span><span class="sxs-lookup"><span data-stu-id="69be9-122">The address that you provide is validated to make sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="69be9-123">L'indirizzo viene quindi assegnato a tutti gli utenti a cui si assegnerà un numero nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="69be9-123">This address is then assigned to all users that you assign a number to in the next step.</span></span> <span data-ttu-id="69be9-124">Se si hanno dipendenti in più ubicazioni, vedere <a href="./customize-business-voice.md">Personalizzazione di Business Voice</a> per aggiungere e assegnare più indirizzi di emergenza dopo aver completato la procedura guidata Attività iniziali.</span><span class="sxs-lookup"><span data-stu-id="69be9-124">If you have employees in more than one location, see <a href="./customize-business-voice.md">Business Voice design customization</a> to add and assign more emergency addresses after you prepare the Getting Started wizard.</span></span></td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400" alt="wizard choose number"></td></tr>
</table>

<span data-ttu-id="69be9-125">Per altre informazioni, vedere [Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?](../what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="69be9-125">For more information, see [What are emergency locations, addresses, and call routing](../what-are-emergency-locations-addresses-and-call-routing.md)?</span></span>

## <a name="company-phone-number"></a><span data-ttu-id="69be9-126">Numero di telefono aziendale</span><span class="sxs-lookup"><span data-stu-id="69be9-126">Company phone number</span></span>

<table>
    <tr>
        <td><span data-ttu-id="69be9-127">Oltre a un nuovo numero di telefono locale, si può acquistare un numero verde o trasferire un numero esistente in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69be9-127">In addition to a new local phone number, you can purchase a toll-free number or port an existing number to Microsoft 365.</span></span> <span data-ttu-id="69be9-128">Per configurare un numero verde, è necessario acquistare Credito per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="69be9-128">To set up a toll-free number, you need to purchase Communications Credits.</span></span> <span data-ttu-id="69be9-129">Per trasferire uno o più numeri in Microsoft 365, accedere all'<a href="https://admin.teams.microsoft.com">interfaccia di amministrazione di Teams</a> al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="69be9-129">To port one or more numbers to Microsoft 365, go to the <a href="https://admin.teams.microsoft.com">Teams admin center</a> after the wizard finishes.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400" alt="choose number">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="69be9-130">Se si trasferisce un numero di telefono esistente in Microsoft 365, nella procedura guidata verrà comunque visualizzato un numero di telefono temporaneo.</span><span class="sxs-lookup"><span data-stu-id="69be9-130">If you port an existing phone number to Microsoft 365, you'll still see a temporary phone number in the wizard.</span></span> <span data-ttu-id="69be9-131">Questo è il comportamento previsto.</span><span class="sxs-lookup"><span data-stu-id="69be9-131">This is expected.</span></span> <span data-ttu-id="69be9-132">Dopo aver completato la procedura guidata e il processo di portabilità, il numero di telefono temporaneo verrà sostituito con il numero preesistente.</span><span class="sxs-lookup"><span data-stu-id="69be9-132">After you complete the wizard and the porting process, the temporary phone number will be replaced by the pre-existing number.</span></span>

## <a name="user-licenses"></a><span data-ttu-id="69be9-133">Licenze utente</span><span class="sxs-lookup"><span data-stu-id="69be9-133">User licenses</span></span>

<table>
    <tr>
        <td><span data-ttu-id="69be9-134">Per assegnare le licenze agli utenti, selezionare le persone dell'organizzazione che vogliono effettuare o ricevere telefonate all'esterno di Teams (ad esempio, per chiamare un fornitore).</span><span class="sxs-lookup"><span data-stu-id="69be9-134">To assign user licenses, select the people in your organization who need to make or receive phone calls outside of Teams (such as calling a supplier).</span></span> <span data-ttu-id="69be9-135">È possibile assegnare solo le licenze di Business Voice già disponibili.</span><span class="sxs-lookup"><span data-stu-id="69be9-135">You can only assign as many Business Voices licenses as you have available.</span></span> <span data-ttu-id="69be9-136">Se ne servono di più, è possibile acquistare altre licenze al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="69be9-136">If you need more, you can buy additional licenses after the wizard is finished.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400" alt="get numbers">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="69be9-137">Dopo aver completato la procedura guidata, è possibile trasferire i numeri di telefono esistenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69be9-137">You can port existing phone numbers to Microsoft 365 after the wizard is finished.</span></span> <span data-ttu-id="69be9-138">Dopo aver completato il processo di portabilità, i numeri di telefono trasferiti sostituiranno i numeri di telefono temporanei forniti dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="69be9-138">After you complete the porting process, the ported phone numbers will replace the temporary phone numbers that the wizard provided.</span></span>

## <a name="incoming-call-greeting"></a><span data-ttu-id="69be9-139">Messaggio di saluto per le chiamate in arrivo</span><span class="sxs-lookup"><span data-stu-id="69be9-139">Incoming-call greeting</span></span>

<table>
    <tr>
        <td><span data-ttu-id="69be9-140">È possibile caricare un file audio (MP3 o WAV) di dimensioni massime di 5 megabyte (MB) da usare come messaggio di saluto, oppure si può digitare il messaggio e Microsoft 365 userà la sintesi vocale per leggerlo al chiamante.</span><span class="sxs-lookup"><span data-stu-id="69be9-140">You can upload a sound file (MP3 or WAV) of up to 5 Megabytes (MB) to use as a call greeting, or you can type your greeting, and Microsoft 365 will use text-to-speech to read it to the caller.</span></span> <span data-ttu-id="69be9-141">Il messaggio di saluto sarà la prima cosa che sentirà chi chiama il numero di telefono dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="69be9-141">The greeting will be the first thing callers hear when they call your company phone number.</span></span> <span data-ttu-id="69be9-142">Per la sintesi vocale, potrebbe essere necessario usare grafie fonetiche per ottenere la pronuncia giusta.</span><span class="sxs-lookup"><span data-stu-id="69be9-142">For text-to-speech, you might need to use phonetic spellings to get the pronunciations correct.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400" alt="greeting">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a><span data-ttu-id="69be9-143">Menu di chiamata e inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="69be9-143">Call menu and forwarding</span></span>

<table>
    <tr>
        <td><span data-ttu-id="69be9-144">È possibile inoltrare tutte le chiamate a un utente specifico oppure configurare un menu di chiamata da cui scegliere opzioni.</span><span class="sxs-lookup"><span data-stu-id="69be9-144">You can forward all calls to a specific user, or you can set up a menu that the caller can choose options from.</span></span> <span data-ttu-id="69be9-145">Se si crea un menu di chiamata, vengono specificate le opzioni che un chiamante può selezionare premendo un numero sul tastierino del telefono o pronunciando l'opzione con un comando vocale.</span><span class="sxs-lookup"><span data-stu-id="69be9-145">If you create a call menu, you specify options that the caller can select by voice or by pressing a number on a phone's keypad.</span></span> <span data-ttu-id="69be9-146">Ogni opzione di menu può inoltrare chiamate a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="69be9-146">Each menu option can forward calls to a specific user.</span></span><br><br>
        <span data-ttu-id="69be9-147">Si può caricare un file audio (MP3 o WAV) fino a un massimo di 5 MB che fornisce istruzioni al chiamante oppure è possibile digitare le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="69be9-147">You can upload a sound file (MP3 or WAV) of up to 5 MB that gives instructions to the caller, or you can type the instructions.</span></span> <span data-ttu-id="69be9-148">Microsoft 365 userà la sintesi vocale per leggere le istruzioni al chiamante.</span><span class="sxs-lookup"><span data-stu-id="69be9-148">Microsoft 365 will use text-to-speech to read them to the caller.</span></span> <span data-ttu-id="69be9-149">Per ottenere la pronuncia giusta potrebbe essere necessario scrivere le parole così come si pronunciano, usando un'ortografia errata.</span><span class="sxs-lookup"><span data-stu-id="69be9-149">You might need to spell words phonetically to get the pronunciations right.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400" alt="call forwarding">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="69be9-150">Le attività iniziali guidate consentono di configurare un semplice menu di chiamata per diventare subito operativi.</span><span class="sxs-lookup"><span data-stu-id="69be9-150">The Getting Started wizard helps you set up a simple call menu to get you up and running quickly.</span></span> <span data-ttu-id="69be9-151">Se si hanno più numeri di telefono con i menu di chiamata da configurare o se si vogliono configurare menu di chiamata più complessi (detti anche operatori automatici), vedere [Configurare un operatore automatico cloud](set-up-auto-attendants.md) al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="69be9-151">If you have multiple phone numbers that you want to set up call menus for or you want to set up more complex call menus (also called auto attendants), see [Set up a Cloud auto attendant](set-up-auto-attendants.md) after you finish the wizard.</span></span>

<table>
    <tr>
        <td> <p><span data-ttu-id="69be9-152">La procedura guidata Attività iniziali considera le informazioni immesse dall'utente e configura Business Voice.</span><span class="sxs-lookup"><span data-stu-id="69be9-152">The Getting Started wizard takes the information that you enter and sets up Business Voice.</span></span> <span data-ttu-id="69be9-153">Nella pagina <b>Panoramica</b>, è possibile visualizzare i numeri di telefono assegnati agli utenti, esaminare il menu di chiamata, ascoltare il messaggio di saluto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="69be9-153">On the <b>Overview</b> page, you can see what phone numbers are assigned to your users, look at your call menu, listen to your greeting, and more.</span></span></p>
             <p><span data-ttu-id="69be9-154">La configurazione richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="69be9-154">Setup takes several minutes.</span></span> <span data-ttu-id="69be9-155">Se si seleziona <b>Fine</b>, la configurazione di Business Voice continua in background.</span><span class="sxs-lookup"><span data-stu-id="69be9-155">If you select <b>Done</b>, we'll continue to set up Business Voice in the background.</span></span> <span data-ttu-id="69be9-156">In alternativa, è possibile attendere il completamento della configurazione.</span><span class="sxs-lookup"><span data-stu-id="69be9-156">Or just wait until setup is finished.</span></span> <span data-ttu-id="69be9-157">Una volta completata la procedura, passare a <b>Voce </b>nell'<a href="https://admin.teams.microsoft.com" target="_blank">interfaccia di amministrazione di Teams</a> per configurare altre funzionalità di Business Voice.</span><span class="sxs-lookup"><span data-stu-id="69be9-157">After it's finished, go to <b>Voice</b> in the <a href="https://admin.teams.microsoft.com" target="_blank">Teams admin center</a> to set up more Business Voice features.</span></span></p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400" alt="finish page">
        </td>
    </tr>
</table>
