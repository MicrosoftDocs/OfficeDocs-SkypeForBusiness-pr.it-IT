---
title: "Lync Server 2013: ripristinare il monitoraggio o l'archiviazione dei dati"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803cb6050d4230653a13f1e3e66c2a092911c509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-18_

Non è necessario ripristinare i dati di monitoraggio e archiviazione per ottenere l'accesso e l'uso di Lync Server dopo un errore. Tuttavia, se il monitoraggio e l'archiviazione dei dati è fondamentale per l'organizzazione, sarà necessario ripristinare i dati dopo la ricreazione dei database.

La procedura seguente descrive come usare SQL Server Management Studio per ripristinare i dati di archiviazione o monitoraggio.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Per ripristinare il monitoraggio o l'archiviazione dei dati da un file di backup

1.  Accedere al server che si sta ripristinando come membro del gruppo Administrators nel computer locale o in un gruppo con diritti utente equivalenti.

2.  Aprire SQL Server Management Studio: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2012** o **Microsoft SQL Server 2008 R2**e quindi fare clic su **SQL Server Management Studio**.

3.  In **Connetti al server**connettersi all'istanza di SQL Server specificando almeno il nome del server e le informazioni di autenticazione.

4.  In **Esplora oggetti**fare clic con il pulsante destro del mouse su **database**e quindi scegliere **Ripristina database**.

5.  In **Seleziona una pagina**fare clic su **generale**e quindi in **database** selezionare il nome del database nel modo seguente:
    
      - Per un database di archiviazione, selezionare **LcsLog**.
    
      - Per un database di registrazione dei dettagli delle chiamate (CDR) selezionare **LcsCDR**.
    
      - Per un database di qualità dell'esperienza (QoE), selezionare **QoEMetrics**.

6.  Fare clic su **da dispositivo**.

7.  In **selezionare i set di backup da ripristinare**, fare clic sul file di backup e quindi su **Ripristina**.

8.  In **Seleziona una pagina**fare clic su **Opzioni**, verificare che il percorso del file di dati e il percorso del log si trovino nella cartella corretta e quindi fare clic su **OK**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Per verificare che gli elenchi di controllo di accesso (ACL) siano corretti

1.  Espandere **database**, espandere il database di archiviazione o monitoraggio, espandere **sicurezza**e quindi espandere **utenti**.

2.  Verificare che il gruppo di domini RTCComponentUniversalServices esista come utente.

3.  Se RTCComponentUniversalServices non è presente in **utenti**, eseguire le operazioni seguenti:
    
    1.  Fare clic con il pulsante destro del mouse su **utenti**e quindi scegliere **nuovo utente**.
    
    2.  In **nome account di accesso**Digitare il nome del gruppo mancante, RTCComponentUniversalServices.
    
    3.  In **appartenenza a ruoli del database**selezionare l'autorizzazione **ServerRole** e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Non è necessario riavviare il servizio archiviazione o monitoraggio.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

