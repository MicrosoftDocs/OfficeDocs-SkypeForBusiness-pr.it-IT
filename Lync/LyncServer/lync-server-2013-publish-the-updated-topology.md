---
title: 'Lync Server 2013: pubblicare la topologia aggiornata'
description: 'Lync Server 2013: pubblicare la topologia aggiornata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c27cca2eae86eadaf1ff37e2c3520eaec3f86c98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571692"
---
# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Pubblicare la topologia aggiornata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Dopo aver aggiornato la topologia in Generatore di topologie, è necessario pubblicare la topologia nell'archivio di gestione centrale prima di poter configurare e utilizzare il server Chat persistente. In tutti i server della topologia vengono replicate copie di sola lettura dei dati in modo che tutti i server siano sincronizzati con la topologia e altre modifiche della configurazione.

<div>

## <a name="to-publish-an-updated-topology"></a>Per pubblicare una topologia aggiornata

Prima di pubblicare la topologia, installare i database per il server Chat persistente. Utilizzare Generatore di topologie per installare i database selezionando **azione** e **Installa database**.

1.  In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere utilizzando un account membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** . e con autorizzazioni di controllo completo, ovvero lettura, scrittura e modifica, nell'archivio file da utilizzare per l'archivio file del server Chat persistente, in modo che il generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale necessari o un account con diritti utente equivalenti.

2.  Avviare Generatore di topologie. Selezionare **Scarica topologia dalla distribuzione esistente** o **Apri topologia da un file locale**, se la topologia è stata salvata in locale.

3.  Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **Pubblica topologia**.

4.  Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.

5.  Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Dopo aver pubblicato la topologia, è necessario configurare il supporto per il server Chat persistente prima che sia possibile archiviare qualsiasi contenuto.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

