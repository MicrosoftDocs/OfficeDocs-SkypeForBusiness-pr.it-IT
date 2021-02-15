---
title: Teams per Virtualized Desktop Infrastructure (VDI)
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Informazioni su come eseguire Microsoft Teams in un ambiente VDI (Virtualized Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8022e6b1c4d6ebcaeb70ec7cc23e1f4cad5d929a
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110289"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams per Virtualized Desktop Infrastructure (VDI)

Questo articolo descrive i requisiti e le limitazioni per l'uso di Microsoft Teams in un ambiente virtualizzato.

## <a name="what-is-vdi"></a>Che cos'è VDI?

Virtual Desktop Infrastructure (VDI) è una tecnologia di virtualizzazione che ospita un sistema operativo desktop e le applicazioni in un server centralizzato in un data center. In questo modo si offre un'esperienza desktop completamente personalizzata agli utenti con un'origine centralizzata completamente protetta e conforme.

Microsoft Teams in un ambiente virtualizzato supporta la chat e la collaborazione. Inoltre, con le piattaforme Windows Virtual Desktop, Citrix e VMware sono supportate anche le funzionalità di chiamata e riunione.

Teams in un ambiente virtualizzato supporta più configurazioni. Sono incluse le modalità VDI, dedicate, condivise, persistenti e non persistenti. Le caratteristiche sono in fase di sviluppo continuo e vengono aggiunte regolarmente e le funzionalità si espanderanno nei prossimi mesi e anni.

L'uso di Teams in un ambiente virtualizzato potrebbe essere piuttosto diverso dall'uso di Teams in un ambiente non virtualizzato. Ad esempio, alcune caratteristiche avanzate potrebbero non essere disponibili in un ambiente virtualizzato e la risoluzione video potrebbe essere diversa.

Per assicurare un'esperienza utente ottimale, seguire le indicazioni fornite in questo articolo.

> [!Note]
> Per informazioni dettagliate su Teams VDI su piattaforme diverse, vedere le [funzionalità di Teams per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams su componenti VDI

L'uso di Teams in un ambiente virtualizzato richiede i componenti seguenti.

- **Broker di virtualizzazione:** la risorsa e la gestione delle connessioni al provider di virtualizzazione, ad esempio Azure
- **Desktop virtuale:** lo stack di macchine virtuali (VM) che esegue Microsoft Teams
- **Thin client:** endpoint con cui l'utente si interfaccia fisicamente
- **App desktop Teams**: L'app client desktop di Teams

## <a name="teams-on-vdi-requirements"></a>Requisiti di Teams su VDI

### <a name="virtualization-provider-requirements"></a>Requisiti del provider di virtualizzazione

L'app desktop di Teams è stata convalidata con i principali provider di soluzioni di virtualizzazione. Con più provider di mercato, è consigliabile consultare il provider di soluzioni di virtualizzazione per assicurarsi di soddisfare i requisiti minimi.
  
Attualmente Teams su VDI con ottimizzazione audio/video (AV) è certificato con Desktop virtuale di Windows, Citrix e VMware. Esaminare le informazioni in questa sezione per assicurarsi di soddisfare tutti i requisiti per le funzionalità appropriate.

### <a name="platforms-certified-for-teams"></a>Piattaforme certificate per Teams

Le piattaforme seguenti hanno soluzioni infrastruttura desktop virtuale per Teams.

|Piattaforma|Soluzione|
|----|---|
|![Il logo che rappresenta Microsoft](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Desktop virtuale di Windows</a> |
|![Logo che rappresenta Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">App virtuali Citrix e desktop</a> |
|![Logo che rappresenta VMware](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Desktop virtuale di Windows

Windows Virtual Desktop offre l'ottimizzazione av per Teams in VDI. Per saperne di più e sui requisiti e l'installazione, [vedi Usare Teams su Windows Virtual Desktop.](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisiti per desktop e app virtuali Citrix

Citrix Virtual Apps e Desktops (precedentemente noti come XenApp e XenDesktop) fornisce l'ottimizzazione AV per Teams su VDI. Con Le app virtuali e i desktop Citrix, Teams su VDI supporta le funzionalità di chiamata e riunione oltre alla chat e alla collaborazione.

È possibile scaricare l'ultima versione di Citrix Virtual Apps e Desktops [sul sito di download di Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Dovrai accedere prima di tutto).) Per impostazione predefinita, i componenti necessari vengono raggruppati nelle [app Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) e Virtual Delivery Agent (VDA). Non è necessario installare componenti o plug-in aggiuntivi in CWA o VDA.

Per informazioni sui requisiti più recenti per server e client, vedere [questo sito Web di Citrix.](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisiti per L'area di lavoro Horizon per VMware e i requisiti per il desktop

Orizzonte di VMware è una piattaforma moderna per la distribuzione sicura di desktop virtuali e app nel cloud ibrido. Per offrire un'esperienza ottimale per l'utente finale, Horizon di VMware fornisce l'ottimizzazione degli elementi multimediali per Teams. Questa ottimizzazione migliora la produttività complessiva tra desktop virtuali e app e migliora l'esperienza utente durante le chiamate e le riunioni con Teams.

È possibile scaricare l'ultima versione di VMware Horizon dalla pagina [di download di VMware.](https://my.vmware.com/web/vmware/downloads/#all_products) I componenti necessari per l'ottimizzazione degli elementi multimediali fanno parte dell'agente Horizon e del client Horizon per impostazione predefinita e non è necessario installare altri plug-in per usare la funzionalità di ottimizzazione per Teams.

Per ottenere i requisiti e le istruzioni più recenti su come configurare l'ottimizzazione multimediale per Teams, vedere [questo sito Web VMware.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installare o aggiornare l'app desktop Teams in VDI

È possibile distribuire l'applicazione desktop di Teams per VDI usando un'installazione per singolo computer o per utente usando il pacchetto MSI. La scelta dell'approccio da usare varia a seconda che si usi una configurazione persistente o non permanente e che si o meno le funzionalità associate siano necessarie per l'organizzazione.

Per una configurazione permanente dedicata, può essere possibile usare uno dei due approcci. Tuttavia, per una configurazione non permanente, Teams richiede un'installazione per singolo computer per lavorare in modo efficiente. Vedere la [sezione Configurazione non permanente.](#non-persistent-setup)

Con l'installazione per computer, gli aggiornamenti automatici sono disabilitati. Questo significa che per aggiornare l'app di Teams, è necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente. Con l'installazione per utente, gli aggiornamenti automatici sono abilitati. Per la maggior parte delle distribuzioni VDI, è consigliabile distribuire Teams usando l'installazione per singolo computer.

Per eseguire l'aggiornamento all'ultima versione di Teams, inizia con la procedura di disinstallazione seguita dalla distribuzione della versione più recente di Teams.

Per il corretto funzionamento dell'ottimizzazione AV di Teams in ambienti VDI, l'endpoint thin client deve avere accesso a Internet. Se l'accesso a Internet non è disponibile nell'endpoint thin client, l'avvio dell'ottimizzazione non riesce. Questo significa che l'utente è in uno stato multimediale non ottimizzato.

#### <a name="dedicated-persistent-setup"></a>Configurazione permanente dedicata

In una configurazione permanente dedicata, le modifiche apportate al sistema operativo locale degli utenti vengono mantenute dopo la disconnessione. Per la configurazione permanente, Teams supporta sia l'installazione per utente che per singolo computer.

Di seguito è riportata la configurazione minima della macchina virtuale consigliata.

|Parametro  |Sistema operativo Workstation  |Sistema operativo server  |
|---------|---------|---------|
|vCPU   |    2 core     |  4,6 o 8<br>È importante comprendere la configurazione di accesso non uniforme alla memoria sottostante (NUMA) e configurare le macchine virtuali di conseguenza.     |
|RAM     |   4 GB      | Da 512 a 1024 MB per utente        |
|Archiviazione    | 8 GB        | Da 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configurazione non permanente

In una configurazione non permanente, le modifiche apportate al sistema operativo locale degli utenti non vengono mantenute dopo la disconnessione. Queste configurazioni sono in genere sessioni multi-utente condivise. La configurazione della macchina virtuale varia in base al numero di utenti e alle risorse fisiche disponibili per la scatola.

Per una configurazione non permanente, l'app desktop di Teams deve essere installata per singolo computer fino all'immagine aurea. Per altre informazioni, vedere la sezione Installare [o aggiornare l'app desktop Teams in VDI.](#install-or-update-the-teams-desktop-app-on-vdi) In questo modo si garantisce un avvio efficiente dell'app Teams durante una sessione utente.

L'uso di Teams in una configurazione non permanente richiede anche un manager di memorizzazione nella cache dei profili per una sincronizzazione efficiente dei dati di runtime di Teams. Una sincronizzazione efficiente dei dati assicura che le informazioni appropriate specifiche dell'utente, ad esempio i dati, il profilo o le impostazioni di un utente, siano memorizzate nella cache durante la sessione dell'utente. Verificare che i dati in queste due cartelle siano sincronizzati:<br>
- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Utenti#D0 omeutente\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> È necessaria una cartella di roaming (o, se si usa il reindirizzamento delle cartelle, un responsabile della memorizzazione nella cache) per assicurarsi che l'app Teams abbia i dati di runtime e i file necessari per eseguire l'applicazione. Questo è necessario per ridurre i problemi di latenza della rete o gli errori di rete, che altrimenti causerebbero errori delle applicazioni e un'esperienza lenta a causa di dati e file non disponibili.

Sono disponibili diverse soluzioni di gestione della cache. Ad esempio, [FSLogix.](https://docs.microsoft.com/fslogix/overview) Per istruzioni di configurazione specifiche, rivolgersi al provider di gestione della cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Elenco di esclusione dei contenuti memorizzati nella cache di Teams per la configurazione non permanente

Escludere i seguenti elementi dalla cartella di memorizzazione nella cache di Teams, %appdata%/Microsoft/Teams. L'esclusione di questi elementi consente di ridurre le dimensioni della cache degli utenti per ottimizzare ulteriormente la configurazione non permanente.

- file txt
- Media-stack folder
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps for Enterprise considerations

Quando si distribuisce Teams con Microsoft 365 Apps for Enterprise in VDI, tenere presente quanto segue.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nuove distribuzioni di Teams tramite Microsoft 365 Apps per le aziende

Prima di distribuire Teams tramite Microsoft 365 Apps per le aziende, devi prima disinstallare le eventuali app Teams pre-esistenti se sono state distribuite con l'installazione per singolo computer.

Teams tramite Microsoft 365 Apps for Enterprise viene installato per utente. Per altre informazioni, vedere la sezione [Installare o aggiornare l'app desktop Teams in VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Distribuzioni di Teams tramite Microsoft 365 Apps per gli aggiornamenti aziendali

È in corso anche l'aggiunta di Teams alle installazioni esistenti di Microsoft 365 Apps per le aziende. Poiché Microsoft 365 Apps per le aziende installa Teams solo per utente, vedere la sezione Installare o aggiornare [l'app desktop Teams in VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Uso di Teams con l'installazione per singolo computer e Microsoft 365 Apps per le aziende

Microsoft 365 Apps for Enterprise non supporta le installazioni per computer di Teams. Per usare l'installazione per singolo computer, è necessario escludere Teams da Microsoft 365 Apps for enterprise. Vedere le [sezioni Distribuire l'app desktop Teams](#deploy-the-teams-desktop-app-to-the-vm) nella macchina virtuale e come escludere la distribuzione di Teams tramite le sezioni App di Microsoft [365 per le](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) aziende.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Come escludere la distribuzione di Teams tramite Microsoft 365 Apps per le aziende

Per ulteriori informazioni su Teams e Microsoft 365 Apps for enterprise, vedi Come escludere Teams dalle nuove installazioni di [Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) e Usare Criteri di gruppo per controllare l'installazione di [Teams.](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Distribuire l'app desktop Teams nella macchina virtuale

1. Scaricare il pacchetto MSI di Teams che corrisponde al sistema operativo VDI VM usando uno dei collegamenti seguenti:

    - [Versione a 32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versione a 64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Per i cloud di enti pubblici, [vedere Installare Microsoft Teams con Microsoft Endpoint Configuration Manager](msi-deployment.md) per i collegamenti di download ai file MSI.

    La versione minima dell'app desktop di Teams richiesta è la versione 1.3.00.4461. Il blocco PSTN non è supportato nelle versioni precedenti.

2. Installare MSI in VDI VM eseguendo uno dei comandi seguenti:

    - Installazione per utente (impostazione predefinita)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Questo processo è l'installazione predefinita, che installa Teams nella cartella utente %AppData%. A questo punto, la configurazione dell'immagine aurea è stata completata. Teams non funziona correttamente con l'installazione per utente in una configurazione non permanente.

    - Installazione per computer

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Questo processo installa Teams nella cartella Programmi (x86) in un sistema operativo a 64 bit e nella cartella Programmi in un sistema operativo a 32 bit. A questo punto, la configurazione dell'immagine aurea è stata completata. L'installazione di Teams per computer è necessaria per le configurazioni non permanenti.

        La prossima sessione di accesso interattiva avvia Teams e chiede le credenziali.

        > [!NOTE]
        > Questi esempi usano anche il **parametro ALLUSERS=1.** Quando si imposta questo parametro, il programma di installazione di Teams per tutte le macchine viene visualizzato in Programmi e funzionalità nel Pannello di controllo e in App e funzionalità nelle Impostazioni di Windows per tutti gli utenti del computer. Tutti gli utenti possono quindi disinstallare Teams se hanno credenziali di amministratore.
        È importante comprendere la differenza tra **ALLUSERS=1** e **ALLUSER=1.** Il parametro **ALLUSERS=1** può essere usato in ambienti non VDI e VDI, mentre il parametro **ALLUSER=1** viene usato solo negli ambienti VDI per specificare un'installazione per singolo computer.

3. Disinstallare MSI da VDI VM. Ci sono due modi per disinstallare Teams.

    - Script di PowerShell: è possibile usare [questo script di PowerShell](scripts/powershell-script-deployment-cleanup.md) per disinstallare Teams e rimuovere la cartella Teams per un utente. Eseguire lo script per ogni profilo utente in cui Teams è stato installato nel computer.
    - Riga di comando: eseguire il comando seguente.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Questo processo disinstalla Teams dalla cartella Programmi (x86) o File di programma, a seconda dell'ambiente del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Considerazioni sulle prestazioni di Teams su VDI

Sono disponibili diverse configurazioni di configurazione virtualizzate, ognuna con uno stato attivo diverso per l'ottimizzazione. Ad esempio, una configurazione potrebbe concentrarsi sulla densità degli utenti. Quando si pianifica, considerare quanto segue per ottimizzare la configurazione in base alle esigenze del carico di lavoro dell'organizzazione.

- Requisito minimo: alcuni carichi di lavoro potrebbero richiedere una configurazione con risorse che sono superiori ai requisiti minimi. Ad esempio, carichi di lavoro per sviluppatori che usano applicazioni che richiedono più risorse di elaborazione.
- Dipendenze: queste includono la dipendenza dall'infrastruttura, dal carico di lavoro e da altre considerazioni relative all'ambiente al di fuori dell'applicazione desktop di Teams.
- Funzionalità disabilitate in VDI: Teams disabilita le funzionalità a uso intensivo di GPU per VDI, che possono contribuire a migliorare l'utilizzo temporaneio della CPU. Le caratteristiche seguenti sono disabilitate:
    - Animazione CSS di Teams
    - Avvio automatico di Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams su VDI con chiamate e riunioni

Oltre alla chat e alla collaborazione, Teams su VDI con chiamate e riunioni è disponibile con piattaforme provider di virtualizzazione supportate. Le caratteristiche supportate sono basate sullo stack degli elementi multimediali WebRTC e sull'implementazione del provider di virtualizzazione. Il diagramma seguente offre una panoramica dell'architettura.

![Diagramma che mostra Teams sull'architettura VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se attualmente si esegue Teams senza ottimizzazione AV in VDI e si usano funzionalità non ancora supportate per l'ottimizzazione (ad esempio Concedere e assumere il controllo durante la condivisione delle app), è necessario impostare i criteri del provider di virtualizzazione per disattivare il reindirizzamento di Teams. Ciò significa che le sessioni multimediali di Teams non saranno ottimizzate. Per la procedura su come impostare i criteri per disattivare il reindirizzamento di Teams, contattare il provider di virtualizzazione.

### <a name="network-requirements"></a>Requisiti di rete

È consigliabile valutare l'ambiente per identificare i rischi e i requisiti che possono influire sulla distribuzione generale di audio e video nel cloud. Usare lo [strumento di valutazione della rete](https://www.microsoft.com/download/details.aspx?id=53885) di Skype for Business per verificare se la rete è pronta per Teams.

Per altre informazioni su come preparare la rete per Teams, vedere Preparare la rete [dell'organizzazione per Teams.](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Eseguire la migrazione da Skype for Business su VDI a Teams in VDI

Se si esegue la migrazione da Skype for Business su VDI a Teams in VDI, oltre alle differenze tra le due applicazioni, vi sono alcune differenze nell'implementazione anche di VDI. Alcune funzionalità attualmente non supportate in Teams VDI in Skype for Business VDI sono le seguenti:

- Criteri per piattaforma per disabilitare alcune funzionalità AV in VDI
- Concedere e assumere il controllo durante la condivisione delle app
- Condivisione dello schermo dalla chat senza audio
- Invio e ricezione simultanee di video e condivisione dello schermo

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Confronto tra Teams nel browser Chrome e l'app desktop Teams per VDI

Teams nel browser Chrome non offre una sostituzione dell'app desktop Teams per VDI con l'ottimizzazione AV. L'esperienza di chat e collaborazione funziona come previsto. Quando sono necessari elementi multimediali, esistono alcune esperienze che potrebbero non soddisfare le aspettative degli utenti nel browser Chrome:

- L'esperienza di streaming audio e video potrebbe non essere ottimale. Gli utenti potrebbero avere ritardi o qualità ridotta.
- Le impostazioni del dispositivo non sono disponibili nelle impostazioni del browser.
- La gestione dei dispositivi viene gestita tramite il browser e richiede più impostazioni nelle impostazioni del sito del browser.
- Potrebbe anche essere necessario configurare le impostazioni del dispositivo in Gestione dispositivi di Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams su VDI con chat e collaborazione

Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in Teams, è possibile impostare criteri a livello utente per disattivare le funzionalità di chiamata e riunione in Teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Impostare i criteri per disattivare la funzionalità di chiamata e riunione

È possibile impostare i criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell. La propagazione delle modifiche ai criteri può richiedere del tempo (alcune ore). Se non si vedono immediatamente le modifiche per un determinato account, riprovare tra qualche ora.

[**Criteri di chiamata:**](teams-calling-policy.md)Teams include il criterio di chiamata DisallowCalling incorporato, in cui tutte le funzionalità di chiamata sono disattivate. Assegnare il criterio DisallowCalling a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

[**Criteri riunione:**](meeting-policies-in-teams.md)Teams include il criterio predefinito per le riunioni AllOff, in cui tutte le funzionalità per le riunioni sono disattivate. Assegnare il criterio AllOff a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri tramite l'interfaccia di amministrazione di Microsoft Teams

Per assegnare il criterio di chiamata DisallowCalling e il criterio Riunione AllOff a un utente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Utenti.**
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1.  In **Criteri di chiamata** fare clic su **DisallowCalling.**
    2.  In **Criteri riunione fare** clic su **AllOff.**
4. Fare clic **su Applica.**

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare al criterio da assegnare. Ad esempio:
    - Passare ai **criteri per**  >  **le chiamate** vocali, quindi fare clic su **DisallowCalling.**
    - Passare ai **criteri**  >  **delle riunioni,** quindi fare clic su **AllOff.**
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, fare clic su **Salva.**

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

L'esempio seguente mostra come utilizzare [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata DisallowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di chiamata, vedi [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

L'esempio seguente mostra come utilizzare il cmdlet [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri di riunione AllOff a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di riunione, vedi [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Eseguire la migrazione di Teams su VDI con chat e collaborazione per ottimizzare Teams con chiamate e riunioni

Se si ha già un'implementazione di Teams su VDI con chat e collaborazione in cui sono stati impostati criteri a livello utente per disattivare le funzionalità di chiamata e riunione e si esegue la migrazione a Teams con ottimizzazione AV, è necessario impostare i criteri per attivare le funzionalità di chiamata e riunione per tali team in utenti VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Impostare i criteri per attivare la funzionalità di chiamata e riunione

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare e assegnare criteri di chiamata e riunione agli utenti. La propagazione delle modifiche ai criteri può richiedere del tempo (alcune ore). Se non si vedono subito le modifiche per un determinato account, riprovare dopo alcune ore.

[**Criteri di chiamata:**](teams-calling-policy.md)i criteri di chiamata in Teams controllano quali funzionalità di chiamata sono disponibili per gli utenti. Teams include il criterio di chiamata AllowCalling incorporato, in cui tutte le funzionalità di chiamata sono attivate. Per attivare tutte le funzionalità di chiamata, assegnare il criterio AllowCalling. In caso contrario, creare un criterio di chiamata personalizzato per attivare le funzionalità di chiamata desiderate e assegnarlo agli utenti. 

[**Criteri per le**](meeting-policies-in-teams.md)riunioni: i criteri di riunione in Teams controllano i tipi di riunioni che gli utenti possono creare e le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti dell'organizzazione. Teams include il criterio predefinito per le riunioni AllOn, in cui tutte le funzionalità per le riunioni sono attivate. Per attivare tutte le funzionalità della riunione, assegnare il criterio AllOn. In caso contrario, creare un criterio di riunione personalizzato per attivare le caratteristiche di riunione desiderate e assegnarle gli utenti.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri tramite l'interfaccia di amministrazione di Microsoft Teams

Per assegnare il criterio di chiamata AllowCalling e il criterio Riunione AllOn a un utente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Utenti.**
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1.  In **Criteri di chiamata** fare clic su **ConsentiChiamata.**
    2.  In **Criteri riunione fare** clic su **Su.**
4. Fare clic **su Applica.**

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare **&#x2713;** clic sul segno di spunta nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare al criterio da assegnare. Ad esempio:
    - Passare ai **criteri per**  >  **le chiamate** vocali, quindi fare clic su **ConsentiChiamata.**
    - Passare a **Criteri**  >  **riunione riunioni,** quindi fare clic su **Su.**
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, fare clic su **Salva.**

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

L'esempio seguente mostra come utilizzare [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata AllowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di chiamata, vedi [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

L'esempio seguente mostra come utilizzare il cmdlet [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri di riunione AllOn a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di riunione, vedi [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="control-fallback-mode-in-teams"></a>Controllare la modalità di fallback in Teams

Quando gli utenti si connettono da un endpoint non supportato, gli utenti sono in modalità di fallback, in cui av non è ottimizzato. È possibile disabilitare o abilitare la modalità di fallback impostando uno dei valori DWORD del Registro di sistema seguenti:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Per disabilitare la modalità di fallback, impostare il valore su **1.** Per abilitare solo l'audio, impostare il valore su **2.** Se il valore non è presente o è impostato su **0** (zero), la modalità di fallback è abilitata.

Questa funzionalità è disponibile in Teams versione 1.3.00.13565 e successive.

## <a name="known-issues-and-limitations"></a>Problemi noti e limitazioni

### <a name="client-deployment-installation-and-setup"></a>Distribuzione, installazione e configurazione client

- Con l'installazione per computer, Teams su VDI non viene aggiornato automaticamente come i client non VDI Teams. È necessario aggiornare l'immagine della macchina virtuale installando un nuovo file MSI come descritto nella sezione Installare o aggiornare l'app desktop Teams in [VDI.](#install-or-update-the-teams-desktop-app-on-vdi) È necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.
- I team devono essere distribuiti per utente o per singolo computer. La distribuzione di Teams per utenti simultanei e per singolo computer non è supportata. Per eseguire la migrazione da un computer o un utente a una di queste modalità, seguire la procedura di disinstallazione e ridistribuire a entrambe le modalità.
- Al momento, Windows Virtual Desktop e VMware non supportano i client basati su MacOS e Linux.
- Citrix non supporta i client MacOs al momento.
- Citrix non supporta l'uso di proxy HTTP espliciti definiti in un endpoint.

### <a name="calling-and-meetings"></a>Chiamate e riunioni

Le seguenti funzionalità di chiamata e riunione non sono supportate:

- Tutte le funzionalità in più finestre, come le nuove esperienze di riunione o tutte le funzionalità disponibili nella nuova esperienza di riunione
- Servizi di emergenza migliorati
- Pulsanti HID e controlli LED tra l'app Teams e i dispositivi
- Sfocatura ed effetti dello sfondo
- Broadcast e produttore di eventi live e ruoli di relatore
- Location-Based routing (LBR)
- Parco delle chiamate
- Coda di chiamata
- Audio/computer di sistema condiviso
- Bypass multimediale per Instradamento diretto

> [!NOTE]
> Stiamo lavorando all'aggiunta di funzionalità per chiamate e riunioni attualmente disponibili solo in ambienti non VDI. Questi potrebbero includere un maggior controllo da parte dell'amministratore sulla qualità, altri scenari di condivisione dello schermo e funzionalità avanzate aggiunte di recente a Teams. Contatta il tuo rappresentante Teams per ulteriori informazioni sulle prossime funzionalità.

Di seguito sono riportati i problemi noti e le limitazioni per le chiamate e le riunioni:

- L'interoperabilità con Skype for Business è limitata alle chiamate audio; non esiste alcuna modalità video.
- Nelle riunioni o chiamate di gruppo è supportato un solo flusso video in arrivo. Quando più persone inviano un video, in un dato momento viene mostrato solo il video dell'altoparlante in prima posizione.
- La risoluzione dei flussi video in ingresso e in uscita è limitata a una risoluzione di 720 p. Si tratta di un limite di WebRTC.
- È supportato un solo flusso video da una videocamera o da uno stream di condivisione dello schermo in arrivo. Quando c'è una condivisione dello schermo in arrivo, viene mostrata quella condivisione dello schermo, invece del video dell'altoparlante in prima posizione.
- Teams non passa all'ultimo dispositivo audio selezionato da un utente, se il dispositivo è disconnesso e quindi riconnesso.
- Condivisione dello schermo in uscita:
    - La condivisione delle applicazioni non è supportata.
- Concedere il controllo e assumere il controllo:
    - Non supportato durante una sessione di condivisione dello schermo o di condivisione applicazioni.
    - Supportata durante una sessione di condivisione PowerPoint.
- Limitazioni solo per Citrix
    - Quando si condivide lo schermo in una configurazione con più monitor, viene condiviso solo il monitor principale.
    - Il ridimensionamento DPI elevato in CWA non è supportato.

Per i problemi noti di Teams non correlati a VDI, vedere Team di [supporto nell'organizzazione.](Known-issues.md)

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="troubleshoot-citrix-components"></a>Risolvere i problemi relativi ai componenti Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams si arresta in modo anomalo o la schermata di accesso a Teams è vuota

Si tratta di un problema noto con citrix VDA 1906 e 1909. Per risolvere il problema, aggiungere il valore DWORD del Registro di sistema seguente e impostarlo su 204 (esadecimale).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Riavviare quindi VDA. Per altre informazioni, vedere questo articolo del supporto Citrix, Risoluzione dei problemi [di ottimizzazione HDX per Teams.](https://support.citrix.com/article/CTX253754)

## <a name="related-topics"></a>Argomenti correlati

- [Installare Microsoft Teams con MSI](msi-deployment.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Usare Microsoft Teams su Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
