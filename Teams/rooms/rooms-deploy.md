---
title: Distribuire Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leggere questo articolo per informazioni su come distribuire le sale di Microsoft Teams, incluse le fasi di distribuzione.
ms.openlocfilehash: 53c4c94717f10dadbad802cff3f233a3a771d166
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662251"
---
# <a name="deployment-overview"></a>Panoramica della distribuzione

La distribuzione delle sale di Microsoft Teams suddivide essenzialmente in fasi:

- Verificare che le posizioni di distribuzione (sale) soddisfino le dipendenze di distribuzione
- Creazione di account Microsoft Teams o Skype for Business ed Exchange e assegnazione dei dispositivi console (vedere Configurare [gli account per le sale di Microsoft Teams)](rooms-configure-accounts.md)
- Uso di tablet Microsoft Surface come console di Microsoft Teams Room (vedere Configurare una console Di [Microsoft Teams Room](console.md) o Distribuire una guida alla distribuzione di massa di sale di Microsoft [Teams)](rooms-scale.md)
- (Facoltativo) Configurazione di Microsoft Operations Management Suite per i sistemi (vedere Distribuire la gestione delle [sale di Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
- Configurazione delle console nelle sale riunioni e collegamento dei dispositivi periferici necessari (vedere la documentazione OEM del set di dispositivi)

I tecnici AV possono essere usati per l'ultima attività, ma il reparto IT dell'organizzazione dovrà eseguire le altre parti del processo. 


## <a name="site-readiness"></a>Conformità del sito 

Mentre i dispositivi ordinati vengono recapitati all'organizzazione, collaborare con le risorse di rete e le strutture e i team AV per assicurarsi che vengano soddisfatte le dipendenze di distribuzione e che ogni sito e sala sia pronto in termini di potenza, rete e visualizzazione. Verificare anche che siano soddisfatti i requisiti di installazione fisica. Per considerazioni sull'installazione fisica, visita il sito del fornitore e sfrutta l'esperienza del team AV durante l'installazione e il montaggio degli schermi e l'esecuzione di cavi.

Per altre informazioni su queste dipendenze, vedere i collegamenti alle indicazioni per la pianificazione seguenti:

-   [Verificare la disponibilità della rete](rooms-prep.md#check-network-availability)
-   [Certificati](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Suggerimento per** professionisti: se si intende utilizzare server proxy per fornire l'accesso a Teams o Skype for Business online, consultare prima di tutto [questo articolo.](../proxy-servers-for-skype-for-business-online.md) Per quanto riguarda il traffico di Skype for Business sui server proxy, è consigliabile ignorare completamente i server proxy. Il traffico di Skype for Business è già crittografato, quindi i server proxy non lo rendono più sicuro. Nell'ambito di una distribuzione più ampia, è consigliabile seguire le indicazioni in Preparare la rete per [Teams](../prepare-network.md) per la pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti principali di Microsoft Teams Rooms.</li><li>Verificare di avere fornito larghezza di banda sufficiente per ogni sito.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione dei dispositivi.</li></ul>| 

## <a name="service-readiness"></a>Prontezza del servizio

Per prepararsi alla distribuzione di Sale di Microsoft Teams, eseguire le operazioni principali seguenti:

-   Definire le funzionalità dell'account di servizio di Microsoft Teams Rooms.
-   Preparare un'unità organizzativa e un gruppo Active Directory per contenere gli account del computer e del servizio Microsoft Teams Rooms e, facoltativamente, preparare oggetti Criteri di gruppo per abilitare PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definire le funzionalità degli account di servizio di Microsoft Teams Rooms 

A seconda degli scenari di collaborazione che hai deciso di abilitare con la distribuzione di Microsoft Teams Rooms, dovrai determinare le funzionalità e le funzionalità da assegnare a ogni account di servizio di Microsoft Teams Room che abiliti.

| **Scenario** | **Descrizione** | **Funzionalità dell'account di servizio Microsoft Teams Rooms** |
|---------- |------------- | --- |
| Riunioni interattive            | Uso di voce, video e condivisione dello schermo; Rendere le sale di Microsoft Teams una risorsa prenotabile                     | Abilitato per Skype for Business, abilitato per Exchange (cassetta postale delle risorse) |
| Chiamate in conferenza            | Abilitare le riunioni *avviate direttamente* dalla console Sale di Microsoft Teams con le coordinate dei servizi di conferenza telefonica con accesso esterno | Abilitato per le audioconferenze                                          |
| Chiamate PSTN in uscita/in entrata | Abilitare la console Sale di Microsoft Teams per effettuare e ricevere chiamate PSTN                                         | Abilitato per Sistema telefonico                                                |

Per altre informazioni sugli account di Microsoft Teams Rooms, vedere [Configurare gli account per le sale di Microsoft Teams.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere quali scenari saranno supportati e identificare i requisiti di licenza per gli account di servizio di Microsoft Teams Rooms.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Prepararsi a ospitare gli account del computer e del servizio.</li></ul>| 


_Tabella di pianificazione dell'account di servizio Microsoft Teams Rooms di esempio_

| **Sito**  | **Nome chat room** | **Tipo di sala** | **Funzionalità future per le chat room**                                                 | **Funzionalità dell'account di Microsoft Teams Rooms**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | Media.        | 1 schermo, audio e video più presentazione <br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Skype for Business, abilitato per Exchange (cassetta postale delle risorse) <br>Abilitato per le audioconferenze <br>Abilitato per Sistema telefonico |
| Sydney HQ | Hill          | Grande         | 2 schermi, audio e video più presentazione<br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Skype for Business, abilitato per Exchange (cassetta postale delle risorse)<br> Abilitato per le audioconferenze <br>Abilitato per Sistema telefonico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Prepararsi a ospitare gli account di computer e servizi di Microsoft Teams Rooms (facoltativo)

Per consentire la gestione e la creazione di report sugli account computer e di servizio di Microsoft Teams Rooms, preparare Active Directory locale o Azure Active Directory (Azure AD). 

Definire un gruppo di Active Directory o Azure AD locale a cui aggiungere tutti gli account del servizio Microsoft Teams Room (utente), quindi creare report sull'utilizzo usando il cmdlet Get-CSUserSession PowerShell nella distribuzione di Microsoft Teams Rooms. Ad esempio, creare un gruppo denominato SkypeRoomSystemsv2-Service-Accounts. 


Definire un'unità organizzativa nella gerarchia di Active Directory o Azure AD locale in modo da contenere tutti gli account computer di Microsoft Teams Room (se fanno parte del dominio) e un'unità organizzativa per contenere tutti gli account utente di Microsoft Teams Rooms. Se si crea un'unità organizzativa per gli account computer di Microsoft Teams Room, è consigliabile disabilitare l'ereditarietà per assicurarsi di applicare solo i criteri che si intende applicare alle sale di Microsoft Teams unite al dominio. 

Creare un oggetto Criteri di gruppo assegnato all'unità organizzativa che contiene gli account computer di Microsoft Teams Room. Usare questa opzione per: 

-   [Configurare le impostazioni di alimentazione e dell'account locale.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Abilitare Windows Update.
-   Abilitare PowerShell# È possibile configurare uno script di avvio per l'esecuzione di uno script semplice: Enable-PSRemoting -Force

È possibile usare PowerShell per eseguire una serie di attività di gestione remota, tra cui ottenere e impostare informazioni di configurazione. PowerShell deve essere  abilitato prima di poter eseguire una gestione remota di PowerShell e deve essere considerato parte dei processi di distribuzione o configurato tramite Criteri di gruppo. Per altre informazioni su queste funzionalità e sull'abilitazione, vedere [Manutenzione e operazioni.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configurazione e distribuzione 

La pianificazione della configurazione e della distribuzione riguarda le aree principali seguenti:

-   Provisioning dell'account
-   Installazione del software del dispositivo
-   Distribuzione di dispositivi
-   Configurazione dell'applicazione Sale di Microsoft Teams e dei dispositivi periferiche
-    Test
-   Gestione beni

### <a name="account-provisioning"></a>Provisioning dell'account 

Ogni dispositivo Microsoft Teams Rooms richiede un account delle risorse dedicato e univoco che deve essere abilitato sia per Microsoft Teams che per Skype for Business ed Exchange. Questo account deve avere una cassetta postale della sala ospitata su Exchange ed essere abilitato come sala riunioni nella distribuzione di Teams o Skype for Business. Sul lato Exchange è necessario configurare l'elaborazione del calendario in modo che il dispositivo possa accettare automaticamente le convocazioni riunione in arrivo. Per altre informazioni sulla creazione di questi account, vedere [Configurare gli account per le sale di Microsoft Teams.](rooms-configure-accounts.md) 

**Suggerimento per professionisti:** usare nomi visualizzati descrittivi e facili da capire per questi account. Questi sono i nomi che gli utenti visualizzano quando cercano e aggiungono sistemi Microsoft Teams Room alle riunioni. Alcune organizzazioni usano la convention *Site* Room Name ( Max Room Capacity )-RS, quindi ad esempio Curie, una sala riunioni con 12 persone a Londra, potrebbe avere il nome visualizzato - LON-CURIE(12)-RS. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Stabilire la convenzione di denominazione per gli account di Microsoft Teams Room.</li><li>Decidere se creare singoli account o usare script di provisioning in blocco.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Installazione del software del dispositivo 

Quando si pianifica la distribuzione di Sale di Microsoft Teams, è possibile scegliere tra diverse opzioni per installare il software necessario. Nella tabella seguente sono descritti gli scenari e gli approcci comuni. 

| **Scenario**            | **Approccio**         |
|-------------------------|-----------------------|   
|Distribuzione di un numero limitato di dispositivi Microsoft Teams Rooms (<10). | Se si usa Microsoft Teams Room basato su Surface Pro, seguire le istruzioni di [installazione per un'installazione per dispositivo.](console.md) [Questo pratico video illustra il processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se si usa una soluzione integrata, eseguire la distribuzione con l'immagine del fornitore e configurare le impostazioni in base alle esigenze. |
| Distribuzione tra 10 e 50 dispositivi da un singolo fornitore.     | Creare un'immagine basata su WIM, fermarsi dopo il passaggio [6](console.md)delle indicazioni e acquisire un'immagine di distribuzione da usare con la tecnologia di distribuzione di clonazione.    |
| Distribuendo più di 50 dispositivi di Microsoft Teams Room, distribuendo dispositivi da più fornitori o richiedendo agenti specifici dell'organizzazione durante la distribuzione. | Usare una piattaforma di distribuzione e build software basata su sequenza di attività, come [Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Suggerimento per professionisti:** ogni sala di Microsoft Teams deve avere un nome di computer valido e univoco nella rete. Molti sistemi di monitoraggio e avviso visualizzano il nome del computer come identificatore di chiave, quindi è importante sviluppare una convenzione di denominazione per le distribuzioni di Sale di Microsoft Teams che consente al personale di supporto di individuare facilmente le sale di Microsoft Teams contrassegnate come che richiedono un'azione. Ad esempio, è possibile usare uno schema di MTR -*Nome* sala - *siti* (MTR-LON-CURIE). 

Nell'ambito della distribuzione, è anche necessario prendere in considerazione [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) la strategia di gestione e configurazione degli account locali creati dal programma di installazione dell'applicazione Microsoft Teams Rooms.

Sono disponibili indicazioni su come usare Il monitor di [Microsoft Azure](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) per monitorare la distribuzione delle sale di Microsoft Teams e determinare la disponibilità, gli errori hardware/software e la versione dell'applicazione Microsoft Teams Rooms. Se si decide di usare Microsoft Operations Management Suite, è necessario installare l'agente di Operations Management Suite nell'ambito del processo di installazione del software e configurare le informazioni di connessione dell'area di lavoro per l'area di lavoro. 

Un altro aspetto da tenere in considerazione è se le sale di Microsoft Teams verranno unite a un dominio. Per informazioni sui vantaggi della partecipazione a un dominio, fare clic su Considerazioni sulla partecipazione a un dominio [in Skype Room System.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione dei dispositivi per Le sale di Microsoft Teams da usare durante la distribuzione.</li><li>Decidere se aggiungere i dispositivi di Microsoft Teams Rooms al dominio e come gestire e configurare gli account locali. </li><li>Decidere se si userà Operations Management Suite per monitorare la distribuzione di Microsoft Teams Rooms.</li><li>Decidere quale metodo si userà per distribuire il software e gli agenti nel sistema Room di Microsoft Teams in preparazione alla distribuzione del dispositivo. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare l'approccio di distribuzione dei dispositivi.</li></ul>| 


### <a name="device-deployment"></a>Distribuzione di dispositivi

Dopo aver distribuito il software nelle unità Sale di Microsoft Teams, creare il piano per la spedizione dei dispositivi e delle periferiche assegnate alle sale, quindi procedere all'installazione e alla configurazione. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno i dispositivi della chat room di Microsoft Teams nel sito e intraprendere le configurazioni e i test.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avviare il test del dispositivo.</li></ul>| 

_Tabella di distribuzione di esempio_

| **Sito**  | **Nome chat room** | **Tipo di sala** | **Sistema Microsoft Teams Rooms**  | **Periferiche**  | **Nome computer di Microsoft Teams Rooms**  | **Account della risorsa Microsoft Teams Rooms**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | Media.        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configurazione dell'applicazione Sale di Microsoft Teams e dei dispositivi periferiche 

Dopo aver distribuito fisicamente ogni sistema Room di Microsoft Teams e collegato i dispositivi periferiche supportati, sarà necessario configurare l'applicazione Sale di Microsoft Teams per assegnare l'account della risorsa Sale di Microsoft Teams e la password creati in precedenza, per consentire al sistema Sale di Microsoft Teams di accedere a Microsoft Teams o Skype for Business ed Exchange. È fondamentale sfruttare le periferiche audio e video USB certificate collegate in un altro punto del documento. In caso non corretto, il comportamento può risultare imprevedibile. 

È possibile configurare manualmente ogni sistema Sale di Microsoft Teams. In alternativa, è possibile usare un file di configurazione XML di Microsoft Teams Rooms archiviato centralmente per gestire le impostazioni dell'applicazione e sfruttare uno script dell'oggetto Criteri di gruppo di avvio per riapplicare la configurazione desiderata, ogni volta che il sistema Microsoft Teams Rooms è stato installato. 

Per altre informazioni su come usare il file di configurazione XML, vedere Gestire le impostazioni della console di Microsoft Teams Room in remoto [con un file di configurazione XML.](xml-config-file.md) 

È possibile usare una [sessione remota di PowerShell per](rooms-operations.md#remote-management-using-powershell) estrarre la configurazione di Sale di Microsoft Teams per soddisfare le esigenze di creazione di report. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se configurare manualmente ogni sistema Microsoft Teams Room o usare un file XML centrale (uno per ogni dispositivo Microsoft Teams Rooms).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Definire l'approccio di gestione remota.</li></ul>| 

### <a name="testing"></a> Test

Dopo aver distribuito il sistema Sale di Microsoft Teams, è necessario testarlo. Verificare che le funzionalità elencate in [Sale di Microsoft Teams siano](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) disponibili nel dispositivo distribuito. È consigliabile che il team di distribuzione verifichi che la chat room di Microsoft Teams 365 365 tasi in Microsoft Operations Management Suite (se utilizzata). È anche importante effettuare un certo numero di chiamate e riunioni di prova per verificare la qualità. Per altre informazioni, vedere questo utile [elenco di controllo per la distribuzione.](console.md#microsoft-teams-rooms-deployment-checklist)

Come parte dell'implementazione generale di Teams o Skype for Business, è consigliabile configurare i file di creazione per Call Quality Dashboard (CQD), monitorare le tendenze della qualità e intraprendere il processo di revisione della qualità dell'esperienza. Per ulteriori informazioni, consulta [Migliorare e monitorare la qualità delle chiamate per Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Gestione beni

Come parte della distribuzione, è necessario aggiornare il registro beni con il nome della sala, il nome del dispositivo Microsoft Teams Rooms, l'account della risorsa Sale di Microsoft Teams e le periferiche assegnate (e quali porte USB usano). 

_Tabella beni di esempio_

| **Sito**  | **Nome chat room** | **Tipo di sala** | **N. seriale di Microsoft Teams Rooms.**  | **Periferiche/ n. seriale/porte**  | **Nome computer di Microsoft Teams Rooms**  | **Account del servizio Microsoft Teams Rooms**  | **Data di distribuzione** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | Media.        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


