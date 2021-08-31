---
title: Teams per Virtualized Desktop Infrastructure (VDI)
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: c1353d46d77f12ea7d829f4170f6dedf335e9395
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729535"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams per Virtualized Desktop Infrastructure (VDI)

Questo articolo descrive i requisiti e le limitazioni per l'Microsoft Teams in un ambiente virtualizzato.

## <a name="what-is-vdi"></a>Che cos'è VDI?

Virtual Desktop Infrastructure (VDI) è una tecnologia di virtualizzazione che ospita un sistema operativo desktop e applicazioni in un server centralizzato in un data center. Questo consente un'esperienza desktop completamente personalizzata per gli utenti con una fonte centralizzata completamente protetta e conforme.

Microsoft Teams in un ambiente virtualizzato supporta la chat e la collaborazione. Inoltre, con le piattaforme Azure Virtual Desktop, Citrix e VMware, sono supportate anche le funzionalità di chiamata e riunione.

Teams in un ambiente virtualizzato supporta più configurazioni. Sono incluse le modalità VDI, dedicate, condivise, persistenti e non persistenti. Le funzionalità sono in continuo sviluppo e vengono aggiunte regolarmente e le funzionalità verranno espanse nei prossimi mesi e anni.

L Teams in un ambiente virtualizzato potrebbe essere leggermente diverso dall'uso Teams in un ambiente non virtualizzato. Ad esempio, alcune funzionalità avanzate potrebbero non essere disponibili in un ambiente virtualizzato e la risoluzione video potrebbe essere diversa.

Per garantire un'esperienza utente ottimale, seguire le indicazioni di questo articolo.

