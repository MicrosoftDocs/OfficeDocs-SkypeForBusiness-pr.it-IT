---
title: 'Lync Server 2013: Procedura di failover del pool ABC front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6cb610d153374f6f4c9ba8a3c2798c50b88ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procedura di failover del pool ABC front-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-22_

Per eseguire la procedura di failover ABC, seguire i passaggi seguenti. Questa procedura contiene una descrizione di alto livello di ogni passaggio, seguita da comandi e cmdlet da eseguire per ogni passaggio.

Per eseguire i cmdlet, aprire un Lync Server Management Shell usando Esegui come amministratore.

<div>

## <a name="to-perform-an-abc-failover"></a>Per eseguire un failover ABC

1.  Verificare se il pool A è l'host per il server di gestione centrale (CMS).
    
      - Eseguire il cmdlet seguente:
        
            Get-CsService -CentralManagement
        
        Se il campo Identity del CMS attivo punta al nome di dominio completo (FQDN) del pool A, verranno usati i passaggi 2 e 3 della procedura per eseguire il failover del server di gestione centralizzato prima. In caso contrario, passare al passaggio 4.

2.  Non superare il CMS per il pool B in modalità di ripristino di emergenza eseguendo il cmdlet seguente:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Dopo aver eseguito questa operazione, è consigliabile trasferire il CMS dal pool B a un altro pool di coppie esistente per una maggiore resilienza. Per informazioni dettagliate, vedere [Move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer).

3.  Se il pool A contiene CMS, importare la configurazione LIS dal pool A nel database LIS del pool B (LIS. MDF). Questo funzionerà solo se è stato eseguito il backup dei dati LIS su base regolare. Per importare la configurazione LIS, eseguire i cmdlet seguenti:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importare flussi di lavoro di servizio di Response Group di Lync Server dal pool A nel pool B.
    
    <div>
    

    > [!NOTE]  
    > Al momento, il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> richiede che i nomi delle code e dei flussi di lavoro nel pool A siano distinti dai nomi delle code e dei flussi di lavoro nel pool B. Se i nomi non sono distinti, viene visualizzato un messaggio di errore quando si esegue il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> e le code e i flussi di lavoro dovranno essere rinominati nel pool B prima di procedere con il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .

    
    </div>
    
    Sono disponibili due opzioni per l'importazione della configurazione del gruppo di risposte dal pool A al pool B. L'opzione che si usa dipende dal fatto che si vuole sovrascrivere le impostazioni a livello di applicazione del pool B con le impostazioni a livello di applicazione in pool A.
    
      - Se si vogliono sovrascrivere le impostazioni del pool B, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se non si vuole sovrascrivere le impostazioni del pool B, usare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tieni presente che se non vuoi sovrascrivere le impostazioni a livello di applicazione del pool di backup (pool B) con le impostazioni del pool principale (pool A), le impostazioni A livello di applicazione di pool A verranno perse se il pool A viene perso, perché l'applicazione Response Group può archiviare solo un set di impostazioni a livello di applicazione per pool. Quando il pool C viene distribuito in sostituzione del pool A, le impostazioni a livello di applicazione devono essere riconfigurate, incluso il file audio predefinito per la musica in blocco.

    
    </div>

5.  Verificare che l'importazione della configurazione del gruppo di risposte abbia avuto successo eseguendo i cmdlet seguenti per visualizzare i gruppi di risposta importati. Tieni presente che i gruppi di risposta importati continuano a essere di proprietà del pool A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Per i numeri non assegnati, sposti gli intervalli di numeri non assegnati che usano "annuncio" come servizio di annuncio selezionato dalla piscina a al pool B. Per eseguire questa operazione:
    
      - Ricrea tutti gli annunci distribuiti in pool A sul pool B. Se sono stati usati file audio durante la distribuzione degli annunci nel pool A, questi file saranno necessari per ricreare gli annunci nel pool B. Per ricreare gli annunci nel pool B, usare i cmdlet **New-CsAnnouncement** , con il pool b come servizio padre.
    
      - Riassegnare la destinazione a tutti gli intervalli di numeri non assegnati destinati a un annuncio nel pool a degli annunci appena distribuiti nel pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati destinato a un annuncio del pool A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio non è necessario per gli intervalli di numeri non assegnati che usano "messaggistica unificata di Exchange" come servizio di annuncio selezionato.

    
    </div>

