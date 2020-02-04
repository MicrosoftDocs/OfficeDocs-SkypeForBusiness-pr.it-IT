---
title: "Lync Server 2013: pubblicazione della topologia aggiornata per l'aggiunta di database di archiviazione"
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
ms.openlocfilehash: d0d12b1b4195e57fc289d11eb54f24903d05ea26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Pubblicazione della topologia aggiornata per l'aggiunta di database di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Dopo l'aggiornamento della topologia in Generatore di topologie, è necessario pubblicare la topologia in Central Management Store prima di poter configurare e usare l'archiviazione. Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia per garantire la sincronizzazione di tutti i server con la topologia e altre modifiche alla configurazione.

<div>

## <a name="to-publish-your-updated-topology"></a>Per pubblicare la topologia aggiornata

1.  In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere con un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
    <div>
    

    > [!NOTE]  
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario usare un account che sia un membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga delle autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione di file in uso per l'archivio di file di Lync Server 2013, in modo che il generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto (DACL). o un account con diritti equivalenti.

    
    </div>

2.  Aprire la topologia creata nella sezione precedente usando generatore di topologie.

3.  Nell'albero della console fare clic con il pulsante destro del mouse su **Lync Server 2013**e quindi scegliere **Pubblica topologia**.

4.  Nella pagina **pubblica la topologia** fare clic su **Avanti**.

5.  Nella pagina **Crea database** verificare che il database sia selezionato e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se non si dispone delle autorizzazioni appropriate per la creazione di database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database. Per informazioni dettagliate sulle autorizzazioni e i diritti di amministratore necessari, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorizzazioni di distribuzione per SQL Server in Lync server 2013</A> nella documentazione relativa alla distribuzione.<BR>Solo i database su server SQL dedicati possono essere installati tramite Generatore di topologie. I database di SQL Server che sono collocati con altri componenti server devono essere installati eseguendo la configurazione locale nel computer in uso.

    
    </div>

6.  Nella pagina **completamento pubblicazione guidata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione prima che sia possibile archiviare qualsiasi contenuto. Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-support-for-archiving.md">configurazione del supporto per l'archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

