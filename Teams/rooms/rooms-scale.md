---
title: Distribuire Microsoft Teams Rooms usando Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Informazioni sulla distribuzione di Microsoft Teams Rooms su larga scala con Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 27cd37df8516973ddf9fbe6401a1e4c21ce01e0a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731575"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Distribuire Microsoft Teams Rooms usando Microsoft Endpoint Configuration Manager

Questo articolo fornisce tutte le informazioni necessarie per creare le distribuzioni Microsoft Teams Rooms tramite Microsoft Endpoint Configuration Manager.

Con i metodi di facile utilizzo forniti da Configuration Manager, è possibile distribuire il sistema operativo e altre applicazioni in più dispositivi di destinazione.

Usare l'approccio illustrato di seguito per illustrare la configurazione di Configuration Manager e personalizzare i pacchetti e gli script di esempio forniti in questa guida in base alle esigenze dell'organizzazione.

![Microsoft Teams Rooms processo di distribuzione usando Configuration Manager.](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Questa soluzione è stata testata solo con Surface Pro basate su Surface Pro. Seguire le linee guida del produttore per le configurazioni non basate su Surface Pro.

## <a name="validate-prerequisites"></a>Convalidare i prerequisiti

Per distribuire Microsoft Teams Rooms con Configuration Manager, assicurarsi di soddisfare i prerequisiti e i requisiti seguenti.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager requisiti

-   Microsoft Endpoint Configuration Manager versione deve essere almeno 1706 o successiva. È consigliabile usare 1710 o versione successiva. Vedere [Supporto per Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) per informazioni sulle versioni Windows 10 supportate da Configuration Manager.

-   È necessario installare una versione supportata di Windows Assessment and Deployment Kit (ADK) per Windows 10. Vedere le versioni del [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) che è possibile usare con diverse versioni di Configuration Manager e verificare che la distribuzione includa la versione corretta.

-   Ai server del sistema del sito deve essere stato assegnato il ruolo di punto di distribuzione e le immagini di avvio devono essere abilitate per il supporto [PXE (Preboot Execution Environment)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) per abilitare le distribuzioni avviate dalla rete. Se il supporto PXE non è abilitato, è possibile usare i supporti [di](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) avvio per le distribuzioni.

-   Un account di accesso alla rete deve essere configurato per supportare nuovi scenari di distribuzione di computer (bare metal). Per altre informazioni sulla configurazione di un account di accesso di rete, vedere [Account usati in Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   È consigliabile abilitare il [supporto multicast,](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)se è probabile che si distribuirà la stessa immagine Microsoft Teams Rooms a più unità contemporaneamente.

### <a name="networking-requirements"></a>Requisiti di rete

-   La rete deve avere un server DYNAMIC Host Configuration Protocol (DHCP), configurato per la distribuzione automatica degli indirizzi IP alle subnet in cui verranno distribuite Microsoft Teams Rooms di rete.

    > [!NOTE]
    > La durata del lease DHCP deve essere impostata su un valore più lungo della durata della distribuzione dell'immagine. In caso contrario, la distribuzione potrebbe non riuscire.

-   La rete, inclusi gli switch e le reti LAN virtuali (VLAN), deve essere configurata per supportare PXE. Per altre informazioni sulla configurazione di HELPER IP e PXE, vedere il fornitore della rete. In alternativa, è possibile usare i supporti [di](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) avvio per le distribuzioni, se il supporto PXE non è abilitato.

    > [!NOTE]
    > Per Surface Pro, l'avvio dalla rete (avvio PXE) è supportato solo quando si usa un adattatore Ethernet o un docking station da Microsoft. Gli adattatori Ethernet di terze parti non supportano l'avvio PXE con Surface Pro. Per altre [informazioni, vedere Adattatori Ethernet](/surface/ethernet-adapters-and-surface-device-deployment) e distribuzione di Surface.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Configurare i Microsoft Endpoint Configuration Manager per la distribuzione del sistema operativo

Questo articolo presuppone che si abbia già una distribuzione di Configuration Manager integra e non descrive in dettaglio tutti i passaggi necessari per distribuire e configurare Configuration Manager da zero. La [documentazione e le indicazioni di configurazione](/configmgr/) sul Microsoft Endpoint Configuration Manager sono una risorsa eccezionale. se Configuration Manager non è ancora stato distribuito, è consigliabile iniziare con queste risorse.

Usare le istruzioni seguenti per verificare che le funzionalità di distribuzione del sistema operativo (OSD) siano configurate correttamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Convalidare e aggiornare Configuration Manager

1.  Nella console di Configuration Manager passare a **Amministrazione** \> **aggiornamenti e manutenzione.**

2.  Controllare la build installata e gli aggiornamenti applicabili che non sono ancora stati installati.

3.  Esaminare [il supporto per Windows 10 in Configuration Manager;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) se è necessario aggiornare la distribuzione, selezionare l'aggiornamento da installare e quindi scegliere **Scarica**.

4.  Al termine del download, selezionare l'aggiornamento e quindi **selezionare Installa pacchetto di aggiornamento.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurare i punti di distribuzione per supportare PXE e multicast

1.  Nella console di Configuration Manager passare a **Punti di** distribuzione \> **di amministrazione**.

2.  Selezionare il server del punto di distribuzione che servirà la Microsoft Teams Rooms distribuzione e quindi selezionare **Proprietà**.

3.  Selezionare la **scheda PXE** e verificare che le impostazioni seguenti siano abilitate:
    -   Abilitare il supporto PXE per i client
    -   Consenti a questo punto di distribuzione di rispondere alle richieste PXE in arrivo
    -   Abilitare il supporto per computer sconosciuti

4.  *Facoltativo:* Per abilitare il supporto multicast, selezionare la **scheda Multicast** e verificare che siano abilitate le impostazioni seguenti:
    -   Abilitare il multicast per l'invio simultaneo di dati a più client
    -   Configurare l'intervallo di porte UDP come da raccomandazione del team di rete

### <a name="configure-the-network-access-account"></a>Configurare l'account di accesso alla rete

1.  Nella console di Configuration Manager passare a **Siti di** configurazione del sito \> **di** \> **amministrazione** e quindi selezionare il sito.

2.  Nel gruppo **Impostazioni** selezionare **Configura distribuzione** software componenti \> **del sito.**

3.  Selezionare la **scheda Account di accesso alla** rete. Configurare uno o più account e quindi scegliere **OK.**

> [!NOTE]
> Gli account non hanno bisogno di diritti speciali, ad eccezione dell'accesso al **computer** dalla rete direttamente nel server del punto di distribuzione. Un account utente di dominio generico sarà appropriato. Per altre informazioni, vedere [Account usati in Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Configurare un'immagine di avvio

1.  Nella console di Configuration Manager passare a **Immagini di avvio** del sistema \> **operativo** \> **raccolta software**.

2.  Selezionare **Immagine di avvio (x64)** e quindi proprietà . 

3.  Selezionare la **scheda Origine dati** e abilitare Distribuisci l'immagine di avvio dal punto di distribuzione abilitato per **PXE.**

4.  Selezionare la **scheda Componenti facoltativi** per installare i componenti necessari:

    1.  Selezionare l'icona a forma di stella e cercare **HTML (WinPE-HTA)**

    2.  Selezionare **OK per** aggiungere il supporto dell'applicazione HTML all'immagine di avvio.

5.  *Facoltativo:* Per personalizzare l'esperienza di distribuzione, selezionare la **scheda Personalizzazione.**
    -   Abilitare **il supporto dei comandi (solo test)** se si vuole avere accesso a un prompt dei comandi durante la distribuzione. Quando questa opzione è abilitata, è possibile avviare un prompt dei comandi selezionando **F8** in qualsiasi momento durante la distribuzione.
    -   È anche possibile specificare un'immagine di sfondo personalizzata da visualizzare durante la distribuzione. Per impostare un'immagine, abilitare Specificare il file di immagine **di sfondo personalizzato (percorso UNC** e selezionare lo sfondo.

6.  Quando richiesto, selezionare **Sì** e distribuire l'immagine di avvio aggiornata ai punti di distribuzione.

Per altre informazioni, vedere [Gestire le immagini di avvio con Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> È possibile creare un supporto USB avviabile per avviare distribuzioni basate sulla sequenza di attività di Configuration Manager per ambienti che non supportano PXE. Il supporto di avvio contiene solo l'immagine di avvio, i comandi di preavvio facoltativi e i file necessari e i file binari di Configuration Manager per supportare l'avvio in Windows PE e la connessione a Configuration Manager per il resto del processo di distribuzione. Per altre informazioni, vedere [Creare supporti avviabili.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Creare pacchetti di Configuration Manager

> [!IMPORTANT]
> La versione del sistema operativo richiesta per ogni versione del programma di installazione di SRS cambia a ogni versione msi. Per determinare la versione migliore del sistema operativo per un determinato file MSI, eseguire lo script di configurazione della console una sola volta. Per altre informazioni, vedere [Distribuire Microsoft Teams Rooms usando Microsoft Endpoint Configuration Manager](rooms-scale.md).

Configuration Manager richiede diversi pacchetti per distribuire e configurare le Microsoft Teams Rooms di distribuzione.

È necessario creare e configurare i pacchetti seguenti e quindi distribuirli ai sistemi del sito di Configuration Manager a cui è stato assegnato il ruolo di server del punto di distribuzione.

| **Nome pacchetto**                     | **Tipo**               | **Descrizione**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - Pacchetto di applicazioni SRS     | Pacchetto software       | Pacchetto per il kit Microsoft Teams Rooms distribuzione                                      |
| SRS v2 - Pacchetto Sysprep             | Pacchetto software       | Pacchetto per le unità di Unattended.xml per configurare le Microsoft Teams Rooms personalizzate            |
| SRS v2 - Set-SRSComputerName pacchetto | Pacchetto software       | Pacchetto per l'applicazione HTML (HTA) per assegnare un nome di computer durante la distribuzione    |
| SRS v2 - Configurare la configurazione di SRS         | Pacchetto software       | Pacchetto per configurare la distribuzione dell Microsoft Teams Rooms app                          |
| SRS v2 - Pacchetto di aggiornamenti del sistema operativo          | Pacchetto software       | Pacchetto per distribuire gli aggiornamenti obbligatori del sistema operativo                                      |
| SRS v2 - Pacchetto di certificati radice    | Pacchetto software       | Facoltativo: pacchetto per distribuire il certificato radice (non necessario per le unità appartenenti al dominio)  |
| SRS v2 - Microsoft Monitoring Agent pacchetto | Pacchetto software       | Facoltativo: pacchetto per distribuire e configurare l'agente di Microsoft Operations Management Suite|
| SRS v2 - Pacchetto in background WinPE    | Pacchetto software       | Pacchetto per l'immagine di sfondo personalizzata da usare con le immagini di avvio                           |
| Windows 10 Enterprise                | Immagine del sistema operativo | Pacchetto per il file di installazione del sistema operativo (install.wim)                          |
| Surface Pro                          | Pacchetto driver         | Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro                     |
| Surface Pro 4                        | Pacchetto driver         | Pacchetto per i driver di dispositivo e il firmware per Microsoft Surface Pro 4                   |

Per altre informazioni, vedere [Pacchetti e programmi in Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>Creare cartelle per i file di origine del pacchetto

Configuration Manager richiede che i file di origine del pacchetto siano organizzati in una struttura di cartelle specifica quando vengono creati per la prima volta e quando vengono aggiornati.

Creare la struttura di cartelle seguente nel Microsoft Endpoint Configuration Manager di amministrazione centrale o nel sito principale oppure in una condivisione server in uso per ospitare i file di origine del pacchetto:

-   SRS v2 - Microsoft Monitoring Agent pacchetto
-   SRS v2 - Pacchetto di aggiornamenti del sistema operativo
-   SRS v2 - Pacchetto di certificati radice
-   SRS v2 - Set-SRSComputerName pacchetto
-   SRS v2 - Pacchetto di applicazioni SRS
-   SRS v2 - Configurare la configurazione di SRS
-   SRS v2 - Pacchetto Sysprep
-   Driver
    -   Surface Pro
    -   Surface Pro 4
-   Sistemi operativi
    -   Windows 10 Enterprise

> [!TIP]
> È anche possibile [scaricare](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usare il file ZIP che include la struttura delle cartelle per i pacchetti, gli script da usare e il modello di sequenza di attività da importare.

### <a name="create-the-monitoring-agent-package"></a>Creare il pacchetto dell'agente di monitoraggio

1. Scaricare l'agente di monitoraggio da <https://go.microsoft.com/fwlink/?LinkId=828603> .

2. Estrarre il pacchetto nella cartella **Pacchetto SRS v2 - Microsoft Monitoring Agent** aprendo una finestra del prompt dei comandi e immettendoMMASetup-AMD64.exe **/C:** al prompt dei comandi.

3. Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**

4. Immettere le informazioni seguenti per creare il pacchetto:

   - Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong>

   - Produttore<strong>: Microsoft Corporation</strong>

   - Versione<strong>: 8.1.11081.0</strong> (immettere la versione del file di installazione scaricato)

   - Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Microsoft Monitoring Agent pacchetto** e quindi selezionare **Avanti**.

5. Selezionare **Non creare un programma** e quindi avanti. 

6. Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.

7. Selezionare **Chiudi**.

### <a name="create-the-operating-system-updates-package"></a>Creare il pacchetto di aggiornamenti del sistema operativo

1. Nella cartella **SRS v2 - Pacchetto** aggiornamenti del sistema operativo creare un nuovo script di PowerShell denominato **Install-SRSv2-OS-Updates.ps1**.

2. Copiare lo script seguente nello script **Install-SRSv2-OS-Updates.ps1.** In alternativa, è possibile scaricare lo script Install-SRSv2-OS-Updates.ps1 da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Scaricare i pacchetti Windows aggiornare i pacchetti nella stessa cartella.
   > [!NOTE]
   > Al momento della pubblicazione di questo articolo, era necessario [solo KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) Selezionare [Configura una Microsoft Teams Rooms ,](console.md)per verificare se sono necessari altri aggiornamenti.

4. Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**

5. Immettere le informazioni seguenti per creare il pacchetto:
   -   Nome: **SRS v2 – Pacchetto di aggiornamenti del sistema operativo**
   -   Produttore: **Microsoft Corporation**
   -   Versione: **1.0.0**
   -   Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto** aggiornamenti del sistema operativo e quindi selezionare **Avanti.**

6. Selezionare **Non creare un programma** e quindi avanti. 

7. Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.

8. Selezionare **Chiudi**.

### <a name="create-the-root-certificate-package-optional"></a>Creare il pacchetto del certificato radice (facoltativo)

Questo pacchetto viene creato per distribuire il certificato radice per i dispositivi che non verranno aggiunti a un dominio di Active Directory. Creare questo pacchetto solo se si applicano entrambe le condizioni seguenti:
-   La distribuzione include Lync locale o Skype for Business Server.
-   Microsoft Teams Rooms sono configurate per lavorare in un gruppo di lavoro invece che in un membro di dominio.

1.  Copiare il certificato radice nella **cartella SRS v2 - Root Certificate Package.**

2.  Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**

3.  Immettere le informazioni seguenti per creare il pacchetto:
    -   Nome: **SRS v2 - Pacchetto di certificati radice**
    -   Produttore: *nome dell'organizzazione*
    -   Versione: **1.0.0**
    -   Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto** certificato radice e quindi selezionare **Avanti.**

4.  Selezionare **Non creare un programma** e quindi avanti. 

5.  Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.

6.  Selezionare **Chiudi**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Creare il pacchetto Microsoft Teams Rooms kit di distribuzione

1.  Scaricare l'ultima versione del **kit Microsoft Teams Rooms di distribuzione** da e <https://go.microsoft.com/fwlink/?linkid=851168> installarlo in una workstation.

2.  Copiare il contenuto **da C: \\ Programmi (x86) \\ Skype Room System Deployment Kit** nella cartella **SRS v2 - Pacchetto applicazioni SRS.**

3.  Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**

4.  Immettere le informazioni seguenti per creare il pacchetto:
    -   Nome: **SRS v2 - Pacchetto dell'applicazione SRS**
    -   Produttore: **Microsoft Corporation**
    -   Versione: **3.1.104.0** (immettere la versione del file di installazione scaricato)
    -   Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto** applicazioni SRS e quindi selezionare **Avanti.**
5.  Selezionare **Non creare un programma** e quindi avanti. 

6.  Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.

7.  Selezionare **Chiudi**.

### <a name="create-the-computer-name-assignment-package"></a>Creare il pacchetto di assegnazione del nome computer

1.  Nella cartella **SRS v2 - Set-SRSComputerName package** creare una nuova applicazione HTML denominata **Set-SRSComputerName.hta.**

2.  Copiare lo script seguente nel file **Set-SRSComputerName.hta.** In alternativa, è possibile scaricare il file Set-SRSComputerName.hta da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3.  Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**

4.  Immettere le informazioni seguenti per creare il pacchetto:

    -   Nome: **SRS v2 - Set-SRSComputerName pacchetto**

    -   Produttore: **Microsoft Corporation**

    -   Versione: **1.0.0**

    -   Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Set-SRSComputerName Package** e quindi selezionare **Avanti**.

5.  Selezionare **Non creare un programma** e quindi avanti. 

6.  Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.

7.  Selezionare **Chiudi**.

### <a name="create-the-sysprep-package"></a>Creare il pacchetto Sysprep

1. Nella cartella **SRS v2 - Pacchetto Sysprep** creare un nuovo file XML denominato **Unattend.xml** .

2. Copiare il testo seguente nel **Unattend.xml** file. In alternativa, è possibile scaricare il file Unattend.xml file da [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**

4. Immettere le informazioni seguenti per creare il pacchetto:
   -   Nome: **SRS v2 - Pacchetto Sysprep**
   -   Produttore: **Microsoft Corporation**
   -   Versione: **1.0.0**
   -   Selezionare la **casella di controllo Questo** pacchetto contiene file di origine, immettere il percorso della cartella **SRS v2 - Pacchetto Sysprep** e quindi selezionare **Avanti.**
5. Selezionare **Non creare un programma** e quindi avanti. 

6. Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.

7. Selezionare **Chiudi**.

### <a name="create-the-windows-10-enterprise-package"></a>Creare il Windows 10 Enterprise pacchetto

1.  Ottenere un Windows 10 Enterprise supporto x64 e copiare il file **install.wim** nella cartella **Operating Systems \\ Windows 10 Enterprise.**

2.  Nella console di Configuration Manager passare a **Software Library** Operating Systems \> **Operating System** \> **Images** e quindi selezionare **Add Operating System Image**.

3.  Specificare il percorso del file **install.wim** appena copiato e quindi scegliere **Avanti**.

4.  Aggiornare il **campo Versione** in modo che corrisponda al numero di build dell'immagine Windows 10 Enterprise e quindi selezionare **Avanti**.

5.  Esaminare la **pagina** Dettagli e quindi selezionare **Avanti.**

6.  Selezionare **Chiudi**.

Per altre informazioni, vedere [Gestire le immagini del sistema operativo con Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Creare Surface Pro pacchetti di driver di dispositivo

Microsoft Teams Rooms è supportato sia per Surface Pro che per Surface Pro 4. È necessario creare un pacchetto driver per ogni Surface Pro modello di driver presente nell'ambiente.

> [!IMPORTANT]
> I driver devono essere compatibili con la build Windows 10 Enterprise e con la Microsoft Teams Rooms del kit di distribuzione. Per altre informazioni, vedere Scaricare il firmware e i driver più [recenti per i dispositivi Surface](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e Configurare una [console.](console.md)

1.  Scarica i driver e il firmware più recenti.
    -   Per Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Per Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Estrarre il driver e il firmware scaricati. Aprire una finestra del prompt dei comandi e al prompt dei comandi immettere uno dei comandi seguenti:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  Nella console di Configuration Manager passare a Driver dei sistemi operativi della raccolta **software** e quindi selezionare \>  \> Importa **driver.**

4.  Selezionare Importa tutti i driver nel percorso di rete **seguente (UNC),** selezionare la cartella di origine, ad esempio C: \\ _Sources Drivers \\ \\ Surface Pro, quindi scegliere **Avanti**.

5.  Nella pagina **Specificare i dettagli per i** driver importati selezionare tutti i driver elencati, quindi selezionare Abilita questi driver e consentire ai computer di **installarli.**

6.  Seleziona **Categorie**, crea una nuova categoria che corrisponda al modello Surface, seleziona **OK** e quindi **seleziona Avanti**.

7.  Selezionare **Nuovo pacchetto**.

8.  Specificare il nome del pacchetto che corrisponde al modello Surface Pro, immettere un percorso di cartella in cui archiviare i file del pacchetto driver, selezionare **OK** e quindi **avanti.**

9.  Nella pagina **immagini di avvio** verificare che non sia selezionata alcuna immagine di avvio e quindi scegliere **Avanti**.

10. Selezionare **Chiudi**.

11. Passare a **Driver dei sistemi** operativi raccolta software , selezionare Crea cartella e immettere un nome di cartella corrispondente al modello di Surface Pro per cui sono stati importati i \>  \> driver. **\>**

12. Spostare tutti i driver importati nella cartella appena creata per semplificare l'esplorazione e il funzionamento.

> [!NOTE]
> Ripetere gli stessi passaggi per altri Surface Pro modelli disponibili. Per altre informazioni, vedere [Gestire i driver in Configuration Manager.](/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Creare un Microsoft Teams Rooms di configurazione

1.  Nella console di Configuration Manager passare a **Pacchetti di gestione** applicazioni raccolta software e quindi selezionare Crea \>  \>  **pacchetto.**

2.  Immettere le informazioni seguenti per creare il pacchetto:

    -   Nome: **SRS v2 - Configurare il pacchetto di installazione SRS**

    -   Produttore: **Microsoft Corporation**

    -   Versione: **1.0.0**

    -   Selezionare la **casella di controllo** Il pacchetto contiene i file di origine, immettere il percorso della cartella **SRS v2 - Configurazione configurazione SRS** e quindi selezionare **Avanti.**

3.  Selezionare **Non creare un programma** e quindi avanti. 

4.  Esaminare la **pagina Conferma le** impostazioni e quindi selezionare **Avanti**.

5.  Selezionare **Chiudi**.



## <a name="distribute-configuration-manager-packages"></a>Distribuire pacchetti di Configuration Manager

Tutti i pacchetti devono essere distribuiti ai server a cui è stato assegnato il ruolo di punto di distribuzione nella gerarchia di Configuration Manager. Seguire le istruzioni seguenti per avviare la distribuzione dei pacchetti.

1.  Distribuire pacchetti software.

    1.  Nella console di Configuration Manager passare a **Pacchetti di gestione applicazioni** \> **raccolta** \> **software**. Selezionare tutti i pacchetti software da distribuire e quindi **scegliere Distribuisci contenuto.**

    2.  Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.

    3.  Aggiungere all'elenco tutti i server dei punti di distribuzione (o gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) e quindi selezionare **Avanti**.

    4.  Selezionare **Avanti** e quindi **chiudi.**

2.  Distribuire pacchetti driver.

    1.  Nella console di Configuration Manager passare a **Pacchetti driver** dei sistemi operativi \> **della** \> **raccolta** software . Selezionare tutti i pacchetti driver da distribuire e quindi **scegliere Distribuisci contenuto**.

    2.  Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.

    3.  Aggiungere all'elenco tutti i server dei punti di distribuzione (o gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) e quindi selezionare **Avanti**.

    4.  Selezionare **Avanti** e quindi **chiudi.**

3.  Distribuire pacchetti del sistema operativo.

    1.  Nella console di Configuration Manager passare a **Software Library** Operating Systems \> **Operating System** \> **Images**. Selezionare tutte le immagini del sistema operativo da distribuire e quindi **scegliere Distribuisci contenuto.**

    2.  Esaminare l'elenco dei pacchetti e quindi selezionare **Avanti**.

    3.  Aggiungere all'elenco tutti i server dei punti di distribuzione (o gruppi di punti di distribuzione, a seconda della gerarchia di Configuration Manager) e quindi selezionare **Avanti**.

    4.  Selezionare **Avanti** e quindi **chiudi.**

> [!NOTE]
> La distribuzione dei pacchetti può richiedere del tempo, a seconda delle dimensioni del pacchetto, della gerarchia di Configuration Manager, del numero di server dei punti di distribuzione e della larghezza di banda disponibile nella rete.
> 
> Tutti i pacchetti devono essere distribuiti prima di iniziare a distribuire un'Microsoft Teams Rooms distribuzione.
> 
> È possibile esaminare lo stato della distribuzione del pacchetto nella console di Configuration Manager in Monitoraggio **stato** \> **distribuzione** \> **Stato contenuto**.

## <a name="configuration-manager-task-sequences"></a>Sequenze di attività di Configuration Manager

Le sequenze di attività con Configuration Manager consentono di automatizzare i passaggi per la distribuzione di un'immagine del sistema operativo in un computer di destinazione. Per distribuire un'unità di Microsoft Teams Rooms in modo automatico, creare una sequenza di attività che fa riferimento all'immagine di avvio usata per avviare il computer Microsoft Teams Rooms di destinazione, all'immagine del sistema operativo Windows 10 Enterprise da installare e a qualsiasi altro contenuto aggiuntivo, ad esempio altre applicazioni o aggiornamenti software.

### <a name="import-the-sample-task-sequence"></a>Importare la sequenza di attività di esempio

È possibile scaricare e importare facilmente una sequenza di attività di esempio e personalizzarla in base alle proprie esigenze.

1.  [**Scaricare**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la sequenza di attività di esempio e copiare il file ZIP scaricato in un percorso condiviso.
2.  Nella console di Configuration Manager passare a Sequenze di attività dei sistemi operativi della raccolta **software** \>  \> e quindi selezionare Importa **sequenza di attività.** 

3.  Selezionare **Sfoglia**, passare al percorso della cartella condivisa usato nel passaggio 1, selezionare il file .zipdistribuzione **di Microsoft Teams Rooms (EN-US)** e quindi **scegliere Avanti**.

4.  Impostare **Azione** **su Crea nuovo** e quindi selezionare **Avanti.**

5.  Confermare le impostazioni e quindi selezionare **Avanti**.

6.  Selezionare **Chiudi**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Verificare che i pacchetti di riferimento siano collegati correttamente a ogni passaggio della sequenza di attività.

1. Selezionare la sequenza di attività importata e quindi scegliere **Modifica**.

    Si apre l'Editor sequenza di attività e vengono visualizzati tutti i passaggi sequenziali necessari per distribuire e configurare un'Microsoft Teams Rooms lavoro.

2. Eseguire ogni passaggio e completare gli aggiornamenti consigliati:

   1. **Riavvia in Windows PE:** questo passaggio riavvia e quindi avvia il computer Windows PXE. Per questo passaggio non sono necessarie modifiche.

   2. **Disco di partizione 0 - UEFI:** questo passaggio cancella la configurazione del disco e crea le partizioni in base alle impostazioni configurate. È consigliabile non apportare modifiche a questo passaggio.

   3. **Imposta nome computer SRS:** questo passaggio include un'applicazione HTML per fornire un'interfaccia utente per impostare un nome di computer per l'unità di Microsoft Teams Rooms durante la distribuzione.
      -  Si tratta di un passaggio facoltativo, ma può essere disabilitato solo se si vuole gestire la denominazione dei computer tramite un processo alternativo.
      -  Verificare che il **pacchetto SRS v2 - Set-SRSComputerName** sia selezionato. In caso contrario, passare al pacchetto e selezionarlo.

   4. **Applica sistema operativo:** questo passaggio specifica l'immagine del sistema operativo da distribuire e il file di risposte Sysprep automatico da usare.
      -  Verificare che sia selezionata la Windows 10 Enterprise file di immagine del sistema operativo corretto.
      -  Verificare che **l'opzione** Usa un file di risposte automatico o Sysprep per un'installazione personalizzata sia abilitata ed è selezionato il pacchetto **SRS v2 - Sysprep.** Assicurarsi inoltre che **Nome file** sia impostato su **unattend.xml**.

   5. **Applica Windows Impostazioni:** questo passaggio raccoglie informazioni sull'Windows installazione.
      -  Fornire informazioni sulle licenze e sulla registrazione, tra cui il codice Product Key, la password dell'account dell'amministratore locale e il fuso orario (a seconda delle esigenze).

   6. **Applica nome Impostazioni** rete: questo passaggio consente di specificare un nome di dominio e un'unità organizzativa del gruppo di lavoro o di Active Directory.
      > [!NOTE]
      > Vedere Skype considerazioni sull'aggiunta a un dominio room [system](domain-joining-considerations.md) per le azioni consigliate da eseguire nella distribuzione di Microsoft Teams Rooms come membri di un dominio directory Actve.
   7. **Applica driver:** Questo passaggio e i relativi passaggi secondari vengono usati per distribuire i driver di dispositivo e il firmware applicabili in base al modello Surface Pro disponibile. Aggiornare ogni passaggio per specificare il pacchetto driver pertinente associato a questa distribuzione.
      -   Ogni pacchetto di driver è configurato per sfruttare Windows filtri di Strumentazione gestione Windows (WMI) per distribuire driver e firmware pertinenti in base alla Surface Pro e al modello.
      -   È consigliabile non modificare la configurazione di questi driver, altrimenti la distribuzione potrebbe non riuscire.

   8. **Configurare Windows e Configuration Manager:** questo passaggio distribuisce e configura il client di Configuration Manager. Aggiornare questo passaggio per specificare il pacchetto client predefinito di Configuration Manager.

   9. **Installa certificato radice:** questo passaggio distribuisce il certificato radice per i dispositivi non appartenenti al dominio e pertanto è facoltativo e disabilitato per impostazione predefinita.
      -   Abilitare questo passaggio se è necessario distribuire un certificato radice nelle unità Microsoft Teams Rooms radice.
      -   Se è necessario eseguire questo passaggio, verificare che l'opzione **SRS v2 - Root Certificate Package** e Disable **64-bit file system redirection** siano selezionate.

   10. **Installare e configurare l'agente** di monitoraggio: questo passaggio installa la versione a 64 bit dell'agente di monitoraggio di Microsoft Azure e configura l'agente per la connessione all'area di lavoro Log Analytics.
       -   Questo passaggio è disabilitato per impostazione predefinita. Abilitare questo passaggio solo se si userà l'agente di monitoraggio per monitorare l'integrità delle unità Microsoft Teams Rooms lavoro.
       -   Modificare questo passaggio e aggiornare i parametri della riga di comando per specificare l'ID area **di lavoro** e la **chiave dell'area di lavoro.**
       -   Per altre informazioni su come ottenere l'ID area di lavoro di Operations Management Suite e la chiave primaria, vedere Configurare i dispositivi di test per il monitoraggio di [Azure.](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)
       -   Verificare che **l'opzione SRS v2 – Microsoft Monitoring Agent pacchetto** e disabilita il reindirizzamento del file system a **64 bit** sia selezionata.
       -   Per altre informazioni sul monitoraggio dell'integrità della distribuzione di Microsoft Teams Rooms, vedere Pianificare la gestione di Microsoft Teams Rooms con Monitor di [Azure,](azure-monitor-plan.md)Distribuire la gestione [Microsoft Teams Rooms](azure-monitor-deploy.md) con Monitoraggio di Azure e Gestire i dispositivi Microsoft Teams Rooms con Monitor di [Azure.](azure-monitor-manage.md)

   11. **Copia file di configurazione SRS v2:** questo passaggio copia i file di configurazione e di configurazione necessari dal kit di distribuzione di Microsoft Teams Rooms nel disco rigido locale. Per questo passaggio non è necessaria alcuna personalizzazione.
       -   Verificare che siano selezionati **il pacchetto dell'applicazione SRS v2 - SRS** e il reindirizzamento del file system a **64 bit.**

   12. **Install-SRSv2-OS-Updates:** questo passaggio distribuisce tutti gli aggiornamenti obbligatori del sistema operativo necessari con la Microsoft Teams Rooms distribuzione. Eseguire le operazioni seguenti:
       -   Selezionare [Configura una Microsoft Teams Rooms per](console.md) vedere quali aggiornamenti sono necessari.
       -   Verificare che il **pacchetto di aggiornamenti del sistema operativo SRS v2** includa tutti gli aggiornamenti necessari.
       -   Verificare che sia **selezionato il pacchetto SRS v2 - Aggiornamenti** del sistema operativo.
       -   Verificare che i criteri di esecuzione di PowerShell siano impostati su **Ignora**.

   13. **Riavvia computer:** questo passaggio riavvia il computer dopo l'installazione degli aggiornamenti obbligatori del sistema operativo. Per questo passaggio non è necessaria alcuna personalizzazione.

   14. **Configurazione Windows componenti:** questo passaggio configura le caratteristiche Windows componenti. Per questo passaggio non è necessaria alcuna personalizzazione.

   15. **Riavvia computer:** questo passaggio riavvia il computer dopo Windows le funzionalità di rete. Per questo passaggio non è necessaria alcuna personalizzazione.

   16. **Aggiungi utente Skype** locale: questo passaggio crea l'account Skype locale usato per accedere automaticamente a Windows e avviare l'applicazione Microsoft Teams Rooms locale. A questo passaggio non è associato alcun pacchetto software e non è necessaria alcuna personalizzazione.

   17. **Configurare e configurare l'applicazione SRS:** questo passaggio configura l Microsoft Teams Rooms installazione dell'applicazione per l'avvio successivo del sistema operativo.
       -   Verificare che **l'opzione SRS v2 - Configura pacchetto** di installazione SRS e Disabilita il reindirizzamento del file system a **64 bit** sia selezionata.

> [!IMPORTANT]
> È molto importante che i passaggi della sequenza di attività siano nell'ordine specificato. La modifica dell'ordine dei passaggi o la configurazione di passaggi aggiuntivi potrebbero interrompere la distribuzione.
>
> **Il passaggio dell'applicazione SRS** deve essere l'ultimo passaggio della sequenza di attività, altrimenti la distribuzione potrebbe non riuscire.

### <a name="create-deployment-for-the-task-sequence"></a>Creare la distribuzione per la sequenza di attività

1. Selezionare la sequenza di attività e quindi scegliere **Distribuisci**.

2. Selezionare **Sfoglia per** selezionare la raccolta di destinazione per la distribuzione.

3. Selezionare **Tutti i computer sconosciuti** e quindi scegliere **OK.**

4. Selezionare **Avanti**.

5. Selezionare **Disponibile** **nell'elenco a** discesa Scopo.

6. Selezionare **Solo elementi multimediali e PXE** nell'elenco Rendi disponibile **per** il seguente e quindi selezionare **Avanti**.
   > [!WARNING]
   > È molto importante che **Scopo** sia impostato su **Disponibile**. Assicurarsi che **l'opzione Scopo** **NON sia** impostata su **Obbligatorio**. Assicurarsi inoltre di selezionare Solo elementi multimediali **e PXE** nell'elenco **Rendi disponibile per l'elemento seguente.**
   >
   > L'impostazione di questi valori su un altro valore potrebbe causare l'Microsoft Teams Rooms di distribuzione di tutti i computer all'avvio.
7. Non specificare alcuna pianificazione e selezionare **Avanti**.

8. Non modificare nulla all'interno **della sezione Esperienza** utente e selezionare **Avanti**.

9. Non modificare nulla all'interno **della sezione Avvisi** e selezionare **Avanti**.

10. Non modificare nulla all'interno **della sezione Punti di** distribuzione e selezionare **Avanti**.

11. Confermare le impostazioni e quindi selezionare **Avanti**.

12. Selezionare **Chiudi**.

**Convalidare e risolvere i problemi della soluzione**

Dopo aver completato le sequenze di Microsoft Endpoint Configuration Manager attività, è necessario eseguire un'esecuzione dei test per verificare che la sequenza di attività sia in grado di distribuire e configurare le Microsoft Teams Rooms lavoro.

1.  Connessione il dispositivo di test alla rete cablata usando uno degli adattatori Ethernet supportati o il Dock di Surface. Se la funzionalità di avvio PXE non è stata configurata per l'ambiente, è possibile usare l'immagine di avvio nell'unità flash USB creata in precedenza per eseguire l'avvio da USB e connettersi a Configuration Manager. [](/configmgr/osd/deploy-use/create-bootable-media)

2.  Accedere al firmware e avviare l'avvio PXE:

    1.  Assicurati che il dispositivo Surface sia spento.

    2.  Tieni premuto il **pulsante Volume** su.

    3.  Premere e rilasciare il **pulsante** Alimentazione.

    4.  Dopo l'avvio del dispositivo, rilasciare il **pulsante Volume** su.

    5.  Selezionare **Configurazione di avvio**.

    6.  Eseguire una delle operazioni seguenti:

        -   Selezionare **Avvio PXE** e trascinarlo all'inizio dell'elenco. In alternativa, è possibile scorrere rapidamente verso sinistra sulla scheda di rete per avviare immediatamente il dispositivo. Questo non influisce sull'ordine di avvio.
        -   Selezionare l'unità flash USB che contiene il supporto di avvio.

3.  Selezionare **Esci** e quindi selezionare **Riavvia adesso.**

4.  Quando richiesto, selezionare **INVIO per** il servizio di avvio di rete.

5.  Windows Pe verrà caricato in memoria e verrà avviata la Creazione guidata Sequenza attività. Selezionare **Avanti** per continuare.

6.  Selezionare la sequenza di attività importata in precedenza e quindi scegliere **Avanti**.

7.  Dopo l'applicazione della configurazione del disco, verrà richiesto di specificare un nome di computer per il dispositivo. L'interfaccia utente visualizza un nome di computer consigliato in base al numero di serie del Surface Pro dispositivo. È possibile accettare il nome proposto o specificarne uno nuovo. Seguire le istruzioni visualizzate nella schermata di assegnazione del nome del computer. Quando si seleziona **Accetta**, viene avviata la distribuzione.

8.  Il resto del processo di distribuzione è automatico e non richiede altri input dell'utente.

9.  Al termine della configurazione del dispositivo da parte della sequenza di attività di distribuzione, verrà visualizzata la schermata di configurazione seguente che chiede di configurare le impostazioni Microsoft Teams Rooms'applicazione.

    ![Schermata di configurazione iniziale per l Microsoft Teams Rooms appalto.](../media/room-systems-scale-image2.png)

10.  Collegare il Surface Pro nella console Microsoft Teams Rooms e configurare le impostazioni dell'applicazione.

11.  Verificare che le funzionalità elencate nella [Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funzionino nel dispositivo distribuito.


Per risolvere i problemi relativi a un'installazione non riuscita, controllare il file **SMSTS.log,** che registra tutti i passaggi eseguiti in una sequenza di attività di Configuration Manager.

Il file SMSTS.log viene archiviato in uno dei diversi percorsi, a seconda della fase del processo di compilazione. Controllare la tabella seguente per identificare il percorso del file SMSTS.log.


| **Fase di distribuzione**                                                            | **Percorso del log della sequenza di attività**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, prima del formato HDD                                                        | X: \\ Windows \\ temp \\ smstslog \\ smsts.log             |
| WinPE, dopo il formato HDD                                                         | C: \\ _SMSTaskSequence \\ log \\ Smstslog \\ smsts.log    |
| Sistema operativo distribuito prima dell'installazione dell'agente di Configuration Manager | c: \\ _SMSTaskSequence \\ log \\ smstslog \\ smsts.log    |
| Sistema operativo e agente di Configuration Manager distribuiti                   | %windir% \\ System32 \\ ccm \\ registra \\ Smstslog \\ smsts.log |
| Esecuzione della sequenza di attività completata                                                | %windir% \\ System32 \\ ccm \\ registra \\ smsts.log           |

> [!TIP]
> È possibile selezionare **F8** in qualsiasi momento durante la sequenza di attività per aprire una console dei comandi e quindi accedere al file SMSTS.log.

Per risolvere i problemi di avvio PXE, controllare i due file di log nel server di Configuration Manager specifici per le azioni PXE:

-   **Pxecontrol.log**, che si trova nella directory dei log di installazione di Configuration Manager

-   **Smspxe.log**, che si trova nella directory dei log di Configuration Manager Management Point (MP)

Per un elenco completo dei file di log che è possibile usare per risolvere ulteriormente i problemi dell'installazione di Configuration Manager, vedere le informazioni di riferimento Microsoft Endpoint Configuration Manager [file di log.](/configmgr/core/plan-design/hierarchy/log-files)
