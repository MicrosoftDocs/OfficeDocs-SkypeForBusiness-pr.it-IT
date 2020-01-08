---
title: 'Lync Server 2013: ripristino di un server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 101cf0cb2fc4073e2b79aa008187465f84d2d439
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Ripristino di un server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Se un server Standard Edition che non ospita il Central Management store non riesce, seguire le procedure descritte in questa sezione. Se l'archivio di gestione centrale non riesce, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino. Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>Per ripristinare un server Standard Edition

1.  Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del computer non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.

    
    </div>

2.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.

3.  Ripristinare l'archivio file copiando l'archivio di file appropriato da $Backup nella posizione dell'archivio di file nel server e condividere la cartella.
    
    <div>
    

    > [!IMPORTANT]  
    > Il percorso e il nome file dell'archivio file ripristinato devono essere esattamente gli stessi dell'archivio di file di cui è stato eseguito il backup in modo che i componenti che usano i file possano accedervi.

    
    </div>

4.  Eseguire Generatore di topologie:
    
    1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.
    
    2.  Fare clic su **Scarica topologia dalla distribuzione esistente**e quindi fare clic su **OK**.
    
    3.  Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.

5.  Passare alla cartella di installazione o al supporto di Lync Server, quindi avviare la distribuzione guidata di Lync Server \\in\\Setup\\amd64 Setup. exe. Usare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:
    
    1.  Eseguire il **passaggio 1: installare l'archivio configurazione locale** per installare i file di configurazione locali.
    
    2.  Eseguire il **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare i ruoli di Lync Server Server.
    
    3.  Eseguire il **passaggio 3: richiedere, installare o assegnare certificati** per assegnare i certificati.
    
    4.  Eseguire il **passaggio 4: avviare i servizi** per avviare i servizi nel server.
    
    Per informazioni dettagliate sull'eseguire la distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.

6.  Ripristinare i dati degli utenti eseguendo le operazioni seguenti:
    
    1.  Copiare ExportedUserData. zip da $Backup\\ a una directory locale.
    
    2.  Prima di ripristinare i dati utente, è necessario arrestare i servizi Lync. A tale scopo, digitare:
        
            Stop-CsWindowsService
    
    3.  Per ripristinare i dati utente, nella riga di comando digitare:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Ad esempio:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Riavviare i servizi Lync digitando:
        
            Start-CsWindowsService

7.  Se il gruppo di risposte è stato distribuito in questo server Standard Edition, ripristinare i dati di configurazione di Response Group. Per informazioni dettagliate, vedere [ripristino delle impostazioni dei gruppi di risposte in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Se è stata distribuita la chat persistente in questo server Standard Edition, ripristinare il database della chat persistente (MGC. MDF).
    
    Se è stato usato backup di SQL Server per eseguire il backup del database della chat persistente, usare le procedure di ripristino di SQL Server per ripristinarlo.
    
    Se è stato usato il cmdlet Export-CsPersistentChatData per eseguire il backup, usare Import-CsPersistentChatData per ripristinarlo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

