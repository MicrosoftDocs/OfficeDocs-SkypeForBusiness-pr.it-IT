---
title: 'Lync Server 2013: procedura di failover del pool ABC front end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa82180853e8835782d1e39d56fe595e5c7b09b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500803"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procedura di failover del pool ABC front end in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-22_

Per eseguire la procedura di failover ABC, attenersi alla seguente procedura. Questa procedura contiene una descrizione di alto livello di ogni passaggio, seguito dai comandi e dai cmdlet da eseguire per ogni passaggio.

Per eseguire i cmdlet, aprire una Lync Server Management Shell utilizzando Esegui come amministratore.

<div>

## <a name="to-perform-an-abc-failover"></a>Per eseguire un failover ABC

1.  Controllare se il pool A è l'host per il server di gestione centrale (CMS).
    
      - Eseguire il seguente cmdlet:
        
            Get-CsService -CentralManagement
        
        Se il campo Identity del CMS attivo punta al nome di dominio completo (FQDN) del pool A, è necessario utilizzare i passaggi 2 e 3 di questa procedura per eseguire il failover del server di gestione centrale. In caso contrario, passare al passaggio 4.

2.  Eseguire il failover del CMS nel pool B in modalità di ripristino di emergenza eseguendo il cmdlet seguente:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Dopo aver eseguito questa operazione, è consigliabile spostare il CMS dal pool B a un altro pool di coppie esistente per una maggiore resilienza. Per informazioni dettagliate, vedere [Move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Se il pool A contiene CMS, importare la configurazione LIS dal pool A nel database LIS del pool B (LIS. MDF). Questo funzionerà solo se è stato eseguito il backup dei dati LIS su base regolare. Per importare la configurazione LIS, eseguire i cmdlet seguenti:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importare i flussi di lavoro di servizio di Response Group per Lync Server di cui è stato eseguito il backup dal pool A nel pool B.
    
    <div>
    

    > [!NOTE]  
    > Al momento, il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> richiede che la coda e i nomi dei flussi di lavoro del pool a siano distinti dalla coda e dai nomi dei flussi di lavoro del pool B. Se i nomi non sono distinti, verrà visualizzato un errore durante l'esecuzione del cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> e le code e i flussi di lavoro dovranno essere rinominati nel pool B prima di continuare con il cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .

    
    </div>
    
    Sono disponibili due opzioni per l'importazione della configurazione di Response Group dal pool A al pool B. L'opzione utilizzata varia a seconda che si desideri sovrascrivere le impostazioni a livello di applicazione del pool B con le impostazioni a livello di applicazione nel pool A.
    
      - Se si desidera sovrascrivere le impostazioni del pool B, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se non si desidera sovrascrivere le impostazioni del pool B, utilizzare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tenere presente che se non si desidera sovrascrivere le impostazioni a livello di applicazione del pool di backup (pool B) con le impostazioni del pool primario (pool A), le impostazioni A livello di applicazione del pool A devono essere perse se il pool A viene perso, in quanto l'applicazione Response Group può archiviare solo un set di impostazioni a livello di applicazione per ogni pool. Dopo la distribuzione del pool C per la sostituzione del pool A, è necessario riconfigurare le impostazioni a livello di applicazione, incluso il file audio predefinito per la musica in attesa.

    
    </div>

5.  Verificare che l'importazione della configurazione di Response Group abbia avuto esito positivo eseguendo i cmdlet seguenti per visualizzare i Response Group importati. Si noti che i Response Group importati sono ancora di proprietà del pool A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Per i numeri non assegnati, spostare gli intervalli di numeri non assegnati che utilizzano "annuncio" come servizio annuncio selezionato dal pool A al pool B. Per eseguire questa operazione:
    
      - Ricreare tutti gli annunci che sono stati distribuiti nel pool A del pool B. Se i file audio sono stati utilizzati durante la distribuzione degli annunci nel pool A, questi file saranno necessari per ricreare gli annunci nel pool B. Per ricreare gli annunci nel pool B, utilizzare i cmdlet **New-CsAnnouncement** , con il pool b come servizio padre.
    
      - Reindirizzare tutti gli intervalli di numeri non assegnati che puntano a un annuncio nel pool a per gli annunci appena distribuiti nel pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati che mira a un annuncio del pool A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio non è necessario per gli intervalli di numeri non assegnati che utilizzano "messaggistica unificata di Exchange" come servizio annuncio selezionato.

    
    </div>

7.  Eseguire il failover del pool a nel pool B in modalità ripristino di emergenza (DR) eseguendo il cmdlet seguente:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Creare il pool C, ma non avviare alcun servizio nel pool C.
    
    Si noti che questo passaggio può essere eseguito contemporaneamente ai passaggi 5 e 6.

9.  Forzare gli utenti ospitati nel pool a per passare al pool C eseguendo il cmdlet seguente:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    A questo punto, gli utenti ospitati nel pool A inizieranno a verificarsi un'interruzione del servizio. Questa interruzione continuerà fino al passaggio 16, a questo punto i servizi vengono avviati nel pool C.

10. Forzare la directory conferenze del pool a per passare al pool C eseguendo il cmdlet seguente:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Forzare l'oggetto contatto dell'operatore automatico conferenza (CAA) a passare dal pool A al pool C eseguendo il cmdlet seguente:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copiare il contenuto delle conferenze dal pool B al pool C.

13. Esportare i dati degli utenti dal pool B e importare i dati degli utenti nel pool C eseguendo i cmdlet seguenti:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Ripristinare i dati dell'applicazione Parcheggio di chiamata di cui è stato eseguito il backup dal pool A nel pool C e assegnare gli intervalli di orbit del parcheggio di chiamata del pool A al pool C.
    
      - È possibile riassegnare un intervallo di orbit del parcheggio di chiamata del pool A al pool C tramite il pannello di controllo di Lync Server o Lync Server Management Shell. Per Lync Server Management Shell, eseguire il cmdlet seguente per ogni intervallo di orbit del parcheggio di chiamata assegnato al pool A (si noti che il parametro Identity si riferisce agli intervalli di orbit del parcheggio di chiamata appartenenti al pool A):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Se un brano musicale personalizzato è stato configurato per il parcheggio di chiamata nel pool A, ripristinare il parcheggio di chiamata personalizzato file di musica di attesa nel pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Ad esempio:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Infine, riconfigurare le impostazioni del parcheggio di chiamata nel pool C utilizzando il cmdlet **Set-CsCpsConfiguration** . L'applicazione Parcheggio di chiamata è in grado di archiviare un solo set di impostazioni e un file audio di musica di attesa personalizzato per pool e tali impostazioni non vengono sottoposte a backup o conservate in caso di emergenza.

15. Se il pool hop successivo per la chat persistente punta al pool A, creare e pubblicare le modifiche della topologia in modo che il server dell'hop successivo punti al pool C.
    
      - In Generatore di topologie, impostare il pool di chat persistente in modo che punti al pool C come hop successivo. A tale scopo, fare clic con il pulsante destro del mouse sul pool di chat persistente, quindi fare clic sulla scheda **generale** e quindi digitare il nome del pool C nel **pool di hop successivo**.
    
      - Avviare i servizi nel pool C eseguendo il cmdlet seguente:
        
            Start-csWindowsService
    
    A questo punto, l'interruzione del servizio termina per gli utenti originariamente ospitati nel pool A.

16. Esportare i flussi di lavoro di servizio di Response Group di Lync Server dal pool B di proprietà del pool A per l'importazione nel pool C eseguendo il cmdlet seguente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importare i flussi di lavoro di servizio di Response Group di Lync Server nel pool C dal pool B.
    
    Sono disponibili due opzioni per l'importazione della configurazione di Response Group dal pool B al pool C. L'opzione utilizzata varia a seconda che si desideri sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni a livello di applicazione nel pool B.
    
      - Se si desidera sovrascrivere le impostazioni del pool C, eseguire il cmdlet **Import-CsRgsConfiguration** con l'opzione **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se non si desidera sovrascrivere le impostazioni del pool C, utilizzare il cmdlet **Import-CsRgsConfiguration** senza l'opzione **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tenere presente che se non si desidera sovrascrivere le impostazioni a livello di applicazione del pool C con le impostazioni del pool di backup (pool B), le impostazioni a livello di applicazione del pool B andranno perse perché l'applicazione Response Group può archiviare solo un set di impostazioni a livello di applicazione per ogni pool.

    
    </div>

18. Verificare che l'importazione della configurazione di Response Group abbia avuto esito positivo eseguendo i cmdlet seguenti per visualizzare i Response Group che sono stati importati nel pool C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Quando la configurazione importata è stata verificata nel pool C, rimuovere i Response Group di proprietà del pool primario dal pool B. Questo consente di ridurre al minimo i tempi di inattività dei Response Group.
    
    Questo passaggio consente di creare un nuovo file con la configurazione esportata e quindi di rimuovere il file dal pool B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Sposta nel pool C gli intervalli di numeri non assegnati spostati dal pool A al pool B.
    
      - Ricreare nel pool C tutti gli annunci che sono stati ricreati dal pool A nel pool B. Se i file audio sono stati utilizzati durante la distribuzione degli annunci da spostare, sarà necessario utilizzare questi file per ricreare gli annunci nel pool C. Per ricreare gli annunci nel pool C, utilizzare i cmdlet **New-CsAnnouncement** , con pool c come servizio padre.
    
      - Reindirizzare al pool C tutti gli intervalli di numeri non assegnati che sono stati ridestinati dal pool A al pool B. eseguire il cmdlet seguente per ogni intervallo di numeri non assegnati che deve essere reindirizzato:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Optional Rimuovi dal pool B gli annunci che sono stati ricreati nel pool C se non sono più in uso nel pool B. Per rimuovere gli annunci, utilizzare il cmdlet **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Questo passaggio non è necessario per gli intervalli di numeri non assegnati che utilizzano "messaggistica unificata di Exchange" come servizio annuncio.

        
        </div>

21. Pulire i dati degli utenti del pool A nel pool B eseguendo il cmdlet seguente:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Eseguire le operazioni seguenti in Generatore di topologie:
    
      - Dispair pool A e pool B. coppia pool B e pool C. Quindi rimuovere il pool A dalla topologia e pubblicarlo. A questo scopo:
        
          - In Generatore di topologie fare clic con il pulsante destro del mouse sul pool B e quindi scegliere **modifica proprietà**.
        
          - Fare clic su **resilienza** nel riquadro sinistro.
        
          - Nella casella al di sotto del **pool di backup associato**selezionare Pool C. tenere presente che la casella di selezione del pool di backup associato visualizzerà inizialmente il pool A, perché il pool B è stato precedentemente associato al pool.
        
          - Selezionare **Failover e failback automatico per VoIP** e quindi fare clic su **OK**.
            
            Quando vengono visualizzati i dettagli su questo pool, il pool associato apparirà nel riquadro a destra sotto **Resilienza**.
        
          - Nell'albero della console fare clic con il pulsante destro del mouse su pool A e quindi scegliere Elimina.
        
          - Pubblicare la topologia.

23. Eseguire l'applicazione di avvio automatico nel pool C per installare l'applicazione del servizio di backup e quindi avviare l'applicazione del servizio di backup eseguendo la seguente procedura dalla cartella di distribuzione di un computer locale nel pool C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Riavviare l'applicazione del servizio di backup nel pool B eseguendo i cmdlet seguenti:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Se pool C è un pool Standard Edition (SE) e il pool B ha CMS, installare il database CMS manualmente sul pool C eseguendo il cmdlet seguente:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Richiamare il servizio di backup per sincronizzare il contenuto delle conferenze obsolete dal pool B al pool C generato prima di associare insieme B e C e sincronizzare il nuovo contenuto delle conferenze dal pool C al pool B che è stato generato dopo l'avvio del pool C e prima che B e C siano stati accoppiati. A tale scopo, eseguire i cmdlet seguenti:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Per ogni Survivable Branch Appliance X associata al pool A:
    
      - Arrestare SBA X eseguendo il cmdlet seguente:
        
            Stop-CsWindowsService
    
      - Creare un file contenente un elenco di utenti ospitati in SBA X. L'elenco sarà necessario quando gli utenti vengono spostati di nuovo su SBA X nel passaggio 30. A tale scopo, eseguire il cmdlet seguente:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Forzare gli utenti ospitati in SBA X a passare al pool C eseguendo il cmdlet seguente:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Aggiornare i dati di tali utenti eseguendo innanzitutto i cmdlet seguenti:
        
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
        > Si verificherà un'interruzione del servizio per gli utenti che si trovano in SBA associati al pool A fino allo spostamento di tali utenti nel pool C.

        
        </div>

28. In Generatore di topologie, per ogni SBA X precedentemente associato al pool A, eseguire le operazioni seguenti:
    
      - Modificare l'associazione nel pool C. A tale scopo, fare clic sul sito di succursale, espandere il nodo Survivable Branch Appliances or Servers e fare clic su **Survivable Branch Appliance**. Quindi selezionare il pool **front end, il pool di servizi utente** a cui si connetterà il Survivable Branch Appliance come pool C e quindi fare clic su **Avanti**.
    
      - Pubblicare la topologia. A tale scopo, nell'albero della console fare clic con il pulsante destro del mouse sul nuovo **Survivable Branch Appliance**, scegliere **topologia**e quindi fare clic su **pubblica**.

29. Per ogni SBA X ora associato al pool C:
    
      - Avviare SBA X eseguendo il cmdlet seguente nel Survivable Branch Appliance:
        
            Start-CsWindowsService
    
      - Spostare gli utenti originariamente ospitati in SBA X dal pool C a SBA X eseguendo il cmdlet seguente.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

