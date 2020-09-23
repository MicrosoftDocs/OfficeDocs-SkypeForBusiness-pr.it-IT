---
title: Usare OneDrive e SharePoint per le registrazioni delle riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come passare da Stream a OneDrive for business e a SharePoint Meeting recording storage in Microsoft teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c0d50686346b715ca7e10b455845927ff22341
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218407"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="1c103-103">Usare OneDrive for business e SharePoint o Stream per le registrazioni delle riunioni</span><span class="sxs-lookup"><span data-stu-id="1c103-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="1c103-104">La modifica dell'uso di Microsoft Stream in OneDrive for business e SharePoint per le registrazioni delle riunioni sarà un approccio graduale.</span><span class="sxs-lookup"><span data-stu-id="1c103-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="1c103-105">All'avvio si sarà in grado di accettare l'opt-in per questa esperienza, in novembre sarà necessario rifiutare l'opt-out se si vuole continuare a usare Stream e qualche volta all'inizio di 2021 è necessario che tutti i clienti usino OneDrive for business e SharePoint per le nuove registrazioni delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="1c103-105">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="1c103-106">Microsoft Teams ha un nuovo metodo per il salvataggio delle registrazioni delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="1c103-106">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="1c103-107">Come partenza da Stream, il metodo usa Microsoft OneDrive e SharePoint in Microsoft 365 e offre numerosi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="1c103-107">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits:</span></span>

<span data-ttu-id="1c103-108">I vantaggi derivanti dall'uso di OneDrive for business e SharePoint per l'archiviazione delle registrazioni includono:</span><span class="sxs-lookup"><span data-stu-id="1c103-108">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="1c103-109">Criteri di conservazione per la registrazione di teams Meeting (TMR) (etichette di autoconservazione S + C E5)</span><span class="sxs-lookup"><span data-stu-id="1c103-109">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="1c103-110">Vantaggi della governance delle informazioni di OneDrive for business e di SharePoint</span><span class="sxs-lookup"><span data-stu-id="1c103-110">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="1c103-111">Facile impostare le autorizzazioni e la condivisione</span><span class="sxs-lookup"><span data-stu-id="1c103-111">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="1c103-112">Condividere le registrazioni con Guest (utenti esterni) con solo condivisione esplicita</span><span class="sxs-lookup"><span data-stu-id="1c103-112">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="1c103-113">Richiedi il flusso di accesso</span><span class="sxs-lookup"><span data-stu-id="1c103-113">Request access flow</span></span>
- <span data-ttu-id="1c103-114">Fornisci collegamenti condivisi di OneDrive for business e SharePoint</span><span class="sxs-lookup"><span data-stu-id="1c103-114">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="1c103-115">Quota aumentata</span><span class="sxs-lookup"><span data-stu-id="1c103-115">Increased quota</span></span>
- <span data-ttu-id="1c103-116">Le registrazioni delle riunioni sono disponibili più rapidamente</span><span class="sxs-lookup"><span data-stu-id="1c103-116">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="1c103-117">Supporto di **go local** tenant</span><span class="sxs-lookup"><span data-stu-id="1c103-117">**Go local** tenant support</span></span>
- <span data-ttu-id="1c103-118">Supporto multi-geo: le registrazioni vengono archiviate in un'area specifica dell'utente</span><span class="sxs-lookup"><span data-stu-id="1c103-118">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="1c103-119">Porta il tuo supporto Key (BYOK)</span><span class="sxs-lookup"><span data-stu-id="1c103-119">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="1c103-120">Qualità della trascrizione migliorata e attribuzione del relatore</span><span class="sxs-lookup"><span data-stu-id="1c103-120">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="1c103-121">Ci sono alcune limitazioni da considerare:</span><span class="sxs-lookup"><span data-stu-id="1c103-121">There are some limitations to consider:</span></span>

