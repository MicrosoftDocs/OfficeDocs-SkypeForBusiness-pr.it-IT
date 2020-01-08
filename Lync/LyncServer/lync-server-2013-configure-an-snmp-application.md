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

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Configurare un'applicazione SNMP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Lync Server 2013 include un'interfaccia di servizio Web standard che consente di connettere il servizio informazioni sulla posizione alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono agli indirizzi MAC con le informazioni sulla porta e sullo switch.

Se è installata un'applicazione SNMP e il servizio informazioni sulla posizione non riesce a trovare una corrispondenza nel database della posizione, il servizio informazioni sulla posizione esegue automaticamente una query nell'applicazione usando l'indirizzo MAC fornito dal client. Il servizio informazioni sulla posizione usa quindi la porta e cambia le informazioni restituite dall'applicazione SNMP per interrogare di nuovo il database della posizione.

Per informazioni dettagliate, vedere [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Per configurare l'URL dell'applicazione SNMP

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

