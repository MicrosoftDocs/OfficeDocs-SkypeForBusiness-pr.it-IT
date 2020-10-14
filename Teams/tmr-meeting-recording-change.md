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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444232"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="61f79-103">Usare OneDrive for business e SharePoint o Stream per le registrazioni delle riunioni</span><span class="sxs-lookup"><span data-stu-id="61f79-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="61f79-104">La modifica dell'uso di Microsoft Stream in OneDrive for business e Microsoft SharePoint per le registrazioni delle riunioni sarà un approccio graduale.</span><span class="sxs-lookup"><span data-stu-id="61f79-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>

|||
|---|-----------------|
|<span data-ttu-id="61f79-105">Data</span><span class="sxs-lookup"><span data-stu-id="61f79-105">Date</span></span>|<span data-ttu-id="61f79-106">Evento</span><span class="sxs-lookup"><span data-stu-id="61f79-106">Event</span></span>|
|<span data-ttu-id="61f79-107">Inizio Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="61f79-107">Early Q4 CY20</span></span>|<span data-ttu-id="61f79-108">**Registrazione delle riunioni di teams in OneDrive for business e SharePoint disponibile per opt-in o opt-out.**</span><span class="sxs-lookup"><span data-stu-id="61f79-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="61f79-109">Gli amministratori del tenant possono optare o rifiutare la disattivazione di OneDrive for business e SharePoint impostando il criterio teams in PowerShell</span><span class="sxs-lookup"><span data-stu-id="61f79-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="61f79-110">Mid Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="61f79-110">Mid Q4 CY20</span></span>|<span data-ttu-id="61f79-111">**Registrazione delle riunioni di teams in OneDrive for business e SharePoint impostato come predefinito per i tenant che non si dissociano**</span><span class="sxs-lookup"><span data-stu-id="61f79-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="61f79-112">Questo è il percorso consigliato per la maggior parte dei clienti</span><span class="sxs-lookup"><span data-stu-id="61f79-112">This is the  recommended path for most customers</span></span>|
<span data-ttu-id="61f79-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="61f79-113">Q1 CY21</span></span>|<span data-ttu-id="61f79-114">**Salvataggio della registrazione delle riunioni di teams in Stream classico non più consentito**</span><span class="sxs-lookup"><span data-stu-id="61f79-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="61f79-115">Tutti i tenant salveranno la registrazione delle riunioni di teams in OneDrive for business e SharePoint</span><span class="sxs-lookup"><span data-stu-id="61f79-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|
|||

