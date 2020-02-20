---
title: "Lync Server 2013: configurare un'applicazione SNMP"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31f220ca823d739fa95ad6edb3aec97b13d6242b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="34300-102">Configurare un'applicazione SNMP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34300-102">Configure an SNMP application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34300-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="34300-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="34300-104">Lync Server 2013 include un'interfaccia del servizio Web standard che è possibile utilizzare per connettere il servizio informazioni percorso alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono a indirizzi MAC con informazioni sulla porta e sull'opzione.</span><span class="sxs-lookup"><span data-stu-id="34300-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="34300-105">Se un'applicazione SNMP è installata e il servizio informazioni percorso non riesce a trovare una corrispondenza nel database delle posizioni, il servizio informazioni percorso esegue automaticamente una query nell'applicazione utilizzando l'indirizzo MAC fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="34300-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="34300-106">Il servizio informazioni percorso utilizza quindi la porta e cambia le informazioni restituite dall'applicazione SNMP per eseguire di nuovo una query sul database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="34300-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="34300-107">Per informazioni dettagliate, vedere [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="34300-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34300-108">Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8.</span><span class="sxs-lookup"><span data-stu-id="34300-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="34300-109">Per configurare l'URL dell'applicazione SNMP</span><span class="sxs-lookup"><span data-stu-id="34300-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="34300-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="34300-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="34300-111">Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP.</span><span class="sxs-lookup"><span data-stu-id="34300-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

