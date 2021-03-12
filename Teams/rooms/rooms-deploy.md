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
description: Leggere questo articolo per informazioni su come distribuire Microsoft Teams Rooms, incluse le fasi di distribuzione.
ms.openlocfilehash: 87ded33b464d6f5248fe1fb71d579d5f191bb6b6
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726307"
---
# <a name="deployment-overview"></a>Panoramica della distribuzione

La distribuzione di Microsoft Teams Rooms si suddivide essenzialmente in fasi:

- Verificare che le posizioni di distribuzione (chat room) soddisfino le dipendenze di distribuzione
- Creazione di account Microsoft Teams o Skype for Business ed Exchange e assegnazione di account ai dispositivi console (vedere [Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md))
- Reimaging Microsoft Surface tablets to work as Microsoft Teams Rooms consoles (see [Configure a Microsoft Teams Rooms console](console.md) or Deploy Microsoft Teams Rooms mass deployment [guide](rooms-scale.md))
- (Facoltativo) Configurazione di Microsoft Operations Management Suite per i sistemi (vedere Distribuire la gestione di [Microsoft Teams Rooms con Azure Monitor](azure-monitor-deploy.md)
- Configurazione di console nelle sale riunioni e connessione dei dispositivi periferici necessari (vedere la documentazione OEM relativa al set di dispositivi)

I tecnici AV possono essere usati per l'ultima attività, ma il reparto IT dell'organizzazione dovrà eseguire le altre parti del processo. 


## <a name="site-readiness"></a>Conformità del sito 

Mentre i dispositivi ordinati vengono recapitati all'organizzazione, collaborare con le reti e le strutture e i team AV per assicurarsi che le dipendenze di distribuzione siano soddisfatte e che ogni sito e sala sia pronto in termini di potenza, rete e visualizzazione. Assicurarsi inoltre che i requisiti di installazione fisica siano soddisfatti. Per considerazioni sull'installazione fisica, visitare il sito del fornitore e sfruttare l'esperienza del team AV durante l'installazione e il montaggio degli schermi e l'esecuzione del cablaggio.

Per altre informazioni su queste dipendenze, vedere i collegamenti alle indicazioni per la pianificazione seguenti:

-   [Verificare la disponibilità della rete](rooms-prep.md#check-network-availability)
-   [Certificati](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Suggerimento per** professionisti: se si prevede di usare server proxy per fornire l'accesso a Teams o Skype for Business online, [leggere questo articolo.](../proxy-servers-for-skype-for-business-online.md) Per quanto riguarda il traffico di Skype for Business sui server proxy, è consigliabile ignorare completamente i server proxy. Il traffico di Skype for Business è già crittografato, quindi i server proxy non lo rendono più sicuro. Nell'ambito della distribuzione più ampia, è consigliabile seguire le indicazioni fornite in Preparare la rete per [Teams](../prepare-network.md) per la pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.

|    |     |
|-----------|------------|
| ![confermare i siti](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti principali per Microsoft Teams Rooms.</li><li>Verificare di aver fornito larghezza di banda sufficiente per ogni sito.</li></ul>| 
| ![pianificare la distribuzione di dispositivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontezza del servizio

Per prepararsi alla distribuzione di Microsoft Teams Rooms, eseguire le attività centrali seguenti:

-   Definire le caratteristiche dell'account del servizio Microsoft Teams Rooms.
-   Preparare un'unità organizzativa e un gruppo di Active Directory per contenere gli account computer e di servizio di Microsoft Teams Rooms e, facoltativamente, preparare gli oggetti Criteri di gruppo (GPO) per abilitare la comunicazione remota di PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definire le caratteristiche dell'account del servizio Microsoft Teams Rooms 

A seconda degli scenari di collaborazione che si è deciso di abilitare con la distribuzione di Microsoft Teams Rooms, sarà necessario determinare le caratteristiche e le funzionalità assegnate a ogni account di servizio di Microsoft Teams Rooms abilitato.

| **Scenario** | **Descrizione** | **Funzionalità dell'account del servizio Microsoft Teams Rooms** |
|---------- |------------- | --- |
| Riunioni interattive            | Uso di voce, video e condivisione dello schermo; rendere le sale di Microsoft Teams una risorsa prenotabile                     | Abilitato per Skype for Business, abilitato per Exchange (cassetta postale delle risorse) |
| Chiamate in conferenza            | Abilitare le riunioni *avviate direttamente* dalla console di Microsoft Teams Rooms con coordinate per i servizi di conferenza telefonica con accesso esterno | Abilitato per le audioconferenze                                          |
| Chiamate PSTN in uscita/in ingresso | Abilitare la console di Microsoft Teams Rooms per effettuare e ricevere chiamate PSTN                                         | Abilitato per Sistema telefonico                                                |

Per altre informazioni sugli account di Microsoft Teams Rooms, vedere [Configurare gli account per le chat room di Microsoft Teams.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![supporto per scenari](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere quali scenari supportare e identificare i requisiti di licenza per gli account di servizio di Microsoft Teams Rooms.</li></ul>| 
| ![preparare il computer host](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare l'hosting degli account del computer e del servizio.</li></ul>| 


_Tabella di pianificazione dell'account del servizio Microsoft Teams Rooms di esempio_

| **Sito**  | **Nome della chat room** | **Tipo di chat room** | **Funzionalità future per le chat room**                                                 | **Caratteristiche dell'account di Microsoft Teams Rooms**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Sede centrale di Londra | Curie         | Media.        | 1 schermo, audio e video più presentazione <br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Skype for Business, abilitato per Exchange (cassetta postale delle risorse) <br>Abilitato per le audioconferenze <br>Abilitato per Sistema telefonico |
| Sede centrale di Sydney | Collina          | Grande         | 2 schermi, audio e video più presentazione<br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Skype for Business, abilitato per Exchange (cassetta postale delle risorse)<br> Abilitato per le audioconferenze <br>Abilitato per Sistema telefonico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparare l'hosting degli account computer e di servizio di Microsoft Teams Rooms (facoltativo)

Per consentire di gestire e creare report sugli account di servizio e computer di Microsoft Teams Rooms, preparare Active Directory locale o Azure Active Directory (Azure AD). 

Definire un gruppo di Active Directory o Azure AD locale a cui aggiungere tutti gli account del servizio Microsoft Teams Rooms (utente) e quindi creare report sull'utilizzo usando il cmdlet di PowerShell di Get-CSUserSession nella distribuzione di Microsoft Teams Rooms. Ad esempio, creare un gruppo denominato SkypeRoomSystemsv2-Service-Accounts. 


Definire un'unità organizzativa nella gerarchia di Active Directory o Azure AD locale per contenere tutti gli account computer di Microsoft Teams Rooms (se fanno parte del dominio) e un'unità organizzativa per contenere tutti gli account utente di Microsoft Teams Rooms. Se si crea un'unità organizzativa per gli account computer di Microsoft Teams Rooms, è consigliabile disabilitare l'ereditarietà per assicurarsi di applicare solo i criteri che si intende applicare alle chat room di Microsoft Teams appartenenti al dominio. 

Creare un oggetto Criteri di gruppo assegnato all'unità organizzativa che contiene gli account computer di Microsoft Teams Rooms. Usare questa opzione per: 

-   [Impostare le impostazioni dell'alimentazione e dell'account locale.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Abilitare Windows Update.
-   Abilitare la comunicazione remota di PowerShell. È possibile configurare uno script di avvio per l'esecuzione di uno script: Enable-PSRemoting -Force

È possibile usare PowerShell per eseguire diverse attività di gestione remota, tra cui il recupero e l'impostazione delle informazioni di configurazione. La comunicazione remota  di PowerShell deve essere abilitata prima di poter eseguire qualsiasi gestione remota di PowerShell e deve essere considerata come parte dei processi di distribuzione o configurata tramite Criteri di gruppo. Per altre informazioni su queste funzionalità e sull'abilitazione, vedere [Manutenzione e operazioni.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configurazione e distribuzione 

La pianificazione della configurazione e della distribuzione riguarda le aree chiave seguenti:

-   Provisioning dell'account
-   Installazione del software per dispositivi
-   Distribuzione di dispositivi
-   Configurazione dell'applicazione Microsoft Teams Rooms e dei dispositivi periferici
-    Test
-   Gestione delle risorse

### <a name="account-provisioning"></a>Provisioning dell'account 

Ogni dispositivo Microsoft Teams Rooms richiede un account delle risorse dedicato e univoco che deve essere abilitato sia per Microsoft Teams che per Skype for Business ed Exchange. Questo account deve avere una cassetta postale della sala ospitata in Exchange ed essere abilitata come sala riunioni nella distribuzione di Teams o Skype for Business. Sul lato Exchange è necessario configurare l'elaborazione del calendario in modo che il dispositivo possa accettare automaticamente le convocazioni di riunione in arrivo. Per altre informazioni sulla creazione di questi account, vedere [Configurare gli account per Microsoft Teams Rooms.](rooms-configure-accounts.md) 

**Suggerimento per i** professionisti: rendere i nomi visualizzati per questi account descrittivi e facili da capire. Questi sono i nomi che gli utenti visualizzano durante la ricerca e l'aggiunta di sistemi Microsoft Teams Rooms alle riunioni. Alcune organizzazioni usano la convenzione *Site* Room Name ( Max Room Capacity )-RS, quindi ad esempio Curie, una sala riunioni di 12 persone a Londra, potrebbe avere il nome visualizzato - LON-CURIE(12)-RS. 

|    |     |
|-----------|------------|
| ![decidere la convenzione di denominazione](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione per gli account di Microsoft Teams Rooms.</li><li>Decidere se creare singoli account o usare script di provisioning in blocco.</li></ul>| 
| ![passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Installazione del software per dispositivi 

Quando si prevede di distribuire Microsoft Teams Rooms, è possibile scegliere di installare il software necessario. Gli scenari e gli approcci comuni sono descritti nella tabella seguente. 

| **Scenario**            | **Approccio**         |
|-------------------------|-----------------------|   
|Distribuzione di alcuni dispositivi Microsoft Teams Rooms (<10). | Se si usa Microsoft Teams Rooms basato su Surface Pro, seguire le istruzioni [di installazione per un'installazione per dispositivo.](console.md) [Questo pratico video illustra il processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se si usa una soluzione integrata, eseguire la distribuzione usando l'immagine del fornitore e configurare le impostazioni in base alle esigenze. |
| Distribuzione da 10 a 50 dispositivi da un singolo fornitore.     | Creare un'immagine basata su WIM, sospendere dopo il passaggio [6](console.md)nelle indicazioni e acquisire un'immagine di distribuzione da usare con la tecnologia di distribuzione della clonazione.    |
| Distribuzione di più di 50 dispositivi Microsoft Teams Rooms, distribuzione di dispositivi da più di un fornitore o richiesta di agenti specifici dell'organizzazione nell'ambito della distribuzione. | Usare una piattaforma di distribuzione e build software basata su sequencer di attività, ad esempio [Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Suggerimento per i** professionisti: ogni chat room di Microsoft Teams deve avere un nome di computer valido e univoco nella rete. Molti sistemi di monitoraggio e avviso visualizzano il nome del computer come identificatore chiave, quindi è importante sviluppare una convenzione di denominazione per le distribuzioni di Microsoft Teams Rooms che consenta al personale di supporto di individuare facilmente le chat room di Microsoft Teams contrassegnate come che richiedono un'azione. Un esempio potrebbe essere l'uso di uno schema MTR-*Site* - *Room Name* (MTR-LON-CURIE). 

Nell'ambito della distribuzione, è anche necessario prendere in considerazione [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) la strategia di gestione e configurazione degli account locali creati dal programma di installazione dell'applicazione Microsoft Teams Rooms.

Microsoft fornisce indicazioni su come usare [Microsoft Azure Monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) per monitorare la distribuzione di Microsoft Teams Rooms e segnalare la disponibilità, gli errori hardware/software e la versione dell'applicazione Microsoft Teams Rooms. Se si decide di usare Microsoft Operations Management Suite, è consigliabile installare l'agente di Operations Management Suite nell'ambito del processo di installazione del software e configurare le informazioni di connessione dell'area di lavoro per l'area di lavoro. 

Un'altra considerazione è se le chat room di Microsoft Teams verranno unite al dominio. Informazioni sui vantaggi dell'aggiunta al dominio sono disponibili in Considerazioni sull'aggiunta al dominio [di Skype Room System.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![denominazione dei dispositivi dei punti decisionali](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione dei dispositivi di Microsoft Teams Rooms da usare durante la distribuzione.</li><li>Decidere se si aggiungeranno i dispositivi Microsoft Teams Rooms al dominio e come gestire e configurare gli account locali. </li><li>Decidere se si userà Operations Management Suite per monitorare la distribuzione di Microsoft Teams Rooms.</li><li>Decidere quale metodo si userà per distribuire il software e gli agenti nel sistema Microsoft Teams Rooms in preparazione per la distribuzione dei dispositivi. </li></ul>| 
| ![Dispositivo piano passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare l'approccio di distribuzione del dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Distribuzione di dispositivi

Dopo aver distribuito il software nelle unità di Microsoft Teams Rooms, creare il piano per spedire i dispositivi e i dispositivi periferici assegnati alle chat room e quindi procedere con l'installazione e la configurazione. 


|    |     |
|-----------|------------|
| ![gestire la distribuzione sito per sito](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno i dispositivi di Microsoft Teams Rooms sul sito e intraprendere la configurazione e il test.</li></ul>| 
| ![Avviare il test del dispositivo](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avviare il test del dispositivo.</li></ul>| 

_Tabella di distribuzione di esempio_

| **Sito**  | **Nome della chat room** | **Tipo di chat room** | **Sistema Microsoft Teams Rooms**  | **Dispositivi periferici**  | **Nome computer di Microsoft Teams Rooms**  | **Account delle risorse di Microsoft Teams Rooms**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Sede centrale di Londra | Curie         | Media.        |                                   |                  |                                          |                                             |
| Sede centrale di Sydney | Collina          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configurazione dell'applicazione Microsoft Teams Rooms e dei dispositivi periferici 

Dopo che ogni sistema Microsoft Teams Rooms è stato distribuito fisicamente e i dispositivi periferici supportati sono connessi, sarà necessario configurare l'applicazione Microsoft Teams Rooms per assegnare l'account della risorsa Microsoft Teams Rooms e la password creati in precedenza, per consentire al sistema Microsoft Teams Rooms di accedere a Microsoft Teams o Skype for Business ed Exchange. È fondamentale sfruttare le periferiche audio e video USB certificate collegate in altre parti del documento. Questa operazione può comportare un comportamento imprevedibile. 

È possibile configurare manualmente ogni sistema Microsoft Teams Rooms. In alternativa, è possibile usare un file di configurazione XML di Microsoft Teams Rooms archiviato centralmente per gestire le impostazioni dell'applicazione e usare uno script di avvio dell'oggetto Criteri di gruppo per riapplicare la configurazione desiderata, ogni volta che viene avviato il sistema Microsoft Teams Rooms. 

Per altre informazioni su come usare il file di configurazione XML, vedere Gestire in remoto le impostazioni della console di [Microsoft Teams Rooms con un file di configurazione XML.](xml-config-file.md) 

È possibile usare [PowerShell remoto per](rooms-operations.md#remote-management-using-powershell) estrarre la configurazione di Microsoft Teams Rooms per le esigenze di creazione di report. 

|    |     |
|-----------|------------|
| ![configurazione del punto di decisione](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se configurare manualmente ogni sistema Microsoft Teams Rooms o usare un file XML centrale (uno per dispositivo Microsoft Teams Rooms).</li></ul>| 
| ![approccio remoto dei passaggi successivi](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Definire l'approccio di gestione remota.</li></ul>| 

### <a name="testing"></a> Test

Dopo aver distribuito il sistema Microsoft Teams Rooms, è consigliabile testarlo. Verificare che le funzionalità elencate nella [Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funzionino sul dispositivo distribuito. È consigliabile che il team di distribuzione verifichi che Microsoft Teams Rooms eseere la registrazione in Microsoft Operations Management Suite (se usato). È anche importante effettuare una serie di chiamate e riunioni di prova per verificare la qualità. Per altre informazioni, vedere questo utile elenco [di controllo per la distribuzione.](console.md#microsoft-teams-rooms-deployment-checklist)

Nell'ambito dell'implementazione generale di Teams o Skype for Business, è consigliabile configurare i file di creazione per Call Quality Dashboard (CQD), monitorare le tendenze qualitative e partecipare al processo di revisione della qualità dell'esperienza. Per altre informazioni, vedere [Migliorare e monitorare la qualità delle chiamate per Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Gestione delle risorse

Nell'ambito della distribuzione, è necessario aggiornare il registro delle risorse con il nome della chat room, il nome del dispositivo Microsoft Teams Rooms, l'account della risorsa Microsoft Teams Rooms connesso e i dispositivi periferici assegnati (e le porte USB usate). 

_Tabella delle risorse di esempio_

| **Sito**  | **Nome della chat room** | **Tipo di chat room** | **Microsoft Teams Rooms n. seriale.**  | **Periferiche/no seriali./ Porte**  | **Nome computer di Microsoft Teams Rooms**  | **Account del servizio Microsoft Teams Rooms**  | **Data distribuzione** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Sede centrale di Londra | Curie         | Media.        |                                          |                                          |                                          |                                            |                   |
| Sede centrale di Sydney | Collina          | Grande         |                                          |                                          |                                          |                                            |                   |