- <span data-ttu-id="1c103-122">Ci saranno solo didascalie e trascrizioni chiuse in inglese.</span><span class="sxs-lookup"><span data-stu-id="1c103-122">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="1c103-123">Non è possibile eseguire ricerche nelle trascrizioni o nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="1c103-123">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="1c103-124">Non sarà possibile modificare le trascrizioni, ma sarà possibile attivare o disattivare le didascalie.</span><span class="sxs-lookup"><span data-stu-id="1c103-124">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="1c103-125">È possibile controllare con chi si condivide la registrazione, ma non sarà possibile bloccare le persone con accesso condiviso dal Download della registrazione.</span><span class="sxs-lookup"><span data-stu-id="1c103-125">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="1c103-126">Non si riceverà un messaggio di posta elettronica quando la registrazione terminerà il salvataggio, ma la registrazione verrà visualizzata nella chat della riunione una volta terminato.</span><span class="sxs-lookup"><span data-stu-id="1c103-126">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="1c103-127">Ciò avverrà molto più rapidamente di quanto abbia fatto in Stream in precedenza</span><span class="sxs-lookup"><span data-stu-id="1c103-127">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="1c103-128">Per altre informazioni, vedere "registrazione della riunione".</span><span class="sxs-lookup"><span data-stu-id="1c103-128">Watch "Meeting Recording" for more information.</span></span> 

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8] 

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="1c103-129">Configurare l'opzione di registrazione della riunione per OneDrive for business e SharePoint</span><span class="sxs-lookup"><span data-stu-id="1c103-129">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="1c103-130">Installare la console di amministrazione di PowerShell per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1c103-130">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="1c103-131">a.</span><span class="sxs-lookup"><span data-stu-id="1c103-131">a.</span></span> <span data-ttu-id="1c103-132">Scaricare [PowerShell per Skype for business online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="1c103-132">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="1c103-133">b.</span><span class="sxs-lookup"><span data-stu-id="1c103-133">b.</span></span> <span data-ttu-id="1c103-134">Seguire le istruzioni per installarlo.</span><span class="sxs-lookup"><span data-stu-id="1c103-134">Follow the prompts to install it.</span></span>

    <span data-ttu-id="1c103-135">c.</span><span class="sxs-lookup"><span data-stu-id="1c103-135">c.</span></span> <span data-ttu-id="1c103-136">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="1c103-136">Restart your machine.</span></span>

