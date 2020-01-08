---
title: 'Lync Server 2013: configurazione della modalità di privacy avanzata della presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="63ea1-102">Configurazione della modalità di privacy della presenza avanzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63ea1-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63ea1-103">_**Argomento Ultima modifica:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="63ea1-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="63ea1-104">Con la modalità di privacy della presenza avanzata, gli utenti possono limitare le informazioni sulla presenza in modo che siano visibili solo ai contatti elencati nell'elenco contatti di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="63ea1-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="63ea1-105">I cmdlet **New-CsPrivacyConfiguration** e **Set-CsPrivacyConfiguration** hanno un parametro EnablePrivacyMode che controlla questa opzione.</span><span class="sxs-lookup"><span data-stu-id="63ea1-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="63ea1-106">Quando EnablePrivacyMode è impostato su true, l'opzione per limitare le informazioni sulla presenza ai contatti diventa disponibile nelle opzioni di stato di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="63ea1-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="63ea1-107">Quando EnablePrivacyMode è impostato su false, gli utenti possono scegliere di consentire sempre a tutti di visualizzare le informazioni sulla presenza o di rispettare le eventuali modifiche future che l'amministratore apporta alla modalità privacy.</span><span class="sxs-lookup"><span data-stu-id="63ea1-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63ea1-108">Le impostazioni di privacy di Lync 2013 e Lync 2010 non vengono rispettate dalle versioni precedenti (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007).</span><span class="sxs-lookup"><span data-stu-id="63ea1-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="63ea1-109">Se è consentito l'accesso alle versioni precedenti di Office Communicator, lo stato di un utente di Lync 2013, le informazioni di contatto o l'immagine potrebbero essere visualizzati da una persona che non è stata autorizzata a visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="63ea1-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="63ea1-110">Inoltre, le impostazioni di privacy di un utente di Lync 2013 vengono reimpostate se successivamente accede con la versione precedente di Communicator.</span><span class="sxs-lookup"><span data-stu-id="63ea1-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="63ea1-111">Per questi motivi, in uno scenario di migrazione, prima di abilitare la modalità di privacy avanzata della presenza:</span><span class="sxs-lookup"><span data-stu-id="63ea1-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="63ea1-112">Assicurarsi che tutti gli utenti dispongano di Lync 2013 installati.</span><span class="sxs-lookup"><span data-stu-id="63ea1-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="63ea1-113">Definire una regola di criteri di versione client per impedire l'accesso alle versioni precedenti di Communicator.</span><span class="sxs-lookup"><span data-stu-id="63ea1-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="63ea1-114">Per abilitare la modalità di privacy della presenza avanzata</span><span class="sxs-lookup"><span data-stu-id="63ea1-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="63ea1-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="63ea1-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="63ea1-116">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="63ea1-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="63ea1-117">Questo comando consente di abilitare la modalità privacy per tutte le impostazioni di configurazione della privacy attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="63ea1-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="63ea1-118">Per altre informazioni sul modo in cui le configurazioni dei criteri di privacy della presenza avanzata di Lync Server gestiscono la presenza dei contatti per il client Lync 2013, vedere l'articolo Microsoft Knowledge che [Abilita la modalità di privacy della presenza avanzata di Lync Server per aggiornare lo stato presenza di alcuni contatti di Lync a "non disponibile"](http://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="63ea1-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63ea1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63ea1-119">See Also</span></span>


[<span data-ttu-id="63ea1-120">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="63ea1-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="63ea1-121">New-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="63ea1-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="63ea1-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="63ea1-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

