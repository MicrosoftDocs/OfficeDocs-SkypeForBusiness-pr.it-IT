---
title: Definizione dell'esperienza utente per l'acquisizione manuale di una posizione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione. Durante una chiamata di emergenza, però, la chiamata verrà prima instradata a un dispatcher di Emergency Call Centre (ECRC) National/Regional E9-1-1, prima di essere indirizzato a un punto di risposta di sicurezza pubblica (PSAP). ECRC eseguirà una query verbale sul chiamante per una posizione e quindi inoltra la chiamata al PSAP appropriato, in base alle informazioni fornite.

  - **Gli utenti devono essere invitati a immettere una posizione quando non vengono forniti automaticamente dal servizio informazioni sulla posizione?**  
    Ad esempio, se un client si trova in una subnet non definita, a casa, in un hotel o in qualsiasi altro punto all'esterno della rete, l'utente deve essere tenuto a immettere una posizione?
    
    Per definire il comportamento del client, è possibile configurare l'impostazione della **posizione necessaria** nel criterio della posizione. L'impostazione di questo valore non significa che l'utente non verrà richiesto per una posizione. L'impostazione di questo valore su Sì significa che l'utente verrà richiesto per una posizione, ma può chiudere la richiesta. L'impostazione di questo valore su Disclaimer indica che all'utente verrà richiesto di trovare una posizione e verrà visualizzata una dichiarazione di non responsabilità se tenta di chiudere il messaggio. In tutti i casi, l'utente può continuare a usare il client come di consueto.

Quando un utente immette manualmente una posizione, la posizione viene mappata all'indirizzo MAC del gateway predefinito della rete del client e viene archiviata in una tabella per utente che si trova nel client. Quando l'utente torna in una posizione archiviata in precedenza, il client Lync si imposta automaticamente in tale posizione.

<div>


> [!NOTE]
> È possibile modificare solo la posizione corrente del client, ma è anche possibile eliminare qualsiasi posizione archiviata nella tabella dell'utente locale.



</div>

</div>

<span> </span>

</div>

</div>

</div>

