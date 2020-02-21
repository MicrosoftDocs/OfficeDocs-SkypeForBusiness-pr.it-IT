---
title: Eseguire la migrazione di dispositivi analogici
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bc1c3420c22f4cc58bd0e617fd9ba98e16102c6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>Eseguire la migrazione di dispositivi analogici

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-16_

Lync Server fornisce il supporto per i dispositivi analogici. Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici. È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'ambiente Lync Server. Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario eseguire la migrazione anche degli oggetti contatto associati ai dispositivi analogici. Utilizzare Lync Server Management Shell per recuperare innanzitutto tutti gli oggetti contatto associati ai dispositivi analogici di Lync Server 2010 e quindi spostare tali oggetti nel pool di Lync Server 2013.

<div>

## <a name="to-migrate-analog-devices"></a>Per eseguire la migrazione dei dispositivi analogici

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Nella riga di comando digitare il comando seguente:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Lync Server 2013. Nella riga di comando digitare il comando seguente:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Verificare che tutti gli oggetti contatto siano ora associati al pool di Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

