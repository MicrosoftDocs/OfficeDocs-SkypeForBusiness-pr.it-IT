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
description: Informazioni su come preparare l'applicazione Cloud Connector per la distribuzione e l'utilizzo con Sistema telefonico (Cloud PBX).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358942"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Predisporre l'appliance di Cloud Connector

> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Informazioni su come preparare l'applicazione Cloud Connector per la distribuzione e l'utilizzo con Sistema telefonico (Cloud PBX).

Questa sezione descrive come ottenere i file di installazione di Skype for Business Cloud Connector Edition, installare il software Cloud Connector e preparare l'applicazione Cloud Connector per la distribuzione. Dopo aver completato tutti i passaggi descritti in questa sezione, si sarà pronti per distribuire Cloud Connector per uno o più siti. Se si dispone di una distribuzione di Cloud Connector esistente e non è stato ancora eseguito l'aggiornamento a Cloud Connector versione 2.1, vedere Eseguire l'aggiornamento a una nuova versione [di Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)

> [!NOTE]
> Microsoft supporta la versione corrente di Cloud Connector Edition, versione 2.1. Se è stato configurato l'aggiornamento automatico, Cloud Connector verrà aggiornato automaticamente. Se è stato configurato l'aggiornamento manuale, sarà necessario eseguire l'aggiornamento alla versione 2.1 entro 60 giorni dal rilascio. Microsoft supporterà la versione precedente per 60 giorni dopo il rilascio della 2.1 per consentire l'aggiornamento. 

> [!NOTE]
> Per Cloud Connector versione 2.1 e successive, nell'applicazione host deve essere installato .NET Framework 4.6.1 o versione successiva. 

> [!IMPORTANT]
> Per una distribuzione corretta, quando si eseguono i cmdlet per configurare Skype for Business Cloud Connector Edition, usare sempre la stessa sessione console di quella avviata. Evitare di passare a sessioni diverse durante la distribuzione e la configurazione. 

> [!NOTE]
> Esistono alcuni passaggi da eseguire solo per il primo dispositivo nella distribuzione: creazione di una condivisione per la directory dei siti, download dei bit e preparazione di un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Scaricare il programma di installazione di Skype for Business Cloud Connector Edition

1. Nel server host in cui verranno eseguite le macchine virtuali di Cloud Connector, scaricare i file di installazione: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > Il server host deve essere in grado di accedere a Internet durante l'installazione di Cloud Connector perché durante l'installazione vengono scaricati file aggiuntivi. 

2. Eseguire il programma di installazione e accettare i valori predefiniti durante l'installazione.

3. Verificare che l'installazione sia stata completata correttamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Verificare l'installazione e configurare l'ambiente

1. Aprire una console di PowerShell come amministratore e verificare che i cmdlet di Skype for Business Cloud Connector Edition siano disponibili utilizzando il cmdlet seguente:

   ```powershell
   Get-Command *-Cc*
   ```

    Il comando deve restituire un elenco di cmdlet per Skype for Business Cloud Connector Edition.

2. I file VHD, SfBBits e VersionInfo verranno archiviati nella **directory dei siti.**

    È possibile trovare il percorso della **directory siti** con il cmdlet seguente:

   ```powershell
   Get-CcSiteDirectory
   ```

    Il comando deve restituire un percorso nel file system. Il percorso può essere una cartella locale o una condivisione file. Il percorso predefinito per la **directory dei** siti è: %USERPROFILE%\CloudConnector\SiteRoot. Il percorso predefinito deve essere modificato in una condivisione file nel primo dispositivo creato in ogni sito.

    La posizione selezionata deve essere:

   - Creato nel primo dispositivo creato in ogni sito.

   - Cartella condivisa accessibile dagli altri server host (appliance) nello stesso sito.

     Per impostare **la directory siti** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Se si distribuisce la disponibilità elevata (HA) per il sito, eseguire il cmdlet per impostare la **directory** siti sullo stesso percorso in ogni server host all'interno del sito.

    Quando si esegue l'accesso e si distribuisce ogni appliance nel sito, verificare che l'account di accesso corrente abbia il diritto di accesso alla **directory siti.**

3. La **directory appliance è** la directory radice di lavoro locale per Skype for Business Cloud Connector Edition e il percorso in cui vengono salvati certificati, istanze e log esterni. Il percorso predefinito è: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Per trovare il percorso della **directory dell'appliance,** eseguire il cmdlet seguente:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Per impostare la **directory dell'appliance** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    La directory dell'applicazione deve essere impostata su una cartella locale nell'appliance. È consigliabile impostare la **directory appliance solo** prima di avviare la distribuzione di Skype for Business Cloud Connector Edition. Se lo si modifica dopo la distribuzione, sarà necessario ridistribuire il server host.

    > [!IMPORTANT]
    > Il percorso della **directory del** dispositivo non deve contenere spazi.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Impostare il percorso per il certificato perimetrale esterno

- Eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato perimetrale esterno. Ad esempio: C:\certs\cce\ap.contoso.com.pfx. Il certificato deve contenere chiavi private.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Si noti che il parametro -Target è specifico delle versioni 1.4.2 e successive. 

    Specificare il percorso completo del certificato esterno, incluso il nome del file. Il certificato può essere archiviato localmente o in una condivisione file. Se il certificato è archiviato in una cartella condivisa, la cartella condivisa deve essere creata nel primo dispositivo di ogni sito e deve essere accessibile da altre appliance appartenenti allo stesso sito. Questo cmdlet copia il certificato esterno nella **directory appliance.**

    > [!IMPORTANT]
    > Se è stato aggiornato **a Cloud Connector versione 1.4.2** o successiva, verificare che il certificato esterno preparato contenga chiavi private e la catena di certificati completa, inclusi il certificato CA radice e i certificati della CA intermedia. **Se NON è stato ancora aggiornato a Cloud Connector versione 1.4.2,** verificare che il certificato esterno preparato contenga chiavi private. Questo certificato esterno deve essere emesso da un'autorità di certificazione attendibile per impostazione predefinita da Windows.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Impostare il percorso per il certificato SBC/gateway PSTN esterno

Se si utilizza TLS tra Mediation Server e il gateway PSTN/SBC, eseguire il cmdlet seguente per impostare il percorso, incluso il nome file, sul certificato del gateway. Ad esempio: C:\certs\cce\sbc.contoso.com.cer. Il certificato deve contenere la CA radice e la catena intermedia per il certificato assegnato al gateway:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Si noti che il parametro -Target è specifico delle versioni 1.4.2 e successive. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Creare commutatori virtuali nella console di gestione di Hyper-V

1. Aprire Virtual Switch Manager di **Hyper-V**  >  **e** selezionare **Nuova console di gestione commutatore virtuale.**

2. Creare un commutatore virtuale esterno e associarlo alla scheda di rete fisica connessa al dominio di rete interno:

    Selezionare **Consenti al sistema operativo di gestione di condividere questa scheda di rete** per questo commutatore virtuale.

3. Creare un commutatore virtuale esterno e associarlo alla scheda di rete fisica instradata a Internet:

    De-select **Allow management operating system to share this network adapter** for this virtual switch.

4. Impostare il nome del commutatore che connette la rete perimetrale al dominio di rete **interno SfB CCE Corpnet Switch.**

    Impostare il nome del commutatore che connette la rete perimetrale a Internet **SfB CCE Internet Switch.**

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aggiornare il file CloudConnector.ini di configurazione

Preparare il file CloudConnector.ini utilizzando le informazioni raccolte in [Determinare](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) i parametri di distribuzione nell'argomento [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)

Per aggiornare il file, eseguire innanzitutto il cmdlet seguente per ottenere il modello di esempio (CloudConnector.Sample.ini):

```powershell
Export-CcConfigurationSampleFile
```

Il modello di esempio è archiviato nella **directory appliance.**

Dopo l'aggiornamento con i valori per l'ambiente, salvare il file come CloudConnector.ini nella **directory appliance.** È possibile eseguire **Get-CcApplianceDirectory** per determinare il percorso della **directory dell'applicazione.**

Quando si aggiorna il file ini, tenere presente quanto segue:

> [!NOTE]
> Non tutti i valori per il file ini vengono illustrati in questa sezione, ma solo quelli con una considerazione speciale sono trattati qui. Per un elenco completo, vedere la sezione [Determinare](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) i parametri di distribuzione dell'argomento [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md) Per ulteriori informazioni sui valori da modificare per ulteriori appliance o nuovi siti, vedere Single [Site with High Availability (HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) rispetto alle distribuzioni multisocietà nell'argomento Distribuire più siti in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 

- **SiteName:** Il valore predefinito è **Site1.** È necessario aggiornarlo prima di distribuire Cloud Connector, perché quando si esegue **Register-CcAppliance** per registrare un'applicazione in un sito esistente o nuovo, il cmdlet utilizzerà **SiteName** per determinare quale sito registrare.

     Se si desidera registrare l'applicazione in un nuovo sito, il valore **di SiteName** deve essere univoco e diverso dai siti esistenti. Se si desidera registrare l'applicazione in un sito esistente, il valore di **SiteName** nel file ini deve corrispondere al nome definito nella configurazione dell'organizzazione di Microsoft 365 o Office 365. Se si copia un file di configurazione da un sito a un altro, aggiornare il valore **di SiteName** per ogni sito di conseguenza.

