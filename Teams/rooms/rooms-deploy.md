---
title: Distribuire Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leggere questo articolo per informazioni su come distribuire Microsoft Teams Rooms, incluse le fasi di distribuzione.
ms.openlocfilehash: 18a5d72fb9c11b34bb994734b8d064c3aaa2cdae
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125771"
---
# <a name="deployment-overview"></a>Panoramica della distribuzione

La distribuzione di Microsoft Teams Rooms essenzialmente suddivide in fasi:

- Confermando che le posizioni di distribuzione (spazi) soddisfano le dipendenze di distribuzione
- Creazione di Microsoft Teams o Skype for Business e Exchange account e assegnazione a Teams Rooms (vedere [Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md))
- (Facoltativo) Configurazione di Monitoraggio di Azure per i sistemi (vedere [Distribuire la gestione Microsoft Teams Rooms con Monitoraggio di Azure](azure-monitor-deploy.md)
- Configurazione di Teams Rooms negli spazi per le riunioni e connessione dei dispositivi periferici necessari (vedere la documentazione OEM per il set di dispositivi in uso)

## <a name="site-readiness"></a>Preparazione del sito 

Mentre i dispositivi ordinati vengono distribuiti all'organizzazione, collaborare con i team di rete, strutture e AV per assicurarsi che le dipendenze di distribuzione siano soddisfatte e che ogni sito e spazio sia pronto in termini di alimentazione, rete e visualizzazione. Inoltre, verifica che i requisiti fisici di installazione siano soddisfatti. Per considerazioni sull'installazione fisica, consulta il tuo fornitore e sfrutta l'esperienza del tuo team av durante l'installazione e il montaggio di schermate e l'esecuzione di cavi.

Per altre informazioni su queste dipendenze, vedere i collegamenti alle linee guida sulla pianificazione seguenti:

-   [Verificare la disponibilità della rete](rooms-prep.md#check-network-availability)
-   [Certificati](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro Suggerimento**: se è necessario usare i server proxy per fornire l'accesso a Teams, [leggere prima di tutto questo articolo](../proxy-servers-for-skype-for-business-online.md). Quando si tratta di Microsoft Teams traffico multimediale in tempo reale sui server proxy, è consigliabile bypassare del tutto i server proxy. Microsoft Teams traffico è già crittografato, quindi i server proxy non lo rendono più sicuro e aggiungono latenza al traffico in tempo reale. Nell'ambito di una distribuzione più ampia, è consigliabile seguire le indicazioni in [Preparare la rete per Teams](../prepare-network.md) per la pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confermare i siti.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti principali per Microsoft Teams Rooms.</li><li>Verificare di aver fornito larghezza di banda sufficiente per ogni sito.</li></ul>| 
| ![pianificare la distribuzione dei dispositivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontezza del servizio

Per prepararsi alla distribuzione Microsoft Teams Rooms, eseguire le attività principali principali seguenti:

-   Definire Microsoft Teams Rooms account delle risorse.
-   Se si partecipa Teams Rooms a Azure Active Directory, preparare un gruppo di Azure AD con appartenenza dinamica in modo da contenere tutti gli account delle risorse Teams Rooms. In questo modo si semplifica la gestione futura, ad esempio l'applicazione dei criteri di accesso condizionale. Per sfruttare più facilmente Azure AD gruppi dinamici, determinare una convenzione di denominazione che identificherà in modo univoco gli account delle risorse Teams Rooms.
-   Se si unisce Teams Rooms ad Active Directory, preparare un'unità organizzativa e un gruppo di Active Directory per tenere gli account di computer e risorse Microsoft Teams Rooms e, facoltativamente, preparare Criteri di gruppo oggetti (GPO) per abilitare la comunicazione remota di PowerShell.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definire Microsoft Teams Rooms caratteristiche dell'account delle risorse 

A seconda degli scenari di collaborazione che si è deciso di abilitare con la distribuzione Microsoft Teams Rooms, è necessario determinare le caratteristiche e le funzionalità assegnate a ogni Microsoft Teams Rooms abilitata.

| **Scenario** | **Descrizione** | **Microsoft Teams Rooms funzionalità dell'account del servizio** |
|---------- |------------- | --- |
| Riunioni interattive            | Uso di voce, video e condivisione dello schermo; rendendo il Microsoft Teams Rooms una risorsa prenotabile                     | Abilitato per Microsoft Teams o Skype for Business; abilitato per Exchange (cassetta postale delle risorse) |
| Chiamate in conferenza            | Disporre di un numero di telefono per i servizi di audioconferenza quando si tocca "Nuova riunione" sulla console | Abilitato per i servizi di audioconferenza                                          |
| Chiamate PSTN in uscita/in ingresso | Abilitare la console Microsoft Teams Rooms per effettuare e ricevere chiamate PSTN                                         | Abilitato per Sistema telefonico                                                |

Per altre informazioni su Microsoft Teams Rooms account, vedere [Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![supporto scenario.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere quali scenari supportare e identificare i requisiti di licenza per gli account delle risorse di Microsoft Teams Rooms.</li></ul>| 
| ![preparare il computer host.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Prepararsi ad ospitare account di computer e risorse.</li></ul>| 


_Tabella di pianificazione dei conti delle risorse Microsoft Teams Rooms di esempio_

| **Sito**  | **Nome chat room** | **Tipo di sala** | **Funzionalità future per le chat room**                                                 | **Funzionalità dell'account Microsoft Teams Rooms**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Sede centrale di Londra | Curie         | Media.        | 1 schermo, audio e video più presentazione <br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Exchange (cassetta postale delle risorse) <br>Abilitato per i servizi di audioconferenza <br>Abilitato per Sistema telefonico |
| Sede centrale di Sydney | Collina          | Grande         | 2 Schermi, audio e video più presentazione<br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Skype for Business <br>Abilitato per Exchange (cassetta postale delle risorse)<br> Abilitato per i servizi di audioconferenza <br>Abilitato per Sistema telefonico |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Preparare l'host degli account di Microsoft Teams Rooms e delle risorse (facoltativo)

Per consentire la gestione e la creazione di report sugli account di Microsoft Teams Rooms e delle risorse, preparare il Active Directory locale o Azure Active Directory (Azure AD). 

Definire un Active Directory locale o un gruppo di Azure Active Directory a cui aggiungere tutti gli account delle risorse Microsoft Teams Rooms. Se si usa Azure Active Directory, è consigliabile usare un gruppo dinamico per aggiungere e rimuovere automaticamente gli account delle risorse dal gruppo.

Definire un'unità organizzativa nella gerarchia di Active Directory locale per contenere tutti gli account Microsoft Teams Rooms computer (se fanno parte del dominio) e un'unità organizzativa per contenere tutti gli account utente Microsoft Teams Rooms. Disabilitare Criteri di gruppo'ereditarietà per assicurarsi di applicare solo i criteri che si intende applicare al Microsoft Teams Rooms aggiunto a un dominio.

Creare un oggetto Criteri di gruppo assegnato all'unità organizzativa che contiene gli account Microsoft Teams Rooms computer. Usare questa opzione per: 

-   [Imposta le impostazioni relative all'alimentazione e all'account locale](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Abilitare Windows Update.
-   Abilitare la comunicazione remota di PowerShell. È possibile configurare uno script di avvio per l'esecuzione di uno script: Enable-PSRemoting -Force

È possibile usare PowerShell per eseguire diverse attività di gestione remota, tra cui il recupero e l'impostazione delle informazioni di configurazione. I servizi remoti di PowerShell devono essere abilitati *prima* che possa essere eseguita una gestione remota di PowerShell e devono essere considerati parte dei processi di distribuzione o configurati tramite Criteri di gruppo. Per altre informazioni su queste funzionalità e per abilitarle, vedere [Manutenzione e operazioni](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configurazione e distribuzione 

La pianificazione della configurazione e dell'implementazione riguarda le seguenti aree principali:

-   Provisioning dell'account delle risorse
-   Installazione software del dispositivo
-   Distribuzione di dispositivi
-   Microsoft Teams Rooms configurazione di applicazioni e periferiche
-    Test
-   Gestione asset

### <a name="resource-account-provisioning"></a>Provisioning dell'account delle risorse 

Ogni dispositivo Microsoft Teams Rooms richiede un account di risorse dedicato e univoco che deve essere abilitato sia per Microsoft Teams che per Skype for Business e Exchange. Questo account deve avere una cassetta postale della sala ospitata in Exchange. L'elaborazione del calendario deve essere configurata in modo che il dispositivo possa accettare automaticamente le convocazioni riunione in arrivo. Per altre informazioni sulla creazione di questi account, vedere [Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md). 

**Pro suggerimento**: ogni Microsoft Teams Rooms deve avere un nome di computer valido e univoco nella rete. Molti sistemi di monitoraggio e avviso visualizzano il nome della macchina come identificatore chiave, quindi è importante sviluppare una convenzione di denominazione per le distribuzioni di Microsoft Teams Rooms che consenta al personale di supporto di individuare facilmente i Microsoft Teams Rooms contrassegnati come necessari per un'azione. Un esempio può essere l'uso di un modello *MTR-SiteRoom*- *Name* (MTR-LON-CURIE). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![decidere la convenzione di denominazione.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione per gli account delle risorse Microsoft Teams Rooms.</li><li>Decidere se creare singoli account o usare script di provisioning in blocco.</li></ul>| 
| ![passaggi successivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Installazione software del dispositivo 

Teams Rooms viene fornito preinstallo dall'OEM (Original Equipment Manufacturer).

Vengono fornite indicazioni su come usare [Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) per monitorare la distribuzione Microsoft Teams Rooms e segnalare la disponibilità, gli errori hardware/software e Microsoft Teams Rooms versione dell'applicazione. Se si decide di usare Microsoft Operations Management Suite, è consigliabile installare l'agente operations management suite nell'ambito del processo di installazione del software e configurare le informazioni di connessione dell'area di lavoro per l'area di lavoro. 

Un ulteriore aspetto da considerare è se il Microsoft Teams Rooms verrà aggiunto a un dominio. Per informazioni sui vantaggi dell'aggiunta a un dominio, vedere [Configurazione di Criteri di gruppo per Microsoft Teams Rooms](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms). 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![denominazione dei dispositivi dei punti di decisione.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione Microsoft Teams Rooms account delle risorse da usare durante la distribuzione.</li><li>Decidere se si aggiungeranno Microsoft Teams Rooms dispositivi al dominio. </li><li>Decidere se usare Monitoraggio di Azure per monitorare la distribuzione Microsoft Teams Rooms.</li> 
| ![passaggi successivi pianificare il dispositivo.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare l'approccio di distribuzione del dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Distribuzione di dispositivi

Dopo aver deciso come creare e gestire gli account delle risorse Microsoft Teams Rooms, creare il piano per spedire i dispositivi e le periferiche assegnate alle chat room, quindi procedere con l'installazione e la configurazione.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gestire la distribuzione sito per sito.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno Microsoft Teams Rooms sul sito e effettueranno la configurazione e i test.</li></ul>| 
| ![avviare il test del dispositivo.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avvia il test del dispositivo.</li></ul>| 

_Tabella di distribuzione di esempio_

| **Sito**  | **Nome chat room** | **Tipo di sala** | **Microsoft Teams Rooms sistema**  | **Periferiche**  | **Microsoft Teams Rooms nome computer**  | **Microsoft Teams Rooms account delle risorse**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Sede centrale di Londra | Curie         | Media.        |                                   |                  |                                          |                                             |
| Sede centrale di Sydney | Collina          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams Rooms configurazione di applicazioni e periferiche 

Dopo che ogni sistema Microsoft Teams Rooms è stato distribuito fisicamente e le periferiche supportate sono connesse, dovrai configurare l'applicazione Microsoft Teams Rooms per assegnare l'account della risorsa Microsoft Teams Rooms e la password per abilitare Teams Rooms per accedere a Microsoft Teams o Skype for Business e Exchange.

È possibile configurare manualmente ogni Microsoft Teams Rooms sistema. In alternativa, è possibile usare un file di configurazione XML archiviato centralmente per Teams Rooms per gestire le impostazioni dell'applicazione.

Per altre informazioni su come usare il file di configurazione XML, vedere [Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md). 

È possibile usare [una configurazione remota di PowerShell](rooms-operations.md#remote-management-using-powershell) per estrarre la configurazione Microsoft Teams Rooms in base alle esigenze di creazione di report. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configurazione del punto di decisione.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se configurare manualmente ogni Microsoft Teams Rooms sistema o usare un file XML centrale (uno per Microsoft Teams Rooms dispositivo).</li></ul>| 
| ![passaggi successivi per l'approccio remoto.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Definire l'approccio di gestione remota.</li></ul>| 

### <a name="testing"></a> Test

Dopo aver distribuito Teams Rooms, è consigliabile testarlo. Verificare che le funzionalità elencate in [Microsoft Teams Rooms Guida](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) funzionino nel dispositivo distribuito. È consigliabile che il team di distribuzione verifichi che Microsoft Teams Rooms venga visualizzato nell Teams interfaccia di amministrazione. È anche importante effettuare una serie di chiamate e riunioni di test per controllare la qualità. Per altre informazioni, vedere questo [utile elenco di controllo per la distribuzione](console.md#microsoft-teams-rooms-deployment-checklist).

Nell'ambito dell'implementazione generale Teams o Skype for Business, è consigliabile configurare la creazione di file per Call Quality Dashboard (CQD), monitorare le tendenze della qualità e partecipare al processo di verifica della qualità dell'esperienza. Per altre informazioni, vedere [Migliorare e monitorare la qualità delle chiamate per Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Gestione asset

Come parte della distribuzione, è consigliabile aggiornare il registro beni con il nome della chat room, il nome Microsoft Teams Rooms, l'account delle risorse Microsoft Teams Rooms e i dispositivi periferici assegnati. 

_Tabella delle risorse di esempio_

| **Sito**  | **Nome chat room** | **Tipo di sala** | **Microsoft Teams Rooms numero di serie.**  | **Periferiche/ n. seriale./ Porte**  | **Microsoft Teams Rooms nome computer**  | **account del servizio Microsoft Teams Rooms**  | **Data distribuzione** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Sede centrale di Londra | Curie         | Media.        |                                          |                                          |                                          |                                            |                   |
| Sede centrale di Sydney | Collina          | Grande         |                                          |                                          |                                          |                                            |                   |