> [!Note]
> Per informazioni dettagliate Teams VDI su piattaforme diverse, vedere Teams [funzionalità per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams nei componenti VDI

L Teams in un ambiente virtualizzato richiede i componenti seguenti.

- **Broker di virtualizzazione:** la risorsa e la gestione connessione al provider di virtualizzazione, ad esempio Azure
- **Desktop virtuale:** stack di macchine virtuali che viene eseguito Microsoft Teams
- **Thin client:** endpoint con cui l'utente si interfaccia fisicamente
- **Teams desktop: l'app** Teams client desktop

## <a name="teams-on-vdi-requirements"></a>Teams requisiti VDI

### <a name="virtualization-provider-requirements"></a>Requisiti del provider di virtualizzazione

L Teams app desktop è stata convalidata con i principali provider di soluzioni di virtualizzazione. Con più provider di mercato, è consigliabile consultare il provider di soluzioni di virtualizzazione per assicurarsi di soddisfare i requisiti minimi.
  
Attualmente, Teams su VDI con l'ottimizzazione audio/video (AV) è certificato con Azure Virtual Desktop, Citrix e VMware. Esaminare le informazioni contenute in questa sezione per assicurarsi di soddisfare tutti i requisiti per le funzionalità appropriate.

### <a name="platforms-certified-for-teams"></a>Piattaforme certificate per Teams

Le piattaforme seguenti hanno soluzioni di infrastruttura desktop virtuale per Teams.

|Piattaforma|Soluzione|
|----|---|
|![Il logo che rappresenta Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Desktop virtuale di Azure</a> |
|![Logo che rappresenta Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">App virtuali e desktop Citrix</a> |
|![Logo che rappresenta VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Desktop virtuale di Azure

Azure Virtual Desktop offre l'ottimizzazione AV Teams in VDI. Per altre informazioni, sui requisiti e sull'installazione, vedere Usare [Teams desktop virtuale di Azure.](/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisiti per app virtuali e desktop Citrix

Citrix Virtual Apps and Desktops (in precedenza noto come XenApp e XenDesktop) fornisce l'ottimizzazione AV per Teams in VDI. Con Le app virtuali e i desktop Citrix, Teams su VDI supporta le funzionalità di chiamata e riunione oltre alla chat e alla collaborazione.

È possibile scaricare l'ultima versione di Citrix Virtual Apps and Desktops [nel sito di download di Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) È necessario eseguire prima l'accesso. Per impostazione predefinita, i componenti necessari vengono raggruppati [nell'app Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) e nell'agente di recapito virtuale (VDA). Non è necessario installare altri componenti o plug-in in CWA o VDA.

Per i requisiti più recenti per il server e il client, vedere [questo sito Web di Citrix.](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisiti di VMware Horizon Workspace e desktop

VMware Horizon è una piattaforma moderna per la distribuzione sicura di desktop virtuali e app nel cloud ibrido. Per offrire un'esperienza utente ottimale, VMware Horizon offre l'ottimizzazione dei supporti multimediali per Teams. Questa ottimizzazione migliora la produttività complessiva di desktop e app virtuali e migliora l'esperienza utente durante le chiamate e le riunioni con Teams.

È possibile scaricare l'ultima versione di VMware Horizon dalla [pagina download di VMware.](https://customerconnect.vmware.com/downloads/#all_products) I componenti di ottimizzazione dei supporti necessari fanno parte di Horizon Agent e Horizon Client per impostazione predefinita e non è necessario installare alcun plug-in aggiuntivo per usare la funzionalità di ottimizzazione per Teams.

Per ottenere i requisiti e le istruzioni più recenti su come configurare l'ottimizzazione multimediale per Teams, vedere questo sito Web [di VMware.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installare o aggiornare l'app desktop Teams in VDI

È possibile distribuire l'app desktop Teams VDI usando un'installazione per computer o per utente usando il pacchetto MSI. La scelta dell'approccio da usare varia a seconda che si usi una configurazione persistente o non persistente e che le funzionalità associate siano necessarie all'organizzazione.

Per una configurazione persistente dedicata, entrambi gli approcci funzionano. Tuttavia, per una configurazione non persistente, Teams un'installazione per computer per lavorare in modo efficiente. Vedere la [sezione Configurazione non persistente.](#non-persistent-setup)

Con l'installazione per computer, gli aggiornamenti automatici vengono disabilitati. Questo significa che per aggiornare l Teams app, è necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente. Con l'installazione per utente, gli aggiornamenti automatici sono abilitati. Per la maggior parte delle distribuzioni VDI, è consigliabile distribuire Teams usando l'installazione per computer.

Per eseguire l'aggiornamento alla versione Teams, iniziare con la procedura di disinstallazione seguita dalla distribuzione Teams versione più recente.

Per Teams'ottimizzazione AV in ambienti VDI per il corretto funzionamento, l'endpoint thin client deve avere accesso a Internet. Se l'accesso a Internet non è disponibile nell'endpoint thin client, l'avvio dell'ottimizzazione non riesce. Questo significa che l'utente è in uno stato multimediale non ottimizzato.

#### <a name="dedicated-persistent-setup"></a>Configurazione persistente dedicata

In una configurazione persistente dedicata, le modifiche al sistema operativo locale degli utenti vengono mantenute dopo la disconnessione degli utenti. Per la configurazione persistente, Teams l'installazione sia per utente che per computer.

Di seguito è riportata la configurazione minima consigliata della macchina virtuale.

|Parametro  |Sistema operativo Workstation  |Sistema operativo server  |
|---------|---------|---------|
|vCPU   |    2 core     |  4,6 o 8<br>È importante comprendere la configurazione NUMA (Non Uniform Memory Access) sottostante e configurare di conseguenza le macchine virtuali.     |
|RAM     |   4 GB      | Da 512 a 1024 MB per utente        |
|Archiviazione    | 8 GB        | Da 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configurazione non persistente

In una configurazione non persistente, le modifiche al sistema operativo locale degli utenti non vengono mantenute dopo la disconnessione degli utenti. Queste configurazioni sono in genere sessioni multi-utente condivise. La configurazione della macchina virtuale varia in base al numero di utenti e alle risorse fisiche disponibili.

Per una configurazione non persistente, Teams'app desktop deve essere installata per computer nell'immagine dorata. Per altre informazioni, vedere la sezione Installare o [aggiornare Teams'app desktop in VDI.](#install-or-update-the-teams-desktop-app-on-vdi) In questo modo si garantisce un avvio efficiente dell'app Teams durante una sessione utente.

L Teams in una configurazione non persistente richiede anche un gestore della memorizzazione nella cache dei profili, per una sincronizzazione efficiente Teams dati di runtime. Una sincronizzazione efficiente dei dati assicura che le informazioni appropriate specifiche dell'utente, ad esempio i dati, il profilo o le impostazioni di un utente, siano memorizzate nella cache durante la sessione dell'utente. Assicurarsi che i dati in queste due cartelle siano sincronizzati:<br>

- C:\Utenti\nomeutente\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Utenti\nomeutente\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Per assicurarsi che l'app Teams abbia i dati di runtime e i file necessari per eseguire l'applicazione, è necessaria una cartella comune (o, se si usa il reindirizzamento delle cartelle, un gestore di memorizzazione nella cache). Questa operazione è necessaria per ridurre i problemi di latenza di rete o gli errori di rete, che altrimenti causerebbero errori delle applicazioni e un'esperienza lenta a causa di dati e file non disponibili.

Sono disponibili diverse soluzioni di gestione della cache. Ad esempio, [FSLogix](/fslogix/overview). Per istruzioni di configurazione specifiche, consultare il provider di gestione della cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams di esclusione del contenuto memorizzato nella cache per la configurazione non persistente

Escludere quanto segue dalla cartella Teams cache, %appdata%/Microsoft/Teams. L'esclusione di questi elementi consente di ridurre le dimensioni della cache degli utenti per ottimizzare ulteriormente la configurazione non persistente.

- .txt file
- Cartella Media-stack
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps for enterprise considerazioni

Tenere presente quanto segue quando si distribuiscono Teams con Microsoft 365 Apps for enterprise in VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nuove distribuzioni di Teams tramite Microsoft 365 Apps for enterprise

Prima di distribuire Teams tramite Microsoft 365 Apps for enterprise, è necessario disinstallare le app Teams esistenti se sono state distribuite usando l'installazione per computer.

Teams tramite Microsoft 365 Apps for enterprise viene installato per utente. Per altre informazioni, vedere la sezione [Installare o aggiornare Teams'app desktop in VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams distribuzioni con Microsoft 365 Apps for enterprise aggiornamenti

Teams viene aggiunto anche alle installazioni esistenti di Microsoft 365 Apps for enterprise. Poiché Microsoft 365 Apps for enterprise installa Teams solo per utente, vedere la sezione Installare o aggiornare l'app desktop Teams in [VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Uso Teams con l'installazione e la Microsoft 365 Apps for enterprise

Microsoft 365 Apps for enterprise non supporta le installazioni per computer di Teams. Per usare l'installazione per computer, è necessario escludere Teams da Microsoft 365 Apps for enterprise. Vedere le [sezioni Distribuire Teams'app desktop](#deploy-the-teams-desktop-app-to-the-vm) nella macchina virtuale e Come escludere la distribuzione Teams tramite [Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) distribuzione.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Come escludere Teams distribuzione tramite Microsoft 365 Apps for enterprise

Per altre informazioni su Teams e Microsoft 365 Apps for enterprise, vedere Come escludere Teams dalle nuove installazioni di [Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) e Usare Criteri di gruppo per controllare l'installazione di [Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Distribuire l Teams app desktop nella macchina virtuale

1. Scaricare il Teams MSI che corrisponde al sistema operativo VDI VM usando uno dei collegamenti seguenti:

    - [Versione a 32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versione a 64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Per i cloud per enti pubblici, vedere Installare Microsoft Teams [usando Microsoft Endpoint Configuration Manager](msi-deployment.md) per i collegamenti di download ai file MSI.

    La versione minima dell'Teams desktop necessaria è la versione 1.3.00.4461. Il blocco PSTN non è supportato nelle versioni precedenti.

2. Installare il file MSI nella macchina virtuale VDI eseguendo uno dei comandi seguenti:

    - Installazione per utente (impostazione predefinita)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Questo processo è l'installazione predefinita, che Teams nella cartella utente %AppData%. A questo punto, la configurazione dell'immagine dorata è completata. Teams non funziona correttamente con l'installazione per utente in una configurazione non persistente.

    - Installazione per computer

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Questo processo aggiunge una chiave del Registro di sistema necessaria al computer che consente al Teams programma di installazione di sapere che si tratta di un'istanza VDI.  Senza di essa, il programma di installazione verrà visualizzato un errore che indica: "Installazione non riuscita.  Non è possibile eseguire l'installazione per tutti gli utenti quando non viene rilevato un ambiente VDI".

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Questo processo Teams nella cartella Programmi (x86) in un sistema operativo a 64 bit e nella cartella Programmi in un sistema operativo a 32 bit. A questo punto, la configurazione dell'immagine dorata è completata. L'Teams per ogni computer è necessario per le configurazioni non persistenti.

        La sessione di accesso interattiva successiva inizia Teams e chiede le credenziali.

        > [!NOTE]
        > Questi esempi usano anche il **parametro ALLUSERS=1.** Quando si imposta questo parametro, il programma di installazione di Teams per tutte le macchine viene visualizzato in Programmi e funzionalità nel Pannello di controllo e in App e funzionalità nelle Impostazioni di Windows per tutti gli utenti del computer. Tutti gli utenti possono quindi disinstallare Teams se hanno credenziali di amministratore.
        È importante comprendere la differenza tra **ALLUSERS=1** e **ALLUSER=1**. Il **parametro ALLUSERS=1** può essere usato in ambienti non VDI e VDI, mentre il **parametro ALLUSER=1** viene usato solo negli ambienti VDI per specificare un'installazione per computer.

3. Disinstallare il file MSI dalla macchina virtuale VDI. Esistono due modi per disinstallare Teams.

    - Script di PowerShell: è possibile usare questo script di [PowerShell](scripts/powershell-script-deployment-cleanup.md) per disinstallare Teams e rimuovere la cartella Teams per un utente. Eseguire lo script per ogni profilo utente in cui Teams è stato installato nel computer.
    - Riga di comando: eseguire il comando seguente.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Questo processo disinstalla Teams dalla cartella Programmi (x86) o Programmi, a seconda dell'ambiente del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Teams sulle prestazioni VDI

Sono disponibili diverse configurazioni di configurazione virtualizzate, ognuna con uno stato attivo diverso per l'ottimizzazione. Ad esempio, una configurazione potrebbe concentrarsi sulla densità degli utenti. Durante la pianificazione, tenere presente quanto segue per ottimizzare la configurazione in base alle esigenze del carico di lavoro dell'organizzazione.

- Requisito minimo: alcuni carichi di lavoro potrebbero richiedere una configurazione con risorse superiori ai requisiti minimi. Ad esempio, carichi di lavoro per sviluppatori che usano applicazioni che richiedono più risorse di elaborazione.
- Dipendenze: includono le dipendenze dall'infrastruttura, dal carico di lavoro e da altre considerazioni ambientali esterne all'app desktop Teams desktop.
- Funzionalità disabilitate in VDI: Teams funzionalità che richiedono un utilizzo intensivo di GPU per VDI, che consentono di migliorare l'utilizzo temporaneo della CPU. Le caratteristiche seguenti sono disabilitate:
    - Teams Animazione CSS
    - Avvio automatico giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams su VDI con chiamate e riunioni

Oltre alla chat e alla collaborazione, Teams su VDI con chiamate e riunioni è disponibile con piattaforme provider di virtualizzazione supportate. Le funzionalità supportate si basano sullo stack multimediale WebRTC e sull'implementazione del provider di virtualizzazione. Il diagramma seguente offre una panoramica dell'architettura.

![Diagramma che mostra Teams'architettura VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se attualmente si esegue Teams senza ottimizzazione AV in VDI e si usano funzionalità non ancora supportate per l'ottimizzazione, ad esempio Assegnare e assumere il controllo durante la condivisione delle app, è necessario impostare i criteri del provider di virtualizzazione per disattivare il reindirizzamento Teams. Questo significa che Teams le sessioni multimediali non verranno ottimizzate. Per istruzioni su come impostare criteri per disattivare il reindirizzamento Teams, contattare il provider di virtualizzazione.

### <a name="network-requirements"></a>Requisiti di rete

È consigliabile valutare l'ambiente per identificare i rischi e i requisiti che possono influire sulla distribuzione globale di voce e video nel cloud. Usare lo [Skype for Business di valutazione della rete per](https://www.microsoft.com/download/details.aspx?id=53885) verificare se la rete è pronta per Teams.

Per altre informazioni su come preparare la rete per Teams, vedere Preparare la rete [dell'organizzazione](prepare-network.md)per Teams .

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Eseguire la migrazione Skype for Business in VDI a Teams in VDI

Se si esegue la migrazione da Skype for Business in VDI a Teams in VDI, oltre alle differenze tra le due applicazioni, esistono alcune differenze quando viene implementato anche VDI. Alcune funzionalità attualmente non supportate in Teams VDI in Skype for Business VDI sono le seguenti:

- Criteri per piattaforma per disabilitare alcune funzionalità AV in VDI
- Assegnare e assumere il controllo durante la condivisione delle app
- Condivisione dello schermo dalla chat senza audio
- Invio e ricezione simultanee di video e condivisione dello schermo

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams nel browser Chrome e Teams'app desktop per VDI

Teams nel browser Chrome non fornisce una sostituzione dell'app desktop Teams per VDI con l'ottimizzazione AV. L'esperienza di chat e collaborazione funziona come previsto. Quando sono necessari elementi multimediali, ci sono alcune esperienze che potrebbero non soddisfare le aspettative degli utenti nel browser Chrome:

- L'esperienza di streaming audio e video potrebbe non essere ottimale. Gli utenti potrebbero subire ritardi o qualità ridotta.
- Le impostazioni del dispositivo non sono disponibili nelle impostazioni del browser.
- La gestione dei dispositivi viene gestita tramite il browser e richiede più impostazioni nelle impostazioni del sito del browser.
- Potrebbe anche essere necessario impostare le impostazioni del dispositivo nella Windows gestione dei dispositivi.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams su VDI con chat e collaborazione

Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in Teams, è possibile impostare criteri a livello di utente per disattivare la funzionalità di chiamata e riunione in Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Impostare i criteri per disattivare la funzionalità di chiamata e riunione

È possibile impostare i criteri usando l'interfaccia Microsoft Teams o PowerShell. La propagazione delle modifiche ai criteri potrebbe richiedere del tempo (alcune ore). Se le modifiche per un determinato account non sono immediatamente disponibili, riprovare tra qualche ora.

[**Criteri di chiamata:**](teams-calling-policy.md)Teams include il criterio di chiamata DisallowCalling predefinito, in cui tutte le funzionalità di chiamata sono disattivate. Assegnare il criterio DisallowCalling a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

[**Criteri riunione:**](meeting-policies-in-teams.md)Teams include i criteri predefiniti per le riunioni AllOff, in cui tutte le caratteristiche della riunione sono disattivate. Assegnare il criterio AllOff a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri usando l'interfaccia Microsoft Teams di amministrazione

Per assegnare i criteri di chiamata DisallowCalling e i criteri della riunione AllOff a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare a **Utenti**.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1. In **Criteri di chiamata** fare clic su **DisallowCalling**.
    2. In **Criteri riunione fare** clic su **AllOff.**
4. Fare clic **su Applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare al criterio da assegnare. Ad esempio:
    - Passare a **Criteri**  >  **chiamate vocali** e quindi fare clic su **DisallowCalling**.
    - Passare a **Criteri**  >  **riunione riunioni** e quindi fare clic su **AllOff.**
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, fare clic su **Salva.**

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

L'esempio seguente mostra come usare [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata DisallowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di chiamata, [vedere Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy)

L'esempio seguente mostra come usare [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri della riunione AllOff a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri delle riunioni, [vedere Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Eseguire la Teams su VDI con chat e collaborazione per ottimizzare Teams con chiamate e riunioni

Se si ha un'implementazione esistente di Teams in VDI con chat e collaborazione in cui sono stati impostati criteri a livello di utente per disattivare le funzionalità di chiamata e riunione e si esegue la migrazione a Teams con l'ottimizzazione AV, è necessario impostare criteri per attivare la funzionalità di chiamata e riunione per gli utenti di Teams per gli utenti VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Impostare i criteri per attivare la funzionalità di chiamata e riunione

È possibile usare l'Microsoft Teams di amministrazione o PowerShell per impostare e assegnare criteri di chiamata e riunione agli utenti. La propagazione delle modifiche ai criteri può richiedere del tempo (alcune ore). Se le modifiche per un determinato account non sono immediatamente disponibili, riprovare dopo alcune ore.

[**Criteri di chiamata:**](teams-calling-policy.md)i criteri di chiamata in Teams le funzionalità di chiamata disponibili per gli utenti. Teams include il criterio di chiamata AllowCalling predefinito, in cui tutte le funzionalità di chiamata sono attivate. Per attivare tutte le funzionalità di chiamata, assegnare il criterio AllowCalling. In caso contrario, creare un criterio di chiamata personalizzato per attivare le funzionalità di chiamata desiderate e assegnarle agli utenti.

[**Criteri riunione:**](meeting-policies-in-teams.md)i criteri riunione in Teams controllare i tipi di riunioni che gli utenti possono creare e le caratteristiche disponibili per i partecipanti alla riunione pianificati dagli utenti dell'organizzazione. Teams include i criteri predefiniti per le riunioni AllOn, in cui tutte le funzionalità della riunione sono attivate. Per attivare tutte le caratteristiche della riunione, assegnare il criterio AllOn. In caso contrario, è possibile creare criteri di riunione personalizzati per attivare le caratteristiche della riunione desiderate e assegnarle gli utenti.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri usando l'interfaccia Microsoft Teams di amministrazione

Per assegnare i criteri di chiamata AllowCalling e i criteri riunione AllOn a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare a **Utenti**.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1. In **Criteri di chiamata** fare clic su **AllowCalling**.
    2. In **Criteri riunione fare** clic su **AllOn.**
4. Fare clic **su Applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare **clic sul&#x2713;** (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare al criterio da assegnare. Ad esempio:
    - Passare a **Criteri**  >  **chiamate vocali** e quindi fare clic su **ConsentiChiamazione.**
    - Passare a **Criteri**  >  **riunione riunioni** e quindi fare clic su **AllOn.**
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, fare clic su **Salva.**

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

L'esempio seguente mostra come usare [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata AllowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di chiamata, [vedere Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy)

L'esempio seguente mostra come usare [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri riunione AllOn a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri delle riunioni, [vedere Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="control-fallback-mode-in-teams"></a>Controllare la modalità di fallback in Teams

Quando gli utenti si connettono da un endpoint non supportato, gli utenti sono in modalità fallback, in cui av non è ottimizzato. È possibile disabilitare o abilitare la modalità di fallback impostando uno dei valori DWORD del Registro di sistema seguenti:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Per disabilitare la modalità di fallback, impostare il valore su **1.** Per abilitare solo l'audio, impostare il valore su **2**. Se il valore non è presente o è impostato su **0** (zero), la modalità di fallback è abilitata.

Questa funzionalità è disponibile nella versione Teams 1.3.00.13565 e successive.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Disabilitare le impostazioni audio e video per VDI

Teams I criteri VDI sono disponibili nel Microsoft Teams modulo. Questi criteri sono attivi e applicati in ambienti VDI non ottimizzati.

- New-CsTeamsVdiPolicy  
- Grant-CsTeamsVdiPolicy
- Remove-CsTeamsVdiPolicy
- Set-CsTeamsVdiPolicy

> [!NOTE]
> Questo è solo per gli ambienti non ottimizzati.

### <a name="update-a-module-name"></a>Aggiornare il nome di un modulo

update-Module -Name MicrosoftTeams -AllowPrerelease

```PowerShell
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

### <a name="set-policies-to-limit-calling-features"></a>Impostare criteri per limitare le funzionalità di chiamata

Quando gli utenti con questa impostazione dei criteri VDI -DisableCallsAndMeetings $true per accedere a Teams in VDI, non dovrebbero essere in grado di:

- Effettuare chiamate.
- Partecipare alle riunioni.
- Fai una condivisione dello schermo dalla chat.

Tutti i tipi di chiamata devono essere disabilitati.

> [!NOTE]
> Questo è solo per gli ambienti non ottimizzati.

```PowerShell
#>
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false
<# Assign Policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<#
Show all Policies  
#>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
<#
```

Quando gli utenti con l'impostazione dei criteri VDI -DisableAudioVideoInCallsAndMeetings $true a Teams in VDI, dovrebbero essere in grado di:

- Fai una condivisione dello schermo dalla chat.
- Partecipare a una riunione e condividere uno schermo. Spostare l'audio in un telefono.
- Gli utenti non dovrebbero essere in grado di effettuare una chiamata audio e video da persona a persona da VDI.

> [!NOTE]
> Questo è solo per gli ambienti non ottimizzati.

```powershell
#>
$PolName = "DisableCallsAndMeetingsAV"
New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<# ## Cleanup afterwards #>
$cleanup = $false
if($cleanup){
    "Doing cleanup"
    # de-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
    # remove Policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>Problemi noti e limitazioni

### <a name="client-deployment-installation-and-setup"></a>Distribuzione, installazione e configurazione del client

- Con l'installazione per computer, Teams in VDI non viene aggiornato automaticamente come nei client non VDI Teams client. È necessario aggiornare l'immagine della macchina virtuale installando un nuovo file MSI come descritto nella sezione Installare o aggiornare l'app desktop Teams in [VDI.](#install-or-update-the-teams-desktop-app-on-vdi) È necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.
- Negli ambienti Citrix, se l'utente si disconnette dalla macchina virtuale mentre Teams è in esecuzione, gli aggiornamenti di Teams possono comportare che l'utente sia in uno stato non ottimizzato per av quando si riconnette. È consigliabile che gli utenti Teams prima di disconnettersi da Citrix Virtual Machine per evitare questo scenario.
- Teams deve essere distribuito per utente o per computer. La distribuzione di Teams per utenti simultanei e per computer non è supportata. Per eseguire la migrazione da un computer o un utente a una di queste modalità, seguire la procedura di disinstallazione e ridistribuire in entrambe le modalità.
- Azure Virtual Desktop non supporta al momento i client basati su macOS e Linux.
- L'opzione tenant veloce può causare problemi relativi alle chiamate in VDI, ad esempio la condivisione dello schermo non disponibile. Il riavvio del client ridurrà questi problemi.

### <a name="calling-and-meetings"></a>Chiamate e riunioni

Le funzionalità di chiamata e riunione seguenti non sono supportate:

- Qualsiasi funzionalità multi-finestra, ad esempio le nuove esperienze di riunione o qualsiasi funzionalità fornita con la nuova esperienza di riunione
- Servizi di emergenza migliorati
- Pulsanti HID e controlli LED tra l Teams app e i dispositivi
- Sfocatura ed effetti dello sfondo
- Ruoli di relatore e produttore di eventi live e broadcast
- Location-Based routing (LBR)
- Tono di squillo delle chiamate PSTN
- Audio/computer di sistema condiviso
- Bypass multimediale per Instradamento diretto
- Parcheggio di chiamata
- Controllo zoom

> [!NOTE]
> Stiamo lavorando per aggiungere funzionalità di chiamata e riunione attualmente disponibili solo in ambienti non VDI. Questi potrebbero includere un maggiore controllo dell'amministratore sulla qualità, altri scenari di condivisione dello schermo e funzionalità avanzate aggiunte di recente a Teams. Contatta il tuo Teams rappresentante per saperne di più sulle funzionalità imminenti.

Di seguito sono riportati i problemi noti e le limitazioni per le chiamate e le riunioni:

- L'interoperabilità con Skype for Business è limitata alle chiamate audio; non esiste alcuna modalità video.
- La risoluzione dello stream video in ingresso e in uscita è limitata a una risoluzione di 720p.
- È supportato un solo flusso video da una fotocamera in arrivo o da uno stream di condivisione dello schermo. Quando c'è una condivisione dello schermo in arrivo, viene visualizzata la condivisione dello schermo, invece del video dell'altoparlante dominante.
- Teams non passa all'ultimo dispositivo audio selezionato da un utente, se il dispositivo è disconnesso e quindi riconnesso.
- Gli eventi live non sono ottimizzati.
- Condivisione dello schermo in uscita:
    - La condivisione delle applicazioni non è supportata.
- Assegnare il controllo e assumere il controllo:
    - Non supportato durante una sessione di condivisione dello schermo o di condivisione applicazioni.
    - Supportata durante una PowerPoint di condivisione.
- Limitazioni solo per Citrix
   - La scala DPI elevata in CWA non è supportata.

Per Teams problemi noti non correlati a VDI, vedere Supporto Teams [nell'organizzazione.](/MicrosoftTeams/troubleshoot/teams-welcome)

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="troubleshoot-citrix-components"></a>Risolvere i problemi relativi ai componenti Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams si arresta in modo anomalo o Teams schermata di accesso è vuota

Si tratta di un problema noto con le versioni 1906 e 1909 di Citrix VDA. Per risolvere questo problema, aggiungere il valore DWORD del Registro di sistema seguente e impostarlo su 204 (esadecimale).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Riavviare quindi VDA. Per altre informazioni, vedere questo articolo del supporto tecnico di Citrix, Risoluzione dei problemi di [ottimizzazione HDX per Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Argomenti correlati

- [Installare Microsoft Teams con MSI](msi-deployment.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Usare Microsoft Teams desktop virtuale di Azure](/azure/virtual-desktop/teams-on-wvd)
