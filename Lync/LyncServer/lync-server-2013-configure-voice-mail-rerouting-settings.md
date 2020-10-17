---
title: 'Lync Server 2013: configurare le impostazioni di reinstradamento della segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b51a529ee7bc4fd1148413058ceaf1f1f6d61e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520183"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="65691-102">Configurare le impostazioni di reinstradamento della segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65691-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65691-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="65691-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="65691-104">Survivable Branch Appliance e Survivable Branch Server sono in grado di garantire la sopravvivenza dei messaggi vocali per gli utenti di succursali durante un'interruzione della rete WAN, se la messaggistica unificata di Exchange è installata nel sito centrale e viene distribuito un operatore automatico di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="65691-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="65691-105">È opportuno che l'amministratore di Exchange configuri l'Operatore automatico in modo che accetti solo i messaggi, disabilitando altre funzionalità generiche come il trasferimento a un utente o a un operatore.</span><span class="sxs-lookup"><span data-stu-id="65691-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="65691-106">In alternativa, è possibile utilizzare un Operatore automatico generico o personalizzato per il routing della chiamata.</span><span class="sxs-lookup"><span data-stu-id="65691-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="65691-107">Per informazioni dettagliate, vedere la sezione relativa alla preparazione per la sopravvivenza dei messaggi vocali [per i requisiti di resilienza del sito di succursale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="65691-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="65691-108">Per configurare il funzionamento ininterrotto della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="65691-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="65691-109">Chiedere all'amministratore di Exchange di configurare l'AA per accettare solo i messaggi (nella shell di Exchange utilizzare il cmdlet seguente: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="65691-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="65691-110">Il parametro che consente di specificare se consentire la visualizzazione di messaggi (*SendVoiceMsgEnabled*) viene impostato su true per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="65691-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="65691-111">In Lync Server Management Shell, utilizzare il cmdlet **New-CsVoicemailReroutingConfiguration** per impostare il numero di telefono dell'operatore automatico di messaggistica unificata di Exchange nella configurazione di reinstradamento della segreteria telefonica nel Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="65691-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65691-112">Se in seguito sarà necessario modificare l'impostazione di rerouting della segreteria telefonica, utilizzare il cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="65691-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="65691-113">Per informazioni dettagliate su <STRONG>New-</STRONG>, vedere <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> negli argomenti della Guida della shell.</span><span class="sxs-lookup"><span data-stu-id="65691-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="65691-114">Impostare il numero di accesso sottoscrittore Messaggistica unificata di Exchange corrispondente al dial plan di messaggistica unificata di Exchange dell'utente di succursale come numero di accesso sottoscrittore Messaggistica unificata di Exchange nella configurazione di reinstradamento della segreteria telefonica nel Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="65691-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65691-115">Configurare il dial plan degli utenti di messaggistica unificata di Exchange in modo che sia presente un solo dial plan associato a tutti gli utenti di succursale che hanno necessità di accedere alla funzionalità di ricezione della posta vocale durante un'interruzione della rete WAN.</span><span class="sxs-lookup"><span data-stu-id="65691-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="65691-116">**Passaggio successivo** per Survivable Branch Appliance o Survivable Branch Server: [Home Users on a Survivable Branch Appliance or server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="65691-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

