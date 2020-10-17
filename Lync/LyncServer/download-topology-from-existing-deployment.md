---
title: Scarica topologia dalla distribuzione esistente
description: Scaricare la topologia dalla distribuzione esistente.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22d746f8faf3fdf14a44e751eeb3c88bf3eef4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551182"
---
# <a name="download-topology-from-existing-deployment"></a>Scarica topologia dalla distribuzione esistente

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-29_

Quando si crea un pool di Lync Server 2013, si utilizzerà l'archivio di gestione centrale associato a Lync Server 2010. All'avvio di Generatore di topologie per il primo utilizzo e le sessioni di modifica successive viene richiesto di specificare la posizione in cui deve essere caricato il documento della configurazione corrente. Poiché la topologia di Lync Server 2010 è già stata definita e è stata stabilita l'archivio di gestione centrale, è necessario scegliere di scaricare una topologia da una distribuzione esistente. Generatore di topologie leggerà il database e recupererà la definizione corrente.

**Per scaricare una topologia da una distribuzione esistente**

1.  Aprire la **Distribuzione guidata di Lync Server**.

2.  Nella pagina **Lync Server 2013 – Distribuzione guidata** fare clic su **Installa Strumenti di amministrazione**.

3.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie di Lync Server**.

4.  Selezionare **Scarica topologia dalla distribuzione esistente**.
    
    ![Impostazioni del generatore di topologie della distribuzione guidata](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Impostazioni del generatore di topologie della distribuzione guidata")

5.  Scegliere un nome di file e salvare la topologia con il tipo di file predefinito con estensione tbxml.

6.  Espandere il nodo Lync Server, come illustrato, per visualizzare i vari ruoli server nella distribuzione.
    
    ![Proprietà generali del ruolo del server generatore di topologie](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Proprietà generali del ruolo del server generatore di topologie")

</div>

<span> </span>

</div>

</div>

</div>

