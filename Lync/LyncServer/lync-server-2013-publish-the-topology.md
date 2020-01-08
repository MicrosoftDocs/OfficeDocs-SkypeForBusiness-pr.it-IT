---
title: 'Lync Server 2013: Pubblicare la topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>Pubblicare la topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-01_

Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario avere effettuato l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È anche possibile delegare i diritti e le autorizzazioni di amministratore appropriati. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

Dopo aver definito la topologia in Generatore di topologie, è necessario pubblicare la topologia in Central Management store. Central Management store offre uno spazio di archiviazione schematizzato robusto dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di 2013 di Lync Server. Consente inoltre di convalidare i dati per garantire la coerenza della configurazione. Tutte le modifiche apportate ai dati di configurazione si verificano presso l'Central Management store, eliminando i problemi di "fuori sincrono". Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia, inclusi i server perimetrali.

<div>


> [!NOTE]  
> SQL Server richiede un minimo di 20 GB di spazio libero su disco per pubblicare correttamente la topologia iniziale e creare il server di gestione centrale.



</div>

<div>


> [!NOTE]  
> Solo per la versione Enterprise Edition: per pubblicare la topologia, il server back-end basato su SQL Server deve essere online e accessibile con le eccezioni del firewall in posizione. Per informazioni dettagliate su come specificare le eccezioni del firewall, vedere <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">informazioni sui requisiti del firewall per SQL Server con Lync server 2013</A>. Per informazioni dettagliate sulla configurazione di SQL Server, vedere <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurare SQL Server per Lync server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Per pubblicare una topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Selezionare per aprire la topologia da un file locale. Se ci si trova nel computer in cui è stata definita la topologia, si trova nella posizione in cui è stato salvato nei passaggi precedenti. In genere, questa sarà la cartella documenti dell'utente che ha configurato la topologia.

3.  Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Pubblica topologia**.

4.  Nella pagina **pubblica la topologia** fare clic su **Avanti**.

5.  Nella pagina **Crea database** selezionare i database che si desidera pubblicare.
    
    <div>
    

    > [!NOTE]  
    > Se non si hanno i diritti appropriati per creare i database, è possibile deselezionare le caselle di controllo accanto a tali database e un utente con diritti appropriati può creare i database in un secondo momento. Per informazioni dettagliate, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorizzazioni di distribuzione per SQL Server in Lync server 2013</A>.

    
    </div>

6.  Facoltativamente, fare clic su **Avanzate**. Le opzioni avanzate di posizionamento dei file di dati di SQL Server consentono di selezionare tra le opzioni seguenti:
    
      - **Determinare automaticamente il percorso del file di database** : questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo il log e i file di dati nella posizione migliore.
    
      - **Usare le impostazioni predefinite dell'istanza di SQL Server** : questa opzione consente di inserire file di log e di dati nel server basato su SQL Server usando le opzioni di istanza. Questa opzione non usa la funzionalità operativa del server basato su SQL Server per determinare le posizioni ottimali per i registri e i dati. L'amministratore di SQL Server sposterebbe in genere il log e i file di dati in posizioni appropriate per le procedure di gestione dell'organizzazione e del server basato su SQL Server.
    
    Fare clic su **OK**e quindi su **Avanti**.

7.  Nella pagina **Seleziona server di gestione centrale** selezionare un pool di front-end.

8.  Facoltativamente, fare clic su **Avanzate**. Le opzioni avanzate di posizionamento dei file di dati di SQL Server consentono di selezionare tra le opzioni seguenti:
    
      - **Determinare automaticamente il percorso del file di database** : questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo il log e i file di dati nella posizione migliore.
    
      - **Usare le impostazioni predefinite dell'istanza di SQL Server** : questa opzione consente di inserire file di log e di dati nel server basato su SQL Server usando le opzioni di istanza. Questa opzione non usa la funzionalità operativa del server basato su SQL Server per determinare le posizioni ottimali per i registri e i dati. L'amministratore di SQL Server sposterebbe in genere il log e i file di dati in posizioni appropriate per le procedure di gestione dell'organizzazione e del server basato su SQL Server.
    
    Fare clic su **OK**.

9.  Fare clic su **Avanti** per completare il processo di pubblicazione.

10. Al termine del processo di pubblicazione, fare clic su **fine**.
    
    Quando la topologia è stata pubblicata correttamente, è possibile iniziare a installare una replica locale di Central Management store in ogni server che esegue Lync Server 2013 nella topologia. È consigliabile iniziare con il primo pool Front-end.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di Front End Server e pool Front End per Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

