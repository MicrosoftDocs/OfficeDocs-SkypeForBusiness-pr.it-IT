---
title: 'Lync Server 2013: eliminazione di un sito di rete esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c8e3828bccb84fcddb4404dd7228173c63ab8a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Eliminazione di un sito di rete esistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1. È possibile usare il pannello di controllo di Lync Server 2013 per configurare i siti e associarli alle aree geografiche. Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver. È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda. Dal pannello di controllo di Lync Server è possibile creare, modificare ed eliminare siti di rete. Usare la procedura seguente per eliminare un sito di rete esistente. Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>Per eliminare un sito di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.

4.  Nella pagina del **sito** fare clic sul sito che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più di un sito alla volta. Per eseguire questa operazione, premere CTRL e selezionare più siti tenendo premuto il tasto CTRL. In alternativa, per selezionare tutti i siti, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.
    
    <div>
    

    > [!WARNING]  
    > Non è possibile rimuovere un sito di rete se associato a una subnet di rete. Se si tenta di rimuovere un sito associato a una subnet, viene visualizzato un messaggio di errore. Per verificare se un sito è associato a qualsiasi subnet, fare clic sul sito e quindi su <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

