---
title: Optional Abilitare e disabilitare gli annunci di partecipazione alla conferenza e di uscita
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50431ee1917c580440f8a47cff0ca09f5e47f07
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524433"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="806b1-102">Optional Abilitare e disabilitare gli annunci di partecipazione alla conferenza e di uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="806b1-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="806b1-103">_**Ultimo argomento modificato:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="806b1-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="806b1-104">Quando gli utenti con accesso esterno si uniscono o lasciano una conferenza, l'applicazione annuncio per le conferenze può annunciare la propria entrata o uscita suonando un tono o pronunciando i propri nomi.</span><span class="sxs-lookup"><span data-stu-id="806b1-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="806b1-105">Il funzionamento degli annunci può essere modificato eseguendo i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="806b1-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="806b1-106">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="806b1-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="806b1-107">Per modificare il comportamento di partecipazione a una conferenza o di abbandono della stessa</span><span class="sxs-lookup"><span data-stu-id="806b1-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="806b1-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="806b1-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="806b1-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="806b1-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="806b1-110">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="806b1-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="806b1-111">Questo cmdlet recupera le informazioni sul fatto che i partecipanti devono registrare il proprio nome quando partecipano a una conferenza e in che modo Lync Server risponde quando i partecipanti si uniscono o lasciano una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="806b1-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="806b1-112">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="806b1-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="806b1-113">**EnableNameRecording**     Determina se ai partecipanti anonimi viene richiesto di registrare il proprio nome prima di accedere alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="806b1-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="806b1-114">Il valore predefinito è "$true" e indica che ai partecipanti anonimi viene richiesto di specificare il proprio nome durante l'accesso a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="806b1-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="806b1-115">I partecipanti autenticati non registrano il proprio nome perché viene utilizzato il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="806b1-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="806b1-116">**EntryExitAnnouncementsEnabledByDefault**     Indica se gli annunci sono attivati o disattivati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="806b1-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="806b1-117">Il valore predefinito è "$false" e indica che per impostazione predefinita non vengono visualizzati annunci quando gli utenti partecipano a una conferenza o la abbandonano.</span><span class="sxs-lookup"><span data-stu-id="806b1-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="806b1-118">L'organizzatore della riunione può sostituire questa impostazione durante la pianificazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="806b1-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="806b1-119">**EntryExitAnnouncementsType**     Indica l'azione intrapresa ogni volta che un partecipante si unisce o lascia una conferenza per la quale gli annunci sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="806b1-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="806b1-120">Il valore predefinito è "UseNames" e indica la visualizzazione di un annuncio simile al seguente: "Davide Garghentini si è unito alla conferenza" quando gli annunci sono attivati.</span><span class="sxs-lookup"><span data-stu-id="806b1-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="806b1-p105">È possibile configurare queste impostazioni a livello globale o di sito. Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale.</span><span class="sxs-lookup"><span data-stu-id="806b1-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="806b1-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="806b1-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="806b1-p106">In questo esempio le impostazioni vengono configurate al livello del sito di Redmond. Gli annunci sono attivati ma ai partecipanti non viene richiesto di specificare il proprio nome durante l'accesso a una conferenza. Quando i partecipanti accedono a una conferenza o la abbandonano viene riprodotto un segnale acustico.</span><span class="sxs-lookup"><span data-stu-id="806b1-p106">In this example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

