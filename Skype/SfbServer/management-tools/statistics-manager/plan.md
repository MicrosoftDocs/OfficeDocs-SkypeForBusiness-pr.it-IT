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
description: 'Riepilogo: leggere questo argomento per informazioni su Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821826"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Pianificare il gestore delle statistiche per Skype for Business Server

**Riepilogo:** Leggere questo argomento per informazioni su Statistics Manager per Skype for Business Server.

 Statistics Manager per Skype for Business Server è uno strumento potente che consente di visualizzare i dati sulle prestazioni e sull'integrità di Skype for Business Server in tempo reale. È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare immediatamente i risultati nel sito Web di Gestione statistiche.

È possibile utilizzare Gestione statistiche per identificare i problemi di prestazioni in corso, visualizzare i risultati di una modifica pianificata all'ambiente, tenere traccia della risoluzione delle interruzioni e molto altro ancora. Gestione statistiche è configurato con soglie KHI (Key Health Indicator) e può essere personalizzato in base alle esigenze specifiche della distribuzione.

È possibile distribuire Gestione statistiche in una distribuzione locale in cui un singolo server ospita tutti i componenti di Gestione statistiche sul lato server. Per ulteriori informazioni sulla distribuzione di Gestione statistiche, vedere [Distribuire Gestione statistiche per Skype for Business Server.](deploy.md) Se si dispone già di una distribuzione esistente di Gestione statistiche, ma non si è ancora eseguito l'aggiornamento alla versione 2.0, vedere Novità della [versione 2.0](plan.md#BKMK_WhatsNew) e Gestione statistiche di aggiornamento per [Skype for Business Server.](upgrade.md)

In questa sezione sono contenute le seguenti sezioni:

