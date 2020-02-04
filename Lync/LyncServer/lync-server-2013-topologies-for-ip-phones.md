---
title: 'Lync Server 2013: topologie per telefoni IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologie per telefoni IP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-21_

Questa sezione offre una panoramica del processo di connettività e spiega le differenze tra il modo in cui un telefono IP si connette in una rete interna ed esterna.

<div>


> [!NOTE]  
> Lync Server offre il supporto per i telefoni IP seguenti: il telefono per l'area comune Aastra 6721ip, il telefono da tavolo Aastra 6725ip, il telefono IP HP 4110 (telefono per l'area comune), il telefono IP HP 4120 (telefono da tavolo), il telefono da tavolo IP di Polycom CX600, il telefono da tavolo IP di Polycom CX700 Polycom IP telefono per area comune e telefono per conferenze IP di Polycom CX3000. Di questi telefoni, tutti tranne il Polycom CX700 può eseguire Lync Phone Edition.



</div>

Il diagramma seguente descrive tutti i componenti coinvolti nella connettività dei dispositivi nell'ambiente aziendale.

**Topologia interna**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> La figura precedente è una rappresentazione logica, non una panoramica fisica. Ad esempio, Active Directory Domain Services (AD DS) si trova raramente nello stesso computer dei componenti di Lync Server. L'archivio utenti può essere posizionato sul server back-end o sui server di archiviazione e monitoraggio. Lync Server Management Shell, Web Server e Update Services fanno parte del ruolo del server front-end.



</div>

Il diagramma seguente offre una panoramica dei componenti coinvolti quando il dispositivo si trova all'esterno della rete aziendale.

**Topologia esterna**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Il servizio Web Update del dispositivo fornisce un sito Web esterno e interno, ma solo quello esterno è illustrato qui.<BR>La posizione del registrar e l'URL del servizio Web di aggiornamento dei dispositivi per l'organizzazione devono essere pubblicati in DNS se è necessario abilitare l'accesso esterno. Inoltre, il server perimetrale deve essere distribuito e configurato correttamente per consentire le comunicazioni esterne dal dispositivo all'ambiente aziendale e viceversa. Questa operazione viene omessa dal diagramma precedente perché la distribuzione di Edge non è specifica della connettività dei dispositivi.



</div>

</div>

<span> </span>

</div>

</div>

</div>

