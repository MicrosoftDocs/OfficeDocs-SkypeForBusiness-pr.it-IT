---
title: Teams per Virtualized Desktop Infrastructure (VDI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Informazioni su come eseguire Microsoft Teams in un ambiente VDI (Virtualized Desktop Infrastructure).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90e577f9d6ef7567387fbc7a26a944d20e976f66
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773705"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams per Virtualized Desktop Infrastructure (VDI)

Questo articolo descrive i requisiti e le limitazioni dell'uso di Microsoft Teams in un ambiente virtualizzato.

## <a name="what-is-vdi"></a>Che cos'è VDI?

Virtual Desktop Infrastructure (VDI) è una tecnologia di virtualizzazione che ospita un sistema operativo desktop e applicazioni in un server centralizzato in un data center. Ciò consente un'esperienza desktop completa e personalizzata per gli utenti con un'origine centralizzata completamente protetta e conforme.

Teams in un ambiente virtualizzato supporta la chat e la collaborazione. Inoltre, con le piattaforme Azure Virtual Desktop, Citrix e VMware, sono supportate anche le funzionalità per chiamate e riunioni.

Teams supporta anche più configurazioni in ambienti virtuali. Tra queste vi sono le modalità VDI, dedicate, condivise, persistenti e non persistenti. Le caratteristiche sono in continua sviluppo e vengono aggiunte regolarmente e le funzionalità si espanderanno nel tempo.

L'uso di Teams in un ambiente virtualizzato potrebbe essere leggermente diverso dall'uso di Teams in un ambiente non virtualizzato. Ad esempio, alcune funzionalità avanzate potrebbero non essere disponibili in un ambiente virtualizzato e la risoluzione video potrebbe essere diversa.

Per garantire un'esperienza utente ottimale, seguire le indicazioni in questo articolo.

> [!Note]
> Per informazioni dettagliate su Teams VDI su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams su componenti VDI

L'uso di Teams in un ambiente virtualizzato richiede i componenti seguenti.

- **Broker di virtualizzazione**: gestore delle risorse e delle connessioni con il provider di virtualizzazione, ad esempio Azure
- **Desktop virtuale**: lo stack di macchine virtuali (VM) che esegue Teams
- **Thin Client**: il dispositivo con cui l'utente interfaccia fisicamente
- **App desktop Teams: l'app** client desktop di Teams

## <a name="teams-on-vdi-requirements"></a>Requisiti di Teams per VDI

### <a name="virtualization-provider-requirements"></a>Requisiti del provider di virtualizzazione

L'app desktop Teams è stata convalidata con i principali provider di soluzioni di virtualizzazione. Con più provider di mercato, ti consigliamo di consultare il provider di soluzioni di virtualizzazione per assicurarti di soddisfare i requisiti minimi.
  
Attualmente, Teams su VDI con ottimizzazione audio/video (AV) è certificato con Azure Virtual Desktop, Citrix e VMware. Esaminare le informazioni in questa sezione per assicurarsi di soddisfare tutti i requisiti per la corretta funzionalità.

### <a name="platforms-certified-for-teams"></a>Piattaforme certificate per Teams

Le piattaforme seguenti includono soluzioni per l'infrastruttura desktop virtuale per Teams.

|Piattaforma|Soluzione|
|----|---|
|![Logo che rappresenta Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Desktop virtuale di Azure</a>, <a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![Il logo che rappresenta Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">App e desktop virtuali Citrix</a> |
|![Logo che rappresenta VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">Orizzonte VMware</a> |

### <a name="azure-virtual-desktop"></a>Desktop virtuale di Azure

Desktop virtuale di Azure fornisce l'ottimizzazione AV per Teams su VDI. Per altre informazioni sui requisiti e sull'installazione, vedere [Usare Teams su Desktop virtuale di Azure](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 usa l'ottimizzazione AV fornita da Desktop virtuale di Azure per garantire un'esperienza ottimale di Teams dai PC cloud. Per altre informazioni sui requisiti e sull'installazione, vedere [Usare Teams su PC cloud](/windows-365/enterprise/teams-on-cloud-pc).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisiti per le app virtuali e i desktop di Citrix

Citrix Virtual Apps and Desktops (precedentemente noto come XenApp e XenDesktop) fornisce l'ottimizzazione AV per Teams su VDI. Con Le app virtuali e i desktop Citrix, Teams su VDI supporta le funzionalità di chiamata e riunione oltre alla chat e alla collaborazione.

È possibile scaricare l'ultima versione di Citrix Virtual Apps e Desktop sul [sito download Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Dovrai eseguire l'accesso prima di tutto). I componenti necessari sono inclusi [nell'app Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) e nell'agente di recapito virtuale (VDA) per impostazione predefinita. Non è necessario installare componenti o plug-in aggiuntivi in CWA o VDA.

Per i requisiti più recenti per server e client, vedere l'articolo [Ottimizzazione per Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) sul sito Web Citrix.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisiti per l'area di lavoro Horizon e desktop di VMware

VMware Horizon è una piattaforma moderna per la distribuzione sicura di desktop virtuali e app nel cloud ibrido. Per offrire un'esperienza ottimale per gli utenti finali, VMware Horizon offre l'ottimizzazione multimediale per Teams. Questa ottimizzazione migliora la produttività complessiva su desktop e app virtuali e migliora l'esperienza utente durante le chiamate e le riunioni con Teams.

È possibile scaricare l'ultima versione di VMware Horizon dalla pagina [Dei download VMware](https://customerconnect.vmware.com/downloads/#all_products) . I componenti di ottimizzazione multimediale necessari fanno parte di Horizon Agent e Horizon Client per impostazione predefinita e non è necessario installare alcun plug-in aggiuntivo per usare la funzionalità di ottimizzazione per Teams.

Per ottenere i requisiti e le istruzioni più recenti su come configurare l'ottimizzazione multimediale per Teams, vedere l'articolo [Configurazione di Ottimizzazione multimediale per Microsoft Teams](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) sul sito Web VMware.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installare o aggiornare l'app desktop Teams in VDI

È possibile distribuire l'app desktop di Teams per VDI usando un'installazione per computer o per utente usando il pacchetto MSI. La scelta dell'approccio da usare dipende dal fatto che si usi una configurazione persistente o non persistente e le esigenze di funzionalità associate dell'organizzazione.

Per un'installazione persistente dedicata, l'installazione per computer e per utente funzionerà. Tuttavia, per una configurazione non persistente, Teams richiede un'installazione per macchina per lavorare in modo efficiente. Vedere la sezione [Configurazione non persistente](#non-persistent-setup) .

Con l'installazione per computer, gli aggiornamenti automatici vengono disabilitati. Ciò significa che per aggiornare l'app Teams, è necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente. Con l'installazione per utente, gli aggiornamenti automatici sono abilitati.

> [!IMPORTANT]
> Mantenere aggiornata l'app desktop Teams nell'ambiente VDI. Le versioni delle app desktop di Teams con date di rilascio che risalgono a più di 90 giorni prima della [data di rilascio della versione corrente](/officeupdates/teams-app-versioning) non sono supportate. Le versioni delle app desktop di Teams non supportate mostrano una pagina di blocco agli utenti e richiedono l'aggiornamento dell'app.

Per la maggior parte delle distribuzioni VDI, è consigliabile distribuire Teams usando l'installazione per computer. Per eseguire l'aggiornamento all'ultima versione di Teams, iniziare con la procedura di disinstallazione seguita dall'ultima distribuzione della versione di Teams.

Affinché l'ottimizzazione AV di Teams in ambienti VDI funzioni correttamente, il dispositivo thin-client deve avere accesso a Internet. Se l'accesso a Internet non è disponibile nel dispositivo thin-client, l'avvio dell'ottimizzazione non riuscirà. Questo significa che l'utente si trova in uno stato multimediale non ottimizzato.

#### <a name="dedicated-persistent-setup"></a>Configurazione persistente dedicata

In una configurazione persistente dedicata, le modifiche al sistema operativo locale degli utenti vengono mantenute dopo la disconnessione degli utenti. Per la configurazione persistente, Teams supporta sia l'installazione per utente che per computer.

Di seguito è indicata la configurazione minima consigliata della macchina virtuale.

|Parametro  |Sistema operativo workstation  |Sistema operativo server  |
|---------|---------|---------|
|vCPU   |    2 core     |  4, 6 o 8 core<br>È importante comprendere la configurazione sottostante dell'accesso alla memoria non uniforme (NUMA) e configurare le macchine virtuali di conseguenza.     |
|RAM     |   4GB      | Da 512 MB a 1 GB per utente        |
|Archiviazione    | 8 GB        | Da 40 GB a 60 GB        |

#### <a name="non-persistent-setup"></a>Configurazione non persistente

In una configurazione non persistente, le modifiche al sistema operativo locale degli utenti non vengono mantenute dopo la disconnessione degli utenti. Tali configurazioni sono in genere sessioni multiutenti condivise. La configurazione della macchina virtuale varia in base al numero di utenti e alle risorse del server fisico disponibili.

Per una configurazione non persistente, l'app desktop di Teams deve essere installata per ogni computer nell'immagine dorata. In questo modo si garantisce un avvio efficiente dell'app Teams durante una sessione utente. Per altre informazioni, vedere la sezione [Installare o aggiornare l'app desktop teams su VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

L'uso di Teams in una configurazione non persistente richiede anche un manager di memorizzazione nella cache dei profili per un'efficiente sincronizzazione dei dati di Runtime di Teams. Una sincronizzazione efficiente dei dati assicura che le informazioni specifiche dell'utente, ad esempio i dati, il profilo o le impostazioni di un utente, vengano memorizzate nella cache durante la sessione dell'utente. Verificare che i dati in queste due cartelle siano sincronizzati:<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Una cartella roaming (o, se si usa il reindirizzamento delle cartelle, un responsabile della memorizzazione nella cache) è necessaria per assicurarsi che l'app Teams disponga dei dati di runtime e dei file necessari per eseguire l'applicazione. Ciò è necessario per ridurre i problemi di latenza della rete o glitch di rete, che altrimenti causerebbero errori dell'applicazione e un'esperienza lenta a causa di dati e file non disponibili.

Sono disponibili diverse soluzioni di gestione della cache, ad esempio [FSLogix](/fslogix/overview). Per istruzioni di configurazione specifiche, consultare il provider di gestione della cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Elenco di esclusione di contenuto memorizzato nella cache di Teams per la configurazione non persistente

Escludere quanto segue dalla cartella di memorizzazione nella cache di Teams, `%AppData%/Microsoft/Teams`. L'esclusione di questi elementi consente di ridurre le dimensioni della cache degli utenti per ottimizzare ulteriormente la configurazione non persistente.

- .txt file
- Cartella dello stack di supporti
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>considerazioni Microsoft 365 Apps for enterprise

Quando si distribuisce Teams con Microsoft 365 Apps for enterprise in VDI, tenere presente quanto segue.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nuove distribuzioni di Teams tramite Microsoft 365 Apps for enterprise

Prima di distribuire Teams tramite Microsoft 365 Apps for enterprise, è necessario disinstallare le app di Teams preesistenti se sono state distribuite con l'installazione per computer.

Teams tramite Microsoft 365 Apps for enterprise è installato per utente. Per altre informazioni, vedere la sezione [Installare o aggiornare l'app desktop teams su VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Distribuzioni di Teams tramite aggiornamenti Microsoft 365 Apps for enterprise

Teams viene aggiunto anche alle installazioni esistenti di Microsoft 365 Apps for enterprise. Poiché Microsoft 365 Apps for enterprise installa Teams solo per utente, vedere la sezione [Installare o aggiornare l'app desktop teams in VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Uso di Teams con l'installazione per computer e Microsoft 365 Apps for enterprise

Microsoft 365 Apps for enterprise non supporta le installazioni per computer di Teams. Per usare l'installazione per computer, è necessario escludere Teams da Microsoft 365 Apps for enterprise. Vedere le sezioni [Distribuire l'app desktop Teams nella macchina virtuale](#deploy-the-teams-desktop-app-to-the-vm) e [Come escludere la distribuzione di Teams tramite Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise).

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Come escludere la distribuzione di Teams tramite Microsoft 365 Apps for enterprise

Per altre informazioni su Teams e Microsoft 365 Apps for enterprise, vedere [Come escludere Teams dalle nuove installazioni di Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) e [Usare Criteri di gruppo per controllare l'installazione di Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Distribuire l'app desktop Teams nella macchina virtuale

1. Scarica il pacchetto Teams MSI che corrisponde al sistema operativo VDI VM utilizzando uno dei collegamenti seguenti:

    - [Versione a 32 bit](https://statics.teams.cdn.office.net/production-windows/1.5.00.11865/Teams_windows.msi)
    - [Versione a 64 bit](https://statics.teams.cdn.office.net/production-windows-x64/1.5.00.11865/Teams_windows_x64.msi)

    > [!NOTE]
    > Per i cloud per enti pubblici, vedere [Installazione in blocco di Teams con Windows Installer (MSI)](msi-deployment.md) per i collegamenti al download dei file MSI.

2. Installa MSI nella macchina virtuale VDI eseguendo uno dei comandi seguenti:

    - Installazione per utente (impostazione predefinita)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Questo processo è l'installazione predefinita, che installa Teams nella cartella degli `%AppData%` utenti. A questo punto, la configurazione dell'immagine dorata è completa.

        > [!IMPORTANT]
        > Teams non funziona correttamente con l'installazione per utente in una configurazione non persistente.

    - Installazione per macchina

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Questo processo aggiunge una chiave del Registro di sistema necessaria al computer che consente al programma di installazione di Teams di sapere che si tratta di un'istanza VDI.  Senza di esso, il programma di installazione verrà generato un errore, affermando: "Installazione non riuscita.  Non è possibile installare per tutti gli utenti quando non viene rilevato un ambiente VDI".

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Questo processo installa Teams nella `%ProgramFiles(x86)%` cartella in un sistema operativo a 64 bit e nella `%ProgramFiles%` cartella in un sistema operativo a 32 bit. A questo punto, la configurazione dell'immagine dorata è completa.

        > [!IMPORTANT]
        >  L'installazione di Teams per computer è necessaria per le configurazioni non persistenti.

        All'avvio della successiva sessione di accesso interattivo, Teams viene avviato e chiede le credenziali.

        > [!NOTE]
        > Questi esempi usano anche il `ALLUSERS=1` parametro. Quando si imposta questo parametro, **Teams Machine-Wide Installer** viene visualizzato in **Programmi e funzionalità** in **Pannello di controllo** e in **App & funzionalità** nelle **impostazioni di Windows** per tutti gli utenti del computer. Tutti gli utenti possono quindi disinstallare Teams se hanno le credenziali di amministratore.
        >
        > È importante comprendere la differenza tra `ALLUSERS=1` e `ALLUSER=1`. Il `ALLUSERS=1` parametro può essere utilizzato in ambienti non VDI e VDI, mentre il `ALLUSER=1` parametro viene utilizzato solo in ambienti VDI per specificare un'installazione per macchina.

3. Disinstallare MSI dalla macchina virtuale VDI. Esistono due modi per disinstallare Teams.

    - **Script di PowerShell**: è possibile usare lo script PowerShell per la [pulizia della distribuzione di Teams](scripts/powershell-script-deployment-cleanup.md) per disinstallare Teams e rimuovere la cartella Teams per un utente. Eseguire lo script per ogni profilo utente in cui Teams è stato installato nel computer.
    - **Riga di comando**: eseguire il comando seguente.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Questo processo disinstalla Teams dalla cartella o `%ProgramFiles%` dalla `%ProgramFiles(x86)%` cartella, a seconda dell'ambiente del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Considerazioni sulle prestazioni di Teams su VDI

Esistono diverse configurazioni di configurazione virtualizzate, ognuna con un obiettivo diverso per l'ottimizzazione. Ad esempio, una configurazione potrebbe concentrarsi sulla densità dell'utente. Durante la pianificazione, considerare quanto segue per ottimizzare la configurazione in base alle esigenze del carico di lavoro dell'organizzazione.

- **Requisito minimo**: alcuni carichi di lavoro potrebbero richiedere una configurazione usando risorse che superano i requisiti minimi. Ad esempio, i carichi di lavoro per gli sviluppatori che utilizzano applicazioni che richiedono più risorse di elaborazione.
- **Dipendenze**: includono le dipendenze da infrastruttura, carico di lavoro e altre considerazioni ambientali all'esterno dell'app desktop Teams.
- **Funzionalità disabilitate in VDI**: Teams disabilita le funzionalità che richiedono un utilizzo intensivo della GPU per VDI, che possono contribuire a migliorare l'utilizzo della CPU transitoria. Le caratteristiche seguenti sono disabilitate:
    - Animazione CSS di Teams
    - Avvio automatico Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams su VDI con chiamate e riunioni

Oltre alla chat e alla collaborazione, Teams su VDI con chiamate e riunioni è disponibile con piattaforme di provider di virtualizzazione supportate. Le funzionalità supportate si basano sullo stack di supporti WebRTC e sull'implementazione del provider di virtualizzazione. Il diagramma seguente fornisce una panoramica dell'architettura.

![Diagramma che mostra Teams nell'architettura VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se attualmente si esegue Teams senza ottimizzazione AV in VDI e si usano funzionalità non ancora supportate per l'ottimizzazione (ad esempio Dare e assumere il controllo durante la condivisione delle app), è necessario impostare i criteri del provider di virtualizzazione per disattivare il reindirizzamento di Teams. Ciò significa che le sessioni multimediali di Teams non verranno ottimizzate. Per i passaggi su come impostare i criteri per disattivare il reindirizzamento di Teams, contattare il provider di virtualizzazione.

### <a name="network-requirements"></a>Requisiti di rete

È consigliabile valutare l'ambiente per identificare eventuali rischi e requisiti che possono influire sulla distribuzione complessiva di voce e video nel cloud. Usare [lo strumento di valutazione della rete Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) per verificare se la rete è pronta per Teams.

Per altre informazioni su come preparare la rete per Teams, vedere [Preparare la rete dell'organizzazione per Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Eseguire la migrazione da Skype for Business su VDI a Teams su VDI

Se stai eseguendo la migrazione da Skype for Business su VDI a Teams su VDI, oltre alle differenze tra le due applicazioni, ci sono alcune differenze quando viene implementato anche VDI. Alcune funzionalità attualmente non supportate in Teams VDI in Skype for Business VDI sono le seguenti:

- Criteri per piattaforma per disabilitare alcune funzionalità AV in VDI
- Concedere e assumere il controllo durante la condivisione delle app
- Condivisione dello schermo dalla chat senza audio
- Invio e ricezione simultanei di video e condivisione dello schermo

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Confronto tra il browser Teams in Chrome e l'app desktop Teams per VDI

Il browser Teams su Chrome non sostituisce l'app desktop Teams per VDI con ottimizzazione AV. L'esperienza di chat e collaborazione funziona come previsto. Quando sono necessari elementi multimediali, esistono alcune esperienze che potrebbero non soddisfare le aspettative degli utenti nel browser Chrome:

- L'esperienza di streaming audio e video potrebbe non essere ottimale. Gli utenti potrebbero riscontrare ritardi o una qualità ridotta.
- Le impostazioni del dispositivo non sono disponibili nelle impostazioni del browser.
- La gestione dei dispositivi viene gestita tramite il browser e richiede più impostazioni nelle impostazioni del sito del browser.
- Potrebbe essere necessario configurare anche le impostazioni dei dispositivi in Gestione dispositivi Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams su VDI con chat e collaborazione

Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in Teams, è possibile impostare criteri a livello utente per disattivare le funzionalità di chiamata e riunione in Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Impostare i criteri per disattivare la funzionalità di chiamata e riunione

È possibile impostare i criteri usando l'interfaccia di amministrazione di Teams o PowerShell. La propagazione delle modifiche ai criteri può richiedere fino a poche ore. Se le modifiche per un determinato account non vengono visualizzate immediatamente, riprova tra poche ore.

[**Criteri per le**](teams-calling-policy.md) chiamate: Teams include il criterio di chiamata **DisallowCalling** integrato, in cui tutte le funzionalità di chiamata sono disattivate. Assegnare il criterio **DisallowCalling** a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

[**Criteri riunione**](meeting-policies-overview.md): Teams include i criteri riunione **AllOff** predefiniti, in cui tutte le funzionalità per le riunioni sono disattivate. Assegnare il criterio **AllOff** a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Assegnare criteri con l'interfaccia di amministrazione di Teams

Per assegnare i criteri di chiamata **DisallowCalling** e **AllOff** a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Utenti**.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1. In **Criteri per le chiamate** fare clic su **DisallowCalling**.
    2. In **Criteri riunione** fare clic su **AllOff**.
4. Fare clic su **Applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Teams, passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per visualizzare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul **&#x2713;** (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare al criterio da assegnare. Ad esempio:
    - Vai a **Criteri per le chiamate** **vocali** >  e quindi fai clic su **Non consentireCalling**.
    - Passare a Criteri **riunione** **riunioni** >  e quindi fare clic su **AllOff**.
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto tutti gli utenti, fare clic su **Salva**.

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

Nell'esempio seguente viene illustrato come utilizzare [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il `DisallowCalling` criterio di chiamata a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Per ulteriori informazioni sull'utilizzo di PowerShell per gestire i criteri di chiamata, vedi [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

L'esempio seguente mostra come utilizzare [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare il criterio riunione `AllOff` a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Per ulteriori informazioni sull'utilizzo di PowerShell per gestire i criteri delle riunioni, vedi [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Eseguire la migrazione di Teams su VDI con chat e collaborazione per ottimizzare Teams con chiamate e riunioni

Se si ha un'implementazione esistente di Teams su VDI con chat e collaborazione in cui sono stati impostati criteri a livello utente per disattivare la funzionalità di chiamata e riunione e si esegue la migrazione a Teams con ottimizzazione AV, è necessario impostare i criteri per attivare le funzionalità di chiamata e riunione per quegli utenti di Teams in VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Impostare i criteri per attivare la funzionalità di chiamata e riunione

È possibile usare l'interfaccia di amministrazione di Teams o PowerShell per impostare e assegnare criteri per le chiamate e le riunioni agli utenti. La propagazione delle modifiche ai criteri può richiedere del tempo (alcune ore). Se non vedi immediatamente le modifiche per un determinato account, riprova dopo alcune ore.

[**Criteri per le chiamate**](teams-calling-policy.md): i criteri per le chiamate in Teams controllano le funzionalità di chiamata disponibili per gli utenti. Teams include il criterio di chiamata **AllowCalling** integrato, in cui tutte le funzionalità di chiamata sono attivate. Per attivare tutte le funzionalità di chiamata, assegnare il criterio **AllowCalling** . In alternativa, creare un criterio di chiamata personalizzato per attivare le funzionalità di chiamata desiderate e assegnarle agli utenti.

[**Criteri riunione**](meeting-policies-overview.md): i criteri delle riunioni in Teams controllano i tipi di riunioni che gli utenti possono creare e le funzionalità disponibili per i partecipanti alla riunione pianificate dagli utenti dell'organizzazione. Teams include i criteri predefiniti per le riunioni **AllOn** , in cui tutte le funzionalità per le riunioni sono attivate. Per attivare tutte le caratteristiche per le riunioni, assegnare il criterio **AllOn** . In alternativa, creare un criterio riunione personalizzato per attivare le funzionalità per le riunioni desiderate e assegnarle agli utenti.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Assegnare criteri con l'interfaccia di amministrazione di Teams

Per assegnare i criteri **di chiamata AllowCalling** e **AllOn** a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **Utenti**.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1. In **Criteri per le chiamate** fare clic su **Consentichiamata**.
    2. In **Criteri riunione** fare clic su **AllOn**.
4. Fare clic su **Applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Teams, passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per visualizzare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul **&#x2713;** (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare al criterio da assegnare. Ad esempio:
    - Passare a **Criteri per le chiamate** **vocali** >  e quindi fare clic su **Consentichiamata**.
    - Passare a **Criteri riunione riunioni** >  e quindi fare clic su **AllOn**.
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto tutti gli utenti, fare clic su **Salva**.

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

Nell'esempio seguente viene illustrato come utilizzare [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il `AllowCalling` criterio di chiamata a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Per ulteriori informazioni sull'utilizzo di PowerShell per gestire i criteri di chiamata, vedi [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

L'esempio seguente mostra come utilizzare [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare il criterio riunione `AllOn` a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Per ulteriori informazioni sull'utilizzo di PowerShell per gestire i criteri delle riunioni, vedi [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Controllare la modalità di fallback in Teams

Quando gli utenti si connettono da un endpoint non supportato, gli utenti sono in modalità di fallback, in cui av non è ottimizzato. È possibile disabilitare o abilitare la modalità di fallback impostando uno dei valori del Registro di sistema `DWORD` seguenti:

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

Per disabilitare la modalità di fallback, impostare il valore su **1**. Per abilitare solo l'audio, impostare il valore su **2**. Se il valore non è presente o è impostato su **0** (zero), la modalità di fallback è abilitata.

Questa funzionalità è disponibile in Teams versione 1.3.00.13565 e successive.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Disabilitare le impostazioni audio e video per VDI

I criteri VDI di Teams sono disponibili nel modulo teams. Questi criteri sono attivi e applicati in ambienti VDI non ottimizzati.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> Questo vale solo per gli ambienti non ottimizzati.

### <a name="update-a-module-name"></a>Aggiornare il nome di un modulo

```PowerShell
Update-Module -Name MicrosoftTeams -AllowPrerelease

<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a>Impostare i criteri per limitare le funzionalità di chiamata

Quando gli utenti il cui criterio VDI `DisableCallsAndMeetings` è impostato per accedere a `$true` Teams in VDI, non possono:

- Effettuare chiamate.
- Partecipa alle riunioni.
- Condivisione dello schermo dalla chat.

Tutti i tipi di chiamata devono essere disabilitati.

> [!NOTE]
> Questo vale solo per gli ambienti non ottimizzati.

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

Quando gli utenti il cui criterio VDI `DisableAudioVideoInCallsAndMeetings` è impostato per `$true` accedere a Teams su VDI, devono:

- Può condividere lo schermo dalla chat.
- Può partecipare a una riunione e condividere uno schermo e spostare l'audio su un telefono.
- Non è possibile effettuare chiamate audio e video da persona a persona da VDI.

> [!NOTE]
> Questo vale solo per gli ambienti non ottimizzati.

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>Problemi noti e limitazioni

### <a name="client-deployment-installation-and-setup"></a>Distribuzione, installazione e configurazione client

- Con l'installazione per ogni computer, Teams su VDI non viene aggiornato automaticamente come lo sono i client non VDI Teams. È necessario aggiornare l'immagine della macchina virtuale installando un nuovo MSI come descritto nella sezione [Installare o aggiornare l'app desktop teams in VDI](#install-or-update-the-teams-desktop-app-on-vdi) . È necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.
- Negli ambienti Citrix, se l'utente si disconnette dalla macchina virtuale mentre Teams è in esecuzione, gli aggiornamenti di Teams possono comportare l'utente in uno stato non ottimizzato per AV quando si riconnette. Consigliamo agli utenti di uscire da Teams prima di disconnettersi dalla macchina virtuale Citrix per evitare questo scenario.
- I team devono essere distribuiti per utente o per computer. La distribuzione di Teams per ogni utente e computer simultaneo non è supportata. Per eseguire la migrazione da un computer o un utente a una di queste modalità, seguire la procedura di disinstallazione e ridistribuirla in entrambe le modalità.
- Desktop virtuale di Azure al momento non supporta i client basati su macOS e Linux.
- Il cambio di tenant veloce può causare problemi relativi alle chiamate in VDI, ad esempio la condivisione dello schermo, non è disponibile. Il riavvio del client ridurrà questi problemi.

### <a name="notifications"></a>Notifiche

- La notifica sul conteggio dei messaggi e la presenza sulla barra delle applicazioni di Windows non sono supportate in un host Windows Server 2016.

### <a name="calling-and-meetings"></a>Chiamate e riunioni

Le seguenti funzionalità di chiamata e riunione non sono supportate:

- Pulsanti HID e controlli LED tra l'app Teams e i dispositivi per Citrix e VMware
- Sfocatura dello sfondo ed effetti per Citrix e VMware
- Ruoli di produttore e relatore di eventi in diretta e dal vivo
- routing Location-Based (LBR)
- Tono di call ringback PSTN
- Audio di sistema/computer condiviso
- Bypass multimediale per Instradamento diretto
- Controllo Zoom

> [!NOTE]
> Stiamo lavorando all'aggiunta di funzionalità per chiamate e riunioni attualmente disponibili solo in ambienti non VDI. Potrebbero includere un maggiore controllo dell'amministratore sulla qualità, ulteriori scenari di condivisione dello schermo e funzionalità avanzate aggiunte di recente a Teams. Contatta il tuo rappresentante di Teams per saperne di più sulle prossime funzionalità.

Di seguito sono riportati i problemi noti e le limitazioni per chiamate e riunioni:

- L'interoperabilità con Skype for Business è limitata alle chiamate audio; non esiste alcuna modalità video.
- La risoluzione dei flussi video in arrivo e in uscita è limitata a 720p.
- Teams non passa all'ultimo dispositivo audio selezionato da un utente, se il dispositivo è disconnesso e quindi riconnesso.
- Gli eventi live non sono ottimizzati.
- Condivisione dello schermo in uscita:
  - La condivisione di applicazioni non è supportata per VMware e AVD/W365.
- Dare il controllo e assumere il controllo:
  - Non supportato durante la sessione di condivisione applicazioni.

Per i problemi noti di Teams che non sono correlati a VDI, vedere [Support Teams nell'organizzazione](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="troubleshoot-citrix-components"></a>Risolvere i problemi relativi ai componenti citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams si arresta in modo anomalo o la schermata di accesso di Teams è vuota

Questo è un problema noto con Citrix VDA versioni 1906 e 1909. Per risolvere il problema, aggiungere il valore del Registro di sistema `DWORD` seguente e impostarlo `204` su (esadecimale).

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

Quindi, riavvia VDA. Per altre informazioni, vedere questo articolo del supporto citrix, [Risoluzione dei problemi di ottimizzazione HDX per Microsoft Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Argomenti correlati

- [Installare Teams in blocco con Windows Installer (MSI)](msi-deployment.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Usare Microsoft Teams su Desktop virtuale di Azure](/azure/virtual-desktop/teams-on-wvd)
