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

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Configurare un'applicazione SNMP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Lync Server 2013 include un'interfaccia del servizio Web standard che è possibile utilizzare per connettere il servizio informazioni percorso alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono a indirizzi MAC con informazioni sulla porta e sull'opzione.

Se un'applicazione SNMP è installata e il servizio informazioni percorso non riesce a trovare una corrispondenza nel database delle posizioni, il servizio informazioni percorso esegue automaticamente una query nell'applicazione utilizzando l'indirizzo MAC fornito dal client. Il servizio informazioni percorso utilizza quindi la porta e cambia le informazioni restituite dall'applicazione SNMP per eseguire di nuovo una query sul database delle posizioni.

Per informazioni dettagliate, vedere [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Per configurare l'URL dell'applicazione SNMP

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

