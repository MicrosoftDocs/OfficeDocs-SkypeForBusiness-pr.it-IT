---
title: 'Lync Server 2013: installare il database del server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0386caebab3b50854ae608d947b6cd674922c155
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Installare il database del server Standard Edition per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Configurazione di un server Standard Edition come unico server dell'infrastruttura che gli utenti di case differiscono da altre installazioni del server, in quanto è presente una selezione nella **distribuzione guidata** specificatamente per la configurazione del server iniziale.

<div>

## <a name="to-install-a-standard-edition-server"></a>Per installare un server Standard Edition

1.  Accedere al server in cui si intende installare il server Standard Edition come amministratore locale o come equivalente di dominio.

2.  Se non è stato preparato Servizi di dominio Active Directory, eseguire prima queste procedure. Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Nella distribuzione guidata di Lync Server, fare clic su **prepara primo server Standard Edition**.

4.  Nella pagina **Prepara singolo Server Standard** fare clic su **Avanti**.

5.  Nella pagina **esecuzione comandi** in corso viene installato SQL Server 2012 Express come archivio di gestione centrale. Vengono create le regole firewall necessarie. Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.
    
    <div>
    

    > [!NOTE]  
    > L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi. Ciò è dovuto all'installazione di SQL Server Express. Se si desidera monitorare l'installazione del database, usare Gestione attività.

    
    </div>

6.  Nella pagina distribuzione guidata di Lync Server, fare clic su **installa Generatore di topologie** se non sono stati precedentemente installati gli strumenti di amministrazione. Per informazioni dettagliate, vedere [Install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Verificare che accanto a "Prepara Active Directory", "Prepara primo Server Standard" e "Installa Generatore di topologie" siano visualizzati segni di spunta di colore verde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

