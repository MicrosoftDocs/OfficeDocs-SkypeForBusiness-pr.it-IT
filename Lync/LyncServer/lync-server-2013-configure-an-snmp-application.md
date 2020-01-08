---
title: "Lync Server 2013: configurare un'applicazione SNMP"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15a911abc614ff30c4130fb2a35886458fcb1dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="1fc96-102">Configurare un'applicazione SNMP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fc96-102">Configure an SNMP application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fc96-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1fc96-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1fc96-104">Lync Server 2013 include un'interfaccia di servizio Web standard che consente di connettere il servizio informazioni sulla posizione alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono agli indirizzi MAC con le informazioni sulla porta e sullo switch.</span><span class="sxs-lookup"><span data-stu-id="1fc96-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="1fc96-105">Se è installata un'applicazione SNMP e il servizio informazioni sulla posizione non riesce a trovare una corrispondenza nel database della posizione, il servizio informazioni sulla posizione esegue automaticamente una query nell'applicazione usando l'indirizzo MAC fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="1fc96-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="1fc96-106">Il servizio informazioni sulla posizione usa quindi la porta e cambia le informazioni restituite dall'applicazione SNMP per interrogare di nuovo il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="1fc96-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="1fc96-107">Per informazioni dettagliate, vedere [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1fc96-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1fc96-108">Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8.</span><span class="sxs-lookup"><span data-stu-id="1fc96-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="1fc96-109">Per configurare l'URL dell'applicazione SNMP</span><span class="sxs-lookup"><span data-stu-id="1fc96-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="1fc96-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1fc96-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1fc96-111">Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP.</span><span class="sxs-lookup"><span data-stu-id="1fc96-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

