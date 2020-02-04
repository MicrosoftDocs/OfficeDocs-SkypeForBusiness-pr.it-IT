---
title: 'Lync Server 2013: Routing della messaggistica unificata di Exchange ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="97ca6-102">Routing della messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97ca6-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97ca6-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="97ca6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="97ca6-104">L'applicazione di routing della messaggistica unificata di Exchange viene eseguita nel server front-end per instradare le chiamate a una distribuzione di messaggistica unificata locale di Microsoft Exchange Server o al servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="97ca6-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="97ca6-105">Applicazione di routing ExUM</span><span class="sxs-lookup"><span data-stu-id="97ca6-105">The ExUM Routing Application</span></span>

<span data-ttu-id="97ca6-106">L'applicazione di routing della messaggistica unificata di Lync Server 2013 usa le informazioni delle impostazioni degli account utente e i parametri dei criteri di segreteria telefonica ospitata per determinare come instradare le chiamate per i messaggi vocali ospitati, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="97ca6-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="97ca6-107">**Esempio di routing della messaggistica unificata di Exchange per la distribuzione**</span><span class="sxs-lookup"><span data-stu-id="97ca6-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="97ca6-108">![Distribuzione della messaggistica unificata di Exchange con Lync Server in locale](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange con Lync Server in locale")</span><span class="sxs-lookup"><span data-stu-id="97ca6-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="97ca6-109">Il routing della messaggistica unificata di Exchange può essere configurato per instradare le chiamate agli utenti abilitati per la messaggistica unificata di Exchange locale, agli utenti abilitati per la messaggistica unificata di Exchange ospitata o a una combinazione dei due.</span><span class="sxs-lookup"><span data-stu-id="97ca6-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="97ca6-110">Supponiamo ad esempio che la cassetta postale di Roy e il servizio di messaggistica unificata di Exchange vengano ospitati in una distribuzione di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="97ca6-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="97ca6-111">Le informazioni sull'indirizzo proxy dell'account utente di Roy forniscono le informazioni che l'applicazione di routing ExUM USA per instradare le chiamate a un server Messaggistica unificata locale di Exchange.</span><span class="sxs-lookup"><span data-stu-id="97ca6-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="97ca6-112">La cassetta postale di Alice e il servizio di messaggistica unificata di Exchange si trovano nel centro dati di un provider di servizi Exchange ospitati.</span><span class="sxs-lookup"><span data-stu-id="97ca6-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="97ca6-113">Il routing delle chiamate di messaggistica unificata di Exchange è configurato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="97ca6-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="97ca6-114">I valori impostati nell'attributo msExchUCVoiceMailSettings dell'account utente di Alice indicano all'applicazione di routing ExUM di controllare i dettagli di routing in un criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="97ca6-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97ca6-115">Il valore dell'attributo msExchUCVoiceMailSettings può essere impostato dal provider di servizi di Exchange o dall'amministratore di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97ca6-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="97ca6-116">Nell'esempio illustrato nel diagramma precedente il valore (CsHostedVoiceMail = 1) è stato impostato dall'amministratore di Lync Server 2013 per abilitare la segreteria telefonica ospitata per Alice.</span><span class="sxs-lookup"><span data-stu-id="97ca6-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="97ca6-117">Per informazioni dettagliate su questo attributo, vedere <A href="lync-server-2013-hosted-exchange-user-management.md">gestione degli utenti di Exchange ospitata in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="97ca6-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="97ca6-118">I criteri di segreteria telefonica ospitati assegnati all'account utente di Alice forniscono informazioni dettagliate sul routing:</span><span class="sxs-lookup"><span data-stu-id="97ca6-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="97ca6-119">La destinazione è il provider di servizi di messaggistica unificata di Exchange ospitata (ls. ExUm. \<hostedExchangeServer\>. com in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="97ca6-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="97ca6-120">Le organizzazioni sono identificate dagli ID tenant, ovvero gli FQDN di routing per i messaggi SIP per i tenant di Exchange Server che si trovano in ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com e Corp.litwareinc.com in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="97ca6-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="97ca6-121">Il nome di dominio completo per Exchange Online è exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="97ca6-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="97ca6-122">Per informazioni dettagliate, vedere Criteri per la segreteria [telefonica ospitati in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="97ca6-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97ca6-123">Se l'attributo msExchUCVoiceMailSettings e le impostazioni dell'indirizzo proxy di messaggistica unificata sono presenti in un account utente, l'attributo msExchUCVoiceMailSettings ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="97ca6-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