- [Caratteristiche e funzionalità](plan.md#BKMK_Features)

- [Novità della versione 2.0](plan.md#BKMK_WhatsNew)

- [Componenti](plan.md#BKMK_Components)

- [Distribuzione in locale](plan.md#BKMK_DeploymentOptions)

- [Requisiti](plan.md#BKMK_Requirements)

- [Considerazioni sulla sicurezza](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Caratteristiche e funzionalità
<a name="BKMK_Features"> </a>

Gestione statistiche consente di:

- Visualizzare i dati non elaborati per tutti i server in tempo reale. I dati vengono campionati a una velocità molto elevata e inviati al sito Web in meno di un secondo.

- Visualizzare i dati aggregati per un ruolo specifico; ad esempio Front End Server, Mediation Server, Server perimetrale e così via.

- Eseguire il drill-down per visualizzare i dati per siti specifici, pool specifici all'interno del sito e quindi server specifici all'interno del pool.

- Creare grafici personalizzati in modo che i contatori scelti siano visualizzati per impostazione predefinita.

- Eseguire lo zoom e la panoramica sugli assi x e y o solo sull'asse x.

- Utilizzare intervalli di date o punti nel tempo per filtrare i dati.

- Visualizzare le prestazioni del server in base agli indicatori di integrità chiave (KHI) stabiliti. Gli indicatori KHI rappresentano una raccolta di contatori delle prestazioni con un intervallo integro definito.

- Visualizzare metriche dettagliate per ogni contatore.

- Confrontare i dati tra più popolazioni o server.

- Visualizzare i rapporti dei contatori latenti per identificare gli agenti che non segnalano i dati correnti al servizio dashboard.

- Salvare una particolare istanza dei dati del grafico in un file.

- Visualizzare gli KHI in tempo reale, inclusi gli aggiornamenti. Se la visualizzazione cronologia è abilitata, vengono visualizzati solo i nuovi errori.

  - Visualizzare tutti gli KHI contemporaneamente

  - Visualizzare gli KHI per server (visualizzazione orizzontale)

  - Visualizzare le definizioni KHI

## <a name="whats-new-in-release-20"></a>Novità della versione 2.0
<a name="BKMK_WhatsNew"> </a>

Di seguito vengono descritte le novità della versione 2.0. Se si dispone di una distribuzione esistente di Gestione statistiche e non si è ancora eseguito l'aggiornamento, vedere [Upgrade Statistics Manager per Skype for Business Server.](upgrade.md)

- Sono state aggiunte visualizzazioni dello scenario per gli scenari di server perimetrali, integrità dell'infrastruttura, failover del pool e registrazione.

- Sono stati aggiunti molti nuovi contatori per SQL server, più contatori di utilizzo di Skype for Business e così via.

- Integrazione del nodo Watcher per l'agente di gestione delle statistiche: se l'agente è installato in un nodo Watcher, le statistiche delle transazioni sintetiche verranno segnalate come contatori a Gestione statistiche.

- Numerosi miglioramenti a livello di affidabilità e prestazioni.

Per verificare la versione del sito Web Gestione statistiche in esecuzione:

- In Esplora file apri (directory predefinita) C:\Programmi\Skype for Business Server StatsMan WebSite\bin

- Fai clic con il pulsante destro del StatsManHubWebSite.dll e visualizzane le proprietà

- La versione del prodotto verrà visualizzata nei dettagli della descrizione.

## <a name="components"></a>Componenti
<a name="BKMK_Components"> </a>

Gestione statistiche è costituito dai componenti seguenti:

- **Agente.** Un agente leggero che viene eseguito su ogni server monitorato. L'agente consente il polling ad alta velocità configurabile dei contatori delle prestazioni con aggregazione locale.

- **Listener.** L'API sul lato server che riceve i dati da tutti gli agenti e aggrega i dati tra più popolazioni.

- **Hub.** Funge da API client per il sistema, viene eseguito nei server Web e fornisce aggiornamenti dei dati in tempo reale ai client connessi tramite il sito Web. L'hub viene installato automaticamente come parte del file msi del sito Web.

- **Sito Web.** Interfaccia utente che riunisce tutte le funzionalità disponibili nel sistema.

Gestione statistiche richiede inoltre **Redis,** un server di struttura dei dati open source per la memorizzazione nella cache in memoria. Per ulteriori informazioni sul download di Redis, vedere [Deploy Statistics Manager.](deploy.md#BKMK_Deploy)

## <a name="on-premises-deployment"></a>Distribuzione in locale
<a name="BKMK_DeploymentOptions"> </a>

In una distribuzione locale, un singolo server ospita tutti i componenti di Gestione statistiche sul lato server.

Il diagramma seguente mostra una distribuzione locale, in cui il sito Web, l'hub, il listener e il sistema di memorizzazione nella cache di Gestione statistiche sono ospitati in un singolo computer. Gestione statistiche monitora tre server Skype for Business, ognuno dei quali dispone di un singolo agente che trasmette i dati al listener. Gli utenti si connettono a un singolo sito Web per visualizzare tutti i dati aggregati da Gestione statistiche:

![Distribuzione locale di Stats Manager](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Requisiti
<a name="BKMK_Requirements"> </a>

Prima di distribuire Gestione statistiche, è necessario considerare i requisiti software, di rete e hardware seguenti.

### <a name="software-requirements"></a>Requisiti software

- Windows Server 2016 e 2019

- IIS (installato automaticamente)

- Redis

- Servizi di Gestione statistiche (installati automaticamente)

- PSExec - Necessario per eseguire la distribuzione degli agenti remoti

- .NET 4.5 (incluso in 2012 R2) - Obbligatorio per agenti e componenti sul lato server
- Scaricare [Skype for Business Server, Real-Time Statistics Manager (64 bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Requisiti di rete


|**Server di hosting**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Rete full duplex minima gigabit.  <br/> |Porta TCP in uscita 8443 (numero di porta personalizzabile) per comunicare con il listener.  <br/> |La porta del listener deve essere la stessa in tutti i server.  <br/> |
|La porta TCP in ingresso 80 o 443 si apre per ospitare il sito Web.  <br/> |||
|Porta TCP in ingresso 8443 (numero di porta personalizzabile) per comunicare con gli agenti.  <br/> |||

Durante l'installazione, le porte del firewall per il listener e il sito Web vengono create automaticamente. Per gli agenti, l'installazione presuppone che le connessioni TCP in uscita siano consentite per impostazione predefinita.

### <a name="hardware-requirements"></a>Requisiti hardware

In una distribuzione locale, in cui un singolo server ospita tutti i componenti di Gestione statistiche sul lato server, un server con 16 GB di RAM e 4 CPU dovrebbe essere in grado di supportare in media circa 150 campioni al secondo. Per determinare il numero di contatori/agenti che è possibile supportare, utilizzare il calcolo seguente:

100 server \* 80 \* contatori 1 campione al minuto da ogni agente / 60 secondi = ~ 133 campioni al secondo.

## <a name="security-considerations"></a>Considerazioni sulla sicurezza
<a name="BKMK_Security"> </a>

Tutto il traffico tra i server è crittografato.

- Il traffico HTTPS crittografato verrà inviato sulla porta 8443 (per impostazione predefinita) dall'agente al server listener.

- L'agente verificherà l'identificazione personale SSL sul server per verificare che il server listener sia il destinatario previsto. Si noti che l'agente usa la verifica dell'identificazione personale del certificato (anziché la verifica della catena). Non verrà eseguita la convalida completa del certificato perché è possibile utilizzare certificati autofirmati.

- Una volta che l'agente è soddisfatto che il listener è autentico, verrà presentata una password dall'agente che viene quindi verificato dal listener.

- L'agente inizia a trasmettere i dati sulle prestazioni tramite la connessione al listener.

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Security"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:

- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)

- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)

- [Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server](troubleshoot.md)
