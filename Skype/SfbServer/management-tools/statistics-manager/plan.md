---
title: Pianificare il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Riepilogo: leggere questo argomento per informazioni su Gestione statistiche per Skype for Business Server.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816235"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Pianificare il gestore delle statistiche per Skype for Business Server

**Riepilogo:** Leggere questo argomento per informazioni su Gestione statistiche per Skype for Business Server.

 Statistics Manager per Skype for Business Server è un potente strumento che consente di visualizzare in tempo reale i dati di integrità e prestazioni di Skype for Business Server. È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione statistiche.

Puoi usare Gestione statistiche per identificare i problemi di prestazioni in corso, visualizzare i risultati di una modifica pianificata per l'ambiente, tenere traccia della risoluzione delle interruzioni e molto altro ancora. Fuori dalla casella, gestione statistiche è configurato con le soglie di KHI (Key Health Indicator) e può essere personalizzato in base alle esigenze specifiche della distribuzione.

È possibile distribuire Gestione statistiche in una distribuzione locale in cui un singolo server ospita tutti i componenti di gestione statistiche sul lato server. Per altre informazioni sulla distribuzione di gestione statistiche, vedere [distribuire Gestione statistiche per Skype for Business Server](deploy.md). Se si dispone già di una distribuzione esistente di gestione statistiche, ma non è ancora stato eseguito l'aggiornamento alla versione 2,0, vedere [novità di release 2,0](plan.md#BKMK_WhatsNew) e [upgrade Statistics Manager per Skype for Business Server](upgrade.md).

Questo argomento contiene le sezioni seguenti:

