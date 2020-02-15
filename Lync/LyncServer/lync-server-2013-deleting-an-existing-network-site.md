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
ms.openlocfilehash: 5b67dcb92fec16c31c2e2a6be780a29eb1eee295
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Eliminazione di un sito di rete esistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1. È possibile utilizzare il pannello di controllo di Lync Server 2013 per configurare i siti e associarli alle aree geografiche. Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di rete come Chicago, Redmond e Vancouver. Deve essere creato un sito di rete del servizio Controllo di ammissione di chiamata per ogni sito di un'organizzazione, anche se tale sito non presenta limitazioni della larghezza di banda. Nel pannello di controllo di Lync Server è possibile creare, modificare ed eliminare siti di rete. Per eliminare un sito di rete esistente, usare la procedura che segue. Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>Per eliminare un sito di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito**.

4.  Nella pagina **Sito** fare clic sul sito che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più siti contemporaneamente. A tale scopo, premere CTRL e selezionare più siti sempre tenendo premuto CTRL. In alternativa, per selezionare tutti i siti, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.

    
    </div>

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.
    
    <div>
    

    > [!WARNING]  
    > Se un sito di rete è associato a una subnet di rete, non è possibile rimuoverlo. Se si tenta di rimuovere un sito associato a una subnet, verrà visualizzato un messaggio di errore. Per controllare se un sito è associato a eventuali subnet, fare clic sul sito e quindi scegliere <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>Modifica</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

