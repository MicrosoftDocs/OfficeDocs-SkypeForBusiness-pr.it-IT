---
title: Creare un nuovo filtro URL per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea
description: Creare un nuovo filtro URL per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e583b3e8cbd04279ab7f54b4138a349fa0d1e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554662"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-26_

Oltre a modificare il filtro URL globale, è possibile configurare filtri URL personalizzati per singoli siti all'interno della distribuzione di Lync Server 2013. Per informazioni dettagliate sul filtro degli URL, vedere [Configuring file transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Per creare un nuovo filtro URL

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **messaggistica istantanea e presenza**e quindi su **filtro URL**.

4.  Nella pagina **filtro URL** fare clic su **nuovo**.

5.  In **Seleziona un sito**fare clic sul sito per il quale si desidera creare il filtro URL e quindi fare clic su **OK**.

6.  Nella finestra di dialogo **nuovo filtro URL** selezionare la casella di controllo **Abilita filtro URL** per abilitare il filtro URL per il sito.

7.  Per bloccare qualsiasi URL attivo contenente un file con un'estensione elencata in **estensioni di file da bloccare** in **Modifica filtro file**, selezionare la casella di controllo **Blocca URL con estensione di file** .

8.  Nella casella di riepilogo a discesa **prefisso collegamento ipertestuale** fare clic sull'opzione corrispondente al modo in cui si desidera gestire gli URL nelle conversazioni istantanee dei messaggi.
    
    La casella **Consenti messaggio** consente di inviare all'utente un messaggio di avviso per l'invio di collegamenti ipertestuali autorizzati a essere inviati.

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Creare un nuovo filtro trasferimento file in Lync Server 2013 per un sito specifico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modificare il filtro di trasferimento file predefinito in Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificare il filtro URL predefinito in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

