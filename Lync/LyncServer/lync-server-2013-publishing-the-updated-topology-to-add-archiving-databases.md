---
title: 'Lync Server 2013: pubblicazione della topologia aggiornata per aggiungere database di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543ee664aeb8f2d8688fd35f7591726c9c0c7392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Pubblicazione della topologia aggiornata per l'aggiunta dei database di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Dopo aver aggiornato la topologia in Generatore di topologie, è necessario pubblicare la topologia nell'archivio di gestione centrale prima di poter configurare e utilizzare l'archiviazione. In tutti i server della topologia vengono replicate copie di sola lettura dei dati in modo che siano sincronizzati con la topologia e altre modifiche della configurazione.

<div>

## <a name="to-publish-your-updated-topology"></a>Per pubblicare una topologia aggiornata

1.  In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
    <div>
    

    > [!NOTE]  
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario utilizzare un account che sia membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga di autorizzazioni di controllo completo (ovvero lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Lync Server 2013 (ovvero, in modo che generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale necessario (DACL) o un account con diritti equivalenti.

    
    </div>

2.  Aprire la topologia creata nella sezione precedente utilizzando Generatore di topologie.

3.  Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **Pubblica topologia**.

4.  Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.

5.  Nella pagina **Crea altri database** verificare che il database sia selezionato e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se non si dispone delle autorizzazioni appropriate per la creazione di database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database. Per informazioni dettagliate sulle autorizzazioni e i diritti di amministratore necessari, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A> nella documentazione relativa alla distribuzione.<BR>Solo i database su server SQL Server dedicati possono essere installati tramite Generatore di topologie. I database nei server SQL Server collocati con altri componenti server devono essere installati eseguendo l'installazione locale in tale computer.

    
    </div>

6.  Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione, prima che sia possibile archiviare qualsiasi contenuto. Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for archiving in Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

