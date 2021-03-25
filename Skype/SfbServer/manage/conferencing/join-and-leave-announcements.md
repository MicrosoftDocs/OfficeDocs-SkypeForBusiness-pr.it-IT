---
title: Gestire gli annunci di partecipazione e di lasciare conferenze in Skype for Business Server
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
description: 'Riepilogo: informazioni su come gestire gli annunci di partecipazione e di lasciare conferenze in Skype for Business Server.'
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119455"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="442b2-103">Gestire gli annunci di partecipazione e di lasciare conferenze in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="442b2-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="442b2-104">**Riepilogo:** Informazioni su come gestire gli annunci di partecipazione e di lasciare conferenze in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="442b2-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="442b2-105">Quando gli utenti con accesso esterno aderiscono o escono da una conferenza, l'applicazione Annuncio conferenza può annunciare l'ingresso o l'uscita riproducendo un tono o pronunciando i nomi.</span><span class="sxs-lookup"><span data-stu-id="442b2-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="442b2-106">È possibile modificare il funzionamento degli annunci utilizzando Skype for Business Server Management Shell e il cmdlet **Set-CsDialinConferencing** con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="442b2-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="442b2-107">EnableNameRecording - Determina se ai partecipanti anonimi viene richiesto di registrare il proprio nome prima di accedere alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="442b2-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="442b2-108">Il valore predefinito è "$true" e indica che ai partecipanti anonimi viene richiesto di specificare il proprio nome durante l'accesso a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="442b2-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="442b2-109">I partecipanti autenticati non registrano il proprio nome perché viene utilizzato il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="442b2-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="442b2-110">EntryExitAnnouncementsEnabledByDefault - Indica se gli annunci sono attivati o disattivati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="442b2-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="442b2-111">Il valore predefinito è "$false" e indica che per impostazione predefinita non vengono visualizzati annunci quando gli utenti partecipano a una conferenza o la abbandonano.</span><span class="sxs-lookup"><span data-stu-id="442b2-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="442b2-112">L'organizzatore della riunione può sostituire questa impostazione durante la pianificazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="442b2-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="442b2-113">EntryExitAnnouncementsType - Indica l'azione eseguita ogni volta che un partecipante partecipa o abbandona una conferenza per la quale sono abilitati gli annunci.</span><span class="sxs-lookup"><span data-stu-id="442b2-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="442b2-114">Il valore predefinito è "UseNames" e indica la visualizzazione di un annuncio simile al seguente: "Davide Garghentini si è unito alla conferenza" quando gli annunci sono attivati.</span><span class="sxs-lookup"><span data-stu-id="442b2-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="442b2-p105">È possibile configurare queste impostazioni a livello globale o di sito. Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale.</span><span class="sxs-lookup"><span data-stu-id="442b2-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="442b2-117">Per modificare il comportamento di partecipazione a una conferenza o di abbandono della stessa</span><span class="sxs-lookup"><span data-stu-id="442b2-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="442b2-118">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="442b2-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="442b2-119">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="442b2-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="442b2-120">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="442b2-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="442b2-121">Questo cmdlet consente di recuperare informazioni sulla necessità o meno ai partecipanti di registrare il proprio nome durante la partecipazione a una conferenza e su come Skype for Business Server risponde quando i partecipanti aderiscono o abbandonano una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="442b2-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="442b2-122">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="442b2-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="442b2-123">Nell'esempio seguente le impostazioni vengono configurate nell'ambito del sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="442b2-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="442b2-124">Gli annunci sono attivati ma ai partecipanti non viene richiesto di specificare il proprio nome durante l'accesso a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="442b2-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="442b2-125">Quando i partecipanti a una conferenza entrano o abbandonano una conferenza, viene riprodotto un tono:</span><span class="sxs-lookup"><span data-stu-id="442b2-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="442b2-126">Per ulteriori informazioni, inclusa la sintassi e un elenco completo dei parametri, [vedere Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="442b2-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
