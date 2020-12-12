---
title: Distribuire le sale di Microsoft teams usando Microsoft endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Informazioni sulla distribuzione di sale Microsoft teams su distribuzioni su larga scala con Microsoft endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662421"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Distribuire le sale di Microsoft teams usando Microsoft endpoint Configuration Manager

In questo articolo vengono fornite tutte le informazioni necessarie per creare le distribuzioni delle sale di Microsoft teams usando Microsoft endpoint Configuration Manager.

Con i metodi di facile utilizzo forniti da Configuration Manager, è possibile distribuire il sistema operativo e altre applicazioni in più dispositivi di destinazione.

Usare l'approccio illustrato di seguito per guidarvi alla configurazione di Configuration Manager e personalizzare i pacchetti di esempio e gli script forniti in tutte le linee guida necessarie per l'organizzazione.

![Processo di distribuzione di Microsoft teams Rooms con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Questa soluzione è stata testata solo con distribuzioni basate su Surface Pro. Seguire le linee guida del produttore per le configurazioni che non sono basate su Surface Pro.

## <a name="validate-prerequisites"></a>Convalidare i prerequisiti

Per distribuire le sale di Microsoft teams con Configuration Manager, verificare di soddisfare i requisiti e i prerequisiti seguenti.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Requisiti di Microsoft endpoint Configuration Manager

-   La versione di Microsoft endpoint Configuration Manager deve essere almeno 1706 o superiore. È consigliabile usare 1710 o versione successiva. Per informazioni sulle versioni di Windows 10 supportate da Configuration Manager, vedere [supporto per Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) .

-   È necessario installare una versione supportata di Windows Assessment and Deployment Kit (ADK) per Windows 10. Vedere le versioni di [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) che è possibile usare con versioni diverse di Configuration Manager e verificare che la distribuzione includa la versione corretta.

-   Ai server di sistema del sito deve essere stato assegnato il ruolo del punto di distribuzione e le immagini di avvio devono essere abilitate per il [supporto PXE (Preboot Execution Environment)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) per abilitare le distribuzioni avviate dalla rete. Se il supporto PXE non è abilitato, è possibile usare i [supporti di avvio](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) per le distribuzioni.

-   Un account di accesso alla rete deve essere configurato per supportare scenari di distribuzione di nuovi computer (Bare Metal). Per ulteriori informazioni sulla configurazione di un account di accesso alla rete, vedere [account usati in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   È consigliabile abilitare il [supporto multicast](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se è probabile che si stia distribuendo la stessa immagine di Microsoft teams rooms in più unità contemporaneamente.

### <a name="networking-requirements"></a>Requisiti di rete

-   La rete deve avere un server DHCP (Dynamic Host Configuration Protocol) configurato per la distribuzione automatica degli indirizzi IP alle subnet in cui verranno distribuite le unità di Microsoft teams rooms.

    > [!NOTE]
    > La durata del lease DHCP deve essere impostata su un valore superiore alla durata della distribuzione delle immagini. In caso contrario, la distribuzione potrebbe non riuscire.

-   La rete, inclusi gli interruttori e le LAN virtuali (VLAN), deve essere configurata per supportare PXE. Per altre informazioni sull'helper IP e la configurazione PXE, vedere il fornitore di rete. In alternativa, puoi usare il supporto di [avvio](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) per le distribuzioni, se il supporto PXE non è abilitato.

    > [!NOTE]
    > Per i dispositivi Surface Pro, l'avvio dalla rete (avvio PXE) è supportato solo quando si usa un adattatore Ethernet o una stazione di ancoraggio da Microsoft. Le schede Ethernet di terze parti non supportano l'avvio PXE con Surface Pro. Per altre informazioni, vedere [schede Ethernet e distribuzione di superfici](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Configurare Microsoft endpoint Configuration Manager per la distribuzione del sistema operativo

Questo articolo presuppone che tu abbia già una distribuzione di Configuration Manager sano e non dettagli tutti i passaggi necessari per la distribuzione e la configurazione di Configuration Manager da zero. La [documentazione e le indicazioni](https://docs.microsoft.com/configmgr/) per la configurazione di Microsoft endpoint Configuration Manager sono un'ottima risorsa. Se non è stato ancora distribuito Configuration Manager, è consigliabile iniziare con queste risorse.

Seguire le istruzioni seguenti per verificare che le caratteristiche OSD (Operating System Deployment) siano configurate correttamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Convalidare e aggiornare Configuration Manager

1.  Nella console di Configuration Manager, vedere  \> **aggiornamenti e manutenzione** di amministrazione.

2.  Controllare la build installata e gli aggiornamenti applicabili che non sono ancora stati installati.

3.  Rivedere il [supporto per Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Se è necessario aggiornare la distribuzione, selezionare l'aggiornamento che si vuole installare e quindi selezionare **Scarica**.

4.  Al termine del download, selezionare l'aggiornamento e quindi selezionare **Installa Update Pack**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurare i punti di distribuzione per supportare PXE e multicast

1.  Nella console di Configuration Manager accedere ai punti di distribuzione di **Amministrazione** \> .

2.  Selezionare il server del punto di distribuzione che servirà la distribuzione di Microsoft teams Rooms e quindi selezionare **Proprietà**.

3.  Selezionare la scheda **PXE** e verificare che siano abilitate le impostazioni seguenti:
    -   Abilitare il supporto PXE per i client
    -   Consentire a questo punto di distribuzione di rispondere alle richieste PXE in arrivo
    -   Abilitare il supporto computer sconosciuto

4.  *Facoltativo:* Per abilitare il supporto multicast, selezionare la scheda **multicast** e verificare che siano abilitate le impostazioni seguenti:
    -   Abilitare il multicast per inviare simultaneamente i dati a più client
    -   Configurare l'intervallo di porte UDP secondo le indicazioni del team di rete

### <a name="configure-the-network-access-account"></a>Configurare l'account di accesso alla rete

1.  Nella console di Configuration Manager accedere ai siti di configurazione del sito di **Amministrazione** \>  \> e quindi selezionare il sito.

2.  Nel gruppo **Impostazioni** selezionare **Configura** \> **distribuzione software** componenti sito.

3.  Selezionare la scheda **account di accesso alla rete** . Configurare uno o più account e quindi fare clic su **OK**.

> [!NOTE]
> Gli account non necessitano di diritti speciali, ad eccezione del fatto che il **computer di Access si** trova direttamente sul server del punto di distribuzione. Un account utente di dominio generico sarà appropriato. Per altre informazioni, vedere [account usati in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Configurare un'immagine di avvio

1.  Nella console di Configuration Manager accedere alle  \> Immagini di avvio del **sistema operativo** della raccolta software \> .

2.  Selezionare **immagine di avvio (x64)**, quindi selezionare **Proprietà**.

3.  Selezionare la scheda **origine dati** e abilitare **Distribuisci questa immagine di avvio dal punto di distribuzione abilitato per PXE**.

4.  Selezionare la scheda **componenti facoltativi** per installare i componenti necessari:

    1.  Selezionare l'icona stella e cercare **HTML (WinPE-HTA)**

    2.  Selezionare **OK** per aggiungere il supporto dell'applicazione HTML all'immagine di avvio.

5.  *Facoltativo:* Per personalizzare l'esperienza di distribuzione, selezionare la scheda **personalizzazione** .
    -   Abilitare il **supporto dei comandi (solo test)** se si vuole avere accesso a un prompt dei comandi durante la distribuzione. Quando questa opzione è abilitata, è possibile avviare un prompt dei comandi selezionando **F8** in qualsiasi momento durante la distribuzione.
    -   È anche possibile specificare un'immagine di sfondo personalizzata da visualizzare durante la distribuzione. Per impostare un'immagine, abilitare **specificare il file di immagine di sfondo personalizzato (percorso UNC** e selezionare lo sfondo.

6.  Quando richiesto, selezionare **Sì** e distribuire l'immagine di avvio aggiornata ai punti di distribuzione.

Per altre informazioni, vedere [gestire le immagini di avvio con Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).

> [!NOTE]
> Puoi creare un supporto USB avviabile per avviare distribuzioni basate su Sequence Manager di configurazione per gli ambienti che non hanno supporto PXE. Il supporto di avvio contiene solo l'immagine di avvio, i comandi di preavvio facoltativi e i file necessari e i binari di Configuration Manager per supportare l'avvio in Windows PE e la connessione a Gestione configurazione per il resto del processo di distribuzione. Per altre informazioni, vedere [creare elementi multimediali avviabili](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Creare pacchetti di Configuration Manager

> [!IMPORTANT]
> La versione del sistema operativo necessaria per ogni versione del programma di installazione di SRS cambia con ogni rilascio MSI. Per determinare la versione del sistema operativo migliore per un determinato MSI, eseguire lo script di configurazione della console una sola volta. Per altre informazioni, vedere [distribuire le sale di Microsoft teams usando Microsoft endpoint Configuration Manager](rooms-scale.md).

Configuration Manager richiede un certo numero di pacchetti per la distribuzione e la configurazione delle unità di Microsoft teams rooms.

È necessario creare e configurare i pacchetti seguenti e quindi distribuirli ai sistemi del sito di Configuration Manager a cui è stato assegnato il ruolo del server del punto di distribuzione.

| **Nome pacchetto**                     | **Tipo**               | **Descrizione**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| Pacchetto di applicazione SRS V2-SRS     | Pacchetto software       | Pacchetto per il kit di distribuzione di Microsoft teams rooms                                      |
| SRS v2-pacchetto Sysprep             | Pacchetto software       | Pacchetto per la Unattended.xml personalizzata per configurare le unità di Microsoft teams rooms            |
| Pacchetto SRS V2-Set-SRSComputerName | Pacchetto software       | Pacchetto per l'applicazione HTML (HTA) per assegnare un nome di computer durante la distribuzione    |
| SRS V2-configurare l'installazione di SRS         | Pacchetto software       | Pacchetto per configurare la distribuzione dell'app Microsoft teams rooms                          |
| Pacchetto aggiornamenti di SRS V2-OS          | Pacchetto software       | Pacchetto per distribuire gli aggiornamenti obbligatori del sistema operativo                                      |
| Pacchetto di certificato radice SRS V2    | Pacchetto software       | Pacchetto facoltativo per distribuire il certificato radice (non necessario per le unità Unite per il dominio)  |
| SRS v2-pacchetto agente di monitoraggio Microsoft | Pacchetto software       | Pacchetto facoltativo per la distribuzione e la configurazione dell'agente Microsoft Operations Management Suite|
| Pacchetto di sfondo SRS V2-WinPE    | Pacchetto software       | Pacchetto per l'immagine di sfondo personalizzata da usare con le immagini di avvio                           |
| Windows 10 Enterprise                | Immagine del sistema operativo | Pacchetto per il file di installazione del sistema operativo (Install. wim)                          |
| Surface Pro                          | Pacchetto del driver         | Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro                     |
| Surface Pro 4                        | Pacchetto del driver         | Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro 4                   |

Per altre informazioni, vedere [pacchetti e programmi in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Creare cartelle per i file di origine del pacchetto

Configuration Manager richiede che i file di origine del pacchetto vengano organizzati in una struttura di cartelle specifica quando vengono creati e aggiornati.

Creare la struttura di cartelle seguente nel sito di amministrazione centrale o nel sito principale di Microsoft endpoint Configuration Manager oppure in una condivisione server che si sta usando per ospitare i file di origine del pacchetto:

-   SRS v2-pacchetto agente di monitoraggio Microsoft
-   Pacchetto aggiornamenti di SRS V2-OS
-   Pacchetto di certificato radice SRS V2
-   Pacchetto SRS V2-Set-SRSComputerName
-   Pacchetto di applicazione SRS V2-SRS
-   SRS V2-configurare l'installazione di SRS
-   SRS v2-pacchetto Sysprep
-   Driver
    -   Surface Pro
    -   Surface Pro 4
-   Sistemi operativi
    -   Windows 10 Enterprise

> [!TIP]
> È anche possibile [scaricare](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usare il file zip che include la struttura delle cartelle per i pacchetti, gli script che è necessario usare e il modello di sequenza di attività che è necessario importare.

### <a name="create-the-monitoring-agent-package"></a>Creare il pacchetto agente di monitoraggio

1. Scaricare l'agente di monitoraggio da <https://go.microsoft.com/fwlink/?LinkId=828603> .

2. Estrarre il pacchetto nella cartella **SRS V2-Microsoft Monitoring Agent Package** aprendo una finestra del prompt dei comandi e immettendo **MMASetup-AMD64.exe/c:**     al prompt dei comandi.

3. Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.

4. Immettere le informazioni seguenti per creare il pacchetto:

   - Nome<strong>: SRS v2-pacchetto agente di monitoraggio Microsoft</strong>

   - Produttore<strong>: Microsoft Corporation</strong>

   - Versione<strong>: 8.1.11081.0</strong> (immettere la versione del file di installazione scaricata)

   - Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella del **pacchetto di agente di monitoraggio SRS V2-Microsoft** e quindi selezionare **Avanti**.

5. Selezionare non **creare un programma** e quindi fare clic su **Avanti**.

6. Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.

7. Selezionare **Chiudi**.

### <a name="create-the-operating-system-updates-package"></a>Creare il pacchetto aggiornamenti del sistema operativo

1. Nella cartella **SRS V2-OS Updates Package** creare un nuovo script di PowerShell denominato **Install-SRSv2-OS-Updates.ps1**.

2. Copiare lo script seguente nello script **Install-SRSv2-OS-Updates.ps1** . In alternativa, è possibile scaricare lo script Install-SRSv2-OS-Updates.ps1 da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. Scaricare i pacchetti di Windows Update obbligatori nella stessa cartella.
   > [!NOTE]
   > Al momento della pubblicazione di questo articolo è stato richiesto solo [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) . Selezionare [Configura una console Microsoft teams Rooms](console.md)per verificare se sono necessari altri aggiornamenti.

4. Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.

5. Immettere le informazioni seguenti per creare il pacchetto:
   -   Nome: **SRS v2-pacchetto OS Updates**
   -   Produttore: **Microsoft Corporation**
   -   Versione: **1.0.0**
   -   Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-OS Updates Package** e quindi selezionare **Avanti**.

6. Selezionare non **creare un programma** e quindi fare clic su **Avanti**.

7. Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.

8. Selezionare **Chiudi**.

### <a name="create-the-root-certificate-package-optional"></a>Creare il pacchetto di certificato radice (facoltativo)

Questo pacchetto viene creato per distribuire il certificato radice per i dispositivi che non verranno aggiunti a un dominio Active Directory. Creare questo pacchetto solo se si applicano entrambe le condizioni seguenti:
-   La distribuzione include Lync locale o Skype for Business Server.
-   Le unità di Microsoft teams Rooms sono configurate per l'utilizzo in un gruppo di lavoro anziché in un membro del dominio.

1.  Copiare il certificato radice nella cartella **SRS V2-Root Certificate Package** .

2.  Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.

3.  Immettere le informazioni seguenti per creare il pacchetto:
    -   Nome: **SRS v2-pacchetto del certificato radice**
    -   Produttore: *nome dell'organizzazione*
    -   Versione: **1.0.0**
    -   Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-Root Certificate Package** e quindi selezionare **Avanti**.

4.  Selezionare non **creare un programma** e quindi fare clic su **Avanti**.

5.  Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.

6.  Selezionare **Chiudi**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Creare il pacchetto kit di distribuzione di Microsoft teams rooms

1.  Scaricare la versione più recente del **Kit di distribuzione di Microsoft teams Rooms** <https://go.microsoft.com/fwlink/?linkid=851168> e installarla in una workstation.

2.  Copiare il contenuto da **C: \\ Program Files (x86) \\ Skype room System Deployment Kit** nella cartella **SRS V2-SRS Application Package** .

3.  Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.

4.  Immettere le informazioni seguenti per creare il pacchetto:
    -   Nome: **SRS v2-pacchetto di applicazioni SRS**
    -   Produttore: **Microsoft Corporation**
    -   Versione: **3.1.104.0** (immettere la versione del file di installazione scaricata)
    -   Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-SRS Application Package** e quindi selezionare **Avanti**.
5.  Selezionare non **creare un programma** e quindi fare clic su **Avanti**.

6.  Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.

7.  Selezionare **Chiudi**.

### <a name="create-the-computer-name-assignment-package"></a>Creare il pacchetto assegnazione nome computer

1.  Nella cartella **SRS V2-Set-SRSComputerName Package** creare una nuova applicazione HTML denominata **set-SRSComputerName. HTA** .

2.  Copiare lo script seguente nel file **set-SRSComputerName. HTA** . In alternativa, è possibile scaricare il file Set-SRSComputerName. hta da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.

4.  Immettere le informazioni seguenti per creare il pacchetto:

    -   Nome: **Pacchetto SRS V2-Set-SRSComputerName**

    -   Produttore: **Microsoft Corporation**

    -   Versione: **1.0.0**

    -   Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella del **Pacchetto SRS V2-Set-SRSComputerName** e quindi selezionare **Avanti**.

5.  Selezionare non **creare un programma** e quindi fare clic su **Avanti**.

6.  Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.

7.  Selezionare **Chiudi**.

### <a name="create-the-sysprep-package"></a>Creare il pacchetto Sysprep

1. Nella cartella **SRS v2-pacchetto Sysprep** creare un nuovo file XML denominato **Unattend.xml** .

2. Copiare il testo seguente nel file **Unattend.xml** . In alternativa, è possibile scaricare il file Unattend.xml da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.

4. Immettere le informazioni seguenti per creare il pacchetto:
   -   Nome: **SRS v2-pacchetto Sysprep**
   -   Produttore: **Microsoft Corporation**
   -   Versione: **1.0.0**
   -   Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella del **Pacchetto SRS V2-Sysprep** e quindi selezionare **Avanti**.
5. Selezionare non **creare un programma** e quindi fare clic su **Avanti**.

6. Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.

7. Selezionare **Chiudi**.

### <a name="create-the-windows-10-enterprise-package"></a>Creare il pacchetto Windows 10 Enterprise

1.  Ottenere un supporto di Windows 10 Enterprise x64 e copiare il file **Install. wim** nella cartella **sistemi operativi \\ Windows 10 Enterprise** .

2.  Nella console di Configuration Manager, passa a immagini del sistema operativo dei sistemi operativi della **raccolta software** \>  \> e quindi seleziona **Aggiungi immagine del sistema operativo**.

3.  Specificare il percorso del file **Install. wim** appena copiato e quindi selezionare **Avanti**.

4.  Aggiornare il campo **Version** per corrispondere al numero di build dell'immagine Enterprise di Windows 10 e quindi selezionare **Avanti**.

5.  Esaminare la pagina dei **Dettagli** e quindi selezionare **Avanti**.

6.  Selezionare **Chiudi**.

Per altre informazioni, vedere [gestire le immagini del sistema operativo con Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Creare pacchetti di driver di dispositivo Surface Pro

Microsoft teams Rooms è supportato sia per Surface Pro che per Surface Pro 4. È necessario creare un pacchetto di driver per ogni modello Surface Pro presente nell'ambiente.

> [!IMPORTANT]
> I driver devono essere compatibili con Windows 10 Enterprise Build e la versione del kit di distribuzione di Microsoft teams rooms. Per altre informazioni, vedere [scaricare il firmware e i driver più recenti per i dispositivi Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e [configurare una console](console.md).

1.  Scaricare i driver e il firmware più recenti.
    -   Per Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484>
    -   Per Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498>

2.  Estrarre il driver e il firmware scaricati. Aprire una finestra del prompt dei comandi e, al prompt dei comandi, immettere uno di questi comandi:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Nella console di Configuration Manager accedere ai driver dei sistemi operativi della **raccolta software** \>  \> e quindi selezionare **Importa driver**.

4.  Selezionare **Importa tutti i driver nel percorso di rete seguente (UNC)**, selezionare la cartella di origine, ad esempio C: \\ _Sources \\ driver \\ Surface Pro, quindi selezionare **Avanti**.

5.  Nella pagina **specificare i dettagli per i driver importati** selezionare tutti i driver elencati e quindi selezionare **Abilita questi driver e consentire ai computer di installarli**.

6.  Selezionare **categorie**, creare una nuova categoria che corrisponda al modello di superficie, selezionare **OK** e quindi scegliere **Avanti**.

7.  Selezionare **nuovo pacchetto**.

8.  Specificare il nome del pacchetto che corrisponde al modello Surface Pro, immettere il percorso di una cartella in cui archiviare i file del pacchetto del driver, selezionare **OK** e quindi scegliere **Avanti**.

9.  Nella pagina **Immagini di avvio** verificare che non siano selezionate immagini di avvio e quindi selezionare **Avanti**.

10. Selezionare **Chiudi**.

11. Passare a  \> driver dei **sistemi operativi** \> della raccolta software, selezionare **cartella \> Crea cartella** e immettere il nome di una cartella corrispondente al modello Surface Pro a cui sono stati appena importati i driver.

12. Sposta tutti i driver importati nella cartella appena creata per semplificare l'esplorazione e l'operazione.

> [!NOTE]
> Ripetere gli stessi passaggi per altri modelli di Surface Pro che si potrebbero avere. Per altre informazioni, vedere [gestire i driver in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Creare un pacchetto di configurazione di Microsoft teams rooms

1.  Nella console di Configuration Manager, passa a pacchetti di gestione applicazioni della **raccolta software** \>  \> e quindi scegli **Crea pacchetto**.

2.  Immettere le informazioni seguenti per creare il pacchetto:

    -   Nome: **SRS V2-configurare il pacchetto di installazione di SRS**

    -   Produttore: **Microsoft Corporation**

    -   Versione: **1.0.0**

    -   Selezionare la casella di controllo **questo pacchetto contiene i file di origine** , immettere il percorso della cartella **SRS V2-Configure SRS Setup** e quindi fare clic su **Avanti**.

3.  Selezionare non **creare un programma** e quindi fare clic su **Avanti**.

4.  Esaminare la pagina **confermare le impostazioni** e quindi scegliere **Avanti**.

5.  Selezionare **Chiudi**.



## <a name="distribute-configuration-manager-packages"></a>Distribuire pacchetti di Configuration Manager

Tutti i pacchetti devono essere distribuiti ai server a cui è stato assegnato il ruolo del punto di distribuzione nella gerarchia di Configuration Manager. Seguire le istruzioni riportate di seguito per avviare la distribuzione del pacchetto.

1.  Distribuire pacchetti software.

    1.  Nella console di Configuration Manager, passa a  \> pacchetti di **Gestione applicazioni** della raccolta software \> . Selezionare tutti i pacchetti software che si desidera distribuire e quindi selezionare **Distribuisci contenuto**.

    2.  Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.

    3.  Aggiungere tutti i server del punto di distribuzione (o i gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) all'elenco e quindi selezionare **Avanti**.

    4.  Selezionare **Avanti**, quindi selezionare **Chiudi**.

2.  Distribuire pacchetti driver.

    1.  Nella console di Configuration Manager passa a  \>  \> **pacchetti driver** dei sistemi operativi della raccolta software. Selezionare tutti i pacchetti di driver che si desidera distribuire e quindi selezionare **Distribuisci contenuto**.

    2.  Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.

    3.  Aggiungere tutti i server del punto di distribuzione (o i gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) all'elenco e quindi selezionare **Avanti**.

    4.  Selezionare **Avanti**, quindi selezionare **Chiudi**.

3.  Distribuire pacchetti di sistemi operativi.

    1.  Nella console di Configuration Manager accedere alle immagini del sistema operativo della **raccolta software** \>  \> . Selezionare tutte le immagini del sistema operativo che si desidera distribuire e quindi selezionare **Distribuisci contenuto**.

    2.  Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.

    3.  Aggiungere tutti i server del punto di distribuzione (o i gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) all'elenco e quindi selezionare **Avanti**.

    4.  Selezionare **Avanti**, quindi selezionare **Chiudi**.

> [!NOTE]
> La distribuzione del pacchetto può richiedere del tempo, a seconda delle dimensioni del pacchetto, della gerarchia di Configuration Manager, del numero di server del punto di distribuzione e della larghezza di banda disponibile nella rete.
> 
> Tutti i pacchetti devono essere distribuiti prima di poter avviare la distribuzione di un'unità Microsoft teams rooms.
> 
> Per verificare lo stato della distribuzione del pacchetto nella console di Configuration Manager, è possibile **monitorare** lo stato del contenuto della \> **distribuzione** \> .

## <a name="configuration-manager-task-sequences"></a>Sequenze di attività di gestione configurazione

Puoi usare le sequenze di attività con Configuration Manager per automatizzare i passaggi per la distribuzione di un'immagine del sistema operativo in un computer di destinazione. Per distribuire un'unità Microsoft teams rooms in modo automatico, è possibile creare una sequenza di attività che faccia riferimento all'immagine di avvio usata per avviare il computer di Microsoft teams rooms, l'immagine del sistema operativo Windows 10 Enterprise che si vuole installare e qualsiasi altro contenuto aggiuntivo, ad esempio altre applicazioni o aggiornamenti software.

### <a name="import-the-sample-task-sequence"></a>Importare la sequenza di attività di esempio

È possibile scaricare e importare facilmente una sequenza di attività di esempio e personalizzarla per soddisfare le proprie esigenze.

1.  [**Scaricare**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la sequenza di attività di esempio e copiare il file zip scaricato in un percorso condiviso.
2.  Nella console di Configuration Manager accedere alle sequenze di attività dei sistemi operativi della **raccolta software** \>  \> e quindi selezionare **Importa sequenza attività**.

3.  Selezionare **Sfoglia**, passare al percorso della cartella condivisa usato nel passaggio 1, selezionare il file **Microsoft teams Deployment Rooms (en-US). zip** e quindi selezionare **Avanti**.

4.  Impostare **Action** per **creare nuovi** e quindi selezionare **Avanti**.

5.  Confermare le impostazioni e quindi fare clic su **Avanti**.

6.  Selezionare **Chiudi**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Verificare che i pacchetti di riferimento siano collegati correttamente a ogni passaggio di sequenza delle attività.

1. Selezionare la sequenza di attività importata e quindi selezionare **modifica**.

    Viene aperto l'editor sequenza attività e viene visualizzato ogni passaggio sequenziale necessario per la distribuzione e la configurazione di un'unità Microsoft teams rooms.

2. Scorrere ogni passaggio e completare gli aggiornamenti consigliati:

   1. **Riavvio in Windows PE**: questo passaggio viene riavviato e il computer viene avviato in Windows PXE. Per questo passaggio non sono necessarie modifiche.

   2. **Partizione disco 0-UEFI**: questo passaggio consente di Wipe la configurazione del disco e crea partizioni in base alle impostazioni configurate. È consigliabile non apportare modifiche a questo passaggio.

   3. **Impostare il nome di computer SRS**: questo passaggio include un'applicazione HTML che fornisce un'interfaccia utente per impostare un nome di computer per l'unità Microsoft teams Rooms durante la distribuzione.
      -  Si tratta di un passaggio facoltativo, ma può essere disabilitato solo se si vuole gestire la denominazione dei computer tramite un processo alternativo.
      -  Verificare che sia selezionato il pacchetto **SRS v2-set-SRSComputerName** . In caso affermativo, passare al pacchetto e selezionarlo.

   4. **Applica sistema operativo**: questo passaggio specifica l'immagine del sistema operativo da distribuire e il file di risposte di Sysprep non presidiato da usare.
      -  Verificare che sia selezionato il file di immagine del sistema operativo Windows 10 corretto.
      -  Verificare che sia abilitato l' **uso di un file di risposte non presidiato o Sysprep per un'installazione personalizzata** e che sia selezionato il **Pacchetto SRS V2-Sysprep** . Verificare inoltre che il **nome file** sia impostato su **unattend.xml**.

   5. **Applica impostazioni di Windows**: questo passaggio raccoglie informazioni sull'installazione di Windows.
      -  Fornisci informazioni sulle licenze e la registrazione, tra cui il codice Product Key, la password dell'account di amministratore locale e il fuso orario (a seconda delle esigenze).

   6. **Applica impostazioni di rete**: questo passaggio consente di specificare un nome di dominio e un'unità organizzativa di gruppo di lavoro o Active Directory.
      > [!NOTE]
      > Vedi [considerazioni sul dominio del sistema room di Skype](domain-joining-considerations.md) per le azioni consigliate necessarie per la distribuzione delle unità di Microsoft teams rooms come membri di un dominio della directory actve.
   7. **Applicare i driver:** Questo passaggio e i relativi passaggi secondari vengono usati per distribuire i driver di dispositivo e il firmware applicabili in base al modello Surface Pro in uso. Aggiornare ogni passaggio per specificare il pacchetto del driver pertinente associato alla distribuzione.
      -   Ogni pacchetto di driver è configurato per sfruttare i filtri di Strumentazione gestione Windows (WMI) per distribuire driver e firmware rilevanti in base alla creazione e al modello di Surface Pro.
      -   Ti consigliamo vivamente di non modificare la configurazione di questi driver, altrimenti la distribuzione potrebbe non riuscire.

   8. Configurare **Windows e Configuration Manager**: questo passaggio consente di distribuire e configurare il client di Configuration Manager. Aggiornare questo passaggio per specificare il pacchetto client predefinito di Configuration Manager.

   9. **Installa certificato radice**: questo passaggio distribuisce il certificato radice per i dispositivi non collegati al dominio e quindi è facoltativo e disabilitato per impostazione predefinita.
      -   Abilitare questo passaggio se è necessario distribuire un certificato radice nelle unità di Microsoft teams rooms.
      -   Se è necessario eseguire questo passaggio, verificare che il **Pacchetto SRS V2-root certificate** e **disabilitare il reindirizzamento del file System di 64 bit** siano selezionati.

   10. **Installare e configurare agente di monitoraggio**: in questo passaggio viene installata la versione a 64 bit dell'agente di monitoraggio Microsoft Azure e viene configurato l'agente per la connessione all'area di lavoro analisi log.
       -   Questo passaggio è disabilitato per impostazione predefinita. Abilitare questo passaggio solo se si vuole usare l'agente di monitoraggio per monitorare l'integrità delle unità di Microsoft teams rooms.
       -   Modificare questo passaggio e aggiornare i parametri della riga di comando per specificare l' **ID area** di lavoro e la **chiave dell'area di lavoro**.
       -   Per altre informazioni su come ottenere l'ID area di lavoro di Operations Management Suite e la chiave primaria, vedere [configurare i dispositivi di test per il monitoraggio di Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .
       -   Verificare che il **Pacchetto SRS V2-Microsoft Monitoring Agent** e **disabilitare il reindirizzamento del file System di 64 bit** siano selezionati.
       -   Per altre informazioni sul monitoraggio dell'integrità della distribuzione di Microsoft teams rooms, vedere [pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md), [distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md) e [gestire i dispositivi Microsoft teams Rooms con Azure monitor](azure-monitor-manage.md).

   11. **Copiare i file di configurazione di SRS V2**: in questo passaggio vengono copiati i file di installazione e configurazione necessari dal kit di distribuzione di Microsoft teams Rooms nel disco rigido locale. Per questo passaggio non è necessario alcun adattamento.
       -   Verificare che il **pacchetto di applicazione SRS V2-SRS** e **disabilitare il reindirizzamento del file System di 64 bit** siano selezionati.

   12. **Install-SRSv2-OS-Updates**: questo passaggio distribuisce gli eventuali aggiornamenti obbligatori del sistema operativo necessari con la distribuzione di Microsoft teams rooms. Eseguire le operazioni seguenti:
       -   Selezionare [Configura una console Microsoft teams Rooms](console.md) per vedere quali aggiornamenti sono necessari.
       -   Verificare che il **pacchetto degli aggiornamenti di SRS V2-OS** includa tutti gli aggiornamenti necessari.
       -   Verificare che sia selezionato il **Pacchetto SRS V2-OS Updates** .
       -   Verificare che il criterio di esecuzione di PowerShell sia impostato su **bypass**.

   13. **Riavviare il computer**: questo passaggio riavvia il computer dopo l'installazione degli aggiornamenti obbligatori del sistema operativo. Per questo passaggio non è necessario alcun adattamento.

   14. **Configurare i componenti di Windows**: questo passaggio Configura le funzionalità di Windows necessarie. Per questo passaggio non è necessario alcun adattamento.

   15. **Riavviare il computer**: questo passaggio riavvia il computer dopo la configurazione delle funzionalità di Windows. Per questo passaggio non è necessario alcun adattamento.

   16. **Aggiungere un utente locale di Skype**: questo passaggio crea l'account Skype locale usato per accedere automaticamente a Windows e avviare l'applicazione Microsoft teams rooms. Questo passaggio non contiene alcun pacchetto software associato e non è necessario alcun adattamento.

   17. **Impostare e configurare l'applicazione SRS**: in questo passaggio viene configurata l'installazione dell'applicazione Microsoft teams Rooms per l'avvio successivo del sistema operativo.
       -   Verificare che il **pacchetto di installazione SRS V2-configura SRS** e **disabilitare il reindirizzamento del file System di 64 bit** sia selezionato.

> [!IMPORTANT]
> È molto importante che i passaggi della sequenza di attività siano nell'ordine specificato. La modifica dell'ordine dei passaggi o la configurazione di passaggi aggiuntivi potrebbero interrompere la distribuzione.
>
> **Impostare e configurare il passaggio dell'applicazione SRS** deve essere l'ultimo passaggio della sequenza di attività, altrimenti la distribuzione potrebbe non riuscire.

### <a name="create-deployment-for-the-task-sequence"></a>Creare la distribuzione per la sequenza di attività

1. Selezionare la sequenza di attività e quindi fare clic su **Distribuisci**.

2. Selezionare **Sfoglia** per selezionare la raccolta di destinazione per la distribuzione.

3. Selezionare **tutti i computer sconosciuti** e quindi fare clic su **OK**.

4. Selezionare **Avanti**.

5. Selezionare **disponibile** nell'elenco a discesa **scopo** .

6. Selezionare **solo elementi multimediali e PXE** nell'elenco **Rendi disponibile per il seguente** e quindi selezionare **Avanti**.
   > [!WARNING]
   > È molto importante che **lo scopo** sia impostato su **available**. Verificare che lo **scopo** **non** sia impostato su **obbligatorio**. Assicurarsi inoltre di selezionare **solo elementi multimediali e PXE** nella finestra **Rendi disponibile per le operazioni seguenti**.
   >
   > L'impostazione di questi valori su qualcos'altro può causare l'avvio di tutti i computer per ottenere l'immagine di distribuzione delle sale di Microsoft teams.
7. Non specificare alcuna pianificazione e quindi selezionare **Avanti**.

8. Non modificare nulla nella sezione **esperienza utente** e selezionare **Avanti**.

9. Non modificare nulla nella sezione **avvisi** e selezionare **Avanti**.

10. Non modificare nulla nella sezione **punti di distribuzione** e selezionare **Avanti**.

11. Confermare le impostazioni e quindi fare clic su **Avanti**.

12. Selezionare **Chiudi**.

<a name="validate-and-troubleshoot-the-solution"></a>Convalidare e risolvere i problemi della soluzione
--------------------------------------

Dopo aver completato le sequenze di attività di Microsoft endpoint Configuration Manager, è necessario eseguire un'esecuzione di test per verificare che la sequenza di attività sia in grado di distribuire e configurare le unità di Microsoft teams rooms.

1.  Connettere il dispositivo di test alla rete cablata usando una delle schede Ethernet supportate o usando Surface Dock. Se la funzionalità di avvio PXE non è stata configurata per l'ambiente in uso, è possibile usare l'immagine di avvio dell'unità flash USB [creata in precedenza](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) per l'avvio da USB e la connessione a Gestione configurazione.

2.  Accedere al firmware e avviare l'avvio PXE:

    1.  Verificare che il dispositivo Surface sia spento.

    2.  Premere e tenere premuto il pulsante **volume su** .

    3.  Premere e rilasciare il pulsante di **accensione** .

    4.  Dopo l'avvio del dispositivo, rilasciare il pulsante **volume su** .

    5.  Selezionare **configurazione di avvio**.

    6.  Eseguire una delle operazioni seguenti:

        -   Selezionare **avvio PXE** e trascinarlo nella parte superiore dell'elenco. In alternativa, è possibile scorrere rapidamente verso sinistra sulla scheda di rete per avviare immediatamente il dispositivo. Questo non influirà sull'ordine di avvio.
        -   Selezionare l'unità flash USB che contiene il supporto di avvio.

3.  Selezionare **Esci** e quindi **Riavvia ora**.

4.  Quando richiesto, selezionare **invio** per il servizio di avvio di rete.

5.  Windows PE verrà caricato in memoria e verrà avviata la procedura guidata per la sequenza di attività. Selezionare **Avanti** per continuare.

6.  Selezionare la sequenza di attività importata in precedenza e quindi fare clic su **Avanti**.

7.  Dopo aver applicato la configurazione del disco, verrà chiesto di specificare un nome di computer per il dispositivo. L'interfaccia utente visualizzerà un nome di computer consigliato in base al numero seriale del dispositivo Surface Pro. Puoi accettare il nome proposto o specificarne uno nuovo. Seguire le istruzioni nella schermata Assegnazione nome computer. Quando si seleziona **accetta**, viene avviata la distribuzione.

8.  Il resto del processo di distribuzione è automatico e non richiede più input da parte dell'utente.

9.  Al termine della configurazione dell'attività di distribuzione, verrà visualizzata la schermata di configurazione seguente che chiede di configurare le impostazioni dell'applicazione Microsoft teams rooms.

    ![Schermata di configurazione iniziale per l'applicazione Microsoft teams rooms](../media/room-systems-scale-image2.png)

10.  Collegare Surface Pro alla console Microsoft teams Rooms e configurare le impostazioni dell'applicazione.

11.  Verificare che le funzionalità elencate nella [Guida di Microsoft teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) stiano lavorando sul dispositivo distribuito.


Per risolvere i problemi di un'installazione non riuscita, selezionare il file **Smsts. log** , che registra tutti i passaggi eseguiti in una sequenza di attività di gestione configurazione.

Il file SMSTS. log viene archiviato in uno di un certo numero di percorsi, a seconda della fase del processo di compilazione. Selezionare la tabella seguente per identificare il percorso del file SMSTS. log.


| **Fase di distribuzione**                                                            | **Percorso log sequenza attività**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, prima del formato HDD                                                        | X: \\ Windows \\ temp \\ smstslog \\ Smsts. log             |
| WinPE, dopo il formato HDD                                                         | C: \\ _SMSTaskSequence \\ log \\ Smstslog \\ Smsts. log    |
| Sistema operativo distribuito prima dell'installazione dell'agente Configuration Manager | c: \\ _SMSTaskSequence \\ log \\ Smstslog \\ Smsts. log    |
| Sistema operativo e agente Configuration Manager distribuito                   | % WINDIR% \\ system32 \\ CCM \\ logs \\ Smstslog \\ Smsts. log |
| Esecuzione della sequenza di attività completata                                                | % WINDIR% \\ system32 \\ CCM \\ logs \\ Smsts. log           |

> [!TIP]
> È possibile selezionare **F8** in qualsiasi momento durante la sequenza di attività per aprire una console dei comandi e quindi accedere al file Smsts. log.

Per risolvere i problemi di avvio PXE, controllare i due file di log nel server Configuration Manager specifici delle azioni PXE:

-   **Pxecontrol. log**, disponibile nella directory log di installazione di Configuration Manager

-   **SMSPXE. log**, situato nella directory dei registri di Configuration Manager Management Point (MP)

Per un elenco completo dei file di log che è possibile usare per risolvere ulteriormente la procedura di installazione di Configuration Manager, vedere il [riferimento al file di log](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)di Microsoft endpoint Configuration Manager.
