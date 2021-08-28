---
title: Impedire nuove connessioni
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: 2ac97c784f2286a2231a5f20f54aa00daf646384
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600011"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedire nuove connessioni a Skype for Business Server per la manutenzione del server


Skype for Business Server consente di portare offline un server ,ad esempio per applicare aggiornamenti software o hardware, senza alcuna perdita di servizio per gli utenti.

Quando si specifica l'opzione per impedire nuove connessioni o chiamate a un server di un pool, smette di accettare nuove connessioni e chiamate non appena si implementa questa opzione. Le nuove connessioni e le nuove chiamate vengono indirizzate attraverso altri server del pool. Un server che impedisce nuove connessioni consente alle sessioni su connessioni esistenti di continuare fino alla loro fine naturale. Quando tutte le sessioni esistenti sono terminate, il server è pronto per essere portato offline.

Quando si impediscono nuove connessioni a un Front End Server, alcune funzionalità e servizi Skype for Business Server si basano sul bilanciamento del carico DNS per garantire che funzioni correttamente. Se non si utilizza il bilanciamento del carico DNS nel pool, le connessioni tramite questi servizi potrebbero non essere nuovamente instradati ad altri server durante il periodo in cui il server impedisce nuove connessioni e pertanto, quando il server viene portato offline, alcune sessioni e chiamate potrebbero essere interrotte. Le funzionalità che si basano sul bilanciamento del carico DNS per garantire il corretto funzionamento di questa opzione sono le seguenti:

  - Attendant

  - Applicazione Annuncio conferenza

  - Applicazione Response Group

  - Applicazione Annuncio

  - Applicazione Parcheggio di chiamata

Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).

Oltre a impedire nuove connessioni per tutti i servizi in un server che esegue Skype for Business Server, è anche possibile impedire nuove connessioni per singoli Skype for Business Server servizi. Ad esempio, questo metodo è utile in una situazione in cui è necessario applicare un aggiornamento Skype for Business Server che non richiede l'arresto dell'intero server. Si noti che quando si impediscono le connessioni per un servizio, è necessario selezionare un servizio nel modo in cui è raggruppato e visualizzato nell'elenco dei servizi di Windows. Ad esempio, il servizio Skype for Business Server Front-End e l'agente di raccolta dati per il monitoraggio sono servizi Skype for Business Server separati, ma nell'elenco dei servizi di Windows vengono consolidati e visualizzati come servizio front-end di Skype for Business Server. È possibile impedire nuove connessioni per il servizio Skype for Business Server Front End, ma non è possibile impedire nuove connessioni per questi due singoli servizi Skype for Business Server separatamente.

> [!IMPORTANT]
> Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Per impedire nuove connessioni a Skype for Business Server

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Aprire la console snap-in Servizi: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** Strumenti di **amministrazione** e quindi **servizi**.

3.  Nell'elenco fare doppio clic sul servizio Skype for Business Server Windows cui si desidera impedire nuove connessioni.

4.  In **Stato servizio: In sospeso** nella finestra di dialogo Proprietà fare clic su **Pausa**.

5.  Accanto a **Tipo di avvio** fare clic su **Manuale**. Questa operazione è facoltativa, ma consigliata.
    
    > [!IMPORTANT]
    > Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.
