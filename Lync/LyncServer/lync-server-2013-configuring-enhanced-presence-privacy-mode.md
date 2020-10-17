---
title: 'Lync Server 2013: configurazione della modalità privacy della presenza avanzata'
description: 'Lync Server 2013: configurazione della modalità privacy della presenza avanzata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8eab347d233c23a9a4becf119dee673d3021dfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548452"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="0d212-103">Configurazione della modalità privacy della presenza avanzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d212-103">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d212-104">_**Ultimo argomento modificato:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="0d212-104">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="0d212-105">Con la modalità di privacy della presenza avanzata, gli utenti possono limitare le informazioni sulla presenza in modo che siano visibili solo ai contatti elencati nell'elenco contatti di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0d212-105">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="0d212-106">I cmdlet **New-CsPrivacyConfiguration**   e **Set-CsPrivacyConfiguration** dispongono di un parametro EnablePrivacyMode che controlla questa opzione.</span><span class="sxs-lookup"><span data-stu-id="0d212-106">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="0d212-107">Quando EnablePrivacyMode è impostato su true, l'opzione per limitare le informazioni sulla presenza ai contatti diventa disponibile nelle opzioni di stato di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0d212-107">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="0d212-108">Se invece EnablePrivacyMode è impostato su False, gli utenti possono scegliere di consentire sempre a tutti di visualizzare le informazioni sulla presenza oppure di accettare qualsiasi modifica futura apportata dall'amministratore alla modalità privacy.</span><span class="sxs-lookup"><span data-stu-id="0d212-108">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d212-109">Le impostazioni relative alla privacy di Lync 2013 e Lync 2010 non sono rispettate dalle versioni precedenti (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007).</span><span class="sxs-lookup"><span data-stu-id="0d212-109">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="0d212-110">Se le versioni precedenti di Office Communicator sono consentite per l'accesso, lo stato di un utente di Lync 2013, le informazioni di contatto o l'immagine potrebbero essere visualizzate da una persona che non è stata autorizzata a visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="0d212-110">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="0d212-111">Inoltre, le impostazioni relative alla privacy di un utente di Lync 2013 vengono reimpostate se successivamente accede con la versione precedente di Communicator.</span><span class="sxs-lookup"><span data-stu-id="0d212-111">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="0d212-112">Per questi motivi, in uno scenario di migrazione, prima di abilitare la modalità privacy della presenza avanzata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d212-112">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="0d212-113">Verificare che tutti gli utenti dispongano di Lync 2013 installato.</span><span class="sxs-lookup"><span data-stu-id="0d212-113">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="0d212-114">Definire una regola dei criteri di versione dei client per impedire alle precedenti versioni di Communicator di accedere.</span><span class="sxs-lookup"><span data-stu-id="0d212-114">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="0d212-115">Per abilitare la modalità privacy della presenza avanzata</span><span class="sxs-lookup"><span data-stu-id="0d212-115">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="0d212-116">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0d212-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0d212-117">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0d212-117">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="0d212-118">Questo comando abilita la modalità privacy per tutte le impostazioni di configurazione della privacy attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d212-118">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="0d212-119">Per ulteriori informazioni sul modo in cui la configurazione dei criteri per la modalità privacy della presenza di Lync Server è in grado di gestire la presenza del contatto per il client Lync 2013, vedere l'articolo Microsoft KB che [Abilita Lync Server Enhanced Presence privacy mode aggiorna lo stato di presenza di alcuni contatti di Lync su "non disponibile"](https://support.microsoft.com/kb/3020057).</span><span class="sxs-lookup"><span data-stu-id="0d212-119">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](https://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d212-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d212-120">See Also</span></span>


[<span data-ttu-id="0d212-121">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d212-121">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="0d212-122">New-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d212-122">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="0d212-123">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d212-123">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

