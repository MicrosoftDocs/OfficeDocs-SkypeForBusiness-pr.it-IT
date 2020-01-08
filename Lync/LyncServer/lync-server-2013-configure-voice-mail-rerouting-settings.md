---
title: 'Lync Server 2013: Configurare le impostazioni di rerouting della segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="fe2a8-102">Configurare le impostazioni di rerouting della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe2a8-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe2a8-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fe2a8-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fe2a8-104">I Survivable Branch Appliances e i Survivable Branch Server possono consentire la sopravvivenza della segreteria telefonica per gli utenti di Branch durante un'interruzione WAN, se la messaggistica unificata di Exchange viene installata presso il sito centrale e viene distribuito un operatore automatico di messaggistica unificata di Exchange (AA).</span><span class="sxs-lookup"><span data-stu-id="fe2a8-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="fe2a8-105">È consigliabile che l'amministratore di Exchange configuri l'AA per accettare solo i messaggi, che Disabilita altre funzionalità generiche, ad esempio il trasferimento a un utente o il trasferimento a un operatore.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="fe2a8-106">In alternativa, è possibile usare un generico AA o un AA personalizzato per instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="fe2a8-107">Per informazioni dettagliate, vedere la sezione "preparazione per la sopravvivenza della segreteria telefonica" dei [requisiti di resilienza del sito filiale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="fe2a8-108">Per configurare la sopravvivenza della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="fe2a8-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="fe2a8-109">Chiedere all'amministratore di Exchange di configurare l'AA solo per accettare i messaggi (nella shell di Exchange utilizzare il cmdlet seguente: **set \<-UMAutoAttendant\> AA Name-CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="fe2a8-110">Il parametro che specifica di consentire l'uscita dei messaggi (*SendVoiceMsgEnabled*) è true per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="fe2a8-111">In Lync Server Management Shell utilizzare il cmdlet **New-CsVoicemailReroutingConfiguration** per impostare il numero di telefono AA come numero di telefono dell'operatore automatico di messaggistica unificata di Exchange nella configurazione di reindirizzamento della segreteria telefonica in Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe2a8-112">Se è necessario modificare l'impostazione di reinstradamento della segreteria telefonica in un secondo momento, usare il cmdlet <STRONG>Set-CsVoicemailReroutingConfiguration</STRONG> per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="fe2a8-113">Per informazioni dettagliate, informazioni su <STRONG>New</STRONG> e <STRONG>Set-CsVoicemailReroutingConfiguration</STRONG>, negli argomenti della Guida di Shell.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="fe2a8-114">Impostare il numero di accesso abbonato alla messaggistica UNIFICAta di Exchange che corrisponde al dial plan di messaggistica unificata di Exchange dell'utente della filiale come numero di accesso del Sottoscrittore di Exchange UM nella configurazione di reindirizzamento della segreteria telefonica in Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe2a8-115">Configurare il dial plan degli utenti di Exchange UM in modo che sia presente un solo dial plan associato a tutti gli utenti della filiale che hanno bisogno di accedere alla funzionalità Get Voice mail durante un'interruzione WAN.</span><span class="sxs-lookup"><span data-stu-id="fe2a8-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="fe2a8-116">**Passaggio successivo** per Survivable Branch Appliances o Survivable Branch Servers: [utenti privati in un Survivable Branch Appliance o server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="fe2a8-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

