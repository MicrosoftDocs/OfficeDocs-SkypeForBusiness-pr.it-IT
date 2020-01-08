---
title: 'Lync Server 2013: modificare il filtro di trasferimento file predefinito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Modificare il filtro di trasferimento file predefinito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Lync Server 2013 offre un filtro di trasferimento di file globale che blocca i tipi specifici di file durante le attività correlate ai file seguenti nella distribuzione di Lync Server 2013:

  - Richieste di trasferimento di file durante le conversazioni di messaggistica istantanea

  - Caricamento e download di file durante l'uso della funzionalità stampati nel client Office Live Meeting 2007

  - Riproduzione multimediale durante le conferenze

A seconda dei tipi di file che si desidera bloccare o consentire, è possibile usare il pannello di controllo di Lync Server per modificare il filtro globale. Per informazioni dettagliate sul filtro per il trasferimento di file, vedere [configurazione del trasferimento di file e filtro URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Per modificare il filtro di trasferimento file predefinito

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **messaggistica istantanea e presenza** e quindi su **filtro file**.

4.  Nella pagina **filtro file** fare doppio clic sul filtro **globale** .

5.  In **Modifica filtro file**selezionare la casella di controllo **Attiva filtro file** .

6.  Nella casella di riepilogo a discesa **trasferimento file** fare clic su **blocca tutto** o **Blocca tipi di file specifici**.

7.  Se si è fatto clic su **blocca tutto**, passare al passaggio 9.

8.  Se si è fatto clic su **Blocca tipi di file specifici**, eseguire le operazioni seguenti:
    
    1.  Fare clic su **Seleziona** per modificare l'elenco predefinito delle estensioni del tipo di file che si vuole bloccare.
    
    2.  In **Seleziona tipo di file**selezionare i tipi di file che si desidera bloccare o consentire aggiungendo o rimuovendo le relative estensioni dalle categorie in **estensioni di tipi di file**.
    
    3.  Se non si vede l'estensione per un tipo di file che si vuole bloccare, digitare l'estensione nella casella di testo in **Aggiungi estensioni di file all'elenco**e quindi fare clic su **Aggiungi**.
    
    4.  Fare clic su **OK**.

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Creare un nuovo filtro per il trasferimento di file in Lync Server 2013 per un sito specifico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni ISTANTANEe](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Modificare il filtro URL predefinito in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

