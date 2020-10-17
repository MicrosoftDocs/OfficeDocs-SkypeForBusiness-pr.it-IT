---
title: 'Lync Server 2013: creare un nuovo filtro per il trasferimento di file per un sito specifico'
description: 'Lync Server 2013: creare un nuovo filtro per il trasferimento di file per un sito specifico.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b5003711c2f2e74b726809fba5da6d9fd0aa57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554702"
---
# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Creare un nuovo filtro trasferimento file in Lync Server 2013 per un sito specifico

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Oltre alla modifica del filtro trasferimento file globale, è possibile configurare filtri di trasferimento file personalizzati per siti specifici all'interno della distribuzione di Lync Server 2013. Per informazioni dettagliate sul filtro per il trasferimento di file, vedere [Configuring file transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Per creare un filtro di trasferimento di file per un sito specifico

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Messaggistica istantanea e presenza** e quindi su **Filtro file**.

4.  Nella pagina **Filtro file** fare clic su **Nuovo**.

5.  Nella finestra di dialogo **Seleziona un sito** fare clic sul sito per il quale si desidera creare il filtro di trasferimento file e quindi fare clic su **OK**.

6.  In **Crea nuovo filtro file** fare clic sulla casella di controllo **Abilita filtro file**.

7.  Nella casella di riepilogo a discesa **Trasferimento di file** fare clic su **Blocca tutto** o su **Blocca tipi di file specifici**.

8.  Se si è fatto clic su **Blocca tutto**, andare al passaggio 10.

9.  Se si è fatto clic su **Blocca tipi di file specifici**, eseguire le operazioni seguenti:
    
    1.  Fare clic su **Seleziona** per modificare l'elenco predefinito di estensioni di file da bloccare.
    
    2.  Nella finestra di dialogo **Seleziona estensioni di file** selezionare i tipi di file da bloccare o consentire aggiungendone o rimuovendone le estensioni dalle categorie in **Estensioni di file**.
    
    3.  Se l'estensione di un tipo di file da bloccare non viene visualizzata, digitarla nella casella di testo in **Aggiungi estensioni di file all'elenco** e quindi fare clic su **Aggiungi**.
    
    4.  Fare clic su **OK**.

10. Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modificare il filtro di trasferimento file predefinito in Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificare il filtro URL predefinito in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

