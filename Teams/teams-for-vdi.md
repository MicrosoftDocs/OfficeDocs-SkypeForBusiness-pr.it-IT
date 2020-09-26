---
title: Teams per Virtualized Desktop Infrastructure (VDI)
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Informazioni su come eseguire Microsoft teams in un ambiente VDI (Virtualizzated Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0d7d20c9faa8dd214c73e1ea759d32c931c7442
ms.sourcegitcommit: 4f7870f0958a3c73bbf57ad4d4f6b228f8dead73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286112"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams per Virtualized Desktop Infrastructure (VDI)

In questo articolo vengono illustrati i requisiti e le limitazioni per l'uso di Microsoft teams in un ambiente virtualizzato.

## <a name="what-is-vdi"></a>Che cos'è VDI?

Virtual Desktop Infrastructure (VDI) è la tecnologia di virtualizzazione che ospita un sistema operativo desktop e le applicazioni su un server centralizzato in un centro dati. Questo consente agli utenti un'esperienza desktop completamente personalizzata con una fonte centralizzata completamente sicura e conforme.

Microsoft teams in un ambiente virtualizzato supporta la chat e la collaborazione. Inoltre, con le piattaforme Windows Virtual Desktop, Citrix e VMware è supportata anche la funzionalità di chiamata e riunione.

I team in un ambiente virtualizzato supportano più configurazioni. Questi includono le modalità VDI, dedicate, condivise, persistenti e non persistenti. Le caratteristiche sono in continuo sviluppo e vengono aggiunte regolarmente e la funzionalità si espanderà nei prossimi mesi e anni.

L'uso di team in un ambiente virtualizzato potrebbe essere alquanto diverso dall'uso di team in un ambiente non virtualizzato. Ad esempio, alcune funzionalità avanzate potrebbero non essere disponibili in un ambiente virtualizzato e la risoluzione del video potrebbe essere diversa.

Per garantire un'esperienza utente ottimale, seguire le istruzioni in questo articolo.

 > [!Note]
> Per informazioni dettagliate sui team VDI su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams su componenti VDI

L'uso di team in un ambiente virtualizzato richiede i componenti seguenti.

- **Broker di virtualizzazione**: Gestione risorse e connessione al provider di virtualizzazione, ad esempio Azure
- **Desktop virtuale**: stack della macchina virtuale (VM) che esegue Microsoft Teams
- **Thin client**: l'endpoint con cui l'utente si connette fisicamente
- **App desktop teams**: app client desktop Teams

## <a name="teams-on-vdi-requirements"></a>Teams su requisiti VDI

### <a name="virtualization-provider-requirements"></a>Requisiti del provider di virtualizzazione

L'app desktop teams è stata convalidata con i principali provider di soluzioni di virtualizzazione. Con più fornitori di mercato, ti consigliamo di consultare il provider di soluzioni di virtualizzazione per assicurarti di soddisfare i requisiti minimi.
  
Attualmente, teams on VDI con ottimizzazione audio/video (AV) è certificato con Windows Virtual Desktop, Citrix e VMware. Esaminare le informazioni in questa sezione per assicurarti di soddisfare tutti i requisiti per la funzionalità appropriata.

### <a name="platforms-certified-for-teams"></a>Piattaforme certificate per Teams

Le piattaforme seguenti hanno soluzioni per l'infrastruttura desktop virtuale per i team.

|Piattaforma|Soluzione|
|----|---|
|![Logo che rappresenta Microsoft](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Desktop virtuale di Windows</a> |
|![Il logo che rappresenta Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">App virtuali e desktop Citrix</a> |
|![Il logo che rappresenta VMware](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Desktop virtuale di Windows

Windows Virtual Desktop offre l'ottimizzazione AV per i team su VDI. Per altre informazioni e requisiti e installazione, vedere [usare teams in Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisiti per le app virtuali e i desktop di Citrix

Le app virtuali e i desktop di Citrix (in precedenza noti come XenApp e XenDesktop) offrono l'ottimizzazione AV per i team su VDI. Con le app virtuali e i desktop di Citrix, teams in VDI supporta le funzionalità di chiamata e riunione oltre alla chat e alla collaborazione.

È possibile scaricare la versione più recente di app virtuali e desktop di Citrix nel [sito di download di Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Prima di tutto è necessario eseguire l'accesso). Per impostazione predefinita, i componenti necessari vengono raggruppati in [app Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) e Virtual Delivery Agent (VDA). Non è necessario installare altri componenti o plug-in CWA o VDA.

Per i requisiti più recenti per i server e i client, vedere [questo sito Web Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Area di lavoro VMware Horizon e requisiti desktop

VMware Horizon è una piattaforma moderna per il recapito sicuro di desktop e app virtuali attraverso il cloud ibrido. Per offrire un'esperienza utente ottimale, VMware Horizon offre l'ottimizzazione dei media per i team. Questa ottimizzazione migliora la produttività complessiva tra desktop e app virtuali e migliora l'esperienza degli utenti durante le chiamate e le riunioni tramite Team.

È possibile scaricare l'ultima versione di VMware Horizon dalla pagina [Download VMware](https://my.vmware.com/web/vmware/downloads/#all_products) . Per impostazione predefinita, i componenti necessari per l'ottimizzazione multimediale fanno parte dell'agente Horizon e del client Horizon e non è necessario installare alcun plug-in aggiuntivo per usare la funzionalità di ottimizzazione per i team.

Per ottenere i requisiti e le istruzioni più recenti su come configurare l'ottimizzazione multimediale per i team, vedere [questo sito Web VMware](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installare o aggiornare l'app desktop teams in VDI

Puoi distribuire l'app desktop teams per VDI usando un'installazione per singolo computer o per utente usando il pacchetto MSI. Decidere l'approccio da usare dipende dal fatto che si usi una configurazione persistente o non persistente e le esigenze di funzionalità associate dell'organizzazione.

Per una configurazione permanente dedicata, l'approccio funzionerebbe. Tuttavia, per una configurazione non persistente, i team richiedono un'installazione per ogni computer per poter funzionare in modo efficiente. Vedere la sezione [configurazione non persistente](#non-persistent-setup) .

Con l'installazione per computer, gli aggiornamenti automatici sono disabilitati. Questo significa che per aggiornare l'app teams devi disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente. Con l'installazione per utente, è abilitato l'aggiornamento automatico. Per la maggior parte delle distribuzioni VDI, è consigliabile distribuire teams con l'installazione per singolo computer.

Per eseguire l'aggiornamento alla versione più recente di teams, iniziare con la procedura di disinstallazione seguita dalla distribuzione della versione più recente di teams.

Per il corretto funzionamento dell'ottimizzazione AV per i team in ambienti VDI, l'endpoint thin client deve avere accesso a Internet. Se l'accesso a Internet non è disponibile nell'endpoint thin client, l'avvio dell'ottimizzazione non avrà successo. Questo significa che l'utente si trova in uno stato multimediale non ottimizzato.

#### <a name="dedicated-persistent-setup"></a>Impostazioni permanenti dedicate

In una configurazione permanente dedicata, le modifiche apportate al sistema operativo locale degli utenti vengono mantenute dopo la disconnessione degli utenti. Per la configurazione persistente, teams supporta sia l'installazione per utente che per il computer.

Di seguito è riportata la configurazione minima consigliata della VM.

|Parametro  |Sistema operativo workstation  |Sistema operativo server  |
|---------|---------|---------|
|vCPU   |    2 Core     |  4, 6 o 8<br>È importante comprendere la configurazione NUMA (non-Uniform Memory Access) sottostante e configurare le VM di conseguenza.     |
|RAM     |   4 GB      | 512 a 1024 MB per utente        |
|Archiviazione    | 8 GB        | 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configurazione non persistente

In una configurazione non persistente, le modifiche apportate al sistema operativo locale degli utenti non vengono mantenute dopo la disconnessione degli utenti. Tali configurazioni sono in genere sessioni multiutente condivise. La configurazione di VM varia in base al numero di utenti e alle risorse fisiche disponibili nella casella.

Per una configurazione non persistente, l'app desktop Teams deve essere installata per ogni computer nell'immagine dorata. Per altre informazioni, vedere l'articolo [installare o aggiornare l'app desktop teams nella sezione VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Questo garantisce un avvio efficiente dell'app teams durante una sessione utente.

L'uso di team con una configurazione non persistente richiede anche un responsabile della gestione della cache dei profili per la sincronizzazione dei dati runtime di teams efficient. In questo modo, le informazioni appropriate specifiche per l'utente, ad esempio dati utente, profilo e impostazioni, vengono memorizzate nella cache durante la sessione utente. Verificare che i dati di queste due cartelle vengano sincronizzati.  

- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

Sono disponibili varie soluzioni di gestione della cache. Ad esempio, [FSLogix](https://docs.microsoft.com/fslogix/overview). Consultare il provider di gestione della cache per istruzioni di configurazione specifiche.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Elenco di esclusione contenuto memorizzato nella cache dei team per la configurazione non persistente

Escludere i seguenti elementi dalla cartella cache di teams% AppData%/Microsoft/Teams. L'esclusione di questi elementi consente di ridurre le dimensioni della cache degli utenti per ottimizzare ulteriormente la configurazione non persistente.

- file txt
- Cartella media-stack
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Considerazioni sulle app Microsoft 365 per le aziende

Quando si distribuiscono team con le app Microsoft 365 per le aziende in VDI, tenere presente quanto segue.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nuove distribuzioni di teams tramite le app Microsoft 365 per le aziende

Prima di distribuire teams tramite le app Microsoft 365 per le aziende, è prima necessario disinstallare le app di Team preesistenti, se distribuite con l'installazione per singolo computer.

I team tramite le app Microsoft 365 per le aziende sono installati per ogni utente. Per altre informazioni, vedere l'articolo [installare o aggiornare l'app desktop teams nella sezione VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Distribuzioni di teams tramite le app Microsoft 365 per gli aggiornamenti aziendali

I team vengono aggiunti anche alle installazioni esistenti delle app Microsoft 365 per le aziende. Poiché le app Microsoft 365 per l'organizzazione installano solo team per singolo utente, vedere la sezione [installare o aggiornare l'app desktop teams in VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Uso di team con l'installazione per computer e le app Microsoft 365 per le aziende

Le app Microsoft 365 per le aziende non supportano le installazioni per computer di teams. Per usare l'installazione per computer, è necessario escludere team dalle app Microsoft 365 per le aziende. Vedere [distribuire l'app desktop teams alla VM](#deploy-the-teams-desktop-app-to-the-vm) e [come escludere la distribuzione dei team tramite le app Microsoft 365 per](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) le sezioni aziendali.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Come escludere la distribuzione di teams tramite le app Microsoft 365 per le aziende

Per altre informazioni sui team e sulle app Microsoft 365 per le aziende, vedere [come escludere team dalle nuove installazioni delle app microsoft 365 per le aziende](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) e [usare criteri di gruppo per controllare l'installazione di teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Distribuire l'app desktop teams alla VM

1. Scaricare il pacchetto MSI teams che corrisponde al sistema operativo VDI VM usando uno dei collegamenti seguenti:

    - [versione a 32 bit](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [versione a 64 bit](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    La versione minima dell'app desktop teams necessaria è la versione 1.3.00.4461. Il blocco PSTN non è supportato nelle versioni precedenti.

2. Installare il file MSI nella VM VDI eseguendo uno dei comandi seguenti:

    - Installazione per utente (impostazione predefinita)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Questo processo è l'installazione predefinita, che installa teams nella cartella% AppData% User. A questo punto, la configurazione dell'immagine dorata è completa. I team non funzionano correttamente con l'installazione per utente in una configurazione non permanente.

    - Installazione per computer

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Questo processo installa i team nella cartella Program Files (x86) in un sistema operativo a 64 bit e nella cartella Program Files in un sistema operativo a 32 bit. A questo punto, la configurazione dell'immagine dorata è completa. Per le configurazioni non permanenti è necessario installare teams per computer.

        La prossima sessione di accesso interattivo avvia team e richiede le credenziali.

        > [!NOTE]
        > Questi esempi usano anche il parametro **ALLUSERS = 1** . Quando si imposta questo parametro, il programma di installazione a livello di computer teams viene visualizzato in programmi e funzionalità nel pannello di controllo e nelle app & funzionalità nelle impostazioni di Windows per tutti gli utenti del computer. Tutti gli utenti possono quindi disinstallare teams se hanno credenziali di amministratore.
        È importante comprendere la differenza tra **ALLUSERS = 1** e **ALLUSER = 1**. Il parametro **ALLUSERS = 1** può essere usato in ambienti non VDI e VDI, mentre il parametro **ALLUSER = 1** viene usato solo in ambienti VDI per specificare un'installazione per singolo computer.

3. Disinstallare il file MSI dalla VM VDI.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Questo processo disinstalla i team dalla cartella programmi (x86) o file di programmi, a seconda dell'ambiente del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Considerazioni sulle prestazioni di teams su VDI

Sono disponibili varie configurazioni di configurazione virtualizzate, ognuna con uno stato di priorità diverso per l'ottimizzazione. Ad esempio, una configurazione può concentrarsi sulla densità degli utenti. Quando si pianifica, tenere presente quanto segue per ottimizzare la configurazione in base alle esigenze del carico di lavoro dell'organizzazione.

- Requisito minimo: alcuni carichi di lavoro potrebbero richiedere una configurazione usando risorse superiori ai requisiti minimi. Ad esempio, i carichi di lavoro per gli sviluppatori che usano applicazioni che richiedono più risorse di elaborazione.
- Dipendenze: queste includono dipendenze da infrastrutture, carichi di lavoro e altre considerazioni ambientali esterne all'app desktop teams.
- Funzionalità disabilitate in VDI: teams disattiva le funzionalità di uso intensivo della GPU per VDI, che possono contribuire a migliorare l'utilizzo temporaneo della CPU. Le caratteristiche seguenti sono disabilitate:
    - Animazione CSS Teams
    - Avvio automatico di Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams su VDI con chiamate e riunioni

Oltre alla chat e alla collaborazione, i team su VDI con chiamate e riunioni sono disponibili con le piattaforme di provider di virtualizzazione supportate. Le caratteristiche supportate si basano sull'implementazione di WebRTC media stack e Virtualization provider. Il diagramma seguente offre una panoramica dell'architettura.

![Diagramma che Mostra team in architettura VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se attualmente si eseguono teams senza ottimizzazione AV in VDI e si usano funzionalità non ancora supportate per l'ottimizzazione, ad esempio dare e prendere il controllo quando si condivide l'app, è necessario impostare i criteri del provider di virtualizzazione per disattivare il reindirizzamento dei team. Ciò significa che le sessioni multimediali di teams non verranno ottimizzate. Per istruzioni su come impostare i criteri per disattivare il reindirizzamento dei team, contattare il provider di virtualizzazione.

### <a name="network-requirements"></a>Requisiti di rete

È consigliabile valutare l'ambiente per identificare i rischi e i requisiti che possono influenzare la distribuzione complessiva del cloud Voice e del video. Usare lo [strumento di valutazione della rete Skype for business](https://www.microsoft.com/download/details.aspx?id=53885) per verificare se la rete è pronta per i team.

Per ulteriori informazioni su come preparare la rete per i team, vedere [preparare la rete dell'organizzazione per i team](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Eseguire la migrazione da Skype for business su VDI a teams in VDI

Se si esegue la migrazione da Skype for business su VDI a teams su VDI, oltre alle differenze tra le due applicazioni, sono presenti alcune differenze quando viene implementata anche VDI. Di seguito sono elencate alcune funzionalità attualmente supportate in team VDI che si trovano in Skype for business VDI:

- Controllo delle esperienze di chiamata VDI con i criteri per limitare la frequenza dei contenuti multimediali
- Criteri per la piattaforma per disabilitare alcune funzionalità AV in VDI
- Dare e prendere il controllo quando si condivide l'app
- Condivisione dello schermo dalla chat senza audio
- Invio e ricezione simultanea di video e condivisione dello schermo

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams su app desktop Chrome browser versus teams per VDI

Teams on Chrome browser non offre una sostituzione per l'app desktop teams per VDI con l'ottimizzazione AV. L'esperienza di chat e collaborazione funziona come previsto. Quando è necessario un elemento multimediale, esistono alcune esperienze che potrebbero non soddisfare le aspettative degli utenti nel browser Chrome:

- L'esperienza di streaming audio e video potrebbe non essere ottimale. Gli utenti possono avere ritardi o qualità ridotta.
- Le impostazioni del dispositivo non sono disponibili nelle impostazioni del browser.
- Gestione di dispositivi viene gestito tramite il browser e richiede più impostazioni nelle impostazioni del sito del browser.
- Le impostazioni dei dispositivi potrebbero anche essere impostate in gestione dispositivi Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams su VDI con chat e collaborazione

Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in teams, è possibile impostare i criteri a livello di utente per disattivare le funzionalità di chiamata e riunione in teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Impostare i criteri per disattivare la funzionalità delle chiamate e delle riunioni

Puoi impostare i criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell. Potrebbe essere necessario un po' di tempo (poche ore) per le modifiche ai criteri di propagazione. Se non si vedono immediatamente le modifiche per un account specifico, riprovare in poche ore.

[**Chiamate di polizia**](teams-calling-policy.md): teams include il criterio di chiamata DisallowCalling incorporato, in cui tutte le funzionalità di chiamata sono disattivate. Assegnare i criteri di DisallowCalling a tutti gli utenti dell'organizzazione che usano team in un ambiente virtualizzato.

[**Criteri**](meeting-policies-in-teams.md)per le riunioni: teams include i criteri di riunione predefiniti di AllOff, in cui tutte le caratteristiche delle riunioni sono disattivate. Assegnare i criteri di AllOff a tutti gli utenti dell'organizzazione che usano team in un ambiente virtualizzato.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri con l'interfaccia di amministrazione di Microsoft Teams

Per assegnare i criteri di chiamata di DisallowCalling e i criteri di riunione di AllOff a un utente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1.  In **criteri di chiamata**fare clic su **DisallowCalling**.
    2.  In **criteri riunione**fare clic su **AllOff**.
4. Fare clic su **applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams passa al criterio che vuoi assegnare. Ad esempio:
    - Accedere ai **Voice**  >  **criteri**per le chiamate vocali e quindi fare clic su **DisallowCalling**.
    - Accedere a **Meetings**  >  **criteri riunione**riunioni e quindi fare clic su **AllOff**.
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri tramite PowerShell

L'esempio seguente mostra come usare [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) per assegnare i criteri di chiamata di DisallowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Per ulteriori informazioni sull'uso di PowerShell per gestire i criteri di chiamata, vedere [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

L'esempio seguente mostra come usare [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri di riunione di AllOff a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri delle riunioni, vedere [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Eseguire la migrazione di teams su VDI con chat e collaborazione per ottimizzare team con chiamate e riunioni

Se si dispone di un'implementazione di teams su VDI con chat e collaborazione in cui sono stati impostati i criteri a livello di utente per disattivare le funzionalità di chiamata e riunione e si esegue la migrazione a teams con l'ottimizzazione AV, è necessario impostare i criteri per attivare le funzionalità di chiamata e riunione per tali team in utenti VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Impostare i criteri per attivare le funzionalità di chiamata e riunione

Puoi usare l'interfaccia di amministrazione di Microsoft teams o PowerShell per impostare e assegnare criteri per le chiamate e le riunioni agli utenti. Può essere necessario un po' di tempo (poche ore) per le modifiche ai criteri di propagazione. Se non si vedono immediatamente le modifiche per un account specifico, riprovare dopo qualche ora.

[**Chiamate di polizia**](teams-calling-policy.md): i criteri di chiamata in teams controllano quali funzionalità di chiamata sono disponibili per gli utenti. Teams include il criterio di chiamata AllowCalling incorporato, in cui tutte le funzionalità di chiamata sono attivate. Per attivare tutte le funzionalità di chiamata, assegnare i criteri di AllowCalling. In alternativa, crea un criterio di chiamata personalizzato per attivare le funzionalità di chiamata desiderate e assegnarle agli utenti. 

[**Criteri riunione**](meeting-policies-in-teams.md): i criteri di riunione in teams controllano i tipi di riunioni che gli utenti possono creare e le caratteristiche disponibili per i partecipanti alla riunione pianificati dagli utenti dell'organizzazione. Teams include i criteri di riunione AllOn predefiniti, in cui tutte le caratteristiche delle riunioni sono attivate. Per attivare tutte le caratteristiche delle riunioni, assegnare il criterio AllOn. In alternativa, crea un criterio di riunione personalizzato per attivare le caratteristiche di riunione desiderate e assegnarle agli utenti.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri con l'interfaccia di amministrazione di Microsoft Teams

Per assegnare i criteri di chiamata AllowCalling e i criteri di riunione AllOn a un utente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. Eseguire le operazioni seguenti:
    1.  In **criteri di chiamata**fare clic su **AllowCalling**.
    2.  In **criteri riunione**fare clic su **Allon**.
4. Fare clic su **applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul **&#x2713;** (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams passa al criterio che vuoi assegnare. Ad esempio:
    - Accedere ai **Voice**  >  **criteri**per le chiamate vocali e quindi fare clic su **AllowCalling**.
    - Accedere a **Meetings**  >  **criteri riunione**riunioni e quindi fare clic su **Allon**.
2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri tramite PowerShell

L'esempio seguente mostra come usare [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) per assegnare i criteri di chiamata di AllowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Per ulteriori informazioni sull'uso di PowerShell per gestire i criteri di chiamata, vedere [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

L'esempio seguente mostra come usare [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri di riunione Allon a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri delle riunioni, vedere [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Controllare la modalità fallback in teams

Quando gli utenti si connettono da un endpoint non supportato, gli utenti si trovano in modalità fallback, in cui AV non è ottimizzato. Puoi disabilitare o abilitare la modalità di fallback impostando uno dei seguenti valori DWORD del registro di sistema:

- HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER \SOFTWARE\Microsoft\Office\Teams\DisableFallback

Per disabilitare la modalità fallback, imposta il valore su **1**. Per abilitare solo l'audio, imposta il valore su **2**. Se il valore non è presente o è impostato su **0** (zero), la modalità fallback è abilitata.

Questa caratteristica è disponibile in teams versione 1.3.00.13565 e versioni successive.

## <a name="known-issues-and-limitations"></a>Problemi noti e limitazioni

### <a name="client-deployment-installation-and-setup"></a>Distribuzione, installazione e configurazione client

- Con l'installazione per computer, teams in VDI non viene aggiornato automaticamente nel modo in cui si trovano i client di team non VDI. È necessario aggiornare l'immagine della VM installando un nuovo MSI, come descritto nella sezione [installare o aggiornare l'app desktop teams in VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Devi disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.
- I team devono essere distribuiti per utente o per computer. La distribuzione di team per ogni utente e per ogni computer non è supportata. Per eseguire la migrazione da ogni computer o per utente a una di queste modalità, seguire la procedura di disinstallazione e ridistribuire in entrambe le modalità.
- In questo momento, Windows Virtual Desktop e VMware non supportano i client basati su MacOS e Linux.
- Citrix non supporta i client MacOs in questo momento.
- Citrix non supporta l'uso di proxy HTTP espliciti definiti in un endpoint.

### <a name="calling-and-meetings"></a>Chiamate e riunioni

Le funzionalità di chiamata e riunione seguenti non sono supportate:

- Servizi di emergenza avanzati
- Pulsanti HID e controlli LED tra l'app e i dispositivi Teams
- Sfocatura ed effetti di sfondo
- Ruoli di produttore e relatore di eventi broadcast e Live
- Routing basato sulla posizione (LBR)
- Parcheggio delle chiamate
- Coda di chiamata
- Audio/computer del sistema condiviso
- Bypass multimediale per Instradamento diretto

> [!NOTE]
> Stiamo lavorando all'aggiunta di funzionalità di chiamata e riunione attualmente disponibili solo in ambienti non VDI. Questi potrebbero includere più controllo di amministrazione sulla qualità, altri scenari di condivisione dello schermo e funzionalità avanzate aggiunte di recente a teams. Contattare il rappresentante teams per altre informazioni sulle caratteristiche future.

Di seguito sono riportati i problemi noti e le limitazioni per le chiamate e le riunioni:

- L'interoperabilità con Skype for business è limitata alle chiamate audio; non esiste una modalità video.
- In riunioni o chiamate di gruppo è supportato solo un singolo flusso video in arrivo. Quando più persone inviano video, viene visualizzato solo il video del relatore dominante in un dato momento.
- La risoluzione del flusso video in entrata e in uscita è limitata alla risoluzione 720p. Si tratta di una limitazione WebRTC.
- È supportato un solo flusso video da una videocamera in arrivo o da un flusso di condivisione dello schermo. Quando c'è una condivisione dello schermo in arrivo, viene visualizzata la condivisione dello schermo, invece del video del relatore dominante.
- Condivisione dello schermo in uscita:
    - La condivisione delle applicazioni non è supportata.
- Dare controllo e prendere il controllo:
    - Non supportato durante una sessione di condivisione dello schermo o di condivisione dell'applicazione.
    - Supportato durante una sessione di condivisione di PowerPoint.
- Limitazioni solo Citrix
    - L'interazione DTMF (Dual Tone Multi Frequency) con i sistemi di telefonia non è attualmente supportata.
    - Quando si condivide la schermata in una configurazione con più monitor, viene condiviso solo il monitor principale.
    - Il ridimensionamento DPI elevato su CWA non è supportato.

Per i problemi noti relativi ai team che non sono correlati a VDI, vedere [supportare team nell'organizzazione](Known-issues.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="troubleshoot-citrix-components"></a>Risolvere i problemi relativi ai componenti Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Il team si arresta in modo anomalo o la schermata di accesso teams è vuota

Si tratta di un problema noto con le versioni 1906 e 1909 di Citrix VDA. Per risolvere il problema, aggiungere il valore DWORD seguente del registro di sistema e impostarlo su 204 (esadecimale).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Quindi riavvia VDA. Per altre informazioni, vedere questo articolo del supporto per Citrix, [risoluzione dei problemi di ottimizzazione dell'HDX per i team](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Argomenti correlati

- [Installare Microsoft teams con MSI](msi-deployment.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Usare Microsoft teams in Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
