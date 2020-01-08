---
title: 'Lync Server 2013: Utilizzo dei cmdlet per annullare la preparazione della foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd186fc3b2c6171b49cf3fd4c9e78b8e66b4cc71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-06-19_

Usa il cmdlet **Disable-CsAdForest** per invertire il passaggio di preparazione della foresta.

<div>


> [!WARNING]  
> Se si esegue il cmdlet <STRONG>Disable-CsAdForest</STRONG> in un ambiente in cui è stata distribuita anche una versione precedente di Lync Server, verranno eliminate anche le impostazioni globali per la versione precedente.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Per usare i cmdlet per invertire la preparazione della foresta

1.  Accedere a un computer collegato a un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Ad esempio:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Il parametro Force specifica se forzare l'esecuzione dell'attività. Se questo parametro non è presente, il comando non verrà eseguito se anche un dominio nella foresta è ancora pronto per Lync Server 2013. Se il parametro Force viene specificato, l'azione continuerà indipendentemente dallo stato di altri domini nella foresta.
    
    Se non specifichi il parametro GroupDomain, il valore predefinito è il dominio locale.

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

