---
title: 'Lync Server 2013: Installare il database del server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Installare il database del server Standard Edition per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Configurazione di un server Standard Edition come unico server nell'infrastruttura in cui gli utenti di case si differenziano da altre installazioni del server, in quanto esiste una selezione nella **distribuzione guidata** in modo specifico per la configurazione del server iniziale.

<div>

## <a name="to-install-a-standard-edition-server"></a>Per installare un server Standard Edition

1.  Accedere al server in cui si vuole installare il server Standard Edition come amministratore locale o come equivalente di dominio.

2.  Se non sono stati preparati servizi di dominio Active Directory, eseguire prima di tutto queste procedure. Per informazioni dettagliate, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Nella distribuzione guidata di Lync Server fare clic su **prepara primo server Standard Edition**.

4.  Nella pagina **prepara Single Standard Edition server** fare clic su **Avanti**.

5.  Nella pagina **esecuzione dei comandi** , SQL Server 2012 Express viene installato come Central Management store. Vengono create le regole firewall necessarie. Dopo aver completato l'installazione del database e del software prerequisito, fare clic su **fine**.
    
    <div>
    

    > [!NOTE]  
    > L'installazione iniziale può richiedere del tempo senza aggiornamenti visibili alla schermata di riepilogo dell'output del comando. Ciò è dovuto all'installazione di SQL Server Express. Se è necessario monitorare l'installazione del database, usare Gestione attività per monitorare la configurazione.

    
    </div>

6.  Nella pagina distribuzione guidata di Lync Server fare clic su **installa Generatore di topologie** se non sono stati installati in precedenza gli strumenti di amministrazione. Per informazioni dettagliate, vedere [installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Verificare che siano presenti segni di spunta verdi accanto a "prepara Active Directory", "prepara First Standard Edition Server" e "Install topologia Builder".

</div>

</div>

<span> </span>

</div>

</div>

</div>

