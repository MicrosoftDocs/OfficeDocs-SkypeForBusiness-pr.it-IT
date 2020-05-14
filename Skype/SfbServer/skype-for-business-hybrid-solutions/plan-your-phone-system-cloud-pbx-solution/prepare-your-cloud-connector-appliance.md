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
description: Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'utilizzo con il sistema telefonico (cloud PBX).
ms.openlocfilehash: d00002719ed8aaac7d0f0fb0e5ceb5722acc289c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220066"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Predisporre l'appliance di Cloud Connector

Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'utilizzo con il sistema telefonico (cloud PBX).

In questa sezione viene descritto come ottenere i file di installazione di Skype for Business Cloud Connector Edition, installare il software Cloud Connector e preparare l'accessorio Cloud Connector per la distribuzione. Dopo aver completato tutti i passaggi illustrati in questa sezione, sarà possibile distribuire il connettore Cloud per un singolo sito o più siti. Se si dispone di una distribuzione del connettore cloud esistente e non è stato ancora eseguito l'aggiornamento a Cloud Connector versione 2,1, vedere [upgrade to a New Version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft supporta la versione corrente di Cloud Connector Edition, versione 2,1. Se è stato configurato l'aggiornamento automatico, il connettore Cloud verrà aggiornato automaticamente. Se è stata configurata l'aggiornamento manuale, è necessario eseguire l'aggiornamento alla versione 2,1 entro 60 giorni dalla relativa versione. Microsoft supporterà la versione precedente per 60 giorni dopo il rilascio di 2,1 per consentire il tempo necessario per l'aggiornamento. 

> [!NOTE]
> Per il connettore Cloud versione 2,1 e versioni successive, è necessario che l'accessorio host disponga di .NET Framework 4.6.1 o versioni successive. 

> [!IMPORTANT]
> Per una distribuzione corretta, quando si eseguono i cmdlet per configurare Skype for Business Cloud Connector Edition, utilizzare sempre la stessa sessione di console di quella in cui è stato avviato. Evitare di passare a sessioni diverse durante la distribuzione e la configurazione. 

> [!NOTE]
> Esistono alcuni passaggi da eseguire solo per il primo dispositivo nella distribuzione: creazione di una condivisione per la directory del sito, download dei bit e preparazione di un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Scaricare il programma di installazione di Skype for Business Cloud Connector Edition

1. Nel server host in cui verranno eseguite le macchine virtuali dei connettori cloud, scaricare i file di installazione: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > Il server host deve essere in grado di accedere a Internet durante l'installazione del connettore cloud perché sono stati scaricati ulteriori file durante l'installazione. 

2. Eseguire il programma di installazione e accettare i valori predefiniti durante l'installazione.

3. Verificare che l'installazione sia stata completata correttamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Verifica dell'installazione e della configurazione dell'ambiente

1. Aprire una console di PowerShell come amministratore e verificare che i cmdlet di Skype for Business Cloud Connector Edition siano disponibili utilizzando il cmdlet seguente:

   ```powershell
   Get-Command *-Cc*
   ```

    Il comando deve restituire un elenco di cmdlet per Skype for Business Cloud Connector Edition.

2. I file VHD, SfBBits e VersionInfo verranno archiviati nella **directory del sito**.

    È possibile trovare il percorso della **directory del sito** con il cmdlet seguente:

   ```powershell
   Get-CcSiteDirectory
   ```

    Il comando deve restituire una posizione nel file System. Il percorso può essere una cartella locale o una condivisione file. Il percorso predefinito della **directory del sito** è:%UserProfile%\CloudConnector\SiteRoot. Il percorso predefinito deve essere modificato in una condivisione file sul primo dispositivo creato in ogni sito.

    Il percorso selezionato deve essere:

   - Creato nel primo dispositivo creato in ogni sito.

   - Una cartella condivisa accessibile dagli altri server host nello stesso sito.

     Per impostare la **directory del sito** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Se si sta distribuendo disponibilità elevata (HA) per il sito, assicurarsi di eseguire il cmdlet per impostare la **directory del sito** nello stesso percorso su ogni server host all'interno del sito.

    Quando si esegue l'accesso e si distribuisce ogni accessorio nel sito, verificare che l'account di accesso corrente disponga del diritto di accedere alla **directory del sito**.

3. La **directory appliance** è la directory radice di lavoro locale per Skype for Business Cloud Connector Edition e il percorso in cui vengono salvati i certificati esterni, le istanze e i registri. Il percorso predefinito è:%USERPROFILE%\CloudConnector\ApplianceRoot.

    Per trovare il percorso della **directory degli elettrodomestici**, eseguire il cmdlet seguente:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Per impostare la **directory degli elettrodomestici** su una posizione diversa da quella predefinita, eseguire il cmdlet seguente:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    La directory appliance deve essere impostata su una cartella locale dell'accessorio. È consigliabile impostare la **directory appliance** solo prima di avviare la distribuzione di Skype for Business Cloud Connector Edition. Se viene modificato dopo la distribuzione, sarà necessario ridistribuire il server host.

    > [!IMPORTANT]
    > Il percorso della **directory appliance** non deve contenere spazi.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Impostare il percorso per il certificato perimetrale esterno

- Eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato del perimetro esterno. Ad esempio: C:\certs\cce\ap.contoso.com.pfx. Il certificato deve contenere chiavi private.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Si noti che il parametro-target è specifico per le versioni 1.4.2 e successive. 

    Specificare il percorso completo del certificato esterno, incluso il nome del file. Il certificato può essere archiviato localmente o in una condivisione file. Se il certificato è archiviato in una cartella condivisa, è necessario creare la cartella condivisa sul primo dispositivo di ogni sito e deve essere accessibile da altri dispositivi che appartengono allo stesso sito. Questo cmdlet copia il certificato esterno nella **directory appliance**.

    > [!IMPORTANT]
    > **Se è stato aggiornato a Cloud Connector versione 1.4.2 o versioni successive**, verificare che il certificato esterno preparato contenga chiavi private e la catena di certificati completa, inclusi il certificato della CA radice e i certificati di CA intermedi. **Se non è stato ancora aggiornato a Cloud Connector versione 1.4.2**, verificare che il certificato esterno preparato contenga chiavi private. Questo certificato esterno deve essere emesso da un'autorità di certificazione considerata attendibile da Windows per impostazione predefinita.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Impostare il percorso per il gateway PSTN esterno/certificato SBC

Se si utilizza TLS tra il Mediation Server e il gateway/SBC PSTN, eseguire il seguente cmdlet per impostare il percorso, incluso il nome del file, sul certificato del gateway. Ad esempio: C:\certs\cce\sbc.contoso.com.cer. Il certificato deve contenere la CA radice e la catena intermedia per il certificato assegnato al gateway:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Si noti che il parametro-target è specifico per le versioni 1.4.2 e successive. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Creare switch virtuali in gestione di Hyper-V

1. Aprire gestione switch virtuale di **Hyper-V Manager**  >  **Virtual Switch Manager**e selezionare **nuovo Virtual Switch Manager**.

2. Creare un'opzione virtuale esterna e associarla alla scheda di rete fisica connessa al dominio di rete interno:

    Selezionare **Consenti sistema operativo di gestione per condividere questa scheda di rete** per questo switch virtuale.

3. Creare un'opzione virtuale esterna e associarla alla scheda di rete fisica che viene instradata a Internet:

    Deselezionare **Consenti al sistema operativo di gestione di condividere questa scheda di rete** per questo switch virtuale.

4. Impostare il nome dell'opzione che connette la rete perimetrale all'opzione del dominio di rete **questo CCE corpnet**.

    Impostare il nome dell'opzione che connette la rete perimetrale all'opzione Internet **questo CCE Internet**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aggiornare il file di configurazione CloudConnector. ini

Preparare il file CloudConnector. ini utilizzando le informazioni raccolte in [Determine Deployment Parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) nell'argomento [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .

Per aggiornare il file, eseguire prima il cmdlet seguente per ottenere il modello di esempio (CloudConnector. Sample. ini):

```powershell
Export-CcConfigurationSampleFile
```

Il modello di esempio è archiviato nella **directory appliance**.

Dopo averlo aggiornato con i valori dell'ambiente, salvare il file come CloudConnector. ini nella **directory appliance**. È possibile eseguire **Get-CcApplianceDirectory** per determinare il percorso della **directory degli elettrodomestici**.

Quando si aggiorna il file ini, prendere in considerazione quanto segue:

> [!NOTE]
> Non tutti i valori per il file ini sono descritti in questa sezione, ma solo quelli con una considerazione particolare sono descritti in questo articolo. Per un elenco completo, vedere la sezione [Determine Deployment Parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dell'argomento [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Per ulteriori informazioni sui valori che devono essere modificati per altri dispositivi o nuovi siti, vedere [Single site with High Availability (ha) rispetto alle distribuzioni multisito](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) nell'argomento [deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** Il valore predefinito è **site1**. È necessario aggiornarlo prima di distribuire il connettore Cloud, poiché quando si esegue **Register-CcAppliance** per registrare un dispositivo in un sito esistente o nuovo, il cmdlet utilizzerà **siteName** per determinare il sito da registrare.

     Se si desidera registrare l'accessorio in un nuovo sito, è necessario che il valore di **siteName** sia univoco e diverso rispetto ai siti esistenti. Se si desidera registrare l'accessorio in un sito esistente, il valore per **siteName** nel file. ini deve corrispondere al nome definito nella configurazione dell'organizzazione di Microsoft 365 o Office 365. Se si sta copiando un file di configurazione da un sito a un altro, accertarsi di aver aggiornato di conseguenza il valore per **siteName** per ogni sito.

- **NomeServer:** Il nome del server non deve contenere il nome di dominio e deve essere limitato a 15 caratteri.

- **HardwareType:** Se non si imposta o non si lascia il valore a null, verrà utilizzato il valore predefinito **Normal** . Utilizzo **normale** se si prevede di distribuire la versione più grande del connettore Cloud per supportare le chiamate simultanee di 500 per ogni computer host, come descritto in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Utilizzare il **valore minimo** per una distribuzione più piccola che supporta le chiamate simultanee 50.

- **Switch virtuali Internet/corpnet/Management:**: aggiungere il nome delle opzioni virtuali create. Per l'opzione gestione virtuale, lasciare il valore predefinito. Lo script di distribuzione creerà l'opzione di gestione virtuale all'inizio della distribuzione ed eliminerà la distribuzione al termine dell'installazione.

- **ManagementIPPrefix:** ManagementIPPrefix nella sezione rete deve essere una subnet diversa da altri indirizzi IP interni. Ad esempio, come indicato nel valore predefinito, ManagementIPPrefix è 192.168.213.0, mentre AD IPAddress è 192.168.0.238.

    Gli script di distribuzione creano una scheda di rete di gestione su ogni macchina virtuale, assegnano un IP di gestione e la collegano a una switch virtuale di gestione. In questo modo il server host è in grado di connettersi e gestire ogni macchina virtuale tramite questa rete di gestione. L'opzione di gestione virtuale viene eliminata al termine della distribuzione.

- **Configurazioni specifiche per VM di base:** Per il cmdlet **Convert-CcIsoToVhdx** è necessario configurare le impostazioni di questa sezione.

    Durante la preparazione dell'immagine di base della VM, la VM di base verrà connessa all'opzione di rete interna. Le impostazioni seguenti sono critiche affinché la VM sia in grado di accedere a Internet:

  - Comune BaseVMIP: l'indirizzo IP di corpnet da assegnare alla VM di base.

  - Rete CorpnetDefaultGateway: il gateway predefinito da assegnare alla VM di base.

  - Rete CorpnetDNSIPAddress: l'indirizzo IP DNS da assegnare alla VM di base.

  - Rete WSUSServer: l'indirizzo IP del servizio Windows Server Update.

  - Rete WSUSStatusServer: l'indirizzo IP del server di stato del servizio Windows Server Update.

  - Rete EnableReferSupport: consente di definire se il supporto SIP REFER è abilitato o disabilitato sulla configurazione trunk nell'IP/PBX.

- **IPs interno:**

  - Assicurarsi che la subnet mask CorpnetIPPrefixLength sia corretta.

  - Verificare che non vi siano conflitti IP per questi indirizzi IPs interni.

- **Indirizzi IP esterni:**

  - Per l'indirizzo IP pubblico di MR: specificare ExternalMRIPs per non NAT o ExternalMRPublicIPs per NAT.

  - ExternalSIPIPs e ExternalMRIPs possono essere uguali.

  - Assicurarsi che la subnet mask InternetIPPrefixLength sia corretta.

  - Verificare che non vi siano conflitti IP per questi indirizzi IPs esterni.

- **Gateway**

  - Se si dispone di un solo gateway, rimuovere la sezione per il gateway secondario. Se si dispone di più di due gateway, creare sezioni aggiuntive copiando e incollando quella esistente e quindi aggiornando.

  - Verificare che l'indirizzo IP e la porta del gateway siano corretti.

  - Per supportare l'HA a livello di gateway PSTN, lasciare il gateway secondario e aggiungere eventuali gateway aggiuntivi che verranno utilizzati. È possibile copiare e incollare una voce esistente e quindi aggiornarla.

- Facoltativamente, è possibile aggiornare il valore LocalRoute per limitare i numeri di chiamata in uscita.

## <a name="download-the-bits-to-the-site-directory"></a>Scaricare i bit nella directory del sito

Eseguire il cmdlet seguente per scaricare i file di informazioni sui bit e la versione nella **directory del sito**:

```powershell
Start-CcDownload
```

> [!NOTE]
> È necessario eseguire questo passaggio solo per il primo accessorio. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparare il disco virtuale di base (VHDX) dal file ISO scaricato

Questo passaggio prepara un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server 2012. Il VHDX verrà utilizzato per creare macchine virtuali durante la distribuzione. Verrà creata una macchina virtuale temporanea (VM di base) e verrà installato Windows Server 2012 dal file ISO. Dopo aver creato la VM, verranno installati alcuni componenti necessari e verrà applicato l'ultimo aggiornamento di Windows. Alla fine, la VM di base verrà generalizzata (Sysprep) e ripulita, lasciando solo il file del disco virtuale generato.

> [!NOTE]
> È necessario eseguire questo passaggio solo per il primo accessorio. 

Prima di procedere con questo passaggio, assicurarsi che l'opzione corpnet sia stata creata. Verificare inoltre che le impostazioni seguenti siano state configurate correttamente nel file CloudConnector. ini:

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

Il file VHD creato è archiviato nella cartella \Bits\VHD **directory del sito** . È possibile ottenere il percorso della **directory del sito** eseguendo il **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Per impostazione predefinita, le impostazioni proxy non sono configurate sulla VM di base. Se nell'ambiente di rete è necessario un proxy per aggiornare la VM tramite Windows Update, è necessario aggiungere l'opzione-PauseBeforeUpdate quando si esegue "Convert-CcIsoToVhdx". Lo script interromperà prima di Windows Update e si avrà la possibilità di configurare manualmente proxy sulla macchina virtuale. Dopo l'installazione del proxy e la VM può accedere a Internet, è possibile riprendere lo script per completare i passaggi rimanenti. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Creare dischi rigidi virtuali per una distribuzione a più siti

Si tratta di un passaggio facoltativo che si applica solo alle distribuzioni multisito.

Se si sta distribuendo una distribuzione a più siti, non è necessario convertire la ISO in un disco rigido virtuale per ogni sito. È possibile copiare il VHDX creato per il primo sito nel server host per un secondo sito.

 Copiare il file nello stesso percorso di file (cartella \Bits\VHD **directory del sito** ) e con lo stesso nome file nel server host per un sito aggiuntivo.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Impostare il criterio di esecuzione di PowerShell su RemoteSigned

Gli script di PowerShell forniti richiedono che il criterio di esecuzione sia impostato su RemoteSigned. Per visualizzare l'impostazione corrente, aprire una console PowerShell come amministratore ed eseguire il cmdlet seguente:

```powershell
Get-ExecutionPolicy
```

Se non è impostato su "RemoteSigned", eseguire il seguente cmdlet per modificarlo:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Modificare criteri di gruppo locali nel computer host (versioni 1.4.1 e precedenti)

> [!NOTE]
> Questa attività non è obbligatoria per le versioni 1.4.2 e successive del connettore Cloud. 

L'account CceService viene creato durante la distribuzione di Skype for Business Cloud Connector Edition. Esegue il servizio di gestione Cloud Connector e richiede l'autorizzazione per la disinstallazione di cloudconnector. msi. È necessario modificare l'impostazione di criteri di gruppo nel computer host del connettore Cloud per specificare che il registro di sistema dell'utente non deve essere scaricato quando l'utente si disconnette. Attenersi alla procedura seguente:

### <a name="to-change-the-group-policy-setting"></a>Per modificare l'impostazione di criteri di gruppo

1. Aprire l' **Editor criteri di gruppo** eseguendo gpedit. msc.

2. Nell' **Editor criteri di gruppo**, passare a modelli amministrativi > System > UserProfile > non scaricare con forza il registro di sistema dell'utente alla disconnessione dell'utente. 

3. Impostarne il valore su **attivato**.

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurare l'organizzazione Microsoft 365 o Office 365

È necessaria un'organizzazione Microsoft 365 o Office 365 con Skype for business online e il sistema telefonico. Verificare che il tenant sia configurato e configurato prima di tentare di utilizzare il connettore Cloud.

Alcuni passaggi di installazione di Microsoft 365 e Office 365 richiedono l'utilizzo di TRPS (tenant Remote PowerShell) per configurare l'organizzazione Microsoft 365 o Office 365. **Tale operazione deve essere installata nel server host.** È possibile scaricare il modulo Skype for business online per PowerShell da: [Skype for business online, modulo di Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366).

Creare un account di amministratore di Skype for business dedicato per la gestione di Cloud Connector online, ad esempio CceOnlineManagmentAdministrator. Questo account verrà utilizzato dall'accessorio per aggiungere o rimuovere Appliance, abilitare o disabilitare l'aggiornamento automatico del sistema operativo, abilitare o disabilitare l'aggiornamento automatico binario. Impostare la password per l'account affinché non scada mai in modo che non sia necessario modificarla per il servizio ogni volta che scade.


