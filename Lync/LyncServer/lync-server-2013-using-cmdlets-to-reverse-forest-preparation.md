---
title: 'Lync Server 2013: utilizzo dei cmdlet per annullare la preparazione della foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dbc7e4001299ef2d722896518291cc2afff001b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-06-19_

Utilizzare il cmdlet **Disable-CsAdForest** per annullare il passaggio di preparazione della foresta.

<div>


> [!WARNING]  
> Se si esegue il cmdlet <STRONG>Disable-CsAdForest</STRONG> in un ambiente in cui è stata distribuita anche una versione precedente di Lync Server, verranno eliminate anche le impostazioni globali per la versione precedente.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Per utilizzare cmdlet per annullare la preparazione della foresta

1.  Accedere a un computer che fa parte di un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Ad esempio:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Il parametro Force specifica se forzare l'esecuzione dell'attività. Se questo parametro non è presente, il comando non verrà eseguito se anche un dominio della foresta è ancora pronto per Lync Server 2013. Se viene specificato il parametro Force, l'azione continuerà indipendentemente dallo stato degli altri domini nella foresta.
    
    Se non si specifica il parametro GroupDomain, il valore predefinito è il dominio locale.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esecuzione della preparazione della foresta per Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Preparazione della foresta per Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

