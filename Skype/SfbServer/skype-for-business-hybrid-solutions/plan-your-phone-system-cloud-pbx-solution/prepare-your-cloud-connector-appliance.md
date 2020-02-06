---
title: Predisporre l'appliance di Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'uso con il sistema telefonico in Office 365 (cloud PBX).
ms.openlocfilehash: 6e6cb71353dc2a2339fe92ce45d0cd3dee9f21a1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814434"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Predisporre l'appliance di Cloud Connector

Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'uso con il sistema telefonico in Office 365 (cloud PBX).

Questa sezione descrive come ottenere i file di installazione di Skype for Business Cloud Connector Edition, installare il software Cloud Connector e preparare l'appliance per il Cloud Connector per la distribuzione. Dopo aver completato tutti i passaggi di questa sezione, si sarà pronti per distribuire il connettore Cloud per un singolo sito o più siti. Se si dispone di una distribuzione di Cloud Connector esistente e non è stato ancora eseguito l'aggiornamento a Cloud Connector versione 2,1, vedere [eseguire l'aggiornamento a una nuova versione di Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft supporta la versione corrente di Cloud Connector Edition, versione 2,1. Se è stato configurato l'aggiornamento automatico, il Cloud Connector verrà aggiornato automaticamente. Se è stato configurato l'aggiornamento manuale, sarà necessario eseguire l'aggiornamento alla versione 2,1 entro 60 giorni dalla relativa versione. Microsoft sosterrà la versione precedente per 60 giorni dopo il rilascio di 2,1 per consentire il tempo necessario per l'aggiornamento. 

> [!NOTE]
> Per Cloud Connector versione 2,1 e successive, l'accessorio host deve avere .NET Framework 4.6.1 o versioni successive installate. 

> [!IMPORTANT]
> Per la distribuzione corretta, quando si eseguono i cmdlet per configurare Skype for Business Cloud Connector Edition, usare sempre la stessa sessione di console di quella avviata. Evitare di passare a sessioni diverse durante la distribuzione e la configurazione. 

> [!NOTE]
> Ci sono alcuni passaggi da eseguire solo per il primo appliance della distribuzione: creare una condivisione per la directory del sito, scaricare i bit e preparare un file VHDX (Virtual Hard disk) dall'immagine ISO di Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Scaricare il programma di installazione di Skype for Business Cloud Connector Edition

1. Nel server host in cui verrà eseguita la VM Connector cloud, scaricare i file di installazione [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller):. 

    > [!IMPORTANT]
    > Il server host deve essere in grado di accedere a Internet durante l'installazione di Cloud Connector perché vengono scaricati altri file durante l'installazione. 

2. Eseguire il programma di installazione e accettare i valori predefiniti durante l'installazione.

3. Verificare che l'installazione sia stata completata correttamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Verificare l'installazione e configurare l'ambiente

1. Aprire una console di PowerShell come amministratore e verificare che i cmdlet Skype for Business Cloud Connector Edition siano disponibili con il cmdlet seguente:

   ```powershell
   Get-Command *-Cc*
   ```

    Il comando deve restituire un elenco di cmdlet per Skype for Business Cloud Connector Edition.

2. I file VHD, SfBBits e VersionInfo verranno archiviati nella **directory del sito**.

    È possibile trovare la posizione della **directory del sito** con il cmdlet seguente:

   ```powershell
   Get-CcSiteDirectory
   ```

    Il comando deve restituire una posizione nel file System. La posizione può essere una cartella locale o una condivisione file. Il percorso predefinito della **directory del sito** è:%UserProfile%\CloudConnector\SiteRoot. La posizione predefinita deve essere modificata in una condivisione file nel primo appliance creato in ogni sito.

    La posizione selezionata deve essere:

   - Creato nel primo appliance creato in ogni sito.

   - Una cartella condivisa accessibile dagli altri server host nello stesso sito.

     Per impostare la **directory del sito** su una posizione diversa da quella predefinita, eseguire il cmdlet seguente:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Se si sta distribuendo la disponibilità elevata (HA) per il sito, assicurarsi di eseguire il cmdlet per impostare la **directory del sito** nella stessa posizione in ogni server host all'interno del sito.

    Quando si accede e si distribuisce ogni appliance nel sito, verificare che l'account di accesso corrente disponga dell'accesso corretto alla **directory del sito**.

3. La **directory appliance** è la directory radice locale di lavoro per Skype for Business Cloud Connector Edition e la posizione in cui vengono salvati i certificati, le istanze e i registri esterni. Il percorso predefinito è:%USERPROFILE%\CloudConnector\ApplianceRoot.

    Per trovare la posizione della **directory appliance**, eseguire il cmdlet seguente:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Per impostare la **directory appliance** su una posizione diversa da quella predefinita, eseguire il cmdlet seguente:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    La directory appliance deve essere impostata su una cartella locale nell'appliance. Devi impostare la **directory appliance** solo prima di avviare la distribuzione di Skype for Business Cloud Connector Edition. Se viene modificata dopo la distribuzione, sarà necessario ridistribuire il server host.

    > [!IMPORTANT]
    > Il percorso della **directory appliance** non deve contenere spazi.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Impostare il percorso per il certificato perimetrale esterno

- Eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato perimetrale esterno. Ad esempio: C:\certs\cce\ap.contoso.com.pfx. Il certificato deve contenere chiavi private.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Tieni presente che il parametro-target è specifico delle versioni 1.4.2 e successive. 

    Specificare il percorso completo del certificato esterno, incluso il nome del file. Il certificato può essere archiviato localmente o in una condivisione file. Se il certificato è archiviato in una cartella condivisa, la cartella condivisa deve essere creata nel primo dispositivo di ogni sito e deve essere accessibile da altri dispositivi appartenenti allo stesso sito. Questo cmdlet copia il certificato esterno nella **directory appliance**.

    > [!IMPORTANT]
    > **Se è stato aggiornato a Cloud Connector versione 1.4.2 o successiva**, verificare che il certificato esterno preparato contenga le chiavi private e la catena di certificati completa, incluso il certificato della CA radice e i certificati intermedi della CA. **Se non è stato ancora aggiornato a Cloud Connector versione 1.4.2**, verificare che il certificato esterno preparato contenga chiavi private. Questo certificato esterno deve essere emesso da un'autorità di certificazione considerata attendibile da Windows per impostazione predefinita.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Impostare il percorso per il certificato del gateway PSTN/SBC esterno

Se si usa TLS tra il Mediation Server e il gateway/SBC PSTN, eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato del gateway. Ad esempio: C:\certs\cce\sbc.contoso.com.cer. Il certificato deve contenere la CA radice e la catena intermedia per il certificato assegnato al gateway:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Tieni presente che il parametro-target è specifico delle versioni 1.4.2 e successive. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Creare switch virtuali in gestione Hyper-V

1. Aprire **Hyper-V Manager** > **Virtual Switch Manager**e selezionare **nuovo Virtual Switch Manager**.

2. Creare uno switch virtuale esterno e associarlo alla scheda di rete fisica connessa al dominio di rete interno:

    Selezionare **Consenti sistema operativo di gestione per condividere questa scheda di rete** per questo switch virtuale.

3. Creare un interruttore virtuale esterno e associarlo alla scheda di rete fisica che viene instradata a Internet:

    Deselezionare Consenti il **sistema operativo di gestione per condividere questa scheda di rete** per questo switch virtuale.

4. Impostare il nome dell'opzione che connette la rete perimetrale al dominio di rete interno **SFB CCE corpnet**.

    Impostare il nome dell'opzione che connette la rete perimetrale a Internet **SFB CCE Internet switch**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aggiornare il file di configurazione CloudConnector. ini

Preparare il file CloudConnector. ini usando le informazioni raccolte in [determinare i parametri di distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) nell'argomento [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .

Per aggiornare il file, eseguire prima di tutto il cmdlet seguente per ottenere il modello di esempio (CloudConnector. Sample. ini):

```powershell
Export-CcConfigurationSampleFile
```

Il modello di esempio è archiviato nella **directory appliance**.

Dopo averla aggiornata con i valori per l'ambiente, salvare il file come CloudConnector. ini nella **directory appliance**. Puoi eseguire **Get-CcApplianceDirectory** per determinare il percorso della **directory appliance**.

Quando si aggiorna il file ini, tenere presente quanto segue:

> [!NOTE]
> Non tutti i valori per il file ini sono discussi in questa sezione, ma solo quelli con una considerazione particolare sono descritti qui. Per un elenco completo, vedi la sezione [determinare i parametri di distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dell'argomento [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Per altre informazioni sui valori che devono essere modificati per altri dispositivi o nuovi siti, vedere [sito singolo con elevata disponibilità (ha) rispetto alle distribuzioni multisito](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) nell'argomento [distribuire più siti in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** Il valore predefinito è **Microsoft1**. È necessario aggiornarlo prima di distribuire Cloud Connector, perché quando si esegue **Register-CcAppliance** per registrare un dispositivo in un sito nuovo o esistente, il cmdlet userà **nomesito** per determinare il sito da registrare.

     Se si vuole registrare l'appliance in un nuovo sito, il valore di **nomesito** deve essere univoco e diverso dai siti esistenti. Se si vuole registrare l'appliance in un sito esistente, il valore per **siteName** nel file ini deve corrispondere al nome definito nella configurazione del tenant di Office 365. Se si sta copiando un file di configurazione da un sito a un altro, assicurarsi di aggiornare di conseguenza il valore per **siteName** per ogni sito.

- **NomeServer:** Il nome del server non deve contenere il nome di dominio e deve essere limitato a 15 caratteri.

- **HardwareType:** Se non si imposta o non si lascia il valore null, verrà usato il valore predefinito **Normal** . Usare **Normal** se si prevede di distribuire la versione più grande di Cloud Connector per supportare le chiamate simultanee di 500 per ogni computer host, come descritto in [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Usare **Minimum** per una distribuzione più piccola che supporta le chiamate simultanee di 50.

- **Switch virtuali Internet/corpnet/Management:**: aggiungere il nome delle opzioni virtuali create. Per l'opzione di gestione virtuale, lascia il valore predefinito. Lo script di distribuzione creerà l'opzione di gestione virtuale all'inizio della distribuzione ed eliminarla al termine della distribuzione.

- **ManagementIPPrefix:** ManagementIPPrefix nella sezione rete deve essere una subnet diversa da altri IPs interni. Ad esempio, come viene visualizzato il valore predefinito, ManagementIPPrefix è 192.168.213.0, mentre AD IPAddress è 192.168.0.238.

    Gli script di distribuzione creano una scheda di rete di gestione in ogni macchina virtuale, assegnano un IP di gestione e la collegano a un interruttore virtuale di gestione. Questo consente al server host di connettersi e gestire ogni macchina virtuale tramite questa rete di gestione. L'opzione di gestione virtuale viene eliminata al termine della distribuzione.

- **Configurazioni specifiche della VM di base:** Le impostazioni in questa sezione devono essere configurate per il cmdlet **Convert-CcIsoToVhdx** .

    Durante la preparazione delle immagini di base della VM, la VM di base verrà connessa allo switch di rete interna. Le impostazioni seguenti sono critiche per consentire alla VM di accedere a Internet:

  - Comune BaseVMIP: l'indirizzo IP di corpnet da assegnare alla VM di base.

  - Rete CorpnetDefaultGateway: il gateway predefinito da assegnare alla VM di base.

  - Rete CorpnetDNSIPAddress: l'indirizzo IP DNS da assegnare alla VM di base.

  - Rete WSUSServer: l'indirizzo IP del servizio di aggiornamento di Windows Server.

  - Rete WSUSStatusServer: l'indirizzo IP del server di stato del servizio Windows Server Update.

  - Rete EnableReferSupport: Questo definirà se il supporto SIP REFER è abilitato o disabilitato nella configurazione trunk per il tuo IP/PBX.

- **IPs interno:**

  - Verificare che CorpnetIPPrefixLength della subnet mask sia corretto.

  - Verificare che non ci siano conflitti IP per questi IPs interni.

- **IPs esterni:**

  - Per MR Public IP: specificare ExternalMRIPs per non NAT o ExternalMRPublicIPs per NAT.

  - ExternalSIPIPs e ExternalMRIPs possono essere uguali.

  - Verificare che InternetIPPrefixLength della subnet mask sia corretto.

  - Verificare che non ci siano conflitti IP per questi IPs esterni.

- **Gateway**

  - Se si ha un solo gateway, rimuovere la sezione per il gateway secondario. Se sono presenti più di due gateway, creare altre sezioni copiando e incollando quello esistente e quindi aggiornando il testo.

  - Verificare che l'indirizzo IP e la porta dei gateway siano corretti.

  - Per supportare il livello HA del gateway PSTN, lascia il gateway secondario e Aggiungi eventuali gateway aggiuntivi che userai. È possibile copiare e incollare una voce esistente e quindi aggiornarla.

- Facoltativamente, puoi aggiornare il valore LocalRoute per limitare i numeri di chiamata in uscita.

## <a name="download-the-bits-to-the-site-directory"></a>Scaricare i bit nella directory del sito

Eseguire il cmdlet seguente per scaricare i file di informazioni sulla versione e i bit nella **directory del sito**:

```powershell
Start-CcDownload
```

> [!NOTE]
> È necessario eseguire questo passaggio solo per la prima Appliance. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparare il disco virtuale di base (VHDX) dal file ISO scaricato

Questo passaggio prepara un file VHDX (Virtual Hard disk) dall'immagine ISO di Windows Server 2012. Il VHDX verrà usato per creare macchine virtuali durante la distribuzione. Verrà creata una macchina virtuale temporanea (VM di base) e il file ISO verrà installato in Windows Server 2012. Dopo la creazione della VM, verranno installati alcuni componenti necessari e verrà applicato l'ultimo aggiornamento di Windows. Alla fine, la VM di base verrà generalizzata (Sysprep) e sarà pulita, lasciando solo il file del disco virtuale generato.

> [!NOTE]
> È necessario eseguire questo passaggio solo per la prima Appliance. 

Prima di procedere con questo passaggio, verificare che l'opzione corpnet sia stata creata. Verificare inoltre che le impostazioni seguenti siano configurate correttamente nel file CloudConnector. ini:

- Rete CorpnetSwitchName

- Comune BaseVMIP

- Rete CorpnetIPPrefixLength

- Rete CorpnetDefaultGateway

- Rete CorpnetDNSIPAddress

Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per convertire l'immagine ISO in un disco rigido virtuale (VHD):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Specificare il percorso completo, incluso il nome del file, nell'immagine ISO. Ad esempio: C:\ISO\WindowsServer2012R2.iso.

Il file VHD creato è archiviato nella cartella \Bits\VHD **directory del sito** . Puoi ottenere il percorso della directory del **sito** eseguendo il **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Per impostazione predefinita, le impostazioni proxy non sono configurate nella VM di base. Se è necessario un proxy nell'ambiente di rete per aggiornare la VM tramite Windows Update, è necessario aggiungere il parametro-PauseBeforeUpdate quando si esegue "Convert-CcIsoToVhdx". Lo script verrà sospeso prima di Windows Update e si avrà la possibilità di impostare manualmente proxy sulla VM. Dopo l'installazione del proxy e la VM può accedere a Internet, è possibile riprendere lo script per completare i passaggi rimanenti. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Creare VHD per una distribuzione multisito

Si tratta di un passaggio facoltativo che si applica solo alle distribuzioni multisito.

Se si sta distribuendo una distribuzione multisito, non è necessario convertire la ISO in un VHD per ogni sito. È possibile copiare il VHDX creato per il primo sito nel server host per un secondo sito.

 Copiare il file nella stessa posizione del file (cartella **directory** \Bits\VHD) e con lo stesso nome file nel server host per un altro sito.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Impostare i criteri di esecuzione di PowerShell su RemoteSigned

Gli script di PowerShell forniti richiedono che il criterio di esecuzione sia impostato su RemoteSigned. Per visualizzare l'impostazione corrente, aprire una console di PowerShell come amministratore e quindi eseguire il cmdlet seguente:

```powershell
Get-ExecutionPolicy
```

Se non è impostato su "RemoteSigned", eseguire il cmdlet seguente per modificarlo:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Modificare i criteri di gruppo locali nel computer host (versioni 1.4.1 e precedenti)

> [!NOTE]
> Questa attività non è necessaria per le versioni 1.4.2 e successive del connettore Cloud. 

L'account CceService viene creato durante la distribuzione di Skype for Business Cloud Connector Edition. Esegue il servizio di gestione dei Cloud Connector e richiede l'autorizzazione per disinstallare cloudconnector. msi. È necessario modificare l'impostazione di criteri di gruppo nel computer host del Cloud Connector per specificare che il registro di sistema dell'utente non deve essere scaricato quando l'utente si disconnette. Eseguire la procedura seguente:

### <a name="to-change-the-group-policy-setting"></a>Per modificare l'impostazione di criteri di gruppo

1. Aprire l' **Editor criteri di gruppo** eseguendo gpedit. msc.

2. In **Editor criteri di gruppo**passare a modelli amministrativi > sistema > UserProfile > non scaricare con forza il registro utenti a fine sessione utente. 

3. Imposta il valore su **Enabled**.

## <a name="set-up-your-office-365-tenant"></a>Configurare il tenant di Office 365

È necessario un tenant di Office 365 con Skype for business online e il sistema telefonico in Office 365. Verificare che il tenant sia configurato e configurato prima di provare a usare Cloud Connector.

Alcuni passaggi di configurazione di Office 365 richiedono l'uso di PowerShell remoto tenant (TRP) per configurare il tenant di Office 365. **Questa operazione deve essere installata nel server host.** È possibile scaricare il modulo Skype for business online per PowerShell da: [Skype for business online, modulo di Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Creare un account di amministratore dedicato di Skype for business per la gestione di Cloud Connector online, ad esempio CceOnlineManagmentAdministrator. Questo account verrà usato da appliance per aggiungere o rimuovere Appliance, abilitare o disabilitare l'aggiornamento automatico del sistema operativo, abilitare o disabilitare l'aggiornamento automatico binario. Impostare la password per l'account in modo che non scada mai per non doverla modificare per il servizio ogni volta che scade.


