---
title: 'Lync Server 2013: Verifica della replica dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Verifica della replica dello schema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Prima di eseguire la preparazione della foresta, verificare manualmente che la partizione dello schema sia stata replicata.

<div>

## <a name="to-manually-verify-schema-replication"></a>Per verificare manualmente la replica dello schema

1.  Accedere a un controller di dominio come membro del gruppo amministratori aziendali.

2.  Aprire ADSI Edit facendo clic sul pulsante **Start**, scegliendo **strumenti di amministrazione**e quindi facendo clic su **Modifica ADSI**.
    
    <div>
    

    > [!TIP]  
    > In alternativa, è possibile eseguire <STRONG>ADSIEdit. msc</STRONG> dalla riga di comando.

    
    </div>

3.  Nell'albero di Microsoft Management Console (MMC), se non è già selezionato, fare clic su **Modifica ADSI**.

4.  Nel menu **azione** fare clic su **Connetti a**.

5.  Nella finestra di dialogo **impostazioni di connessione** in **selezionare un contesto di denominazione ben noto**Selezionare **schema**e quindi fare clic su **OK**.

6.  In contenitore schema cercare CN = ms-RTC-SIP-SchemaVersion. Se l'oggetto esiste e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **RangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se l'oggetto non esiste o se i valori degli attributi **rangeUpper** e **RangeLower** non sono specificati, lo schema non è stato modificato o non è stato replicato.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esecuzione della preparazione dello schema in Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

