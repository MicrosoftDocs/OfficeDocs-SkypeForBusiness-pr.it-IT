---
title: Gestire gli annunci di partecipazione alla conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Riepilogo: informazioni su come gestire gli annunci di partecipazione alle conferenze e per lasciare messaggi in Skype for Business Server.'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828106"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="202e0-103">Gestire gli annunci di partecipazione alla conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="202e0-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="202e0-104">**Riepilogo:** Informazioni su come gestire gli annunci per la partecipazione alle conferenze e per lasciare messaggi in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="202e0-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="202e0-105">Quando gli utenti con accesso esterno si uniscono o lasciano una conferenza, l'applicazione annuncio per le conferenze può annunciare la propria entrata o uscita suonando un tono o pronunciando i propri nomi.</span><span class="sxs-lookup"><span data-stu-id="202e0-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="202e0-106">È possibile modificare il modo in cui gli annunci funzionano utilizzando Skype for Business Server Management Shell e il cmdlet **set-CsDialinConferencing** con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="202e0-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="202e0-107">EnableNameRecording-Determina se ai partecipanti anonimi viene richiesto di registrare il proprio nome prima di accedere alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="202e0-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="202e0-108">Il valore predefinito è "$true" e indica che ai partecipanti anonimi viene richiesto di specificare il proprio nome durante l'accesso a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="202e0-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="202e0-109">I partecipanti autenticati non registrano il proprio nome perché viene utilizzato il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="202e0-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="202e0-110">EntryExitAnnouncementsEnabledByDefault-indica se gli annunci sono attivati o disattivati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="202e0-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="202e0-111">Il valore predefinito è "$false" e indica che per impostazione predefinita non vengono visualizzati annunci quando gli utenti partecipano a una conferenza o la abbandonano.</span><span class="sxs-lookup"><span data-stu-id="202e0-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="202e0-112">L'organizzatore della riunione può sostituire questa impostazione durante la pianificazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="202e0-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="202e0-113">EntryExitAnnouncementsType-indica l'azione intrapresa ogni volta che un partecipante si unisce o lascia una conferenza per la quale gli annunci sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="202e0-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="202e0-114">Il valore predefinito è "UseNames" e indica la visualizzazione di un annuncio simile al seguente: "Davide Garghentini si è unito alla conferenza" quando gli annunci sono attivati.</span><span class="sxs-lookup"><span data-stu-id="202e0-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="202e0-p105">È possibile configurare queste impostazioni a livello globale o di sito. Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale.</span><span class="sxs-lookup"><span data-stu-id="202e0-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="202e0-117">Per modificare il comportamento di partecipazione a una conferenza o di abbandono della stessa</span><span class="sxs-lookup"><span data-stu-id="202e0-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="202e0-118">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="202e0-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="202e0-119">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="202e0-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="202e0-120">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="202e0-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="202e0-121">Questo cmdlet recupera le informazioni sul fatto che i partecipanti siano tenuti a registrare il proprio nome quando partecipano a una conferenza e in che modo Skype for Business Server risponde quando i partecipanti si uniscono o lasciano una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="202e0-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="202e0-122">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="202e0-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="202e0-123">Nell'esempio seguente, le impostazioni vengono configurate nell'ambito del sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="202e0-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="202e0-124">Gli annunci sono attivati ma ai partecipanti non viene richiesto di specificare il proprio nome durante l'accesso a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="202e0-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="202e0-125">Viene riprodotto un tono quando i partecipanti entrano o lasciano una conferenza:</span><span class="sxs-lookup"><span data-stu-id="202e0-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="202e0-126">Per ulteriori informazioni, tra cui la sintassi e l'elenco completo dei parametri, vedere [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="202e0-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

