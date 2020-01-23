---
title: Distribuire le sale di Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leggere questo articolo per informazioni sulla distribuzione delle sale di Microsoft teams.
ms.openlocfilehash: abe9b49febe313bb3b8d503b31562d6ae99128a0
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269003"
---
# <a name="deployment-overview"></a>Panoramica della distribuzione

La distribuzione delle sale di Microsoft teams si suddivide essenzialmente in fasi:

- Conferma che le posizioni di distribuzione (sale) soddisfano le dipendenze di distribuzione
- Creare account Microsoft teams o Skype for business e Exchange e assegnarli ai dispositivi console (vedere [configurare gli account per Microsoft teams Rooms](rooms-configure-accounts.md))
- Riimaging di Microsoft Surface Tablets per lavorare come console di Microsoft teams Rooms (vedere [configurare una console Microsoft teams Rooms](console.md) o [distribuire la guida alla distribuzione di massa di Microsoft teams Rooms](rooms-scale.md))
- Opzionale Configurazione di Microsoft Operations Management Suite per i sistemi (vedere [distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md)
- Configurare le console nelle sale riunioni e connettere i dispositivi periferici necessari (vedere la documentazione OEM per il set di dispositivi)

I tecnici AV possono essere usati per l'ultima attività, ma il reparto IT dell'organizzazione dovrà eseguire le altre parti del processo. 


## <a name="site-readiness"></a>Disponibilità del sito 

Mentre i dispositivi ordinati vengono recapitati all'organizzazione, collaborare con la rete e le strutture e i team AV per verificare che le dipendenze di distribuzione vengano soddisfatte e che ogni sito e spazio sia pronto in termini di potenza, networking e visualizzazione. Verificare inoltre che siano soddisfatti i requisiti di installazione fisici. Per considerazioni sull'installazione fisica, visitare il sito del fornitore e sfruttare l'esperienza del team AV durante l'installazione e il montaggio di schermate e di cavi in uso.

Per altre informazioni su queste dipendenze, vedere i collegamenti alle linee guida per la pianificazione seguenti:

-   [Verificare la disponibilità della rete](rooms-prep.md#check-network-availability)
-   [Certificati](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Suggerimento PRO** : se si intende usare i server proxy per consentire l'accesso a Microsoft teams o Skype for business online, vedere prima di [tutto questo articolo](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Tieni presente che quando si tratta di traffico di Skype for business sui server proxy, ti consigliamo di ignorare completamente i server proxy. Il traffico di Skype for business è già crittografato, quindi i server proxy non lo rendono più sicuro. Come parte della distribuzione più ampia, ti consigliamo di seguire le indicazioni in valutare l' [ambiente](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) per la pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti principali per le sale di Microsoft teams.</li><li>Verificare di avere fornito larghezza di banda sufficiente per ogni sito.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Disponibilità del servizio

Per preparare la distribuzione di Microsoft teams rooms, eseguire le attività principali seguenti:

-   Definire le caratteristiche dell'account del servizio Microsoft teams rooms.
-   Preparare un'unità organizzativa e un gruppo di Active Directory per contenere gli account del computer e del servizio di Microsoft teams Rooms e, facoltativamente, preparare gli oggetti Criteri di gruppo per abilitare la comunicazione remota di PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definire le caratteristiche dell'account del servizio Microsoft teams rooms 

A seconda degli scenari di collaborazione che hai deciso di abilitare con la distribuzione di Microsoft teams rooms, devi determinare le funzionalità e le funzionalità assegnate a ogni account del servizio Microsoft teams Rooms abilitato.

| **Scenario** | **Descrizione** | **Caratteristica dell'account del servizio Microsoft teams rooms** |
|---------- |------------- | --- |
| Riunioni interattive            | Uso della condivisione vocale, video e dello schermo; creazione di una risorsa prenotabile in Microsoft teams rooms                     | Abilitato per Skype for business, abilitato per Exchange (cassetta postale delle risorse) |
| Chiamate in conferenza            | Abilitare le riunioni avviate *direttamente* dalla console Microsoft teams Rooms con le coordinate per i servizi di conferenza telefonica con accesso esterno | Abilitato per i servizi di audioconferenza                                          |
| Chiamate PSTN in uscita/in ingresso | Abilitare la console Microsoft teams Rooms per effettuare e ricevere chiamate PSTN                                         | Abilitato per il sistema telefonico                                                |

Per altre informazioni sugli account di Microsoft teams rooms, vedere [configurare gli account per Microsoft teams Rooms](rooms-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Scegliere gli scenari supportati e identificare i requisiti di licenza per gli account del servizio Microsoft teams rooms.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Prepararsi a ospitare account di computer e servizi.</li></ul>| 


_Esempio di tabella di pianificazione dell'account del servizio Microsoft teams rooms_

| **Sito**  | **Nome sala** | **Tipo di sala** | **Funzionalità future della sala**                                                 | **Caratteristiche dell'account di Microsoft teams rooms**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| HQ di Londra | Curie         | Media        | 1 schermata, audio e video + presentazione <br>Accesso ai servizi di conferenza telefonica con chiamata in ingresso<br> Accesso PSTN  | Abilitato per Skype for business, abilitato per Exchange (cassetta postale delle risorse) <br>Abilitato per i servizi di audioconferenza <br>Abilitato per il sistema telefonico |
| HQ di Sydney | Collina          | Grande         | 2 schermi, audio e video + presentazione<br>Accesso ai servizi di conferenza telefonica con chiamata in ingresso<br> Accesso PSTN  | Abilitato per Skype for business, abilitato per Exchange (cassetta postale delle risorse)<br> Abilitato per i servizi di audioconferenza <br>Abilitato per il sistema telefonico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparare l'hosting degli account del computer e del servizio di Microsoft teams Rooms (facoltativo)

Per consentire la gestione e il report sugli account del computer e del servizio di Microsoft teams rooms, preparare l'Active Directory locale o Azure Active Directory (Azure AD). 

Definire un gruppo di Active Directory o di Azure AD in locale per aggiungere tutti gli account del servizio (utente) di Microsoft teams Rooms a e quindi creare report sull'utilizzo usando il cmdlet Get-CSUserSession di PowerShell in tutta la distribuzione di Microsoft teams rooms. Ad esempio, crea un gruppo denominato SkypeRoomSystemsv2-Service-Accounts. 


Definire un'unità organizzativa nella gerarchia Active Directory locale o Azure AD per contenere tutti gli account del computer di Microsoft teams Rooms (se sono stati aggiunti al dominio) e un'unità organizzativa per contenere tutti gli account utente delle sale di Microsoft teams. Se si crea un'unità organizzativa per gli account del computer di Microsoft teams rooms, è consigliabile disabilitare l'ereditarietà per assicurarsi di applicare solo i criteri da applicare alle sale di Microsoft teams appartenenti al dominio. 

Creare un oggetto Criteri di gruppo assegnato all'unità organizzativa che contiene gli account del computer di Microsoft teams rooms. Usare questa pagina per: 

-   [Impostare le impostazioni di Power e local account](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Abilitare Windows Update.
-   Abilitare la comunicazione remota di PowerShell. È possibile configurare uno script di avvio per eseguire un semplice script: Enable-PSRemoting-force

È possibile usare PowerShell per eseguire numerose attività di gestione remota, ad esempio ottenere e impostare le informazioni di configurazione. I servizi remoti di PowerShell devono essere abilitati *prima* che qualsiasi gestione remota di PowerShell possa avere luogo e debba essere considerata parte dei processi di distribuzione o configurati tramite criteri di gruppo. Per altre informazioni su queste funzionalità e sull'abilitazione, vedere [manutenzione e operazioni](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configurazione e distribuzione 

La pianificazione della configurazione e della distribuzione comprende le aree principali seguenti:

-   Provisioning degli account
-   Installazione del software del dispositivo
-   Distribuzione di dispositivi
-   Configurazione di applicazioni e periferiche di Microsoft teams rooms
-    Test
-   Asset Management

### <a name="account-provisioning"></a>Provisioning degli account 

Ogni dispositivo Microsoft teams Rooms richiede un account di risorse dedicato e univoco che deve essere abilitato sia per Microsoft teams che per Skype for business ed Exchange. Questo account deve avere una cassetta postale della sala ospitata in Exchange ed essere abilitata come sala riunioni nella distribuzione di teams o Skype for business. Sul lato Exchange l'elaborazione del calendario deve essere configurata in modo che il dispositivo possa accettare automaticamente le convocazioni di riunione in arrivo. Per altre informazioni sulla creazione di questi account, vedere [configurare gli account per Microsoft teams Rooms](rooms-configure-accounts.md). 

**Suggerimento PRO** : rende i nomi visualizzati per questi account descrittivi e di facile comprensione. Questi sono i nomi che gli utenti vedranno durante la ricerca e l'aggiunta di sistemi Microsoft teams Rooms alle riunioni. Alcune organizzazioni usano il*nome della sala*del *sito*-Convenzione (*capacità massima della sala*)-RS, quindi ad esempio Curie, una sala riunioni di 12 persone a Londra, potrebbe avere il nome visualizzato Lon-Curie (12)-RS. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione per gli account di Microsoft teams rooms.</li><li>Decidere se creare singoli account o usare gli script di provisioning in blocco.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Installazione del software del dispositivo 

Quando si pianifica di distribuire le sale di Microsoft teams, è possibile prendere in considerazione una serie di opzioni per installare il software richiesto. Gli scenari e gli approcci comuni sono descritti nella tabella seguente. 

| **Scenario**            | **Approccio**         |
|-------------------------|-----------------------|   
|Distribuzione di un numero limitato di dispositivi Microsoft teams Rooms (<10). | Se si usano le sale Microsoft teams di Surface Pro, seguire le [istruzioni per l'installazione di un'installazione per dispositivo](console.md). [Questo pratico video illustra il processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se si usa una soluzione integrata, eseguire la distribuzione usando l'immagine del fornitore e configurare le impostazioni in base alle esigenze. |
| Distribuzione tra i dispositivi 10 e 50 da un singolo fornitore.     | Creare un'immagine basata su WIM, sospendere [il passaggio 6 nelle linee guida](console.md)e acquisire un'immagine di distribuzione da usare con la tecnologia di distribuzione della clonazione.    |
| Distribuire più di 50 dispositivi Microsoft teams rooms, distribuire dispositivi da più fornitori o richiedere agli agenti specifici dell'organizzazione come parte della distribuzione. | Usare una piattaforma di distribuzione e creazione di software basato su sequencer, ad esempio [System Center Configuration Manager](rooms-scale.md).  |

**Suggerimento PRO** : ogni sala di Microsoft Teams deve avere un nome di computer valido e univoco nella rete. Molti sistemi di monitoraggio e avviso visualizzano il nome del computer come identificatore chiave, quindi è importante sviluppare una convenzione di denominazione per le distribuzioni di Microsoft teams Rooms che consente al personale di supporto di individuare facilmente le sale di Microsoft teams contrassegnate che richiedono un'azione. Un esempio potrebbe essere l'uso di un modello di**-*nome della sala* MTR-sito (MTR-Lon-Curie). 

Nell'ambito della distribuzione è anche necessario considerare la strategia per la gestione e la configurazione degli [account locali](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) creati dal programma di installazione dell'applicazione Microsoft teams rooms.

Forniamo indicazioni su come usare [Microsoft Azure monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) per monitorare la distribuzione e il report di Microsoft teams Rooms sulla disponibilità, gli errori hardware/software e la versione dell'applicazione sale di Microsoft teams. Se si decide di usare Microsoft Operations Management Suite, è necessario installare l'agente di Operations Management Suite nell'ambito del processo di installazione del software e configurare le informazioni di connessione dell'area di lavoro per l'area di lavoro. 

Una considerazione ulteriore è se le sale di Microsoft teams verranno unite a un dominio. Le informazioni sui vantaggi di Domain Joining sono disponibili in [considerazioni su come partecipare al dominio di Skype room System](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione dei dispositivi di Microsoft teams rooms da usare durante la distribuzione.</li><li>Decidere se partecipare ai dispositivi Microsoft teams Rooms al proprio dominio e come gestire e configurare gli account locali. </li><li>Decidere se usare Operations Management Suite per monitorare la distribuzione di Microsoft teams rooms.</li><li>Scegliere il metodo che verrà usato per distribuire il software e gli agenti al sistema Microsoft teams rooms in preparazione della distribuzione del dispositivo. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare l'approccio di distribuzione del dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Distribuzione di dispositivi

Dopo aver distribuito il software alle unità Microsoft teams rooms, è possibile creare un piano per spedire i dispositivi e i dispositivi periferici assegnati alle proprie camere e quindi procedere con l'installazione e la configurazione. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno i dispositivi Microsoft teams Rooms nel sito e intraprendere la configurazione e i test.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avviare il test del dispositivo.</li></ul>| 

_Tabella di distribuzione di esempio_

| **Sito**  | **Nome sala** | **Tipo di sala** | **Sistema Microsoft teams rooms**  | **Periferiche**  | **Nome computer di Microsoft teams rooms**  | **Account delle risorse di Microsoft teams rooms**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| HQ di Londra | Curie         | Media        |                                   |                  |                                          |                                             |
| HQ di Sydney | Collina          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configurazione di applicazioni e periferiche di Microsoft teams rooms 

Dopo che ogni sistema di Microsoft teams Rooms è stato distribuito fisicamente e i dispositivi periferici supportati sono connessi, è necessario configurare l'applicazione Microsoft teams Rooms per assegnare l'account delle risorse di Microsoft teams Rooms e la password create in precedenza , per consentire al sistema Microsoft teams Rooms di accedere a Microsoft teams o Skype for business ed Exchange. È fondamentale sfruttare le periferiche audio e video USB certificate collegate in un punto qualsiasi del documento. L'operazione non può causare un comportamento imprevedibile. 

È possibile configurare manualmente ogni sistema di Microsoft teams rooms. In alternativa, puoi usare un file di configurazione XML centralizzato, per-Microsoft teams Rooms per gestire le impostazioni dell'applicazione e sfruttare uno script di GPO per la riapplicazione della configurazione desiderata, ogni volta che viene avviato il sistema di Microsoft teams rooms. 

Per altre informazioni su come usare il file di configurazione XML, vedere [gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md). 

È possibile usare [Remote PowerShell](rooms-operations.md#remote-management-using-powershell) per estrarre la configurazione di Microsoft teams Rooms per la creazione di report. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se configurare manualmente ogni sistema di Microsoft teams rooms o usare un file XML centralizzato (uno per il dispositivo Microsoft teams rooms).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Definire l'approccio di gestione remota.</li></ul>| 

### <a name="testing"></a> Test

Dopo la distribuzione del sistema Microsoft teams rooms, è consigliabile testarlo. Verificare che le funzionalità elencate nella [Guida di Microsoft teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) stiano lavorando sul dispositivo distribuito. È consigliabile che il team di distribuzione verifichi che le sale di Microsoft teams accedano a Microsoft Operations Management Suite (se usato). È anche importante effettuare numerose chiamate di test e riunioni per verificare la qualità. Per altre informazioni, Vedi questo [elenco di controllo della distribuzione utile](console.md#microsoft-teams-rooms-deployment-checklist).

Ti consigliamo di configurare i file di costruzione per Call Quality Dashboard (Call Quality Dashboard) come parte dei team generali o di Skype for business, di monitorare le tendenze della qualità e di impegnarti nel processo di revisione della qualità dell'esperienza. Per altre informazioni, vedi la [Guida alla revisione della qualità della prova](https://aka.ms/qerguide). 

### <a name="asset-management"></a>Asset Management

Come parte della distribuzione, è necessario aggiornare il registro delle risorse con il nome della sala, il nome del dispositivo Microsoft teams rooms, l'account delle risorse di Microsoft teams Rooms e i dispositivi periferici assegnati (e le porte USB che usano). 

_Tabella risorse di esempio_

| **Sito**  | **Nome sala** | **Tipo di sala** | **Microsoft teams Rooms Nr. seriale**  | **Dispositivi periferici/nos seriale/porte**  | **Nome computer di Microsoft teams rooms**  | **Account del servizio Microsoft teams rooms**  | **Data di distribuzione** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| HQ di Londra | Curie         | Media        |                                          |                                          |                                          |                                            |                   |
| HQ di Sydney | Collina          | Grande         |                                          |                                          |                                          |                                            |                   |


