---
title: 'Lync Server 2013: verifica della replica dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 483a8125969fffc0db2c8f72bca3fc5b8001d943
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527623"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Verifica della replica dello schema di Active Directory in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Prima di eseguire la preparazione della foresta, verificare manualmente che la partizione dello schema sia stata replicata.

<div>

## <a name="to-manually-verify-schema-replication"></a>Per verificare manualmente la replica dello schema

1.  Accedere a un controller di dominio come membro del gruppo Enterprise Admins.

2.  Aprire ADSI Edit. A tale scopo, fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione**, quindi **ADSI Edit**.
    
    <div>
    

    > [!TIP]  
    > In alternativa, è possibile eseguire <STRONG>adsiedit.msc</STRONG> dalla riga di comando.

    
    </div>

3.  Nell'albero di Microsoft Management Console (MMC) fare clic su **ADSI Edit** se la voce non è già selezionata.

4.  Scegliere **Connetti a** dal menu **Azioni**.

5.  Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.

6.  Nel contenitore Schema individuare la voce CN=ms-RTC-SIP-SchemaVersion. Se questo oggetto è presente e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **rangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se l'oggetto non è presente o i valori degli attributi **rangeUpper** e **rangeLower** non sono quelli previsti, lo schema non è stato modificato o replicato.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esecuzione della preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

