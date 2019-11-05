---
title: Usare la procedura guidata Attività iniziali per configurare Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46f6f75ce0ac14193a4f7a8cfccadf8312f92a98
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972197"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a><span data-ttu-id="32acb-102">Usare la procedura guidata Attività iniziali per configurare Business Voice</span><span class="sxs-lookup"><span data-stu-id="32acb-102">Use the Getting Started wizard to set up Business Voice</span></span>

<span data-ttu-id="32acb-103">La procedura guidata Attività iniziali per Microsoft 365 Business Voice offre un modo semplice e veloce per iniziare a ricevere ed effettuare telefonate in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="32acb-103">The Getting Started wizard for Microsoft 365 Business Voice gives you an easy and quick way to start receiving and making phone calls in Microsoft Teams.</span></span> <span data-ttu-id="32acb-104">Per le aziende di piccole dimensioni che partono da zero, la procedura guidata consente di iniziare a usare il sistema in pochi minuti con numeri di telefono, menu di chiamata, messaggi di saluto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="32acb-104">If you're a small business just starting out, the wizard can get you up and running in a few minutes with phone numbers, call menus, greetings, and more.</span></span> <span data-ttu-id="32acb-105">Per le aziende più grandi con una soluzione di telefonia consolidata, la procedura consente di configurare una distribuzione pilota di Business Voice, in modo da poterlo usare con pochi utenti prima di configurarlo per tutti.</span><span class="sxs-lookup"><span data-stu-id="32acb-105">If you're a larger business with an established telephony solution, the wizard can help you set up a Business Voice pilot so you can try it out with a few users before you set it up for everyone.</span></span> <span data-ttu-id="32acb-106">In entrambi i casi, si può iniziare a usare Business Voice appena terminata la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32acb-106">Either way, you can start using Business Voice as soon as the wizard is finished!</span></span>

<span data-ttu-id="32acb-107">È consigliabile leggere questo articolo prima di avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32acb-107">It's a good idea to read this article before you start the wizard.</span></span> <span data-ttu-id="32acb-108">Quando si è pronti, è possibile aprire la procedura guidata dall'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/AdminPortal/Home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="32acb-108">When you're ready, you can open the wizard from the [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/Home#/homepage).</span></span> <span data-ttu-id="32acb-109">Assicurarsi di accedere con l'account usato per creare l'abbonamento o un altro account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="32acb-109">Make sure you sign in either with the account you used to create your subscription or another account that's a Global Administrator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32acb-110">Business Voice è attualmente disponibile in Canada e nel Regno Unito.</span><span class="sxs-lookup"><span data-stu-id="32acb-110">Business Voice is currently available in Canada and the United Kingdom.</span></span> <span data-ttu-id="32acb-111">Altri paesi e aree geografiche diventeranno disponibili nel 2020.</span><span class="sxs-lookup"><span data-stu-id="32acb-111">More countries and regions will become available in 2020.</span></span>
>
> <span data-ttu-id="32acb-112">Microsoft Teams e Business Voice funzionano solo quando le cassette postali degli utenti si trovano in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32acb-112">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="32acb-113">Le cassette postali ubicate nel server di Exchange locale non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="32acb-113">We don't support mailboxes located on on-premises Exchange server.</span></span>

<!-- After you've finished the wizard, here are a couple articles you can check out to see what you can do with Business Voice and learn how to customize it. If you don't want to customize anything, you're done! You can start using Business Voice right away.

* [Things to try with Business Voice](things-to-try.md)
* [Customize Business Voice](customize-business-voice.md)
-->

## <a name="emergency-services-location"></a><span data-ttu-id="32acb-114">Ubicazione dei servizi di emergenza</span><span class="sxs-lookup"><span data-stu-id="32acb-114">Emergency services location</span></span>

<table>
    <tr>
        <td><span data-ttu-id="32acb-115">Se si vuole modificare l'indirizzo di emergenza, fare clic su <b>Modifica</b> e immettere un nuovo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="32acb-115">If you'd like to change the emergency address, click <b>Edit</b> and enter a new address.</span></span> <span data-ttu-id="32acb-116">L'indirizzo specificato viene convalidato per verificare che sia legittimo e formattato correttamente per i servizi di risposta alle emergenze.</span><span class="sxs-lookup"><span data-stu-id="32acb-116">The address you provide is validated to make sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="32acb-117">Se è valido, l'indirizzo viene assegnato a tutti gli utenti a cui si assegnerà un numero nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="32acb-117">If it's valid, the address is assigned to all of the users you assign a number to in the next step.</span></span> <span data-ttu-id="32acb-118">Se si hanno dipendenti in più ubicazioni, l'argomento Personalizzare Business Voice illustra come aggiungere e assegnare più indirizzi di emergenza dopo aver completato la procedura guidata Attività iniziali.</span><span class="sxs-lookup"><span data-stu-id="32acb-118">If you have employees in more than one location, the Customize Business Voice topic will show you how to add and assign more emergency addresses after you finish the Getting Started wizard.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

