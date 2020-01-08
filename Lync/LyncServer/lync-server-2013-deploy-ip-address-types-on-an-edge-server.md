---
title: 'Lync Server 2013: Distribuire i tipi di indirizzi IP in un server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a094a39fd74ab30ee1dd3a5a3da4e777bcf7e338
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>Distribuire i tipi di indirizzi IP in un server perimetrale per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-14_

Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un server perimetrale.

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Per distribuire i tipi di indirizzo IP in un server perimetrale

1.  In Generatore di topologie, in **pool di bordi**, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**. In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .

2.  Nella finestra **modifica proprietà** selezionare la configurazione dell'indirizzo IP che si vuole supportare. Le figure seguenti mostrano una configurazione dual stack per l'interfaccia interna e l'interfaccia esterna.
    
    **Interfaccia interna del server Edge in pila doppia**
    
    Pagina delle proprietà ![generali di Lync Server pagina]delle(images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Proprietà generali di Lync Server")
    
    **Interfaccia esterna per server Edge in pila doppia**
    
    ![Lync Server Next Hop/pagina di configurazione esterna](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server Next Hop/pagina di configurazione esterna")

3.  Per ogni tipo di indirizzo selezionato, è necessario specificare indirizzi interni ed esterni appropriati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

