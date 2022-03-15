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
ms.openlocfilehash: 8240eaff652a0ff465c9eb06242075b0d6baeba8
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503683"
---
# <a name="deployment-overview"></a>Panoramica della distribuzione

La distribuzione Microsoft Teams Rooms essenzialmente suddivisa in fasi:

- Verificare che i percorsi di distribuzione (spazi) soddisfino le dipendenze di distribuzione
- Creare Microsoft Teams o Skype for Business e Exchange e assegnarli a Teams Rooms (vedere [Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md))
- (Facoltativo) Configurazione di Azure Monitor per i sistemi (vedere Distribuire [Microsoft Teams Rooms gestione dei dati con Monitor di Azure](azure-monitor-deploy.md)
- Configurazione di Teams Rooms negli spazi riunioni e connessione dei dispositivi periferici necessari (vedere la documentazione OEM per il set di dispositivi)

## <a name="site-readiness"></a>Conformità del sito 

Mentre i dispositivi ordinati vengono recapitati all'organizzazione, collaborare con i team di rete, strutture e av per assicurarsi che le dipendenze di distribuzione siano soddisfatte e che ogni sito e spazio sia pronto in termini di potenza, rete e visualizzazione. Assicurarsi inoltre che i requisiti di installazione fisica siano soddisfatti. Per considerazioni sull'installazione fisica, rivolgersi al fornitore e sfruttare l'esperienza del team AV durante l'installazione e il montaggio degli schermi e l'esecuzione del cablaggio.

Per altre informazioni su queste dipendenze, vedere i collegamenti alle indicazioni per la pianificazione seguenti:

-   [Verificare la disponibilità della rete](rooms-prep.md#check-network-availability)
-   [Certificati](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro suggerimento**: se è necessario usare server proxy per fornire l'accesso a Teams, leggere [prima questo articolo](../proxy-servers-for-skype-for-business-online.md). Quando si tratta di Microsoft Teams traffico multimediale in tempo reale sui server proxy, è consigliabile ignorare del tutto i server proxy. Microsoft Teams il traffico è già crittografato, quindi i server proxy non lo rendono più sicuro e aggiungono latenza al traffico in tempo reale. Nell'ambito della distribuzione più ampia, è consigliabile seguire le indicazioni fornite in Preparare la rete [per il Teams per](../prepare-network.md) la pianificazione della larghezza di banda e valutare l'idoneità della rete per il traffico in tempo reale.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confermare i siti.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che i siti soddisfino i requisiti principali per Microsoft Teams Rooms.</li><li>Verificare di aver fornito larghezza di banda sufficiente per ogni sito.</li></ul>| 
| ![pianificare la distribuzione dei dispositivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione e la configurazione del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontezza del servizio

Per preparare la distribuzione Microsoft Teams Rooms, eseguire le attività centrali seguenti:

-   Definire Microsoft Teams Rooms account delle risorse.
-   Se si partecipa Teams room a Azure Active Directory, preparare un gruppo Azure AD con appartenenza dinamica per contenere tutti gli account Teams Rooms risorse. In questo modo si semplificherà la gestione futura, ad esempio l'applicazione di criteri di accesso condizionale. Per sfruttare al meglio i Azure AD dinamici, determinare una convenzione di denominazione che identififii in modo univoco gli account Teams Rooms risorse.
-   Se si partecipa Teams Room Teams Active Directory, preparare un'unità organizzativa e un gruppo di Active Directory per contenere gli account del computer e delle risorse di Microsoft Teams Rooms e, facoltativamente, preparare gli oggetti Criteri di gruppo (GPO) per abilitare la comunicazione remota di PowerShell.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definire le Microsoft Teams Rooms dell'account delle risorse 

A seconda degli scenari di collaborazione che si è deciso di abilitare con la distribuzione di Microsoft Teams Rooms, è necessario determinare le caratteristiche e le funzionalità assegnate a ogni Microsoft Teams Room abilitata.

| **Scenario** | **Descrizione** | **Microsoft Teams Rooms dell'account del servizio** |
|---------- |------------- | --- |
| Riunioni interattive            | Uso di voce, video e condivisione dello schermo; rendendo il Microsoft Teams Rooms una risorsa prenotabile                     | Abilitato per Microsoft Teams o Skype for Business, abilitato per Exchange (cassetta postale delle risorse) |
| Chiamate in conferenza            | Avere un numero di telefono per i servizi di audioconferenza quando si tocca "Nuova riunione" sulla console | Abilitato per le audioconferenze                                          |
| Chiamate PSTN in uscita/in ingresso | Abilitare la Microsoft Teams Rooms per effettuare e ricevere chiamate PSTN                                         | Abilitato per Sistema telefonico                                                |

Per altre informazioni sugli account Microsoft Teams Rooms, vedere [Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![supporto per scenari.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere quali scenari supportare e identificare i requisiti di licenza per gli account Microsoft Teams Rooms delle risorse.</li></ul>| 
| ![preparare il computer host.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Preparare l'hosting di account di computer e risorse.</li></ul>| 


_Tabella di Microsoft Teams Rooms pianificazione dell'account delle risorse_

| **Sito**  | **Nome della chat room** | **Tipo di chat room** | **Funzionalità future per le chat room**                                                 | **Microsoft Teams Rooms dell'account**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Sede centrale di Londra | Curie         | Media.        | 1 schermo, audio e video più presentazione <br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Exchange (Cassetta postale risorse) <br>Abilitato per le audioconferenze <br>Abilitato per Sistema telefonico |
| Sede centrale di Sydney | Collina          | Grande         | 2 schermi, audio e video più presentazione<br>Accesso ai servizi di conferenza telefonica con accesso esterno<br> Accesso PSTN  | Abilitato per Skype for Business <br>Abilitato per Exchange (Cassetta postale risorse)<br> Abilitato per le audioconferenze <br>Abilitato per Sistema telefonico |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Preparare l'hosting Microsoft Teams Rooms e gli account delle risorse (facoltativo)

Per consentire di gestire e creare report sugli account Microsoft Teams Rooms e sulle risorse, preparare Active Directory locale o Azure Active Directory (Azure AD). 

Definire un gruppo di active directory o Azure Active Directory locale a cui aggiungere Microsoft Teams Rooms account delle risorse. Se si usa Azure Active Directory, è consigliabile usare un gruppo dinamico per aggiungere e rimuovere automaticamente gli account delle risorse dal gruppo.

Definire un'unità organizzativa nella gerarchia di Active Directory locale per contenere tutti gli account computer Microsoft Teams Rooms (se fanno parte del dominio) e un'unità organizzativa per contenere tutti gli account Microsoft Teams Rooms utente. Disabilitare l'ereditarietà dei Criteri di gruppo per assicurarsi di applicare solo i criteri che si intende applicare ai criteri aggiunti al Microsoft Teams Rooms.

Creare un oggetto Criteri di gruppo assegnato all'unità organizzativa che contiene gli account Microsoft Teams Rooms computer. Usare questa opzione per: 

-   [Impostare le impostazioni dell'alimentazione e dell'account locale](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Abilitare Windows aggiorna.
-   Abilitare la comunicazione remota di PowerShell. È possibile configurare uno script di avvio per l'esecuzione di uno script: Enable-PSRemoting -Force

È possibile usare PowerShell per eseguire diverse attività di gestione remota, tra cui il recupero e l'impostazione delle informazioni di configurazione. La comunicazione remota di PowerShell  deve essere abilitata prima di poter eseguire qualsiasi gestione remota di PowerShell e deve essere considerata come parte dei processi di distribuzione o configurata tramite Criteri di gruppo. Per altre informazioni su queste funzionalità e sull'abilitazione, vedere [Manutenzione e operazioni](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configurazione e distribuzione 

La pianificazione della configurazione e della distribuzione riguarda le aree chiave seguenti:

-   Provisioning dell'account delle risorse
-   Installazione del software per dispositivi
-   Distribuzione di dispositivi
-   Microsoft Teams Rooms delle applicazioni e dei dispositivi periferici
-    Test
-   Gestione delle risorse

### <a name="resource-account-provisioning"></a>Provisioning dell'account delle risorse 

Ogni Microsoft Teams Rooms dispositivo richiede un account delle risorse dedicato e univoco che deve essere abilitato sia per Microsoft Teams che per Skype for Business e Exchange. Questo account deve avere una cassetta postale della chat room ospitata Exchange. L'elaborazione del calendario deve essere configurata in modo che il dispositivo possa accettare automaticamente le convocazioni di riunione in arrivo. Per altre informazioni sulla creazione di questi account, vedere [Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md). 

**Pro suggerimento**: ogni Microsoft Teams Rooms deve avere un nome di computer valido e univoco nella rete. Molti sistemi di monitoraggio e avviso visualizzano il nome del computer come identificatore chiave, quindi è importante sviluppare una convenzione di denominazione per le distribuzioni di Microsoft Teams Rooms che consenta al personale di supporto di individuare facilmente il Microsoft Teams Rooms contrassegnato come necessario per un'azione. Un esempio potrebbe essere l'uso di uno schema *MTR-SiteRoom*- *Name* (MTR-LON-CURIE). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![decidere la convenzione di denominazione.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la convenzione di denominazione per gli Microsoft Teams Rooms account delle risorse.</li><li>Decidere se creare singoli account o usare script di provisioning in blocco.</li></ul>| 
| ![passaggi successivi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare la distribuzione del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Installazione del software per dispositivi 

Teams Rooms viene preinstallato dal produttore dell'apparecchiatura originale (OEM).

Vengono fornite indicazioni su come usare [Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) per monitorare la distribuzione Microsoft Teams Rooms e segnalare la disponibilità, gli errori hardware/software e la versione Microsoft Teams Rooms'applicazione. Se si decide di usare Microsoft Operations Management Suite, è consigliabile installare l'agente di Operations Management Suite nell'ambito del processo di installazione del software e configurare le informazioni di connessione dell'area di lavoro per l'area di lavoro. 

Una considerazione aggiuntiva è se il Microsoft Teams Rooms verrà aggiunto al dominio. Informazioni sui vantaggi dell'aggiunta al dominio sono disponibili in [Configurazione di Criteri di gruppo per](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms) Microsoft Teams Rooms. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![denominazione dei dispositivi dei punti decisionali.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere la Microsoft Teams Rooms di denominazione degli account delle risorse da usare durante la distribuzione.</li><li>Decidere se si aggiungeranno Microsoft Teams Rooms dispositivi al dominio. </li><li>Decidere se si userà Monitoraggio di Azure per monitorare la distribuzione Microsoft Teams Rooms distribuzione.</li> 
| ![i passaggi successivi pianificano il dispositivo.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Iniziare a pianificare l'approccio di distribuzione del dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Distribuzione di dispositivi

Dopo aver deciso come creare e manager gli account delle risorse di Microsoft Teams Rooms, creare il piano per spedire i dispositivi e le relative periferiche assegnate alle chat room e quindi procedere con l'installazione e la configurazione.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gestire la distribuzione sito per sito.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere chi gestirà la distribuzione sito per sito.</li><li> Identificare le risorse che installeranno Microsoft Teams Rooms sul sito e intraprendere la configurazione e il test.</li></ul>| 
| ![avviare il test del dispositivo.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Avviare il test del dispositivo.</li></ul>| 

_Tabella di distribuzione di esempio_

| **Sito**  | **Nome della chat room** | **Tipo di chat room** | **Microsoft Teams Rooms sistema**  | **Dispositivi periferici**  | **Microsoft Teams Rooms computer**  | **Microsoft Teams Rooms account della risorsa**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Sede centrale di Londra | Curie         | Media.        |                                   |                  |                                          |                                             |
| Sede centrale di Sydney | Collina          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams Rooms delle applicazioni e dei dispositivi periferici 

Dopo che ogni sistema Microsoft Teams Rooms è stato distribuito fisicamente e le periferiche supportate sono connesse, è necessario configurare l'applicazione Microsoft Teams Rooms per assegnare l'account della risorsa Microsoft Teams Rooms e la password per abilitare Teams Rooms accedere a Microsoft Teams o Skype for Business e Exchange.

È possibile configurare manualmente ogni Microsoft Teams Rooms sistema. In alternativa, è possibile usare un file di configurazione XML archiviato centralmente per Teams Rooms xml per gestire le impostazioni dell'applicazione.

Per altre informazioni su come usare il file di configurazione XML, vedere Gestire le impostazioni di [una console Microsoft Teams Rooms remoto con un file di configurazione XML](xml-config-file.md). 

È possibile usare [PowerShell remoto per](rooms-operations.md#remote-management-using-powershell) estrarre la configurazione Microsoft Teams Rooms per le esigenze di creazione di report. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configurazione del punto di decisione.](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Decidere se configurare manualmente ogni sistema Microsoft Teams Rooms o usare un file XML centrale (uno per Microsoft Teams Rooms dispositivo).</li></ul>| 
| ![prossimo approccio remoto dei passaggi.](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Definire l'approccio di gestione remota.</li></ul>| 

### <a name="testing"></a> Test

Dopo Teams Rooms distribuzione, è consigliabile testarlo. Verificare che le funzionalità elencate nella [Guida Microsoft Teams Rooms](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) funzionino nel dispositivo distribuito. È consigliabile che il team di distribuzione verifichi che Microsoft Teams Rooms visualizzato nell'Teams di amministrazione. È anche importante effettuare una serie di chiamate e riunioni di prova per verificare la qualità. Per altre informazioni, vedere questo utile elenco [di controllo per la distribuzione](console.md#microsoft-teams-rooms-deployment-checklist).

Nell'ambito dell'implementazione generale di Teams o Skype for Business, è consigliabile configurare i file di creazione per Call Quality Dashboard (CQD), monitorare le tendenze qualitative e partecipare al processo di revisione della qualità dell'esperienza. Per altre informazioni, vedere [Migliorare e monitorare la qualità delle chiamate per Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Gestione delle risorse

Nell'ambito della distribuzione, è necessario aggiornare il registro beni con il nome della chat room, il nome Microsoft Teams Rooms, l'account Microsoft Teams Rooms risorsa e i dispositivi periferici assegnati. 

_Tabella delle risorse di esempio_

| **Sito**  | **Nome della chat room** | **Tipo di chat room** | **Microsoft Teams Rooms seriale no.**  | **Periferiche/no seriali./ Porte**  | **Microsoft Teams Rooms computer**  | **Microsoft Teams Rooms di servizio**  | **Data distribuzione** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Sede centrale di Londra | Curie         | Media.        |                                          |                                          |                                          |                                            |                   |
| Sede centrale di Sydney | Collina          | Grande         |                                          |                                          |                                          |                                            |                   |
