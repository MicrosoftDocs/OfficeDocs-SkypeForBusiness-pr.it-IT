---
title: Scarica topologia dalla distribuzione esistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>Scarica topologia dalla distribuzione esistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-29_

Quando si crea un pool di Lync Server 2013, si utilizzerà l'Central Management Store associato a Lync Server 2010. Quando si avvia il generatore di topologia al primo utilizzo e alle successive sessioni di modifica, viene richiesto il percorso in cui si vuole che il generatore di topologia carichi il documento di configurazione corrente. Dato che la topologia di Lync Server 2010 è già stata definita e che è stata stabilita l'Central Management store, è consigliabile scegliere di scaricare una topologia da una distribuzione esistente. Generatore di topologia leggerà il database e recupererà la definizione corrente.

**Per scaricare una topologia da una distribuzione esistente**

1.  Aprire la **distribuzione guidata di Lync Server**.

2.  Nella pagina **Lync Server 2013-Deployment Wizard** fare clic su **installa strumenti di amministrazione**.

3.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013** e quindi fare clic su **Generatore di topologia di Lync Server**.

4.  Selezionare **Scarica topologia dalla distribuzione esistente**.
    
    ![Impostazioni del Generatore di topologie per la Distribuzione guidata](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Impostazioni del Generatore di topologie per la Distribuzione guidata")

5.  Scegliere un nome file e salvare la topologia con il tipo di file default. tbxml.

6.  Espandere il nodo Lync Server, come illustrato, per rivelare i vari ruoli del server nella distribuzione.
    
    ![Proprietà generali del ruolo server del Generatore di topologie](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Proprietà generali del ruolo server del Generatore di topologie")

</div>

<span> </span>

</div>

</div>

</div>