<span data-ttu-id="61f79-116">Microsoft Teams ha un nuovo metodo per il salvataggio delle registrazioni delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="61f79-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="61f79-117">Come prima fase di una transizione da Microsoft Stream classico al [nuovo flusso](https://docs.microsoft.com/stream/streamnew/new-stream), questo metodo archivia le registrazioni in Microsoft OneDrive e SharePoint in Microsoft 365 e offre numerosi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="61f79-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="61f79-118">I vantaggi derivanti dall'uso di OneDrive for business e SharePoint per l'archiviazione delle registrazioni includono:</span><span class="sxs-lookup"><span data-stu-id="61f79-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="61f79-119">Criteri di conservazione per la registrazione di teams Meeting (TMR) (etichette di autoconservazione S + C E5)</span><span class="sxs-lookup"><span data-stu-id="61f79-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="61f79-120">Vantaggi della governance delle informazioni di OneDrive for business e di SharePoint</span><span class="sxs-lookup"><span data-stu-id="61f79-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="61f79-121">Facile impostare le autorizzazioni e la condivisione</span><span class="sxs-lookup"><span data-stu-id="61f79-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="61f79-122">Condividere le registrazioni con Guest (utenti esterni) con solo condivisione esplicita</span><span class="sxs-lookup"><span data-stu-id="61f79-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="61f79-123">Richiedi il flusso di accesso</span><span class="sxs-lookup"><span data-stu-id="61f79-123">Request access flow</span></span>
- <span data-ttu-id="61f79-124">Fornisci collegamenti condivisi di OneDrive for business e SharePoint</span><span class="sxs-lookup"><span data-stu-id="61f79-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="61f79-125">Quota aumentata</span><span class="sxs-lookup"><span data-stu-id="61f79-125">Increased quota</span></span>
- <span data-ttu-id="61f79-126">Le registrazioni delle riunioni sono disponibili più rapidamente</span><span class="sxs-lookup"><span data-stu-id="61f79-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="61f79-127">Supporto di **go local** tenant</span><span class="sxs-lookup"><span data-stu-id="61f79-127">**Go local** tenant support</span></span>
- <span data-ttu-id="61f79-128">Supporto multi-geo: le registrazioni vengono archiviate in un'area specifica dell'utente</span><span class="sxs-lookup"><span data-stu-id="61f79-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="61f79-129">Porta il tuo supporto Key (BYOK)</span><span class="sxs-lookup"><span data-stu-id="61f79-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="61f79-130">Qualità della trascrizione migliorata e attribuzione del relatore</span><span class="sxs-lookup"><span data-stu-id="61f79-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="61f79-131">Ci sono alcune limitazioni da considerare:</span><span class="sxs-lookup"><span data-stu-id="61f79-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="61f79-132">Ci saranno solo didascalie e trascrizioni chiuse in inglese.</span><span class="sxs-lookup"><span data-stu-id="61f79-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="61f79-133">Non è possibile eseguire ricerche nelle trascrizioni o nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="61f79-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="61f79-134">Non sarà possibile modificare le trascrizioni, ma sarà possibile attivare o disattivare le didascalie.</span><span class="sxs-lookup"><span data-stu-id="61f79-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="61f79-135">È possibile controllare con chi si condivide la registrazione, ma non sarà possibile bloccare le persone con accesso condiviso dal Download della registrazione.</span><span class="sxs-lookup"><span data-stu-id="61f79-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="61f79-136">Non si riceverà un messaggio di posta elettronica quando la registrazione terminerà il salvataggio, ma la registrazione verrà visualizzata nella chat della riunione una volta terminato.</span><span class="sxs-lookup"><span data-stu-id="61f79-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="61f79-137">Ciò avverrà molto più rapidamente di quanto abbia fatto in Stream in precedenza</span><span class="sxs-lookup"><span data-stu-id="61f79-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="61f79-138">Per altre informazioni, vedere "registrazione della riunione".</span><span class="sxs-lookup"><span data-stu-id="61f79-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="61f79-139">Configurare l'opzione di registrazione della riunione per OneDrive for business e SharePoint</span><span class="sxs-lookup"><span data-stu-id="61f79-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="61f79-140">Installare la console di amministrazione di PowerShell per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="61f79-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="61f79-141">a.</span><span class="sxs-lookup"><span data-stu-id="61f79-141">a.</span></span> <span data-ttu-id="61f79-142">Scaricare [PowerShell per Skype for business online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="61f79-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="61f79-143">b.</span><span class="sxs-lookup"><span data-stu-id="61f79-143">b.</span></span> <span data-ttu-id="61f79-144">Seguire le istruzioni per installarlo.</span><span class="sxs-lookup"><span data-stu-id="61f79-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="61f79-145">c.</span><span class="sxs-lookup"><span data-stu-id="61f79-145">c.</span></span> <span data-ttu-id="61f79-146">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="61f79-146">Restart your machine.</span></span>

