---
title: 'Lync Server 2013: Home Users on a Survivable Branch Appliance o server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98ef5adb3fafc40e4afe02384492be4a88fd2b24
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="88ac9-102">Utenti domestici in un Survivable Branch Appliance o server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88ac9-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88ac9-103">_**Ultimo argomento modificato:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="88ac9-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="88ac9-104">Il processo di homing degli utenti in un Survivable Branch Appliance o Survivable Branch Server è simile al processo di homing degli utenti in un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="88ac9-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="88ac9-105">Eseguire la procedura Survivable Branch Appliance o Survivable Branch Server nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="88ac9-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="88ac9-106">Per gli utenti privati di Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="88ac9-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="88ac9-107">Prima di spostare gli utenti nel Survivable Branch Server o nel Survivable Branch Server, aprire Lync Server Management Shell e quindi eseguire tutte le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88ac9-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="88ac9-108">Eseguire il cmdlet **Test-CsPstnOutboundCall** per verificare che il Survivable Branch Server sia in esecuzione e che sia configurata la connettività PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="88ac9-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="88ac9-109">Se è necessario modificare le proprietà del gateway PSTN, utilizzare il cmdlet **Set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="88ac9-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="88ac9-110">Eseguire il cmdlet **Get-CsVoicePolicy** per verificare che gli utenti che verranno ospitati nel Survivable Branch Server dispongano del criterio di routing VoIP appropriato.</span><span class="sxs-lookup"><span data-stu-id="88ac9-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="88ac9-111">Se è necessario modificare il criterio VoIP, utilizzare il cmdlet **Set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="88ac9-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="88ac9-112">Eseguire il cmdlet **Get-CsVoicemailReroutingConfiguration** per verificare che le impostazioni di reinstradamento della segreteria telefonica siano configurate.</span><span class="sxs-lookup"><span data-stu-id="88ac9-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="88ac9-113">Se è necessario modificare le impostazioni di reinstradamento della segreteria telefonica, utilizzare il cmdlet **Set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="88ac9-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="88ac9-114">In Lync Server Management Shell, eseguire il cmdlet **Move-CsUser** per spostare gli utenti privati.</span><span class="sxs-lookup"><span data-stu-id="88ac9-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88ac9-115">È inoltre possibile utilizzare il pannello di controllo di Lync Server per verificare i prerequisiti e gli utenti privati.</span><span class="sxs-lookup"><span data-stu-id="88ac9-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="88ac9-116">Gli utenti ospitati in un Survivable Branch Appliance di Lync Server non sono in grado di creare nuove chat room o di visualizzare la scheda sala per le sale esistenti.</span><span class="sxs-lookup"><span data-stu-id="88ac9-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88ac9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88ac9-117">See Also</span></span>


[<span data-ttu-id="88ac9-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="88ac9-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="88ac9-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="88ac9-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="88ac9-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="88ac9-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="88ac9-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="88ac9-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

