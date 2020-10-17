---
title: 'Lync Server 2013: ripristino dei dati di monitoraggio o archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e908792e8a2563094b11bcce73d4ac6ce6c7121
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511423"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Ripristino dei dati di monitoraggio o archiviazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-18_

Il ripristino dei dati di monitoraggio e archiviazione non è necessario per ottenere Lync Server attivo e in esecuzione dopo un errore. Tuttavia, se il monitoraggio e l'archiviazione dei dati sono fondamentali per l'organizzazione, sarà necessario ripristinare i dati dopo aver ricreato i database.

Nella procedura seguente viene descritto come utilizzare SQL Server Management Studio per ripristinare i dati di archiviazione o di monitoraggio.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Per ripristinare i dati di monitoraggio o archiviazione da un file di backup

1.  Accedere al server che si sta ripristinando come membro del gruppo Administrators nel computer locale o di un gruppo con diritti utente equivalenti.

2.  Aprire SQL Server Management Studio: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2012** o **Microsoft SQL Server 2008 R2**e quindi fare clic su **SQL Server Management Studio**.

3.  In **Connetti al server**, connettersi all'istanza di SQL Server specificando almeno il nome del server e le informazioni di autenticazione.

4.  In **Esplora oggetti**fare clic con il pulsante destro del mouse su **database**e quindi scegliere **Ripristina database**.

5.  In **Seleziona una pagina**, fare clic su **generale**e quindi in **database** selezionare il nome del database come indicato di seguito:
    
      - Per un database di archiviazione, selezionare **LcsLog**.
    
      - Per un database di registrazione dettagli chiamata, selezionare **LcsCDR**.
    
      - Per un database QoE (Quality of Experience), selezionare **QoEMetrics**.

6.  Fare clic su **da dispositivo**.

7.  In **selezionare i set di backup da ripristinare**, fare clic sul file di backup, quindi fare clic su **Ripristina**.

8.  In **Seleziona una pagina**fare clic su **Opzioni**, verificare che il percorso del file di dati e il percorso del registro siano presenti nella cartella corretta e quindi fare clic su **OK**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Per assicurarsi che gli elenchi di controllo di accesso (ACL, Access Control List) siano corretti

1.  Espandere **database**, espandere il database di archiviazione o di monitoraggio, espandere **sicurezza**e quindi espandere **utenti**.

2.  Verificare che il gruppo di dominio RTCComponentUniversalServices esista come utente.

3.  Se RTCComponentUniversalServices non esiste in **utenti**, eseguire le operazioni seguenti:
    
    1.  Fare clic con il pulsante destro del mouse su **Utenti** e quindi scegliere **Nuovo utente**.
    
    2.  In **nome account di accesso**Digitare il nome del gruppo mancante, RTCComponentUniversalServices.
    
    3.  In **appartenenza a ruoli del database**selezionare l'autorizzazione **ServerRole** e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Non è necessario riavviare il servizio di archiviazione o di monitoraggio.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

