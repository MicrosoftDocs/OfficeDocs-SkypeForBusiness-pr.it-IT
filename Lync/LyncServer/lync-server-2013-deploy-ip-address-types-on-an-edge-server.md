---
title: 'Lync Server 2013: Distribuire i tipi di indirizzi IP in un server perimetrale'
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
ms.openlocfilehash: ece4b55f42958916876539f05b951e862e0d493f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729666"
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
    
    ![Pagina delle proprietà generali di Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Pagina delle proprietà generali di Lync Server")
    
    **Interfaccia esterna per server Edge in pila doppia**
    
    ![Pagina di configurazione esterna o dell'hop successivo di Lync Server](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Pagina di configurazione esterna o dell'hop successivo di Lync Server")

3.  Per ogni tipo di indirizzo selezionato, è necessario specificare indirizzi interni ed esterni appropriati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