<span data-ttu-id="32acb-119">Per saperne di più, vedere [Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?](../what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="32acb-119">If you want to know more about emergency addresses, see [What are emergency locations, addresses and call routing?](../what-are-emergency-locations-addresses-and-call-routing.md)</span></span>

## <a name="company-phone-number"></a><span data-ttu-id="32acb-120">Numero di telefono aziendale</span><span class="sxs-lookup"><span data-stu-id="32acb-120">Company phone number</span></span>

<table>
    <tr>
        <td><span data-ttu-id="32acb-121">Oltre a configurare un nuovo numero di telefono locale, si può scegliere di acquistare un numero verde o trasferire un numero esistente in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32acb-121">In addition to setting up a new phone local phone number, you can choose to purchase a toll-free number or port an existing number to Microsoft 365.</span></span> <span data-ttu-id="32acb-122">Se si sceglie di configurare un numero verde, è necessario acquistare un piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="32acb-122">If you choose to set up a toll-free number, you'll need to purchase a calling plan.</span></span> <span data-ttu-id="32acb-123">Se si vuole trasferire un numero in Microsoft 365, è possibile farlo nell'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com) al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32acb-123">If you want to port a number to Microsoft 365, you'll have an option to do so in the [Teams admin center](https://admin.teams.microsoft.com) after the wizard completes.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="32acb-124">Se si sceglie di trasferire un numero di telefono esistente in Microsoft 365, nella procedura guidata verrà comunque visualizzato un numero di telefono temporaneo.</span><span class="sxs-lookup"><span data-stu-id="32acb-124">If you choose to port an existing phone number to Microsoft 365, you'll still see a temporary phone number in the wizard.</span></span> <span data-ttu-id="32acb-125">Non si tratta di un errore.</span><span class="sxs-lookup"><span data-stu-id="32acb-125">This is ok.</span></span> <span data-ttu-id="32acb-126">Dopo aver completato la procedura guidata e completato il processo di portabilità, il numero di telefono temporaneo verrà sostituito con il numero di telefono effettivo.</span><span class="sxs-lookup"><span data-stu-id="32acb-126">After you complete the wizard, and you complete the porting process, the temporary phone number will be replaced with your phone number.</span></span>

## <a name="assigning-licenses-to-users"></a><span data-ttu-id="32acb-127">Assegnazione di licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="32acb-127">Assigning licenses to users</span></span>

<table>
    <tr>
        <td><span data-ttu-id="32acb-128">Selezionare le persone dell'organizzazione che vogliono effettuare o ricevere telefonate all'esterno di Teams, ad esempio per chiamare un fornitore.</span><span class="sxs-lookup"><span data-stu-id="32acb-128">Select the people in your organization that want to make or receive phone calls outside of Teams (such as calling a supplier).</span></span> <span data-ttu-id="32acb-129">È possibile selezionare un numero di utenti corrispondente al numero di licenze di Business Voice disponibili.</span><span class="sxs-lookup"><span data-stu-id="32acb-129">You can select up to the number of available Business Voice licenses you have available.</span></span> <span data-ttu-id="32acb-130">Se ne servono di più, è possibile acquistare altre licenze al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32acb-130">If you need more, you can buy additional licenses when the wizard is finished.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="32acb-131">Se si vogliono trasferire i numeri di telefono esistenti in Microsoft 365 per singoli utenti, è possibile farlo al termine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32acb-131">If you want to port existing phone numbers to Microsoft 365 for individual users, you can do so after the wizard is complete.</span></span> <span data-ttu-id="32acb-132">Dopo aver completato il processo di portabilità, i numeri di telefono trasferiti sostituiranno i numeri di telefono temporanei selezionati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="32acb-132">After you complete the porting process, the ported phone numbers will replace the temporary phone numbers selected by the wizard.</span></span>

## <a name="incoming-call-greeting"></a><span data-ttu-id="32acb-133">Messaggio di saluto per le chiamate in arrivo</span><span class="sxs-lookup"><span data-stu-id="32acb-133">Incoming call greeting</span></span>

<table>
    <tr>
        <td><span data-ttu-id="32acb-134">È possibile caricare un file audio (MP3 o WAV) di dimensioni massime di 5 megabyte (MB) da usare come messaggio di saluto, oppure si può digitare il messaggio e Microsoft 365 userà la sintesi vocale per leggerlo ai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="32acb-134">You can upload a sound file (MP3 or WAV) that's up to 5 Megabytes (MB) to use as a greeting, or you can type out your greeting and Microsoft 365 will use text-to-speech to read it to a caller.</span></span> <span data-ttu-id="32acb-135">Il messaggio di saluto sarà la prima cosa che udrà chi chiama il numero di telefono dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="32acb-135">The greeting will be the first time callers hear when they call your company phone number.</span></span> <span data-ttu-id="32acb-136">Potrebbe essere necessario scrivere le parole con ortografia errata o usare grafie fonetiche per ottenere la pronuncia giusta.</span><span class="sxs-lookup"><span data-stu-id="32acb-136">You might need to mis-spell the words or use phonetic spellings to get the pronunciations correct.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a><span data-ttu-id="32acb-137">Menu di chiamata e inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="32acb-137">Call menu and forwarding</span></span>

<table>
    <tr>
        <td><span data-ttu-id="32acb-138">È possibile inoltrare tutte le chiamate a un utente specifico oppure configurare un menu di chiamata da cui scegliere opzioni.</span><span class="sxs-lookup"><span data-stu-id="32acb-138">You can forward all calls to a specific user, or you can set up a call menu they can choose options from.</span></span> <span data-ttu-id="32acb-139">Se si crea un menu di chiamata, è possibile specificare le opzioni che un chiamante può selezionare premendo un numero sul tastierino del telefono o pronunciando l'opzione con un comando vocale.</span><span class="sxs-lookup"><span data-stu-id="32acb-139">If you create a call menu, you can specify options that a caller can select either by pressing a number on a phone's keypad, or by speaking the option via the voice command.</span></span> <span data-ttu-id="32acb-140">Ogni opzione di menu può essere inoltrata a un utente.</span><span class="sxs-lookup"><span data-stu-id="32acb-140">Each menu option can be forwarded to one user.</span></span> <br>
<span data-ttu-id="32acb-141">Si può scegliere di caricare un file audio (MP3 o WAV) fino a un massimo di 5 MB che fornisce istruzioni al chiamante oppure è possibile digitare le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="32acb-141">You can choose whether to upload a sound file (MP3 or WAV) that's up to 5MB that gives instructions to the caller or you can type out the instructions instead.</span></span> <span data-ttu-id="32acb-142">Microsoft 365 userà la sintesi vocale per leggere le istruzioni al chiamante.</span><span class="sxs-lookup"><span data-stu-id="32acb-142">Microsoft 365 will use text-to-speech to read the instructions to the caller.</span></span> <span data-ttu-id="32acb-143">Per ottenere la pronuncia giusta potrebbe essere necessario scrivere le parole così come si pronunciano, usando un'ortografia errata.</span><span class="sxs-lookup"><span data-stu-id="32acb-143">You might need to spell words phonetically to get the pronunciations right.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

<table>
    <tr>
        <td> <p><span data-ttu-id="32acb-144">Nella pagina di<b> </b>panoramica, la procedura guidata Attività iniziali raccoglie tutti i dati inseriti e configura Business Voice.</span><span class="sxs-lookup"><span data-stu-id="32acb-144">On the <b>Overview</b> page, the Getting Started wizard takes everything you've entered and sets up Business Voice for you.</span></span> <span data-ttu-id="32acb-145">È possibile visualizzare i numeri di telefono assegnati agli utenti, esaminare il menu di chiamata, ascoltare il messaggio di saluto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="32acb-145">You can see what phone numbers will be assigned to your users, take a look at your call menu, listen to your greeting, and more.</span></span> </p>
             <p><span data-ttu-id="32acb-146">La configurazione di Business Voice richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="32acb-146">Setting up Business Voice takes several minutes.</span></span> <span data-ttu-id="32acb-147">Si può fare clic su <b>Fatto</b> e la configurazione di Business Voice continuerà in background oppure si può attendere il completamento.</span><span class="sxs-lookup"><span data-stu-id="32acb-147">You can click on <b>Done</b> and we'll continue to set up Business Voice in the background, or you can wait until it's finished.</span></span> <span data-ttu-id="32acb-148">Una volta completata la procedura, passare a <b>Voce </b>nell'<a href="https://admin.teams.microsoft.com" target="_blank">interfaccia di amministrazione di Teams</a> per configurare altre funzionalità di Business Voice.</span><span class="sxs-lookup"><span data-stu-id="32acb-148">After it's finished, go to <b>Voice</b> in the <a href="https://admin.teams.microsoft.com" target="_blank">Teams admin center</a> to set up more Business Voice features.</span></span></p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>