- [Caratteristiche e funzionalità](plan.md#BKMK_Features)

- [Novità della versione 2,0](plan.md#BKMK_WhatsNew)

- [Componenti](plan.md#BKMK_Components)

- [Distribuzione locale](plan.md#BKMK_DeploymentOptions)

- [Requisiti](plan.md#BKMK_Requirements)

- [Considerazioni sulla sicurezza](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Caratteristiche e funzionalità
<a name="BKMK_Features"> </a>

Gestione statistiche consente di:

- Visualizzare i dati non elaborati per tutti i server in tempo reale. I dati vengono campionati a un prezzo molto elevato e inviati al sito Web in meno di un secondo.

- Visualizzare i dati aggregati per un ruolo specifico; ad esempio, Front End Server, Mediation Server, Edge Server e così via.

- Eseguire il drill-down per visualizzare i dati per siti specifici, pool specifici all'interno del sito e quindi Server specifici all'interno del pool.

- Creare grafici personalizzati in modo che i contatori scelti vengano visualizzati per impostazione predefinita.

- Eseguire lo zoom e la panoramica sugli assi x e y oppure solo sull'asse x.

- Usare gli intervalli di date o i punti nel tempo per filtrare i dati.

- Visualizzare le prestazioni del server in base agli indicatori di integrità chiave stabiliti (KHIs). KHIs rappresentano una raccolta di contatori delle prestazioni con un intervallo sano definito.

- Visualizzare le metriche dettagliate per ogni contatore.

- Confrontare i dati in più popolazioni o server.

- Visualizzare i report dei contatori latenti per identificare gli agenti che non segnalano i dati correnti al servizio dashboard.

- Salvare una particolare istanza di dati del grafico in un file.

- Visualizzare KHIs in tempo reale, inclusi gli aggiornamenti. Se la visualizzazione cronologia è abilitata, vengono visualizzati solo i nuovi errori.

  - Visualizzare tutti i KHIs in una sola volta

  - Visualizzare KHIs per server (visualizzazione orizzontale)

  - Visualizzare le definizioni di KHI

## <a name="whats-new-in-release-20"></a>Novità della versione 2,0
<a name="BKMK_WhatsNew"> </a>

Di seguito vengono illustrate le novità della versione 2,0. Se si ha una distribuzione esistente di gestione statistiche e non è ancora stato eseguito l'aggiornamento, vedere [aggiornare statistiche Manager per Skype for Business Server](upgrade.md).

- Le visualizzazioni scenario sono state aggiunte per gli scenari Edge media, integrità tessuto, failover del pool e registrazione.

- Sono stati aggiunti molti nuovi contatori per SQL Server, altri contatori per l'utilizzo di Skype for business e così via.

- Integrazione di nodi Watcher per l'agente di gestione statistiche-se l'agente è installato in un nodo Watcher, segnala le statistiche delle transazioni sintetiche come contatori di nuovo in gestione statistiche.

- Numerosi miglioramenti per l'affidabilità e le prestazioni.

Per verificare la versione del sito Web di gestione statistiche in esecuzione:

- In Esplora file aprire (directory predefinita) C:\Program Skype for Business Server stats WebSite\bin

- Fare clic con il pulsante destro del mouse su StatsManHubWebSite. dll e visualizzare le relative proprietà

- La versione del prodotto verrà visualizzata nei dettagli della descrizione.

## <a name="components"></a>Componenti
<a name="BKMK_Components"> </a>

Gestione statistiche è costituito dai componenti seguenti:

- **Agente.** Agente leggero eseguito in ogni server monitorato. L'agente consente il polling a tasso elevato configurabile dei contatori delle prestazioni con l'aggregazione locale.

- **Listener.** API lato server che riceve i dati da tutti gli agenti e aggrega i dati tra le popolazioni.

- **Hub.** Funge da API client per il sistema, viene eseguito sul server Web e consente di aggiornare i dati in tempo reale ai client connessi tramite il sito Web. L'hub viene installato automaticamente come parte del sito Web MSI.

- **Sito Web.** Interfaccia utente che raggruppa tutte le funzionalità disponibili nel sistema.

Inoltre, gestione statistiche richiede **Redis**, un server di struttura dati open-source per la memorizzazione nella cache in memoria. Per altre informazioni sul download di redis, vedere [deploy Statistics Manager](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Distribuzione locale
<a name="BKMK_DeploymentOptions"> </a>

In una distribuzione locale, un singolo server ospita tutti i componenti di gestione statistiche sul lato server.

Il diagramma seguente mostra una distribuzione locale, in cui il sito Web di gestione statistiche, l'hub, il listener e il sistema di Caching Redis sono ospitati in un singolo computer. Statistics Manager sta monitorando tre server Skype for business, ognuno dei quali ha un singolo agente che trasmette i dati al listener. Gli utenti si connettono a un singolo sito Web per visualizzare tutti i dati aggregati da Gestione statistiche:

![Distribuzione locale di stats Manager](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisiti
<a name="BKMK_Requirements"> </a>

Prima di distribuire Gestione statistiche, sarà necessario prendere in considerazione i requisiti software, di rete e hardware seguenti.

### <a name="software-requirements"></a>Requisiti software

- Windows Server 2016 e 2019

- IIS (installazione automatica)

- Redis

- Servizi di gestione statistiche (installati automaticamente)

- PSExec-obbligatorio eseguire la distribuzione di agenti remoti

- .NET 4,5 (incluso con 2012 R2)-obbligatorio per gli agenti e i componenti lato server
- Scaricare [Skype for Business Server, gestione statistiche in tempo reale (64 bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisiti di rete


|**Server di hosting**|**Agenti**|**Listener**|
|:-----|:-----|:-----|
|Minima rete full duplex Gigabit.  <br/> |Porta TCP in uscita 8443 (numero di porta personalizzabile) per comunicare con il listener.  <br/> |La porta del listener deve essere uguale in tutti i server.  <br/> |
|Porta TCP in entrata 80 o 443 aperta per ospitare il sito Web.  <br/> |||
|Porta TCP in entrata 8443 (numero di porta personalizzabile) per gli agenti per comunicare con esso.  <br/> |||

Durante l'installazione, vengono create automaticamente le porte del firewall per il listener e il sito Web. Per gli agenti, l'installazione presuppone che le connessioni TCP in uscita siano consentite per impostazione predefinita.

### <a name="hardware-requirements"></a>Requisiti hardware

In una distribuzione locale, in cui un singolo server ospita tutti i componenti di gestione statistiche lato server, un server con 16 GB di RAM e 4 CPU dovrebbe essere in grado di supportare circa 150 campioni al secondo in media. Per determinare il numero di contatori/agenti che è possibile supportare, usare il calcolo seguente:

100 server \*80 contatori \* 1 campione al minuto da ogni agente/60 secondi = ~ 133 campioni al secondo.

## <a name="security-considerations"></a>Considerazioni sulla sicurezza
<a name="BKMK_Security"> </a>

Tutto il traffico tra i server è crittografato.

- Il traffico HTTPS crittografato verrà inviato tramite la porta 8443 (per impostazione predefinita) dall'agente al server di listener.

- L'agente verificherà l'identificazione personale SSL nel server per verificare che il server di listener sia il destinatario previsto. Tieni presente che l'agente usa la verifica dell'identificazione personale del certificato anziché la verifica della catena. La convalida del certificato non sarà completa perché è possibile usare certificati autofirmati.

- Dopo aver soddisfatto l'agente, il listener è autentico, una password verrà presentata dall'agente che viene quindi verificata dal listener.

- L'agente avvia la trasmissione dei dati sulle prestazioni tramite la connessione al listener.

## <a name="for-more-information"></a>Per altre informazioni
<a name="BKMK_Security"> </a>

Per altre informazioni, vedere quanto segue:

- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)

- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)

- [Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server](troubleshoot.md)
