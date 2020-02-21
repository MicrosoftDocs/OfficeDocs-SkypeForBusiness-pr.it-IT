---
title: 'Lync Server 2013: modificare il filtro di trasferimento file predefinito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a99847739b134c97172b26a6ebfbb2d808cdd3af
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Modificare il filtro di trasferimento file predefinito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Lync Server 2013 fornisce un filtro di trasferimento di file globale che consente di bloccare tipi specifici di file durante le attività correlate ai file seguenti all'interno della distribuzione di Lync Server 2013:

  - Richieste di trasferimento file durante conversazioni di messaggistica istantanea

  - Caricamenti e download di file tramite la caratteristica relativa agli stampati nel client Office Live Meeting 2007

  - Riproduzione multimediale durante le conferenze

A seconda dei tipi di file che si desidera bloccare o consentire, è possibile utilizzare il pannello di controllo di Lync Server per modificare il filtro globale. Per informazioni dettagliate sul filtro per il trasferimento di file, vedere [Configuring file transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Per modificare il filtro trasferimento file predefinito

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Messaggistica istantanea e presenza** e quindi su **Filtro file**.

4.  Nella pagina **Filtro file** fare doppio clic sul filtro **Globale**.

5.  In **Modifica filtro file** selezionare la casella di controllo **Abilita filtro file**.

6.  Nella casella di riepilogo a discesa **Trasferimento di file** fare clic su **Blocca tutto** o su **Blocca tipi di file specifici**.

7.  Se si è selezionato **Blocca tutto**, ignorare il passaggio 9.

8.  Se si è selezionato **Blocca tipi di file specifici**, eseguire le operazioni seguenti:
    
    1.  Fare clic su **Seleziona** per modificare l'elenco predefinito delle estensioni di file che si desidera bloccare.
    
    2.  In **Seleziona estensioni di file** selezionare i tipi di file che si desidera bloccare o consentire aggiungendone o rimuovendone le estensioni nelle categorie in **Estensioni di file**.
    
    3.  Se un'estensione di file che si desidera bloccare non è visualizzata, digitarla nella casella di testo in **Aggiungi estensioni di file all'elenco** e quindi fare clic su **Aggiungi**.
    
    4.  Fare clic su **OK**.

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Creare un nuovo filtro trasferimento file in Lync Server 2013 per un sito specifico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Modificare il filtro URL predefinito in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

