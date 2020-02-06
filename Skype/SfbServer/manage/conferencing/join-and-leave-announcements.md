---
title: Gestire gli annunci di conferenza e lasciarli in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Riepilogo: informazioni su come gestire gli annunci di conferenza e uscire da Skype for Business Server.'
ms.openlocfilehash: 5f975637ca1d85e11c6889a07ff90055ef79ffc5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818547"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="a5540-103">Gestire gli annunci di conferenza e lasciarli in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5540-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="a5540-104">**Riepilogo:** Informazioni su come gestire gli annunci in Skype for Business Server e partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a5540-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="a5540-105">Quando gli utenti con accesso esterno entrano o lasciano una conferenza, l'applicazione di annunci per conferenze può annunciare l'entrata o l'uscita suonando un tono o pronunciando i loro nomi.</span><span class="sxs-lookup"><span data-stu-id="a5540-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="a5540-106">È possibile modificare la modalità di funzionamento degli annunci usando Skype for Business Server Management Shell e il cmdlet **set-CsDialinConferencing** con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5540-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="a5540-107">EnableNameRecording-Determina se i partecipanti anonimi vengono invitati a registrare il nome prima di partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="a5540-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="a5540-108">Il valore predefinito è "$true", che indica che ai partecipanti anonimi viene richiesto di indicare il loro nome quando partecipano a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a5540-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="a5540-109">I partecipanti autenticati non registrano il proprio nome perché viene usato il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a5540-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="a5540-110">EntryExitAnnouncementsEnabledByDefault: indica se gli annunci sono attivati o disattivati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a5540-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="a5540-111">Il valore predefinito è "$false", che indica che per impostazione predefinita non ci sono annunci quando i partecipanti partecipano o lasciano una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a5540-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="a5540-112">L'organizzatore della riunione può eseguire l'override di questa impostazione durante la pianificazione di una riunione.</span><span class="sxs-lookup"><span data-stu-id="a5540-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="a5540-113">EntryExitAnnouncementsType-indica l'azione eseguita ogni volta che un partecipante partecipa o esce da una conferenza per cui sono abilitati gli annunci.</span><span class="sxs-lookup"><span data-stu-id="a5540-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="a5540-114">Il valore predefinito è "UseNames", che indica che è presente un annuncio simile al seguente: "Ken si è unito alla conferenza" quando gli annunci sono attivati.</span><span class="sxs-lookup"><span data-stu-id="a5540-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="a5540-115">Queste impostazioni possono essere configurate nell'ambito globale o nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="a5540-115">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="a5540-116">Le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="a5540-116">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="a5540-117">Per modificare il comportamento dell'annuncio per la conferenza e il permesso</span><span class="sxs-lookup"><span data-stu-id="a5540-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="a5540-118">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5540-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="a5540-119">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a5540-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a5540-120">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="a5540-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="a5540-121">Questo cmdlet recupera informazioni sul fatto che i partecipanti siano tenuti a registrare il loro nome quando partecipano a una conferenza e in che modo Skype for Business Server risponde quando i partecipanti partecipano o lasciano una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a5540-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="a5540-122">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="a5540-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="a5540-123">Nell'esempio seguente le impostazioni sono configurate nell'ambito del sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="a5540-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="a5540-124">Gli annunci sono attivati, ma ai partecipanti non viene chiesto di pronunciare il loro nome quando partecipano a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a5540-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="a5540-125">Viene riprodotto un tono quando i partecipanti entrano o lasciano una conferenza:</span><span class="sxs-lookup"><span data-stu-id="a5540-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="a5540-126">Per altre informazioni, tra cui la sintassi e un elenco completo dei parametri, vedere [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a5540-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

