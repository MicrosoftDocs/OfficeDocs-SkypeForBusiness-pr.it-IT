---
title: 'Lync Server 2013: supporto per la messaggistica unificata di Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd46b19ea52b56b70cc5bd4c459f2260a97306d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="aebd9-102">Supporto della messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebd9-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aebd9-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="aebd9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="aebd9-104">Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange per la combinazione di messaggi vocali e messaggi di posta elettronica in un'unica infrastruttura di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="aebd9-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="aebd9-105">In Exchange 2013, la messaggistica unificata di Exchange è costituita dal servizio di messaggistica unificata di Exchange, installato e eseguito nel server cassette postali, e dal router delle chiamate di messaggistica unificata, installato e eseguito sul server Accesso client.</span><span class="sxs-lookup"><span data-stu-id="aebd9-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="aebd9-106">Per le distribuzioni di VoIP aziendale di Lync Server 2013, la messaggistica UNIFICAta di Exchange combina i messaggi vocali e i messaggi di posta elettronica in un singolo archivio accessibile da un telefono, ovvero Outlook Voice Access, o da un computer.</span><span class="sxs-lookup"><span data-stu-id="aebd9-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="aebd9-107">La messaggistica unificata di Exchange e Lync Server 2013 interagiscono per fornire servizi di ricezione chiamata, Outlook Voice Access e operatore automatico agli utenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="aebd9-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="aebd9-108">Oltre al supporto per l'integrazione con distribuzioni locali della messaggistica unificata di Exchange, Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="aebd9-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="aebd9-109">Questo consente di fornire la funzionalità di messaggistica vocale agli utenti di cui viene eseguita la migrazione in parte o completamente in un provider di servizi di Exchange ospitato, ad esempio Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aebd9-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="aebd9-110">Lync Server 2013 supporta le versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aebd9-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="aebd9-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="aebd9-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="aebd9-112">Microsoft Exchange Server 2010 (obbligatorio) o con il Service Pack più recente (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="aebd9-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="aebd9-113">Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obbligatorio) o Service Pack più recente (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="aebd9-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="aebd9-114">Non è possibile collocare la messaggistica unificata di Exchange con Lync Server 2013 o un database Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aebd9-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="aebd9-115">È possibile installare la messaggistica unificata di Exchange e Lync Server 2013 in foreste separate.</span><span class="sxs-lookup"><span data-stu-id="aebd9-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aebd9-116">La messaggistica unificata di Exchange potrebbe non essere necessaria nelle distribuzioni di Enterprise Voice con integrazione PBX in quanto il sistema PBX può continuare a fornire a tutti gli utenti il servizio di segreteria telefonica e gli altri servizi correlati.</span><span class="sxs-lookup"><span data-stu-id="aebd9-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="aebd9-117">Se il sistema PBX viene eventualmente ritirato, ad esempio se si distribuisce il trunking SIP per la connettività PSTN (Public Switched Telephone Network), è necessario riconfigurare la messaggistica unificata di Exchange per fornire alla segreteria telefonica gli utenti che in precedenza hanno utilizzato il dispositivo di segreteria telefonica PBX.</span><span class="sxs-lookup"><span data-stu-id="aebd9-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aebd9-118">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="aebd9-118">In This Section</span></span>

  - [<span data-ttu-id="aebd9-119">Componenti e topologie per la messaggistica unificata locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebd9-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="aebd9-120">Supporto per l'integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebd9-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

