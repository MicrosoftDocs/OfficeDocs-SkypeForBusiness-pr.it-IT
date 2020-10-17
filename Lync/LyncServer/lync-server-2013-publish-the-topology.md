---
title: 'Lync Server 2013: pubblicare la topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e94e47536c8af6ef8fd3c22dba245b03c961c575
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512363"
---
# <a name="publish-the-topology-in-lync-server-2013"></a>Pubblicare la topologia in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-01_

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario essere connessi come utenti membri dei gruppi RTCUniversalServerAdmins e Domain Admins. È inoltre possibile delegare le autorizzazioni e i diritti di amministratore appropriati. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Per poter apportare altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

Dopo aver definito la topologia in Generatore di topologie, è necessario pubblicare la topologia nell'archivio di gestione centrale. Nell'archivio di gestione centrale è disponibile un'archiviazione schematizzato e robusta dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync Server 2013. Consente inoltre di convalidare i dati per garantire la coerenza della configurazione. Tutte le modifiche apportate ai dati di configurazione si verificano nell'archivio di gestione centrale, eliminando i problemi di "fuori sincrono". Le copie di sola lettura dei dati sono replicate in tutti i server della topologia, inclusi i server perimetrali.

<div>


> [!NOTE]  
> SQL Server richiede almeno 20 GB di spazio libero su disco per pubblicare correttamente la topologia iniziale e creare il server di gestione centrale.



</div>

<div>


> [!NOTE]  
> Solo per Enterprise Edition: per pubblicare la topologia, il server back-end basato su SQL Server deve essere online e accessibile con le eccezioni del firewall configurate. Per informazioni dettagliate su come specificare le eccezioni del firewall, vedere <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync server 2013</A>. Per informazioni dettagliate sulla configurazione di SQL Server, vedere <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Per pubblicare una topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Scegliere di aprire la topologia da un file locale. Se si utilizza il computer in cui è stata definita la topologia, il file si troverà nel percorso in cui è stato precedentemente salvato, generalmente nella cartella Documenti dell'utente che ha configurato la topologia.

3.  Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Pubblica topologia**.

4.  Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.

5.  Nella pagina **Creare database** selezionare i database che si desidera pubblicare.
    
    <div>
    

    > [!NOTE]  
    > Se non si dispone dei diritti appropriati per creare i database, è possibile deselezionare le caselle di controllo accanto a tali database e un utente con i diritti appropriati potrà successivamente crearli. Per informazioni dettagliate, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.

    
    </div>

6.  Facoltativamente, fare clic su **Avanzate**. Le opzioni avanzate di posizionamento dei file di dati di SQL Server consentono di scegliere tra le opzioni seguenti:
    
      - **Determina automaticamente il percorso dei file di database** - Questa opzione determinerà le prestazioni operative migliori in base alla configurazione del disco nel server basato su SQL Server distribuendo i file di registro e di dati nel percorso migliore.
    
      - **Utilizza i valori predefiniti dell'istanza di SQL Server** - Questa opzione posiziona i file di registro e di dati nel server basato su SQL Server utilizzando le impostazioni dell'istanza. Non utilizza la funzionalità operativa del server basato su SQL Server di determinazione dei percorsi ottimali per i registri e i dati. L'amministratore di SQL Server in genere sposta i file di registro e di dati nei percorsi appropriati per le procedure di gestione del server basato su SQL Server e dell'organizzazione.
    
    Fare clic su **OK** e quindi su **Avanti**.

7.  Nella pagina **Selezione server di gestione centrale** selezionare un pool Front end.

8.  Facoltativamente, fare clic su **Avanzate**. Le opzioni avanzate di posizionamento dei file di dati di SQL Server consentono di scegliere tra le opzioni seguenti:
    
      - **Determina automaticamente il percorso dei file di database** - Questa opzione determinerà le prestazioni operative migliori in base alla configurazione del disco nel server basato su SQL Server distribuendo i file di registro e di dati nel percorso migliore.
    
      - **Utilizza i valori predefiniti dell'istanza di SQL Server** - Questa opzione posiziona i file di registro e di dati nel server basato su SQL Server utilizzando le impostazioni dell'istanza. Non utilizza la funzionalità operativa del server basato su SQL Server di determinazione dei percorsi ottimali per i registri e i dati. L'amministratore di SQL Server in genere sposta i file di registro e di dati nei percorsi appropriati per le procedure di gestione del server basato su SQL Server e dell'organizzazione.
    
    Fare clic su **OK**.

9.  Fare clic su **Avanti** per completare il processo di pubblicazione.

10. Al termine del processo di pubblicazione, fare clic su **Fine**.
    
    Quando la topologia è stata pubblicata correttamente, è possibile iniziare a installare una replica locale dell'archivio di gestione centrale in ogni server che esegue Lync Server 2013 nella topologia. Si consiglia di iniziare con il primo pool Front end.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di front end server e pool Front end per Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

