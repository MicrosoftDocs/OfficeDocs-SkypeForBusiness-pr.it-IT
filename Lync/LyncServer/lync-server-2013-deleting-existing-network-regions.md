---
title: 'Lync Server 2013: eliminazione delle aree di rete esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea9d08121a7d62d10b44f97ff46ff8d4a5ca129e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Eliminazione delle aree di rete esistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC). È possibile usare il pannello di controllo di Lync Server per configurare le aree di rete. Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video. Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare un'area geografica di rete. Usare questo argomento per eliminare le aree di rete esistenti. Per informazioni dettagliate sulla creazione o la modifica di aree di rete esistenti, vedere [creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Per eliminare un'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.

4.  Nella pagina **area** fare clic sull'area che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > Puoi eliminare più di un'area alla volta. A tale scopo, premere CTRL e selezionare più aree mentre si tiene premuto il tasto CTRL. In alternativa, per selezionare tutte le aree geografiche, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.
    
    <div>
    

    > [!WARNING]  
    > Un'area di rete non può essere rimossa se associata a un sito di rete. Se si tenta di rimuovere un'area associata a un sito, viene visualizzato un messaggio di errore. Per verificare se un'area è associata a qualsiasi sito, selezionare l'area geografica e quindi fare clic su <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