7.  Eseguire il failover del pool da a al pool B in modalità ripristino di emergenza (DR) eseguendo il cmdlet seguente:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Creare il pool C, ma non avviare alcun servizio nel pool C.
    
    Tieni presente che questo passaggio può essere eseguito contemporaneamente ai passaggi 5 e 6.

9.  Imporre agli utenti ospitati nel pool a di trasferirsi nel pool C eseguendo il cmdlet seguente:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    A questo punto, gli utenti ospitati nel pool A inizieranno a provare un'interruzione del servizio. Questa interruzione continuerà fino al passaggio 16, in cui i servizi Point vengono avviati nel pool C.

10. Forzare la directory conferenza del pool a per il passaggio al pool C eseguendo il cmdlet seguente:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Forzare l'oggetto contatto CAA (Conference Auto Attendant) a trasferirsi dal pool A al pool C eseguendo il cmdlet seguente:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copiare il contenuto della conferenza dal pool B al pool C.

13. Esportare i dati degli utenti dal pool B e importare i dati utente nel pool C eseguendo i cmdlet seguenti:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Ripristinare i dati dell'applicazione di parcheggio di Call backed-up da pool A in pool C e assegnare gli intervalli orbit Park Call del pool A al pool C.
    
      - È possibile riassegnare l'intervallo di Orbit di un parcheggio di chiamata del pool A al pool C tramite il pannello di controllo di Lync Server o Lync Server Management Shell. Per Lync Server Management Shell, eseguire il cmdlet seguente per ogni intervallo di orbit del parcheggio di chiamata assegnato al pool A (si noti che il parametro Identity fa riferimento agli intervalli di orbita del parcheggio di chiamata che appartengono al pool A):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Se una musica in blocco personalizzata è stata configurata per il parcheggio delle chiamate in pool A, ripristinare il file di musica in blocco di Call Park personalizzato nel pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Ad esempio:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Infine, riconfigurare le impostazioni del parcheggio delle chiamate nel pool C usando il cmdlet **Set-CsCpsConfiguration** . L'applicazione per il parcheggio delle chiamate può archiviare solo un set di impostazioni e un file audio di musica in attesa personalizzato per ogni pool e queste impostazioni non vengono supportate o conservate in caso di emergenza.

15. Se il pool hop successivo per la chat persistente punta al pool A, imposta e pubblica le modifiche della topologia in modo che il server hop successivo punti al pool C.
    
      - In Generatore di topologie cambiare il pool di chat persistente in modo che punti al pool C come hop successivo. A questo scopo, fai clic con il pulsante destro del mouse sul pool di chat persistente, quindi fai clic sulla scheda **generale** e quindi digita il nome del pool C nel **pool hop successivo**.
    
      - Avviare i servizi nel pool C eseguendo il cmdlet seguente:
        
            Start-csWindowsService
    
    A questo punto, l'interruzione del servizio termina per gli utenti originariamente assegnati al pool A.

16. Esportare i flussi di lavoro del servizio Response Group di Lync Server dal pool B di proprietà del pool A per l'importazione nel pool C eseguendo il cmdlet seguente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importare i flussi di lavoro del servizio Response Group di Lync Server nel pool C dal pool B.
    
    Sono disponibili due opzioni per l'importazione della configurazione del gruppo di risposte dal pool B al pool C. L'opzione che si usa dipende dal fatto che si vuole sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni a livello di applicazione nel pool B.
    
      - Se si vogliono sovrascrivere le impostazioni del pool C, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se non si vogliono sovrascrivere le impostazioni del pool C, usare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tieni presente che se non vuoi sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni del pool di backup (pool B), le impostazioni a livello di applicazione del pool B andranno perse perché l'applicazione Response Group può archiviare solo un set di livello di applicazione impostazioni per pool.

    
    </div>

18. Verificare che l'importazione della configurazione del gruppo di risposte abbia avuto successo eseguendo i cmdlet seguenti per visualizzare i gruppi di risposte importati nel pool C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Quando la configurazione importata è stata verificata nel pool C, rimuovere i gruppi di risposta di proprietà del pool principale dal pool B. In questo modo si minimizza il tempo di inattività dei gruppi di risposta.
    
    Questo passaggio crea un nuovo file con la configurazione esportata e quindi rimuove il file dal pool B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Sposta nel pool C gli intervalli di numeri non assegnati spostati dal pool A al pool B.
    
      - Ricrea in pool C tutti gli annunci ricreati dal pool A nel pool B. Se sono stati usati file audio durante la distribuzione degli annunci da spostare, sarà necessario usare questi file per ricreare gli annunci nel pool C. Per ricreare gli annunci nel pool C, usare i cmdlet **New-CsAnnouncement** , con il pool c come servizio padre.
    
      - Ridestinazione del pool C tutti gli intervalli di numeri non assegnati che sono stati ridestinati dal pool A al pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati che deve essere destinato alla destinazione:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Opzionale Rimuovi dal pool B gli annunci che sono stati ricreati nel pool C se non sono più in uso nel pool B. Per rimuovere gli annunci, usa il cmdlet **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Questo passaggio non è necessario per gli intervalli di numeri non assegnati che usano "messaggistica unificata di Exchange" come servizio di annuncio.

        
        </div>

