---
title: 'Lync Server 2013: ripristino di un server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 479e4c690d0ca7931631f3bc553d1dafc2a10ea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511563"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Ripristino di un server Standard Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Se si verifica un errore in un server Standard Edition che non ospita l'archivio di gestione centrale, seguire le procedure illustrate in questa sezione. Se l'archivio di gestione centrale ha esito negativo, vedere [ripristino del server che ospita l'archivio di gestione centrale in Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino. È possibile acquisire la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>Per ripristinare un server Standard Edition

1.  Iniziare con un server pulito o nuovo che abbia lo stesso nome di dominio completo (FQDN) del computer in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.

    
    </div>

2.  Da un account utente membro del gruppo RTCUniversalServerAdmins e del gruppo Administrators locale, accedere al server che si sta ripristinando.

3.  Ripristinare l'archivio file copiando l'archivio file appropriato da $Backup al percorso dell'archivio file nel server e condividere la cartella.
    
    <div>
    

    > [!IMPORTANT]  
    > Il percorso e il nome del file dell'archivio file ripristinato devono essere identici a quelli dell'archivio file di cui è stato eseguito il backup in modo che i componenti che utilizzano i file possano accedervi.

    
    </div>

4.  Eseguire Generatore di topologie:
    
    1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.
    
    2.  Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **OK**.
    
    3.  Selezionare la topologia e quindi fare clic su **Salva**. Fare clic su **Sì** per confermare la selezione.

5.  Passare alla cartella o al supporto di installazione di Lync Server e quindi avviare la distribuzione guidata di Lync Server in \\ Setup \\ amd64 \\Setup.exe. Utilizzare la distribuzione guidata di Lync Server per eseguire le operazioni seguenti:
    
    1.  Eseguire **Passaggio 1: Installazione dell'archivio di configurazione locale** per installare i file della configurazione locale.
    
    2.  Eseguire il **passaggio 2: installazione o rimozione dei componenti di Lync Server** per installare i ruoli del server Lync Server.
    
    3.  Eseguire **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** per assegnare i certificati.
    
    4.  Eseguire **Passaggio 4: Avvio servizi** per avviare i servizi nel server.
    
    Per informazioni dettagliate sull'esecuzione della Distribuzione guidata, vedere nella documentazione relativa alla distribuzione le informazioni sul ruolo del server che si desidera ripristinare.

6.  Ripristinare i dati utente eseguendo le operazioni seguenti:
    
    1.  Copiare ExportedUserData.zip da $Backup \\ in una directory locale.
    
    2.  Prima di ripristinare i dati degli utenti, è necessario arrestare i servizi Lync. A tale scopo, digitare:
        
            Stop-CsWindowsService
    
    3.  Per ripristinare i dati utente, nella riga di comando digitare:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Ad esempio:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Riavviare i servizi di Lync digitando:
        
            Start-CsWindowsService

7.  Se è stato distribuito Response Group su questo server Standard Edition, ripristinare i dati di configurazione di Response Group. Per informazioni dettagliate, vedere [Restoring Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Se è stata distribuita la chat persistente in questo server Standard Edition, ripristinare il database di Persistent Chat (MGC. MDF).
    
    Se è stato utilizzato SQL Server backup per eseguire il backup del database di chat persistente, utilizzare le procedure di ripristino di SQL Server per ripristinarlo.
    
    Se è stato utilizzato il cmdlet Export-CsPersistentChatData per eseguirne il backup, utilizzare il Import-CsPersistentChatData per ripristinarlo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

