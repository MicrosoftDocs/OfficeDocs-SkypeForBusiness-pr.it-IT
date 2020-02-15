---
title: 'Lync Server 2013: configurazione del log shipping di SQL Server per il database primario del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4da247e50975ecbed5e64a6e4bebc31d531218b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Configurazione del log shipping di SQL Server in Lync Server 2013 per il database primario del server Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-12_

Se si utilizza SQL Server Management Studio, connettersi all'istanza del database secondario di log shipping del server di chat persistente e verificare che SQL Server Agent sia in esecuzione.

Se si utilizza SQL Server Management Studio connesso all'istanza del database primario di Persistent Chat, eseguire le operazioni seguenti:

1.  Verificare che SQL Server Agent sia in esecuzione.

2.  Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.

3.  In **Seleziona una pagina**fare clic su **log shipping delle transazioni**.

4.  Selezionare la casella **di controllo Abilita come database primario in una configurazione per il log shipping** .

5.  In **backup dei log delle transazioni**fare clic su **impostazioni di backup**.

6.  Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.

7.  Se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova sul server primario, digitare un percorso locale per la cartella (ad esempio: c\\: backup)** . Se la cartella di backup non è presente nel server primario, è possibile lasciare vuota questa casella.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'account di servizio di SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.

    
    </div>

8.  Configurare i **file di eliminazione precedenti e di** **avviso se nessun backup viene eseguito all'interno** dei parametri.

9.  Esaminare la pianificazione di backup elencata nella casella **pianificazione** in **processo di backup**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e modificare la pianificazione di SQL Server Agent in base alle esigenze.

10. In **compressione**selezionare **utilizza l'impostazione predefinita del server**e quindi fare clic su **OK**.

11. In **istanze e database secondari del server**, fare clic su **Aggiungi**.

12. Fare clic su **Connetti** e connettersi all'istanza di SQL Server configurata come server secondario.

13. Nella casella **database secondario** selezionare il database di **MGC** dall'elenco.

14. Nella scheda **Inizializza database secondario** selezionare l'opzione **Sì, generare un backup completo del database primario e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.

15. Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni. Questa cartella si trova spesso nel server secondario.

16. Tenere presente la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e modificare la pianificazione di SQL Server Agent in base alle esigenze. Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.

17. Nella scheda **Ripristina** , in **stato di database durante il ripristino dei backup**, scegliere l'opzione **modalità No Recovery** .

18. In **delay Restoring backups almeno:**, selezionare **0 minuti**.

19. Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.

20. Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**. Per personalizzare la pianificazione dell'installazione, fare clic su **pianificazione**, modificare la pianificazione di SQL Server Agent in base alle esigenze e quindi fare clic su **OK**. Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.

21. Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.

</div>

<span> </span>

</div>

</div>

</div>