- **ServerName:** Il nome del server non deve contenere il nome di dominio e deve contenere un massimo di 15 caratteri.

- **HardwareType:** Se non si imposta o non si lascia il valore su Null, verrà utilizzato il valore predefinito **Normal.** Utilizzare **Normal** se si prevede di distribuire la versione più grande di Cloud Connector per supportare 500 chiamate simultanee per computer host, come descritto in [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md) Utilizzare **Minimum** per una distribuzione di piccole dimensioni che supporta 50 chiamate simultanee.

- **Commutatori virtuali Internet/Corpnet/Gestione:** aggiungere il nome dei commutatori virtuali creati. Per il commutatore virtuale di gestione, lasciare il valore predefinito. Lo script di distribuzione creerà il commutatore virtuale di gestione all'inizio della distribuzione ed lo eliminerà al termine della distribuzione.

- **ManagementIPPrefix:** ManagementIPPrefix nella sezione Network deve essere una subnet diversa da altri indirizzi IP interni. Ad esempio, come mostra il valore predefinito, ManagementIPPrefix è 192.168.213.0, mentre AD IPAddress è 192.168.0.238.

    Gli script di distribuzione creano una scheda di rete di gestione in ogni macchina virtuale, assegnano un IP di gestione e la connettono a un commutatore virtuale di gestione. In questo modo il server host può connettersi e gestire ogni macchina virtuale tramite questa rete di gestione. Il commutatore virtuale di gestione viene eliminato al termine della distribuzione.

- **Configurazioni specifiche della macchina virtuale di base:** Le impostazioni in questa sezione devono essere configurate per il cmdlet **Convert-CcIsoToVhdx.**

    Durante la preparazione dell'immagine della macchina virtuale di base, la macchina virtuale di base verrà connessa al commutatore di rete interno. Le impostazioni seguenti sono fondamentali per la macchina virtuale per poter accedere a Internet:

  - [Comune] BaseVMIP: l'indirizzo IP della corpnet da assegnare alla macchina virtuale di base.

  - [Rete] CorpnetDefaultGateway: gateway predefinito da assegnare alla macchina virtuale di base.

  - [Rete] CorpnetDNSIPAddress: l'indirizzo IP DNS da assegnare alla macchina virtuale di base.

  - [Rete] WSUSServer: l'indirizzo IP di Windows Server Update Service.

  - [Rete] WSUSStatusServer: l'indirizzo IP del server di stato di Windows Server Update Service.

  - [Rete] EnableReferSupport: in questo modo verrà definito se il supporto SIP REFER è abilitato o disabilitato nella configurazione trunk per l'IP/PBX.

- **IP interni:**

  - Verificare che la subnet mask CorpnetIPPrefixLength sia corretta.

  - Assicurarsi che non vi siano conflitti IP per questi indirizzi IP interni.

- **IP esterni:**

  - Per l'IP pubblico MR: specificare ExternalMRIPs per non NAT o ExternalMRPublicIPs per NAT.

  - ExternalSIPIPs e ExternalMRIPs possono essere uguali.

  - Verificare che la subnet mask InternetIPPrefixLength sia corretta.

  - Assicurarsi che non vi siano conflitti IP per questi indirizzi IP esterni.

- **Gateway:**

  - Se si dispone di un solo gateway, rimuovere la sezione per il gateway secondario. Se sono disponibili più di due gateway, creare sezioni aggiuntive copiando e incollando quello esistente e quindi aggiornarlo.

  - Verificare che l'indirizzo IP e la porta dei gateway siano corretti.

  - Per supportare la messaggistica unificata a livello di gateway PSTN, lasciare il gateway secondario e aggiungere eventuali gateway aggiuntivi che verranno utilizzati. È possibile copiare e incollare una voce esistente e quindi aggiornarla.

- Facoltativamente, è possibile aggiornare il valore LocalRoute per limitare i numeri delle chiamate in uscita.

## <a name="download-the-bits-to-the-site-directory"></a>Scaricare i bit nella directory dei siti

Eseguire il cmdlet seguente per scaricare i bit e i file di informazioni sulla versione nella **directory dei siti:**

```powershell
Start-CcDownload
```

> [!NOTE]
> È necessario eseguire questo passaggio solo per il primo dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparare il disco virtuale di base (VHDX) dal file ISO scaricato

Questo passaggio prepara un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server 2012. Il VHDX verrà usato per creare macchine virtuali durante la distribuzione. Verrà creata una macchina virtuale temporanea (macchina virtuale di base) e Windows Server 2012 verrà installato dal file ISO. Dopo la creazione della macchina virtuale, verranno installati alcuni componenti necessari e verrà applicato l'aggiornamento di Windows più recente. Alla fine, la macchina virtuale di base verrà generalizzata (sysprep) e pulita, lasciando solo il file del disco virtuale generato.

