---
title: 'Lync Server 2013: Pubblicare la topologia aggiornata'
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
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Pubblicare la topologia aggiornata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Dopo l'aggiornamento della topologia in Generatore di topologie, è necessario pubblicare la topologia in Central Management Store prima di poter configurare e usare il server di chat persistente. Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia per garantire la sincronizzazione di tutti i server con la topologia e altre modifiche alla configurazione.

<div>

## <a name="to-publish-an-updated-topology"></a>Per pubblicare una topologia aggiornata

Prima di pubblicare la topologia, installare i database per il server di chat persistente. Usare generatore di topologie per installare i database selezionando **azione** e **Installa database**.

1.  In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere usando un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** . e con autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nell'archivio di file da usare per il file Store del server di chat persistente (in modo che il generatore di topologia possa configurare gli elenchi di controllo di accesso discrezionale (DACL) necessari) o un account con diritti utente equivalenti.

2.  Avviare Generatore di topologie. Selezionare **Scarica la topologia dalla distribuzione esistente**o **Apri la topologia da un file locale** se è stata salvata localmente.

3.  Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **Pubblica topologia**.

4.  Nella pagina **pubblica la topologia** fare clic su **Avanti**.

5.  Nella pagina **completamento pubblicazione guidata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Dopo aver pubblicato la topologia, è necessario configurare il supporto per il server di chat persistente prima di poter archiviare qualsiasi contenuto.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

