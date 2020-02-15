---
title: 'Lync Server 2013: distribuire i tipi di indirizzi IP in un server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd057c79132200dbe5be8ee2551a711d8fb8e95c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>Distribuire i tipi di indirizzi IP in un server perimetrale per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-14_

Utilizzando Generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzi IP in un server perimetrale.

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Per distribuire tipi di indirizzo IP su un server perimetrale

1.  In Generatore di topologie, in pool di server **perimetrali**, fare clic con il pulsante destro del mouse su di esso in un pool e quindi scegliere **modifica proprietà**. (Alternativamente, selezionare il server e fare clic su **Modifica proprietà** dal menu **Azione**.)

2.  Nella finestra **Modifica proprietà**, selezionare la configurazione dell'indirizzo IP che si desidera supportare. Nelle figure seguenti è mostrata una configurazione dual stack per l'interfaccia interna e l'interfaccia esterna.
    
    **Interfaccia interna del server perimetrale dual stack**
    
    ![Pagina delle proprietà generali di Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Pagina delle proprietà generali di Lync Server")
    
    **Interfaccia esterna del server perimetrale dual stack**
    
    ![Lync Server Next Hop/pagina di configurazione esterna](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server Next Hop/pagina di configurazione esterna")

3.  Per ciascun tipo di indirizzo selezionato, è necessario fornire gli indirizzi interni e esterni appropriati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