2. <span data-ttu-id="61f79-147">Avviare PowerShell come amministratore</span><span class="sxs-lookup"><span data-stu-id="61f79-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="61f79-148">Importare il connettore SkypeOnline e accedere come amministratore di teams.</span><span class="sxs-lookup"><span data-stu-id="61f79-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="61f79-149">Usare [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per impostare un criterio per la riunione di teams in transizione dallo spazio di archiviazione del flusso a ODSP.</span><span class="sxs-lookup"><span data-stu-id="61f79-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="61f79-150">Rifiutare la disattivazione di OneDrive for business e SharePoint per continuare a usare Stream</span><span class="sxs-lookup"><span data-stu-id="61f79-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="61f79-151">Anche se un criterio indica che è impostato su **Stream**, potrebbe non essere impostato.</span><span class="sxs-lookup"><span data-stu-id="61f79-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="61f79-152">In genere, se il criterio non è impostato, l'impostazione predefinita è **Stream**.</span><span class="sxs-lookup"><span data-stu-id="61f79-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="61f79-153">Tuttavia, con questa nuova modifica, se si vuole rifiutare l'uso di SharePoint o OneDrive, è necessario reimpostare i criteri in **Stream** per assicurarsi che sia l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="61f79-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="61f79-154">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="61f79-154">Frequently asked questions</span></span>

<span data-ttu-id="61f79-155">**Dove verrà archiviata la registrazione della riunione?**</span><span class="sxs-lookup"><span data-stu-id="61f79-155">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="61f79-156">Per le riunioni non di canale, la registrazione viene archiviata in una cartella denominata **registrazioni** che si trova al primo livello di OneDrive che appartiene alla persona che ha avviato la registrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="61f79-156">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="61f79-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="61f79-157">Example:</span></span>

  <span data-ttu-id="61f79-158"><i>OneDrive for business</i> / del registratore **Registrazioni**</span><span class="sxs-lookup"><span data-stu-id="61f79-158"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="61f79-159">Per le riunioni di canale, la registrazione viene archiviata nella raccolta documentazione sito teams in una cartella denominata **registrazioni**.</span><span class="sxs-lookup"><span data-stu-id="61f79-159">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="61f79-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="61f79-160">Example:</span></span>

  <span data-ttu-id="61f79-161"><i>Nome teams-nome canale</i> / **Documenti** / **Registrazioni**</span><span class="sxs-lookup"><span data-stu-id="61f79-161"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="61f79-162">**Come si gestiscono le registrazioni da ex dipendenti?**</span><span class="sxs-lookup"><span data-stu-id="61f79-162">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="61f79-163">Dato che i video sono come qualsiasi altro file in OneDrive e SharePoint, la gestione della proprietà e la conservazione dopo il congedo da parte di un dipendente seguirà il normale [processo di OneDrive e SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span><span class="sxs-lookup"><span data-stu-id="61f79-163">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="61f79-164">**Chi ha le autorizzazioni per visualizzare la registrazione delle riunioni?**</span><span class="sxs-lookup"><span data-stu-id="61f79-164">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="61f79-165">Per le riunioni non di canale, tutti gli invitati alle riunioni, ad eccezione degli utenti esterni, riceveranno automaticamente un collegamento condiviso personalmente.</span><span class="sxs-lookup"><span data-stu-id="61f79-165">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="61f79-166">Gli utenti esterni dovranno essere aggiunti esplicitamente all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="61f79-166">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="61f79-167">Per le riunioni di canale, le autorizzazioni vengono ereditate dall'elenco proprietari e membri nel canale.</span><span class="sxs-lookup"><span data-stu-id="61f79-167">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="61f79-168">**Come si gestiscono le trascrizioni?**</span><span class="sxs-lookup"><span data-stu-id="61f79-168">**How can I manage transcripts?**</span></span>

<span data-ttu-id="61f79-169">I clienti che optano per questa anteprima non avranno le didascalie chiuse disponibili nelle registrazioni delle riunioni del team migrate in OneDrive e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="61f79-169">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="61f79-170">Stiamo lavorando per aggiungere didascalie, a partire da didascalie chiuse in inglese, per la riunione delle registrazioni in ottobre 2020.</span><span class="sxs-lookup"><span data-stu-id="61f79-170">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="61f79-171">Le didascalie chiuse saranno disponibili nelle registrazioni delle riunioni di teams per i clienti che hanno scelto di consentire le trascrizioni come descritto in [Teams cloud Recordings](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="61f79-171">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="61f79-172">Le didascalie consentono di creare contenuti inclusivi per gli utenti di tutte le abilità.</span><span class="sxs-lookup"><span data-stu-id="61f79-172">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="61f79-173">Come proprietario puoi nascondere le didascalie, anche se la trascrizione sarà ancora disponibile in teams a meno che tu non elimini le didascalie da teams.</span><span class="sxs-lookup"><span data-stu-id="61f79-173">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="61f79-174">Vedere [come attivare o disattivare le registrazioni delle riunioni](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="61f79-174">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="61f79-175">Le didascalie chiuse sono supportate per le registrazioni delle riunioni di teams per 60 giorni dopo la registrazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="61f79-175">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="61f79-176">**Come viene influenzata la quota di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="61f79-176">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="61f79-177">I team che partecipano a una riunione di file Live in OneDrive for business e SharePoint sono inclusi nella quota per tali servizi.</span><span class="sxs-lookup"><span data-stu-id="61f79-177">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="61f79-178">Vedere [quota di SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [quota di OneDrive for business] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="61f79-178">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="61f79-179">**Come si gioca una registrazione di una riunione di Teams?**</span><span class="sxs-lookup"><span data-stu-id="61f79-179">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="61f79-180">Il video verrà riprodotto sul lettore video di OneDrive for business o SharePoint a seconda di dove si accede al file.</span><span class="sxs-lookup"><span data-stu-id="61f79-180">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="61f79-181">**Se si prevede di aggiungere al flusso deprecato, i video esistenti rimarranno così come sono e per quanto tempo?**</span><span class="sxs-lookup"><span data-stu-id="61f79-181">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="61f79-182">Il flusso come piattaforma non sarà deprecato nel prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="61f79-182">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="61f79-183">I video che attualmente vivono in Stream rimarranno lì fino a quando non inizieremo a eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="61f79-183">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="61f79-184">Dopo la migrazione, anche questi video verranno migrati in ODSP.</span><span class="sxs-lookup"><span data-stu-id="61f79-184">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="61f79-185">Per altre informazioni, vedere [qui](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="61f79-185">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