> [!NOTE]
> È necessario eseguire questo passaggio solo per il primo dispositivo. 

Prima di procedere con questo passaggio, verificare che il commutatore corpnet sia stato creato. Verificare inoltre che le impostazioni seguenti siano configurate correttamente nel file CloudConnector.ini seguente:

- [Rete] CorpnetSwitchName

- [Comune] BaseVMIP

- [Rete] CorpnetIPPrefixLength

- [Rete] CorpnetDefaultGateway

- [Rete] CorpnetDNSIPAddress

Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per convertire l'immagine ISO in un disco rigido virtuale (VHD):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Specifica il percorso completo, incluso il nome del file, dell'immagine ISO. Ad esempio: C:\ISO\WindowsServer2012R2.iso.

Il file VHD creato viene archiviato nella **cartella Site Directory** \Bits\VHD. È possibile ottenere il percorso della **directory** siti eseguendo **Get-CcSiteDirectory.**

> [!IMPORTANT]
> Per impostazione predefinita, le impostazioni proxy non sono configurate nella macchina virtuale di base. Se nell'ambiente di rete è necessario un proxy per aggiornare la macchina virtuale tramite Windows Update, è necessario aggiungere l'opzione -PauseBeforeUpdate quando si esegue "Convert-CcIsoToVhdx". Lo script verrà sospeso prima di Windows Update e avrai la possibilità di configurare manualmente il proxy nella macchina virtuale. Dopo l'installazione del proxy e la macchina virtuale può accedere a Internet, puoi riprendere lo script per completare i passaggi rimanenti. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Creare dischi rigidi virtuali per una distribuzione multisode

Si tratta di un passaggio facoltativo che si applica solo alle distribuzioni multisnode.

Se si distribuisce una distribuzione multisnodo, non è necessario convertire l'ISO in un disco rigido virtuale per ogni sito. È possibile copiare il VHDX creato per il primo sito nel server host per un secondo sito.

 Copiare il file nello stesso percorso del file ( **Directory** siti \Bits\cartella VHD) e con lo stesso nome file nel server host per un sito aggiuntivo.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Impostare il criterio di esecuzione di PowerShell su RemoteSigned

Gli script di PowerShell forniti richiedono che il criterio di esecuzione sia impostato su RemoteSigned. Per visualizzare l'impostazione corrente, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:

```powershell
Get-ExecutionPolicy
```

Se non è impostato su "RemoteSigned", eseguire il cmdlet seguente per modificarlo:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Modificare Criteri di gruppo locali nel computer host (versioni 1.4.1 e precedenti)

> [!NOTE]
> Questa attività non è necessaria per Cloud Connector versioni 1.4.2 e successive. 

L'account CceService viene creato durante la distribuzione di Skype for Business Cloud Connector Edition. Esegue il servizio di gestione del connettore cloud e richiede l'autorizzazione per disinstallare il cloudconnector.msi. È necessario modificare l'impostazione di Criteri di gruppo nel computer host Cloud Connector per specificare che il Registro di sistema dell'utente non deve essere scaricato quando l'utente si disconnette. Seguire i passaggi seguenti:

### <a name="to-change-the-group-policy-setting"></a>Per modificare l'impostazione di Criteri di gruppo

1. Apri **l'Editor Criteri di** gruppo eseguendo gpedit.msc.

2. **Nell'Editor** Criteri di gruppo passare a Modelli amministrativi > Sistema > UserProfile > Non scaricare forzatamente il Registro di sistema utente alla disconnessione dell'utente. 

3. Impostarne il valore su **Abilitato.**

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurare l'organizzazione di Microsoft 365 o Office 365

È necessaria un'organizzazione di Microsoft 365 o Office 365 con Skype for Business online e Sistema telefonico. Verificare che il tenant sia configurato e configurato prima di tentare di utilizzare Cloud Connector.

Alcuni passaggi di configurazione di Microsoft 365 e Office 365 richiedono l'uso di Tenant Remote PowerShell (TRPS) per configurare l'organizzazione di Microsoft 365 o Office 365. **Deve essere installato nel server host.** È possibile scaricare il modulo di Skype for Business online per PowerShell da: [Skype for Business online, Windows PowerShell modulo.](https://www.microsoft.com/download/details.aspx?id=39366)

Creare un account amministratore Skype for Business dedicato per la gestione online di Cloud Connector, ad esempio CceOnlineManagmentAdministrator. Questo account verrà utilizzato dal dispositivo per aggiungere o rimuovere appliance, abilitare o disabilitare l'aggiornamento automatico del sistema operativo, abilitare o disabilitare l'aggiornamento binario automatico. Impostare la password per questo account in modo che non scada mai, in modo che non sia necessario modificarla per il servizio ogni volta che scade.


