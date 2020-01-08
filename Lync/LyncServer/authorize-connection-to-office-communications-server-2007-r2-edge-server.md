---
title: Autorizzare la connessione a Office Communications Server 2007 R2 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc5d92b45f65c864da046951ce7ebd42155ed2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40978610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorizzare la connessione a Office Communications Server 2007 R2 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Per ogni server front end server o standard di Lync Server 2013 nel pool pilota è necessario aggiornare l'elenco dei server interni autorizzati a connettersi a Office Communications Server 2007 R2 Edge Server. Senza questi aggiornamenti, le conferenze audio/visive (A/V) esterne per gli utenti che partecipano tramite il server perimetrale legacy non funzioneranno.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Per autorizzare la connessione a Office Communications Server 2007 R2 Edge Server

1.  Da Office Communications Server 2007 R2 Edge Server, dal gruppo **strumenti di amministrazione** , aprire lo snap-in **Gestione computer** .

2.  Nell'albero della console espandere **Servizi e applicazioni**.

3.  Fare clic con il pulsante destro del mouse su **Office Communications Server 2007 R2**e quindi scegliere **Proprietà**.

4.  Fare clic sulla scheda **interno** .

5.  In **Aggiungi server**fare clic su **Aggiungi**.

6.  Nella finestra di dialogo **Aggiungi Office Communications Server** immettere le informazioni appropriate:
    
      - Specificare il nome di dominio completo (FQDN) di ogni server di Lync Server 2013 front-end o Standard Edition e Lync Server 2013 pool.
    
      - Specificare il nome di dominio completo di Lync Server 2013 Director se è stata configurata una route statica nel pool che specifica il computer hop successivo per il nome di dominio completo.

7.  Dopo aver aggiunto una voce per ogni Lync Server 2013, Front End Server, Standard Edition Server, pool e Director, fare clic su **applica** e quindi su **OK** per chiudere la pagina delle proprietà.

</div>

</div>

<span> </span>

</div>

</div>

</div>