21. Pulire i dati degli utenti del pool A nel pool B eseguendo il cmdlet seguente:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Eseguire le operazioni seguenti in Generatore di topologie:
    
      - Raggruppamento A e pool B. Pair pool B e pool C. Quindi Rimuovi pool A dalla topologia e pubblicalo. Per eseguire questa operazione:
        
          - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool B e quindi scegliere **modifica proprietà**.
        
          - Fare clic su **resilienza** nel riquadro sinistro.
        
          - Nella casella sotto il **pool di backup associato**selezionare Pool C. si noti che la casella di selezione del pool di backup associato visualizzerà inizialmente il pool A, perché il pool B è stato associato in precedenza al pool.
        
          - Selezionare **failover automatico e failback per la voce**e quindi fare clic su **OK**.
            
            Quando si visualizzano i dettagli su questo pool, il pool associato ora viene visualizzato nel riquadro destro in **resilienza**.
        
          - Nell'albero della console fare clic con il pulsante destro del mouse su pool A e quindi scegliere Elimina.
        
          - Pubblicare la topologia.

23. Eseguire l'applicazione di avvio automatico nel pool C per installare l'applicazione del servizio di backup e quindi avviare l'applicazione di servizio di backup eseguendo la seguente procedura dalla cartella di distribuzione in un computer locale nel pool C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Riavviare l'applicazione del servizio di backup nel pool B eseguendo i cmdlet seguenti:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Se pool C è un pool di Standard Edition (SE) e il pool B include CMS, installare il database CMS manualmente nel pool C eseguendo il cmdlet seguente:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Richiamare il servizio di backup per sincronizzare i vecchi contenuti di conferenza dal pool B al pool C generati prima di associare B e C insieme e per sincronizzare il contenuto di una nuova conferenza dal pool C al pool B generato dopo l'avvio del pool C e prima che le coppie di B e C vengano raggruppate. A questo scopo, eseguire i cmdlet seguenti:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Per ogni appliance Survivable Branch X associato al pool A:
    
      - Arrestare SBA X eseguendo il cmdlet seguente:
        
            Stop-CsWindowsService
    
      - Creare un file contenente un elenco di utenti ospitati in SBA X. L'elenco sarà necessario quando gli utenti verranno spostati di nuovo in SBA X nel passaggio 30. A tale scopo, eseguire il cmdlet seguente:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Imporre agli utenti residenti in SBA X di trasferirsi nel pool C eseguendo il cmdlet seguente:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Aggiornare i dati di questi utenti eseguendo prima di tutto i cmdlet seguenti:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        E quindi Esegui questo script:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > Si verificherà un'interruzione del servizio per gli utenti residenti in SBAs associati al pool A finché questi utenti non vengono spostati nel pool C.

        
        </div>

28. In Generatore di topologie, per ogni SBA X precedentemente associato al pool A, eseguire le operazioni seguenti:
    
      - Modificare l'associazione in pool C. A questo scopo, fai clic sul sito della filiale, Espandi il nodo Survivable Branch Appliances o Servers e fai clic su **Survivable Branch Appliance**. Selezionare quindi il pool di **Servizi utente** in cui l'appliance Survivable Branch si connette a pool C e quindi fare clic su **Avanti**.
    
      - Pubblicare la topologia. A tale scopo, nell'albero della console fare clic con il pulsante destro del mouse sul nuovo **dispositivo Survivable Branch Appliance**, scegliere **topologia**e quindi fare clic su **pubblica**.

29. Per ogni SBA X ora associato al pool C:
    
      - Avviare SBA X eseguendo il cmdlet seguente nell'appliance Survivable Branch:
        
            Start-CsWindowsService
    
      - Sposta gli utenti originariamente ospitati in SBA X dal pool C a SBA X eseguendo il cmdlet seguente.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

