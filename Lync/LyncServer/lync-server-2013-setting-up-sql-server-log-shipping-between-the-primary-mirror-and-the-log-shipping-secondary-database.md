---
title: 'Lync Server 2013: Configurazione del log shipping di SQL Server tra il mirror primario e il database secondario di log shipping'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>Configurazione del log shipping di SQL Server tra il mirror primario e il database secondario di log shipping in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Eseguire la procedura seguente per continuare il log shipping se il database principale della chat persistente non viene superato nel database mirror.

1.  Eseguire manualmente il failover del database principale della chat persistente in mirror. Questa operazione viene eseguita tramite Lync Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** . Per informazioni dettagliate, vedere "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione di mirroring SQL per l'elevata disponibilità del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  In SQL Server Management Studio connettersi all'istanza del mirror del server di chat persistente principale.

3.  Verificare che l'agente SQL Server sia in uso.

4.  Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.

5.  In **selezionare una pagina**fare clic su **distribuzione log transazioni**.

6.  Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .

7.  In **backup del log delle transazioni**fare clic su **impostazioni di backup**.

8.  Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.

9.  Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella finestra di dialogo **se la cartella di backup si trova nel server principale, digitare un percorso locale nella casella della cartella** . Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella.

    
    </div>

10. Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.

11. Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent, se necessario.
    
    <div>
    

    > [!IMPORTANT]  
    > Usa le stesse impostazioni usate per il database primario.

    
    </div>

12. In **compressione**selezionare **Usa l'impostazione predefinita del server**e fare clic su **OK**.

13. In **istanze server secondarie e database**fare clic su **Aggiungi**.

14. Fare clic su **Connetti**e connettersi all'istanza di SQL Server configurata come server secondario.

15. Nella casella **database secondario** selezionare il database **MGC** dall'elenco.

16. Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato**.

17. Nella scheda **copia file** , nella **cartella di destinazione per i file copiati**, digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni e fare clic su **OK**. Questa cartella si trova spesso nel server secondario.

18. Aprire l'elenco a discesa **configurazione script** e selezionare **configurazione script nella finestra nuova query**.

19. Nella finestra nuova query, in **Proprietà database**, fare clic su **OK** per avviare il processo di configurazione.

20. Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga:-- \* \* \* \* \* \* end: script da eseguire \* \* \* \* \* \*in primo piano:.
    
    <div>
    

    > [!IMPORTANT]  
    > L'esecuzione manuale di questo script è necessaria perché in SQL Server Management Studio non è supportato più database primari in una configurazione di log shipping di SQL Server.

    
    </div>

21. Selezionare **Annulla** per chiudere il pannello di configurazione del file di log shipping e stabilire una configurazione di lavoro che implementi correttamente la spedizione del file di log sia per il database primario che per il mirroring (in caso di failover).

22. Non eseguire manualmente il backup del database principale della chat persistente. Questa operazione viene eseguita tramite Lync Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** . Per informazioni dettagliate, vedere "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione di mirroring SQL per l'elevata disponibilità del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

