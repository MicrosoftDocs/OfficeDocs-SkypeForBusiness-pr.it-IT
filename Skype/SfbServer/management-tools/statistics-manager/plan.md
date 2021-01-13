---
title: Pianificare il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Riepilogo: leggere questo argomento per informazioni sulla gestione delle statistiche per Skype for Business Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821826"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Pianificare il gestore delle statistiche per Skype for Business Server

**Riepilogo:** Leggere questo argomento per informazioni su gestione delle statistiche per Skype for Business Server.

 La gestione delle statistiche per Skype for Business Server è uno strumento potente che consente di visualizzare i dati di integrità e prestazioni di Skype for Business Server in tempo reale. È possibile eseguire il polling dei dati delle prestazioni tra centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione delle statistiche.

È possibile utilizzare Gestione statistiche per identificare i problemi di prestazioni in esecuzione, visualizzare i risultati di una modifica pianificata per l'ambiente, monitorare la risoluzione delle interruzioni e molto altro ancora. Fuori dalla casella, gestione statistiche è configurato con le soglie di indicatore di integrità chiave (KHI) e può essere personalizzato in base alle esigenze specifiche della distribuzione.

È possibile distribuire Gestione statistiche in una distribuzione locale in cui un singolo server ospita tutti i componenti di gestione delle statistiche sul server. Per ulteriori informazioni sulla distribuzione di gestione statistiche, vedere [deploy Statistics Manager for Skype for Business Server](deploy.md). Se si dispone già di una distribuzione di gestione delle statistiche esistente, ma non è ancora stato eseguito l'aggiornamento alla versione 2,0, vedere [What ' s New in release 2,0](plan.md#BKMK_WhatsNew) e [upgrade Statistics Manager for Skype for Business Server](upgrade.md).

In questa sezione sono contenute le seguenti sezioni:

- [Caratteristiche e funzionalità](plan.md#BKMK_Features)

- [Novità della versione 2,0](plan.md#BKMK_WhatsNew)

- [Componenti](plan.md#BKMK_Components)

- [Distribuzione in locale](plan.md#BKMK_DeploymentOptions)

- [Requisiti](plan.md#BKMK_Requirements)

- [Considerazioni sulla sicurezza](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Caratteristiche e funzionalità
<a name="BKMK_Features"> </a>

Gestione statistiche consente di:

- Visualizzare i dati non elaborati per tutti i server in tempo reale. I dati vengono campionati a una velocità molto elevata e inviati al sito Web in meno di un secondo.

- Visualizzare i dati aggregati per un ruolo specifico. ad esempio, Front End Server, Mediation Server, Edge Server e così via.

- Eseguire il drill-down per visualizzare i dati relativi a siti specifici, pool specifici all'interno del sito e quindi Server specifici all'interno del pool.

- Creare grafici personalizzati in modo che i contatori scelti vengano visualizzati per impostazione predefinita.

- Eseguire lo zoom e la panoramica sugli assi x e y o solo sull'asse x.

- Utilizzare gli intervalli di date o i punti nel tempo per filtrare i dati.

- Visualizzare le prestazioni del server in base a indicatori di integrità chiave stabiliti (KHIs). KHIs rappresenta un insieme di contatori delle prestazioni con un intervallo integro definito.

- Visualizzare le metriche dettagliate per ogni contatore.

- Confrontare i dati tra più popolazioni o server.

- Visualizzare i report dei contatori latenti per identificare gli agenti che non segnalano i dati correnti al servizio dashboard.

- Salvare una determinata istanza di dati del grafico in un file.

- Visualizzare KHIs in tempo reale, inclusi gli aggiornamenti. Se la visualizzazione cronologia è abilitata, vengono visualizzati solo i nuovi errori.

  - Visualizzazione di tutti i KHIs in una sola volta

  - Visualizzazione di KHIs per server (visualizzazione orizzontale)

  - Visualizzazione delle definizioni di KHI

## <a name="whats-new-in-release-20"></a>Novità della versione 2,0
<a name="BKMK_WhatsNew"> </a>

Di seguito vengono descritte le novità della versione 2,0. Se si dispone di una distribuzione esistente di gestione statistiche e non è ancora stato eseguito l'aggiornamento, vedere [upgrade Statistics Manager for Skype for Business Server](upgrade.md).

- Sono state aggiunte visualizzazioni dello scenario per i supporti perimetrali, l'integrità dei tessuti, il failover del pool e gli scenari di registrazione.

- Sono stati aggiunti numerosi nuovi contatori per SQL Server, più contatori di utilizzo di Skype for business e così via.

- Integrazione dei nodi Watcher per l'agente di gestione delle statistiche-se l'agente è installato in un nodo Watcher, riporterà le statistiche sulle transazioni sintetiche come contatori di nuovo in gestione statistiche.

- Numerosi miglioramenti relativi a prestazioni e affidabilità.

Per verificare la versione del sito Web di gestione delle statistiche in esecuzione:

- In Esplora file aprire (directory predefinita) C:\Program Skype for Business Server stats WebSite\bin

- Fare clic con il pulsante destro del mouse su StatsManHubWebSite.dll e visualizzare le proprietà

- La versione del prodotto verrà visualizzata nei dettagli della descrizione.

## <a name="components"></a>Componenti
<a name="BKMK_Components"> </a>

Gestione statistiche è costituito dai componenti seguenti:

- **Agente.** Agente Lightweight che viene eseguito in ogni server monitorato. L'agente consente il polling ad alta velocità configurabile dei contatori delle prestazioni con l'aggregazione locale.

- **Listener.** API lato server che riceve i dati da tutti gli agenti e aggrega i dati tra le popolazioni.

- **Hub.** Funge da API client per il sistema, viene eseguito nei server Web e fornisce aggiornamenti dei dati in tempo reale ai client connessi tramite il sito Web. (L'hub viene installato automaticamente come parte del sito Web MSI).

- **Sito Web.** Interfaccia utente che unisce tutte le funzionalità disponibili nel sistema.

Inoltre, gestione statistiche richiede **ReDim**, un server di struttura dati open source per la memorizzazione nella cache in memoria. Per ulteriori informazioni sul download delle redini, vedere [deploy Statistics Manager](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Distribuzione in locale
<a name="BKMK_DeploymentOptions"> </a>

In una distribuzione locale, un singolo server ospita tutti i componenti di gestione delle statistiche sul server.

Nel diagramma seguente viene illustrata una distribuzione locale, in cui il sito Web di gestione delle statistiche, l'hub, l'ascoltatore e il sistema di memorizzazione nella cache di ReDim sono ospitati in un singolo computer. Gestione statistiche sta monitorando tre server Skype for business, ognuno dei quali ha un singolo agente per la trasmissione dei dati al listener. Gli utenti si connettono a un singolo sito Web per visualizzare tutti i dati aggregati da Gestione statistiche:

![Distribuzione in locale di stats Manager](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisiti
<a name="BKMK_Requirements"> </a>

Prima di distribuire Gestione statistiche, è necessario prendere in considerazione i seguenti requisiti software, di rete e hardware.

### <a name="software-requirements"></a>Requisiti software

- Windows Server 2016 e 2019

- IIS (installazione automatica)

- Redis

- Servizi di gestione delle statistiche (installati automaticamente)

- PSExec-obbligatorio per la distribuzione di agenti remoti

- .NET 4,5 (incluso con 2012 R2)-obbligatorio per gli agenti e i componenti sul server
- Scaricare il [Server Skype for business, Real-Time gestione delle statistiche (64 bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisiti di rete


|**Server di hosting**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Minima rete Gigabit full duplex.  <br/> |Porta TCP in uscita 8443 (numero di porta personalizzabile) per comunicare con il listener.  <br/> |La porta del listener deve essere la stessa su tutti i server.  <br/> |
|La porta TCP in ingresso 80 o 443 aperta per ospitare il sito Web.  <br/> |||
|Porta TCP in ingresso 8443 (numero di porta personalizzabile) per gli agenti per comunicare con esso.  <br/> |||

Durante l'installazione, vengono create automaticamente le porte del firewall per il listener e il sito Web. Per gli agenti, l'installazione presuppone che le connessioni TCP in uscita siano consentite per impostazione predefinita.

### <a name="hardware-requirements"></a>Requisiti hardware

In una distribuzione locale, in cui un singolo server ospita tutti i componenti di gestione delle statistiche sul server, un server con 16 GB di RAM e 4 CPU dovrebbe essere in grado di supportare circa 150 campioni al secondo in media. Per determinare il numero di contatori/agenti che è possibile supportare, utilizzare il calcolo seguente:

100 server \* 80 contatori \* 1 campione al minuto da ogni agente/60 secondi = ~ 133 campioni al secondo.

## <a name="security-considerations"></a>Considerazioni sulla sicurezza
<a name="BKMK_Security"> </a>

Tutto il traffico tra i server è crittografato.

- Il traffico HTTPS crittografato verrà inviato tramite la porta 8443 (per impostazione predefinita) dall'agente al server listener.

- L'agente verificherà l'identificazione personale SSL sul server per assicurarsi che il server listener sia il destinatario previsto. Si noti che l'agente utilizza la verifica dell'identificazione personale del certificato (anziché la verifica della catena). La convalida del certificato non sarà completa perché è possibile utilizzare certificati autofirmati.

- Dopo che l'agente è stato soddisfatto, il listener è autentico, una password verrà presentata dall'agente che viene quindi verificata dal listener.

- L'agente inizia a trasmettere i dati sulle prestazioni tramite la connessione al listener.

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Security"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:

- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)

- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)

- [Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server](troubleshoot.md)
