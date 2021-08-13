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
description: Informazioni su come preparare l'appliance Cloud Connector per la distribuzione e l'uso con Sistema telefonico (Cloud PBX).
ms.openlocfilehash: 58f9765f211a3961db8baf5929956feecf1eb4fd7e7744490cb21f1967dcb46f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340812"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Predisporre l'appliance di Cloud Connector

> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Informazioni su come preparare l'appliance Cloud Connector per la distribuzione e l'uso con Sistema telefonico (Cloud PBX).

In questa sezione viene descritto come ottenere i Skype for Business Cloud Connector Edition di installazione, installare il software Cloud Connector e preparare l'appliance Cloud Connector per la distribuzione. Dopo aver completato tutti i passaggi descritti in questa sezione, sarà possibile distribuire Cloud Connector per uno o più siti. Se si dispone di una distribuzione di Cloud Connector esistente e non è stato ancora eseguito l'aggiornamento a Cloud Connector versione 2.1, vedere [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft supporta la versione corrente di Cloud Connector Edition, versione 2.1. Se è stato configurato l'aggiornamento automatico, Cloud Connector verrà aggiornato automaticamente. Se è stato configurato l'aggiornamento manuale, sarà necessario eseguire l'aggiornamento alla versione 2.1 entro 60 giorni dal rilascio. Microsoft supporterà la versione precedente per 60 giorni dopo il rilascio della 2.1 per consentire l'aggiornamento. 

> [!NOTE]
> Per Cloud Connector versione 2.1 e successive, l'appliance host deve .NET Framework 4.6.1 o versione successiva. 

> [!IMPORTANT]
> Per una distribuzione corretta, quando si eseguono i cmdlet per configurare Skype for Business Cloud Connector Edition, utilizzare sempre la stessa sessione della console di quella avviata. Evitare di passare a sessioni diverse durante la distribuzione e la configurazione. 

> [!NOTE]
> Esistono alcuni passaggi da eseguire solo per la prima appliance della distribuzione: la creazione di una condivisione per la directory dei siti, il download dei bit e la preparazione di un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Scaricare il programma Skype for Business Cloud Connector Edition di installazione

1. Nel server host in cui verranno eseguite le macchine virtuali del connettore cloud, scaricare i file di installazione: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > Il server host deve essere in grado di accedere a Internet durante l'installazione di Cloud Connector perché durante l'installazione vengono scaricati file aggiuntivi. 

2. Eseguire il programma di installazione e accettare i valori predefiniti durante l'installazione.

3. Verificare che l'installazione sia stata completata correttamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Verificare l'installazione e configurare l'ambiente

1. Aprire una console di PowerShell come amministratore e verificare che i cmdlet Skype for Business Cloud Connector Edition siano disponibili utilizzando il cmdlet seguente:

   ```powershell
   Get-Command *-Cc*
   ```

    Il comando deve restituire un elenco di cmdlet per Skype for Business Cloud Connector Edition.

2. I file VHD, SfBBits e VersionInfo verranno archiviati nella **directory dei siti.**

    È possibile trovare il percorso della **directory siti** con il cmdlet seguente:

   ```powershell
   Get-CcSiteDirectory
   ```

    Il comando deve restituire un percorso nel file system. Il percorso può essere una cartella locale o una condivisione file. Il percorso predefinito per la **directory siti** è: %USERPROFILE%\CloudConnector\SiteRoot. Il percorso predefinito deve essere modificato in una condivisione file nel primo dispositivo creato in ogni sito.

    Il percorso selezionato deve essere:

   - Creato nel primo dispositivo creato in ogni sito.

   - Cartella condivisa accessibile dagli altri server host (appliance) nello stesso sito.

     Per impostare **la directory siti** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Se si distribuisce disponibilità elevata (HA) per il sito, eseguire il cmdlet per impostare la **directory** siti sullo stesso percorso in ogni server host all'interno del sito.

    Quando si accede e si distribuisce ogni appliance nel sito, verificare che l'account di accesso corrente abbia il diritto di accesso alla **directory del sito.**

3. La **directory appliance è** la directory radice di lavoro locale per Skype for Business Cloud Connector Edition e il percorso in cui vengono salvati i certificati, le istanze e i registri esterni. Il percorso predefinito è: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Per trovare il percorso della **directory appliance,** eseguire il cmdlet seguente:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Per impostare la **directory dell'appliance** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    La directory dell'appliance deve essere impostata su una cartella locale nell'appliance. È consigliabile impostare la **directory dell'appliance solo** prima di avviare la Skype for Business Cloud Connector Edition distribuzione. Se lo si modifica dopo la distribuzione, sarà necessario ridistribuire il server host.

    > [!IMPORTANT]
    > Il percorso della **directory appliance** non deve contenere spazi.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Impostare il percorso per il certificato perimetrale esterno

- Eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato edge esterno. Ad esempio: C:\certs\cce\ap.contoso.com.pfx. Il certificato deve contenere chiavi private.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Si noti che il parametro -Target è specifico per le versioni 1.4.2 e successive. 

    Specificare il percorso completo del certificato esterno, incluso il nome del file. Il certificato può essere archiviato in locale o in una condivisione file. Se il certificato è archiviato in una cartella condivisa, la cartella condivisa deve essere creata nel primo dispositivo di ogni sito e deve essere accessibile da altre appliance appartenenti allo stesso sito. Questo cmdlet copia il certificato esterno nella **directory appliance.**

    > [!IMPORTANT]
    > Se è stato aggiornato a **Cloud Connector versione 1.4.2** o successiva, verificare che il certificato esterno preparato contenga chiavi private e la catena di certificati completa, inclusi il certificato CA radice e i certificati ca intermedi. **Se NON è stato ancora aggiornato a Cloud Connector versione 1.4.2,** verificare che il certificato esterno preparato contenga chiavi private. Questo certificato esterno deve essere emesso da un'autorità di certificazione attendibile Windows per impostazione predefinita.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Impostare il percorso per il gateway PSTN esterno/certificato SBC

Se si utilizza TLS tra Mediation Server e il gateway PSTN/SBC, eseguire il cmdlet seguente per impostare il percorso, incluso il nome file, sul certificato del gateway. Ad esempio: C:\certs\cce\sbc.contoso.com.cer. Il certificato deve contenere la CA radice e la catena intermedia per il certificato assegnato al gateway:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Si noti che il parametro -Target è specifico per le versioni 1.4.2 e successive. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Creare commutatori virtuali nella console di gestione di Hyper-V

1. Aprire Virtual Switch Manager di **Hyper-V**  >  **Manager** e selezionare **Nuova gestione commutatore virtuale.**

2. Creare un commutatore virtuale esterno e associarlo alla scheda di rete fisica connessa al dominio di rete interno:

    Selezionare **Consenti al sistema operativo di gestione di condividere questa scheda di rete** per questo commutatore virtuale.

3. Creare un commutatore virtuale esterno e associarlo alla scheda di rete fisica instradata a Internet:

    De-select **Allow management operating system to share this network adapter** for this virtual switch.

4. Impostare il nome del commutatore che connette la rete perimetrale al dominio di rete interno **SfB CCE Corpnet Switch**.

    Impostare il nome del commutatore che connette la rete perimetrale a Internet **SfB CCE Internet Switch**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aggiornare il file CloudConnector.ini file di configurazione

Preparare il file CloudConnector.ini utilizzando le informazioni raccolte in [Determinare](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) i parametri di distribuzione [nell'argomento Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)

Per aggiornare il file, eseguire innanzitutto il cmdlet seguente per ottenere il modello di esempio (CloudConnector.Sample.ini):

```powershell
Export-CcConfigurationSampleFile
```

Il modello di esempio è archiviato nella **directory appliance**.

Dopo l'aggiornamento con i valori per l'ambiente, salvare il file CloudConnector.ini nella **directory appliance**. È possibile eseguire **Get-CcApplianceDirectory** per determinare il percorso della **directory dell'appliance.**

Quando si aggiorna il file .ini, tenere presente quanto segue:

> [!NOTE]
> Non tutti i valori per il file .ini vengono illustrati in questa sezione, solo quelli con una considerazione speciale sono trattati qui. Per un elenco completo, vedere la [sezione Determinare](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) i parametri di distribuzione dell'argomento [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md) Per ulteriori informazioni sui valori da modificare per ulteriori appliance o nuovi siti, vedere [Single site with High Availability (HA) rispetto](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) alle distribuzioni multisnome nell'argomento Deploy multiple sites in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 

- **SiteName:** Il valore predefinito è **Site1.** È necessario aggiornarlo prima di distribuire Cloud Connector, perché quando si esegue **Register-CcAppliance** per registrare un'appliance in un sito esistente o nuovo, il cmdlet utilizzerà **SiteName** per determinare quale sito registrare.

     Se si desidera registrare l'appliance in un nuovo sito, il valore **di SiteName** deve essere univoco e diverso dai siti esistenti. Se si desidera registrare l'appliance in un sito esistente, il valore di **SiteName** nel file .ini deve corrispondere al nome definito nella configurazione dell'organizzazione di Microsoft 365 o Office 365. Se si copia un file di configurazione da un sito a un altro, assicurarsi di aggiornare il valore **di SiteName** per ogni sito di conseguenza.

- **ServerName:** Il nome del server non deve contenere il nome di dominio e deve contenere un massimo di 15 caratteri.

- **HardwareType:** Se non si imposta o non si lascia il valore su null, verrà utilizzato il valore predefinito **Normal.** Utilizzare **Normal** se si prevede di distribuire la versione più grande di Cloud Connector per supportare 500 chiamate simultanee per computer host, come descritto in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Utilizzare **Minimum** per una distribuzione più piccola che supporta 50 chiamate simultanee.

- **Commutatori virtuali Internet/Corpnet/Gestione:**: aggiungere il nome dei commutatori virtuali creati. Per il commutatore virtuale di gestione, lasciare il valore predefinito. Lo script di distribuzione creerà il commutatore virtuale di gestione all'inizio della distribuzione e lo eliminerà al termine della distribuzione.

- **ManagementIPPrefix:** ManagementIPPrefix nella sezione Network deve essere una subnet diversa da altri INDIRIZZI IP interni. Ad esempio, come mostra il valore predefinito, ManagementIPPrefix è 192.168.213.0, mentre AD IPAddress è 192.168.0.238.

    Gli script di distribuzione creano una scheda di rete di gestione in ogni macchina virtuale, assegnano un IP di gestione e la connettono a un commutatore virtuale di gestione. In questo modo il server host può connettersi e gestire ogni macchina virtuale tramite questa rete di gestione. Il commutatore virtuale di gestione viene eliminato al termine della distribuzione.

- **Configurazioni specifiche della** macchina virtuale di Impostazioni in questa sezione devono essere configurate per il cmdlet **Convert-CcIsoToVhdx.**

    Durante la preparazione dell'immagine della macchina virtuale di base, la macchina virtuale di base verrà connessa al commutatore di rete interno. Le impostazioni seguenti sono fondamentali per la macchina virtuale per poter accedere a Internet:

  - [Common] BaseVMIP: l'indirizzo IP della rete corpnet da assegnare alla macchina virtuale di base.

  - [Rete] CorpnetDefaultGateway: gateway predefinito da assegnare alla macchina virtuale di base.

  - [Rete] CorpnetDNSIPAddress: l'indirizzo IP DNS da assegnare alla macchina virtuale di base.

  - [Rete] WSUSServer: l'indirizzo IP di Windows Server Update Service.

  - [Rete] WSUSStatusServer: l'indirizzo IP Windows server di stato del servizio aggiornamento server.

  - [Rete] EnableReferSupport: in questo modo verrà definito se il supporto SIP REFER è abilitato o disabilitato nella configurazione trunk per l'IP/PBX.

- **IP interni:**

  - Verificare che la subnet mask CorpnetIPPrefixLength sia corretta.

  - Assicurarsi che non vi siano conflitti IP per questi indirizzi IP interni.

- **IP esterni:**

  - For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.

  - ExternalSIPIPs e ExternalMRIPs possono essere uguali.

  - Verificare che la subnet mask InternetIPPrefixLength sia corretta.

  - Assicurarsi che non vi siano conflitti IP per questi indirizzi IP esterni.

- **Gateway:**

  - Se si dispone di un solo gateway, rimuovere la sezione per il gateway secondario. Se si dispone di più di due gateway, creare sezioni aggiuntive copiando e incollando quello esistente e quindi aggiornarlo.

  - Verificare che l'indirizzo IP e la porta dei gateway siano corretti.

  - Per supportare l'ha a livello di gateway PSTN, lasciare il gateway secondario e aggiungere eventuali altri gateway che verranno utilizzati. È possibile copiare e incollare una voce esistente e quindi aggiornarla.

- Facoltativamente, è possibile aggiornare il valore LocalRoute per limitare i numeri di chiamata in uscita.

## <a name="download-the-bits-to-the-site-directory"></a>Scaricare i bit nella directory dei siti

Eseguire il cmdlet seguente per scaricare i bit e i file di informazioni sulla versione nella **directory dei siti:**

```powershell
Start-CcDownload
```

> [!NOTE]
> È necessario eseguire questo passaggio solo per il primo dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparare il disco virtuale di base (VHDX) dal file ISO scaricato

Questo passaggio prepara un file del disco rigido virtuale (VHDX) dall'Windows Server 2012'immagine ISO. Il disco rigido virtuale verrà utilizzato per creare macchine virtuali durante la distribuzione. Verrà creata una macchina virtuale temporanea (macchina virtuale di base) Windows Server 2012 verrà installata dal file ISO. Dopo la creazione della macchina virtuale, verranno installati alcuni componenti necessari e verrà applicato Windows'aggiornamento più recente. Alla fine, la macchina virtuale di base verrà generalizzata (sysprep) e pulita, lasciando solo il file del disco virtuale generato.

> [!NOTE]
> È necessario eseguire questo passaggio solo per il primo dispositivo. 

Prima di procedere con questo passaggio, verificare che il commutatore corpnet sia stato creato. Verificare inoltre che le impostazioni seguenti siano configurate correttamente nel file CloudConnector.ini:

- [Rete] CorpnetSwitchName

- [Common] BaseVMIP

- [Rete] CorpnetIPPrefixLength

- [Rete] CorpnetDefaultGateway

- [Rete] CorpnetDNSIPAddress

Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per convertire l'immagine ISO in un disco rigido virtuale :Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Specificare il percorso completo, incluso il nome del file, per l'immagine ISO. Ad esempio: C:\ISO\WindowsServer2012R2.iso.

Il file VHD creato viene archiviato nella **cartella Directory** siti \Bits\VHD. È possibile ottenere il percorso della **directory siti** eseguendo **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Per impostazione predefinita, le impostazioni proxy non sono configurate nella macchina virtuale di base. Se nell'ambiente di rete è necessario un proxy per aggiornare la macchina virtuale tramite Windows Update, è necessario aggiungere l'opzione -PauseBeforeUpdate quando si esegue "Convert-CcIsoToVhdx". Lo script verrà sospeso prima Windows Update e si avrà la possibilità di configurare manualmente il proxy nella macchina virtuale. Dopo l'installazione del proxy e la macchina virtuale può accedere a Internet, è possibile riprendere lo script per completare i passaggi rimanenti. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Creare dischi rigidi virtuali per una distribuzione multis sito

Si tratta di un passaggio facoltativo che si applica solo alle distribuzioni multis sito.

Se si distribuisce una distribuzione multisnodo, non è necessario convertire l'ISO in un disco rigido virtuale per ogni sito. È possibile copiare il disco rigido virtuale creato per il primo sito nel server host per un secondo sito.

 Copiare il file nello stesso percorso del file ( **Directory** siti \Cartella Bits\VHD) e con lo stesso nome file nel server host per un sito aggiuntivo.

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

L'account CceService viene creato durante la Skype for Business Cloud Connector Edition distribuzione. Esegue il servizio di gestione del connettore cloud e richiede l'autorizzazione per disinstallare il cloudconnector.msi. È necessario modificare l'impostazione di Criteri di gruppo nel computer host Cloud Connector per specificare che il Registro di sistema dell'utente non deve essere scaricato quando l'utente si disconnette. Seguire la procedura seguente:

### <a name="to-change-the-group-policy-setting"></a>Per modificare l'impostazione di Criteri di gruppo

1. Aprire **l'Editor Criteri di** gruppo eseguendo gpedit.msc.

2. **Nell'Editor Criteri** di gruppo passare a Modelli amministrativi > Sistema > UserProfile > Non scaricare forzatamente il Registro di sistema utente alla disconnessione dell'utente. 

3. Impostarne il valore su **Enabled**.

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurare l'organizzazione Microsoft 365 o Office 365 locale

È Microsoft 365 o Office 365 un'organizzazione con Skype for Business Online e Sistema telefonico è necessaria. Assicurati che il tenant sia configurato e configurato prima di tentare di usare Cloud Connector.

Alcuni Microsoft 365 e Office 365 di configurazione richiedono l'utilizzo di Tenant Remote PowerShell (TRPS) per configurare l'Microsoft 365 o Office 365 organizzazione. **Deve essere installato nel server host.** È possibile scaricare il modulo Skype for Business Online per PowerShell da: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).

Creare un account Skype for Business amministratore dedicato per la gestione online del connettore cloud, ad esempio CceOnlineManagmentAdministrator. Questo account verrà utilizzato dall'appliance per aggiungere o rimuovere appliance, abilitare o disabilitare l'aggiornamento automatico del sistema operativo, abilitare o disabilitare l'aggiornamento binario automatico. Impostare la password per questo account in modo che non scada mai in modo che non sia necessario modificarla per il servizio ogni volta che scade.