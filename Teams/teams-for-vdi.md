---
title: Team per l'infrastruttura desktop virtualizzata
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: Informazioni su come eseguire Microsoft teams in un ambiente VDI (Virtualizzated Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fa560347d7263dafafc4f98e031b3b267f8fb12
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570224"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Team per l'infrastruttura desktop virtualizzata

In questo articolo vengono illustrati i requisiti e le limitazioni per l'uso di Microsoft teams in un ambiente virtualizzato.

## <a name="what-is-vdi"></a>Che cos'è VDI?

Virtual Desktop Infrastructure (VDI) è la tecnologia di virtualizzazione che ospita un sistema operativo desktop e le applicazioni su un server centralizzato in un centro dati. Questo consente agli utenti un'esperienza desktop completamente personalizzata con una fonte centralizzata completamente sicura e conforme. 
 
Attualmente, i team in un ambiente virtualizzato sono disponibili con il supporto per la collaborazione e la funzionalità di chat con un computer virtualizzato persistente dedicato (VM). Per garantire un'esperienza utente ottimale, seguire le istruzioni in questo articolo. 

## <a name="teams-requirements"></a>Requisiti per i team

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Impostare i criteri per disattivare le funzionalità di chiamata e riunione in teams

L'esperienza di chiamata e riunione di teams non è ottimizzata per un ambiente VDI (presto disponibile). È consigliabile impostare i criteri a livello di utente per disattivare le funzionalità di chiamata e riunione in teams.

Puoi comunque scegliere di eseguire teams completamente in VDI usando l'app desktop teams o l'app Web. Tuttavia, ti consigliamo di impostare i criteri per evitare di compromettere l'esperienza utente.  

Può essere necessario un po' di tempo (poche ore) per le modifiche ai criteri di propagazione. Se non si vedono immediatamente le modifiche per un account specifico, riprovare in poche ore.

> [!NOTE]
> Quando le chiamate e le riunioni di team sono ottimizzate per l'uso in ambienti desktop virtuali, è possibile ripristinare questi criteri e consentire agli utenti di usare i team in modo normale. 

#### <a name="calling"></a>Chiamate

USA i cmdlet **CSTeamsCallingPolicy** per controllare se gli utenti possono usare le opzioni di chiamata e chiamata in chat private e di gruppo. Ecco l'elenco delle impostazioni dei criteri e i valori consigliati.

|Nome del criterio  |Descrizione |Valore consigliato  |
|---------|---------|---------|
|AllowCalling    |Controlla le funzionalità delle chiamate di interoperabilità. Questa operazione consente agli utenti di Skype for business di avere chiamate uno-a-uno con gli utenti di team e viceversa.         |Impostare su false per evitare che le chiamate di utenti di Skype for business vengano sbarcate in teams.          |
|AllowPrivateCalling     | Controlla se l'app chiamante è disponibile nella barra dell'app sul lato sinistro del client teams e se gli utenti vedono le opzioni per le chiamate e le videochiamate nella chat privata         |Impostare su false per rimuovere l'app chiamante dalla barra dell'app sul lato sinistro di teams e per rimuovere le opzioni per la chiamata e la videochiamata in chat privata.          |

#### <a name="create-and-assign-a-calling-policy"></a>Creare e assegnare un criterio di chiamata

1. Avviare una sessione di Windows PowerShell come amministratore.
2. Connettersi al connettore Skype online.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Visualizzare un elenco di opzioni dei criteri di chiamata.

       Get-CsTeamsCallingPolicy
 
4. Cercare l'opzione criteri predefiniti in cui sono disabilitati tutti i criteri di chiamata. Ha un aspetto simile a questo.
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. Applicare l'opzione dei criteri predefiniti di DisallowCalling a tutti gli utenti che useranno teams in un ambiente virtualizzato.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Per altre informazioni sui criteri di chiamata dei team, vedere [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a> Riunioni

Usare i cmdlet **CsTeamsMeetingPolicy** per controllare il tipo di riunioni che gli utenti possono creare, le caratteristiche a cui possono accedere durante una riunione e le caratteristiche della riunione disponibili per gli utenti anonimi ed esterni. Ecco l'elenco delle impostazioni dei criteri e i valori consigliati.

|Nome criterio |Descrizione|Valore consigliato                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Determina se un utente può pianificare riunioni private.| Impostato su false per impedire che l'utente possa pianificare riunioni private.  |
|AllowChannelMeetingScheduling  | Determina se un utente è autorizzato a pianificare le riunioni del canale. | Impostare su false per impedire che l'utente possa pianificare le riunioni del canale.                       |
|AllowMeetNow |Determina se un utente può creare o avviare riunioni ad hoc.              |  Imposta questo valore su false per impedire che l'utente possa avviare riunioni ad hoc.                     |
|ScreenSharingMode | Determina la modalità in cui un utente può condividere lo schermo in chiamate o riunioni. | Impostato su Disabled per impedire all'utente di condividere gli schermi                          |
|AllowIPVideo |Determina se il video è abilitato nelle riunioni o nelle chiamate di un utente.                  |    Impostato su false per impedire all'utente di condividere il video                                         |
| AllowAnonymousUsersToDialOut | Determina se gli utenti anonimi possono effettuare la chiamata a un numero PSTN. | Impostato su false per impedire la chiamata degli utenti anonimi                                  |
| AllowAnonymousUsersToStartMeeting | Determina se gli utenti anonimi possono avviare una riunione.     |  Impostare su false per impedire agli utenti di avviare una riunione                                            |
| AllowOutlookAddIn |Determina se un utente può pianificare le riunioni di Teams nel client desktop di Outlook.| Impostato su false per impedire a un utente di pianificare le riunioni di Teams nel client desktop di Outlook|
| AllowParticipantGiveRequestControl|Determina se i partecipanti possono richiedere o dare il controllo della condivisione dello schermo.| Impostato su false per impedire all'utente di concedere e richiedere il controllo in una riunione    |
| AllowExternalParticipantGiveRequestControl | Determina se i partecipanti esterni possono richiedere o dare il controllo della condivisione dello schermo.| Impostato su false per impedire l'assegnazione di un utente esterno, richiedendo il controllo in una riunione|
|AllowPowerPointSharing|Determina se la condivisione di PowerPoint è consentita nelle riunioni di un utente. |Impostato su false per impedire a un utente di condividere i file di PowerPoint in una riunione  |
|AllowWhiteboard | Determina se la lavagna è consentita nelle riunioni di un utente. |   Impostare su false per impedire la lavagna in una riunione |
| AllowTranscription |Determina se le didascalie e le trascrizioni in tempo reale e/o post-riunione sono consentite nelle riunioni di un utente.|    Impostare su false per impedire la trascrizione e le didascalie in una riunione  |  
| AllowSharedNotes | Determina se gli utenti possono prendere note condivise. | Impostato su false per impedire agli utenti di accettare note condivise |
|MediaBitRateKB |Determina la velocità in bit media per le trasmissioni di condivisione audio/video/app nelle riunioni  | Il valore suggerito è 5000 (5 MB). È possibile modificarla in base alle esigenze dell'organizzazione.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Creare e assegnare un criterio di riunione

1. Avviare una sessione di Windows PowerShell come amministratore.
2. Connettersi al connettore Skype online.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Visualizzare un elenco delle opzioni dei criteri di riunione.

       Get-CsTeamsMeetingPolicy
 
4. Cercare l'opzione criteri predefiniti in cui sono disabilitati tutti i criteri riunione. Ha un aspetto simile a questo.
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. Applicare l'opzione dei criteri predefiniti di AllOff a tutti gli utenti che useranno teams in un ambiente virtualizzato. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Per altre informazioni sui criteri di riunione dei team, vedere [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Requisiti del provider di virtualizzazione

L'app teams è stata convalidata nei principali provider di soluzioni di virtualizzazione. Con più fornitori di mercato, consulta il provider di soluzioni di virtualizzazione per verificare che siano soddisfatti i requisiti minimi.

### <a name="virtual-machine-requirements"></a>Requisiti della macchina virtuale

Con i diversi carichi di lavoro e le esigenze degli utenti in un ambiente virtualizzato, di seguito è riportata la configurazione minima consigliata per le VM.

|Parametro  |Misura  |
|---------|---------|
|vCPU    |  2 Core       |
|RAM     |  4 GB      |
|Archiviazione     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>Requisiti del sistema operativo della macchina virtuale

I sistemi operativi supportati per VM sono:

- Windows 10 e versioni successive
- Windows Server 2012 R2 e versioni successive

## <a name="install-teams-on-vdi"></a>Installare teams su VDI

Ecco il processo e gli strumenti per distribuire l'app desktop teams. 

1. Scaricare il pacchetto MSI teams usando uno dei collegamenti seguenti, a seconda dell'ambiente. È consigliabile usare la versione a 64 bit per una VM VDI con un sistema operativo a 64 bit.

    - [versione a 32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versione a 64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Eseguire il comando seguente per installare il file MSI nella VM VDI o per completare l'aggiornamento.

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Questo consente di installare i team nei file di programma. A questo punto, la configurazione dell'immagine dorata è completa.
 
    La prossima sessione di accesso interattivo avvia team e richiede le credenziali. Tieni presente che non è possibile disabilitare l'avvio automatico dei team durante l'installazione di teams in VDI tramite la proprietà ALLUSER. 

3. Eseguire il comando seguente per disinstallare il file MSI dalla VM VDI o prepararsi per l'aggiornamento.

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    In questo articolo vengono disinstallati team da file di programma.

## <a name="known-issues-and-limitations"></a>Problemi noti e limitazioni

Di seguito sono riportati i problemi noti e le limitazioni per i team in VDI.

- **Distribuzioni di tipo host sessione condivisa**: le distribuzioni di tipo host sessione condivisa, ad esempio la configurazione della VM non persistente condivisa, non sono nell'ambito.
- **Chiamate e riunioni**:

    - Gli scenari di chiamata e riunione non sono ottimizzati per VDI. Questi scenari si esibiranno male. È consigliabile usare criteri a livello di utente come descritto nella sezione [Imposta criteri per disattivare le funzionalità di chiamata e riunione in teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .  
    - Applicando i criteri descritti in questo articolo si ha un impatto sulla possibilità di usare le funzionalità di chiamata e riunione, che a seconda di altri criteri possono influire su altri utenti dell'organizzazione. Se gli utenti dell'organizzazione usano client non VDI, è possibile scegliere di non applicare i criteri.  

- **Partecipare a chiamate e riunioni create da altri utenti**: anche se i criteri impediscono agli utenti di creare riunioni, possono ancora partecipare alle riunioni se un altro utente effettua la chiamata dalla riunione. In queste riunioni, la possibilità dell'utente di condividere video, usare lavagna e altre funzionalità dipende dal fatto che siano state disabilitate le caratteristiche usando TeamsMeetingPolicy.  
- **Contenuto memorizzato nella cache**: se l'ambiente virtuale in cui il team è in esecuzione non è persistente (e i dati vengono eliminati alla fine di ogni sessione utente), gli utenti potrebbero notare il degrado delle prestazioni a causa dell'aggiornamento del contenuto, indipendentemente dal fatto che l'utente abbia eseguito la stessa operazione contenuto di una sessione precedente.
- **Aggiornamenti client**: teams on VDI non viene aggiornato automaticamente con l'installazione MSI per computer. È necessario aggiornare l'immagine della VM installando un nuovo MSI, come descritto nella sezione [installare teams in VDI](#install-teams-on-vdi) . Devi disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.
- **Esperienza utente**: l'esperienza utente di teams in un ambiente VDI può essere diversa da un ambiente non VDI. Le differenze potrebbero essere causate dalle impostazioni dei criteri e/o dal supporto delle funzionalità nell'ambiente.

Per i problemi noti relativi ai team che non sono correlati a VDI, vedere [problemi noti di Microsoft teams](Known-issues.md).

## <a name="related-topics"></a>Argomenti correlati

- [Installare Microsoft teams con MSI](msi-deployment.md)
