---
title: (Facoltativo) Abilitare e disabilitare gli annunci di partecipazione e abbandono delle conferenze
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 778969dfa5ed6b84fdbcd2b204e497f8d649f1a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="156ee-102">(Facoltativo) Abilitare e disabilitare gli annunci di partecipazione e abbandono delle conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="156ee-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="156ee-103">_**Argomento Ultima modifica:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="156ee-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="156ee-104">Quando gli utenti con accesso esterno entrano o lasciano una conferenza, l'applicazione di annunci per conferenze può annunciare l'entrata o l'uscita suonando un tono o pronunciando i loro nomi.</span><span class="sxs-lookup"><span data-stu-id="156ee-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="156ee-105">È possibile modificare la modalità di funzionamento degli annunci eseguendo i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="156ee-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="156ee-106">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="156ee-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="156ee-107">Per modificare il comportamento dell'annuncio per la conferenza e il permesso</span><span class="sxs-lookup"><span data-stu-id="156ee-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="156ee-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="156ee-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="156ee-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="156ee-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="156ee-110">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="156ee-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="156ee-111">Questo cmdlet recupera informazioni sul fatto che i partecipanti debbano registrare il loro nome quando partecipano a una conferenza e come risponde Lync Server quando i partecipanti partecipano o lasciano una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="156ee-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="156ee-112">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="156ee-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="156ee-113">**EnableNameRecording**   determina se i partecipanti anonimi vengono invitati a registrare il loro nome prima di accedere alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="156ee-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="156ee-114">Il valore predefinito è "$true", che indica che ai partecipanti anonimi viene richiesto di indicare il loro nome quando partecipano a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="156ee-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="156ee-115">I partecipanti autenticati non registrano il proprio nome perché viene usato il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="156ee-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="156ee-116">**EntryExitAnnouncementsEnabledByDefault**   indica se gli annunci sono attivati o disattivati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="156ee-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="156ee-117">Il valore predefinito è "$false", che indica che per impostazione predefinita non ci sono annunci quando i partecipanti partecipano o lasciano una conferenza.</span><span class="sxs-lookup"><span data-stu-id="156ee-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="156ee-118">L'organizzatore della riunione può eseguire l'override di questa impostazione durante la pianificazione di una riunione.</span><span class="sxs-lookup"><span data-stu-id="156ee-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="156ee-119">**EntryExitAnnouncementsType**   indica l'azione eseguita ogni volta che un partecipante partecipa o esce da una conferenza per cui sono abilitati gli annunci.</span><span class="sxs-lookup"><span data-stu-id="156ee-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="156ee-120">Il valore predefinito è "UseNames", che indica che è presente un annuncio simile al seguente: "Ken si è unito alla conferenza" quando gli annunci sono attivati.</span><span class="sxs-lookup"><span data-stu-id="156ee-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="156ee-121">Queste impostazioni possono essere configurate nell'ambito globale o nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="156ee-121">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="156ee-122">Le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="156ee-122">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="156ee-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="156ee-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="156ee-124">In questo esempio le impostazioni vengono configurate nell'ambito del sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="156ee-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="156ee-125">Gli annunci sono attivati, ma ai partecipanti non viene chiesto di pronunciare il loro nome quando partecipano a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="156ee-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="156ee-126">Viene riprodotto un tono quando i partecipanti entrano o lasciano una conferenza.</span><span class="sxs-lookup"><span data-stu-id="156ee-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

