---
title: 'Lync Server 2013: creare un nuovo filtro per il trasferimento di file per un sito specifico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ddb23081acba6eb208607a0bacddb7b403468b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Creare un nuovo filtro per il trasferimento di file in Lync Server 2013 per un sito specifico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Oltre a modificare il filtro di trasferimento file globale, è possibile configurare filtri di trasferimento file personalizzati per siti specifici all'interno della distribuzione di Lync Server 2013. Per informazioni dettagliate sul filtro per il trasferimento di file, vedere [configurazione del trasferimento di file e filtro URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Per creare un filtro per il trasferimento di file per un sito specifico

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **messaggistica istantanea e presenza** e quindi su **filtro file**.

4.  Nella pagina **filtro file** fare clic su **nuovo**.

5.  Nella finestra di dialogo **Seleziona sito** fare clic sul sito per il quale si vuole creare il filtro di trasferimento file e quindi fare clic su **OK**.

6.  In **nuovo filtro file**fare clic sulla casella di controllo **Attiva filtro file** .

7.  Nella casella di riepilogo a discesa **trasferimento file** fare clic su **blocca tutto** o **Blocca tipi di file specifici**.

8.  Se si è fatto clic su **blocca tutto**, passare al passaggio 10.

9.  Se si è fatto clic su **Blocca tipi di file specifici**, eseguire le operazioni seguenti:
    
    1.  Fare clic su **Seleziona** per modificare l'elenco predefinito delle estensioni del tipo di file che si vuole bloccare.
    
    2.  Nella finestra di dialogo **Seleziona tipo di file** selezionare i tipi di file che si desidera bloccare o consentire aggiungendo o rimuovendo le relative estensioni dalle categorie in **estensioni di tipo file**.
    
    3.  Se non si vede l'estensione per un tipo di file che si vuole bloccare, digitare l'estensione nella casella di testo in **Aggiungi estensioni di file all'elenco**e quindi fare clic su **Aggiungi**.
    
    4.  Fare clic su **OK**.

10. Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni ISTANTANEe](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modificare il filtro di trasferimento file predefinito in Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificare il filtro URL predefinito in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

