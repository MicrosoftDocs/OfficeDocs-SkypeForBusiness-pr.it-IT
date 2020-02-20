---
title: 'Lync Server 2013: (facoltativo) modificare il mapping dei tasti per i comandi DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcf6f6b2dd65d9429bf23397baff5bbe072800f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="500f9-102">Optional Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="500f9-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="500f9-103">_**Ultimo argomento modificato:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="500f9-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="500f9-104">Gli utenti delle conferenze telefoniche con accesso esterno possono premere i tasti sul tastierino del telefono per eseguire i comandi DTMF (Dual-Tone Multi-Frequency).</span><span class="sxs-lookup"><span data-stu-id="500f9-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="500f9-105">I comandi DTMF consentono agli utenti che accedono a una conferenza di controllare le impostazioni di conferenza, ad esempio il muting e la riattivazione o il blocco e lo sblocco della conferenza, tramite la tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="500f9-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="500f9-106">È possibile utilizzare i cmdlet per modificare le chiavi utilizzate per i comandi DTMF.</span><span class="sxs-lookup"><span data-stu-id="500f9-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="500f9-107">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="500f9-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="500f9-108">Per informazioni dettagliate su questi cmdlet e sulle possibili opzioni DTMF, vedere Lync Server Management Shell Documentation o la guida della riga di comando di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="500f9-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="500f9-109">Per modificare il mapping dei tasti per i comandi DTMF</span><span class="sxs-lookup"><span data-stu-id="500f9-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="500f9-110">Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** o come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="500f9-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="500f9-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="500f9-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="500f9-112">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="500f9-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="500f9-113">Questo cmdlet restituisce le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="500f9-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="500f9-114">Eseguire il cmdlet seguente e specificare il tasto da premere per ogni opzione che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="500f9-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="500f9-115">Questo cmdlet consente di modificare le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="500f9-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="500f9-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="500f9-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="500f9-117">In questo esempio viene scambiato il tasto premuto per abilitare o disabilitare gli annunci e il tasto premuto per disattivare e riattivare l'audio di tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="500f9-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="500f9-118">Poiché non viene specificata alcuna identità, queste modifiche sono valide per le impostazioni DTMF globali.</span><span class="sxs-lookup"><span data-stu-id="500f9-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="500f9-119">Optional Per creare ulteriori insiemi di comandi DTMF per siti specifici, utilizzare il cmdlet **New-CsDialInConferencingDtmfConfiguration** con un'identità del sito.</span><span class="sxs-lookup"><span data-stu-id="500f9-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="500f9-120">Quando si creano nuove impostazioni DTMF per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="500f9-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="500f9-121">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell o la guida della riga di comando di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="500f9-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