2. <span data-ttu-id="1c103-137">Avviare PowerShell come amministratore</span><span class="sxs-lookup"><span data-stu-id="1c103-137">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="1c103-138">Importare il connettore SkypeOnline e accedere come amministratore di teams.</span><span class="sxs-lookup"><span data-stu-id="1c103-138">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="1c103-139">Usare [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per impostare un criterio per la riunione di teams in transizione dallo spazio di archiviazione del flusso a ODSP.</span><span class="sxs-lookup"><span data-stu-id="1c103-139">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="1c103-140">Rifiutare la disattivazione di OneDrive for business e SharePoint per continuare a usare Stream</span><span class="sxs-lookup"><span data-stu-id="1c103-140">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="1c103-141">Anche se un criterio dice che è già impostato su **Stream**, potrebbe non essere impostato.</span><span class="sxs-lookup"><span data-stu-id="1c103-141">Even if a policy says it’s already set to **Stream**, it might not be set.</span></span> <span data-ttu-id="1c103-142">Se è impostato su Nothing, il valore predefinito è Stream.</span><span class="sxs-lookup"><span data-stu-id="1c103-142">If it's set to nothing, then the default is Stream.</span></span> <span data-ttu-id="1c103-143">Se si vuole rifiutare l'opt-out, è **necessario** reimpostare i criteri in **Stream** per assicurarsi che Stream sia l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1c103-143">If you want to opt-out, you **must** reset the policy to **Stream** to ensure that Stream is the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="1c103-144">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="1c103-144">Frequently asked questions</span></span>

<span data-ttu-id="1c103-145">**Dove verrà archiviata la registrazione della riunione?**</span><span class="sxs-lookup"><span data-stu-id="1c103-145">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="1c103-146">Per le riunioni non di canale, la registrazione viene archiviata in una cartella denominata.</span><span class="sxs-lookup"><span data-stu-id="1c103-146">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="1c103-147">Registrazioni \* \* che si trova al primo livello del OneDrive che appartiene alla persona che ha avviato la registrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="1c103-147">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="1c103-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c103-148">Example:</span></span>

  <span data-ttu-id="1c103-149"><i>OneDrive for business</i> / del registratore **Registrazioni**</span><span class="sxs-lookup"><span data-stu-id="1c103-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="1c103-150">Per le riunioni di canale, la registrazione viene archiviata nella raccolta documentazione sito teams in una cartella denominata **registrazioni**.</span><span class="sxs-lookup"><span data-stu-id="1c103-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="1c103-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c103-151">Example:</span></span>

  <span data-ttu-id="1c103-152"><i>Nome teams-nome canale</i> / **Documenti** / **Registrazioni**</span><span class="sxs-lookup"><span data-stu-id="1c103-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="1c103-153">**Chi ha le autorizzazioni per visualizzare la registrazione delle riunioni?**</span><span class="sxs-lookup"><span data-stu-id="1c103-153">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="1c103-154">Per le riunioni non di canale, tutti gli invitati alle riunioni, ad eccezione degli utenti esterni, riceveranno automaticamente un collegamento condiviso personalmente.</span><span class="sxs-lookup"><span data-stu-id="1c103-154">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="1c103-155">Gli utenti esterni dovranno essere aggiunti esplicitamente all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="1c103-155">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="1c103-156">Per le riunioni di canale, le autorizzazioni vengono ereditate dall'elenco proprietari e membri nel canale.</span><span class="sxs-lookup"><span data-stu-id="1c103-156">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="1c103-157">**Come si gestiscono le trascrizioni?**</span><span class="sxs-lookup"><span data-stu-id="1c103-157">**How can I manage transcripts?**</span></span>

<span data-ttu-id="1c103-158">I clienti che optano per questa anteprima non avranno le didascalie chiuse disponibili nelle registrazioni delle riunioni del team migrate in OneDrive e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1c103-158">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="1c103-159">Stiamo lavorando per aggiungere didascalie, a partire da didascalie chiuse in inglese, per la riunione delle registrazioni in ottobre 2020.</span><span class="sxs-lookup"><span data-stu-id="1c103-159">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="1c103-160">Le didascalie chiuse saranno disponibili nelle registrazioni delle riunioni di teams per i clienti che hanno scelto di consentire le trascrizioni come descritto in [Teams cloud Recordings](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="1c103-160">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="1c103-161">Le didascalie consentono di creare contenuti inclusivi per gli utenti di tutte le abilità.</span><span class="sxs-lookup"><span data-stu-id="1c103-161">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="1c103-162">Come proprietario puoi nascondere le didascalie, anche se la trascrizione sarà ancora disponibile in teams a meno che tu non elimini le didascalie da teams.</span><span class="sxs-lookup"><span data-stu-id="1c103-162">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="1c103-163">Vedere [come attivare o disattivare le registrazioni delle riunioni](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="1c103-163">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="1c103-164">Le didascalie chiuse sono supportate per le registrazioni delle riunioni di teams per 60 giorni dopo la registrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="1c103-164">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="1c103-165">**Come viene influenzata la quota di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="1c103-165">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="1c103-166">I team che partecipano a una riunione di file Live in OneDrive for business e SharePoint sono inclusi nella quota per tali servizi.</span><span class="sxs-lookup"><span data-stu-id="1c103-166">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="1c103-167">Vedere [quota di SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [quota di OneDrive for business] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="1c103-167">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="1c103-168">**Come si gioca una registrazione di una riunione di Teams?**</span><span class="sxs-lookup"><span data-stu-id="1c103-168">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="1c103-169">Il video verrà riprodotto sul lettore video di OneDrive for business o SharePoint a seconda di dove si accede al file.</span><span class="sxs-lookup"><span data-stu-id="1c103-169">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>
