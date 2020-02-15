---
title: Autorizzare la connessione al server perimetrale di Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64786c29027c99de2f3b5e01846a5283ec57a084
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorizzare la connessione al server perimetrale di Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Per ogni server Lync Server 2013 front end server o Standard Edition nel pool pilota, è necessario aggiornare l'elenco dei server interni autorizzati per la connessione al server perimetrale di Office Communications Server 2007 R2. In caso contrario, la conferenza audio/visiva (A/V) con accesso esterno per utenti che partecipano utilizzando il server perimetrale legacy non funzionerà.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Per autorizzare la connessione al server perimetrale di Office Communications Server 2007 R2

1.  Dal server perimetrale di Office Communications Server 2007 R2, dal gruppo **strumenti di amministrazione** , aprire lo snap-in **Gestione computer** .

2.  Nell'albero della console espandere **Servizi e applicazioni**.

3.  Fare clic con il pulsante destro del mouse su **Office Communications Server 2007 R2** e quindi scegliere **Proprietà**.

4.  Fare clic sulla scheda **Interno**.

5.  In **Aggiungi server** fare clic su **Aggiungi**.

6.  Nella finestra di dialogo **Aggiungi Office Communications Server** immettere le informazioni appropriate:
    
      - Specificare il nome di dominio completo (FQDN) di ogni server Lync Server 2013 front end server o Standard Edition e il pool Lync Server 2013.
    
      - Specificare il nome di dominio completo di Lync Server 2013 Director se è stata configurata una route statica nel pool che specifica il computer dell'hop successivo in base al nome di dominio completo.

7.  Dopo aver aggiunto una voce per ogni Lync Server 2013, Front End Server, server Standard Edition, pool e Director, fare clic su **applica** e quindi fare clic su **OK** per chiudere la pagina delle proprietà.

</div>

</div>

<span> </span>

</div>

</div>

</div>

