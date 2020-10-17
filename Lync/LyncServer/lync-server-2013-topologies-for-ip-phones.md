---
title: 'Lync Server 2013: topologie per i telefoni IP'
description: 'Lync Server 2013: topologie per i telefoni IP.'
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
ms.openlocfilehash: 7a151a83a69e1f7e14dcbed8d8ab1038157fa839
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549132"
---
# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologie per i telefoni IP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-21_

In questa sezione viene fornita una panoramica del processo di connettività e vengono illustrate le differenze tra la modalità di connessione di un telefono IP in una rete interna e in una rete esterna.

<div>


> [!NOTE]  
> Lync Server fornisce il supporto per i seguenti telefoni IP: Aastra 6721ip common area Phone, Aastra 6725ip Desk Phone, HP 4110 IP Phone (Common area Phone), HP 4120 IP Phone (Desk Phone), Polycom CX600 IP Desk Phone, Polycom CX700 IP Desk Phone, Polycom CX500 IP common area Phone e Polycom CX3000 IP Conference Phone. Di tali telefoni, tutti gli utenti di Polycom CX700 possono eseguire Lync Phone Edition.



</div>

Nel diagramma seguente vengono descritti tutti i componenti coinvolti nella connettività di un dispositivo nell'ambiente aziendale.

**Topologia interna**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> La figura precedente è una rappresentazione logica e non una panoramica fisica. Ad esempio, Active Directory Domain Services (AD DS) si trova raramente nello stesso computer di qualsiasi componente di Lync Server. L'archivio utente può essere contenuto nel server back-end, nel server di archiviazione o nel Monitoring Server. Lync Server Management Shell, il server Web e i servizi di aggiornamento fanno parte del ruolo del server front-end.



</div>

Nel diagramma seguente viene fornita una panoramica dei componenti coinvolti quando il dispositivo si trova all'esterno della rete aziendale.

**Topologia esterna**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Il Servizio Web aggiornamento dispositivi offre un sito Web esterno e uno interno, ma in questo diagramma viene illustrato solo quello esterno.<BR>La posizione della funzione di registrazione e l'URL del Servizio Web aggiornamento dispositivi dell'organizzazione devono essere pubblicati in DNS se deve essere abilitato l'accesso esterno. Il server perimetrale inoltre deve essere distribuito e configurato correttamente per consentire le comunicazioni esterne dal dispositivo all'ambiente aziendale e viceversa. Questo viene omesso nel diagramma precedente perché la distribuzione di server perimetrali non è specifica della connettività di un dispositivo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

