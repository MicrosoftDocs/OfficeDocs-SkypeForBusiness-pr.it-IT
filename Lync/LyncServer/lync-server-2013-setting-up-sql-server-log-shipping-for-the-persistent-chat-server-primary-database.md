---
title: 'Lync Server 2013: Configurazione del log shipping di SQL Server per il database primario del server chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de2285d77ba2228b90d244c841efc0b986bf454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Configurazione del log shipping di SQL Server in Lync Server 2013 per il database primario del server chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-12_

In SQL Server Management Studio connettersi all'istanza del database di log shipping secondario del server di chat persistente e verificare che SQL Server Agent sia in uso.

Con SQL Server Management Studio connesso all'istanza del database primario della chat persistente, eseguire la procedura seguente:

1.  Verificare che l'agente SQL Server sia in uso.

2.  Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.

3.  In **selezionare una pagina**fare clic su **distribuzione log transazioni**.

4.  Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .

5.  In **backup del log delle transazioni**fare clic su **impostazioni di backup**.

6.  Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.

7.  Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova nel server principale, digitare un percorso locale alla cartella (esempio: c:\\backup)** . Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella.

    
    </div>

8.  Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.

9.  Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio.

10. In **compressione**selezionare **Usa l'impostazione predefinita del server**e quindi fare clic su **OK**.

11. In **istanze server secondarie e database**fare clic su **Aggiungi**.

12. Fare clic su **Connetti** e Connetti all'istanza di SQL Server configurata come server secondario.

13. Nella casella **database secondario** selezionare il database **MGC** dall'elenco.

14. Nella scheda **Inizializza database secondario** scegliere l'opzione **Sì, generare un backup completo del database principale e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.

15. Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni. Questa cartella si trova spesso nel server secondario.

16. Nota la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio. Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.

17. Nella scheda **Ripristina** , in **stato del database durante il ripristino dei backup**, scegliere l'opzione **Nessuna modalità di recupero** .

18. In **delay Restoring backups almeno:** selezionare **0 minuti**.

19. Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.

20. Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**, regolare la pianificazione di SQL Server Agent come richiesto e fare clic su **OK**. Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.

21. Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.

</div>

<span> </span>

</div>

</div>

</div>

