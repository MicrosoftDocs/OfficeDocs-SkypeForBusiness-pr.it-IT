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
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823466"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Impedire nuove connessioni a Skype for Business Server per la manutenzione del server


Skype for Business Server consente di portare offline un server (ad esempio, per applicare aggiornamenti software o hardware) senza alcuna perdita di servizio per gli utenti.

Quando si specifica l'opzione per impedire nuove connessioni o chiamate a un server di un pool, smette di accettare nuove connessioni e chiamate non appena si implementa questa opzione. Le nuove connessioni e le nuove chiamate vengono indirizzate attraverso altri server del pool. Un server che impedisce nuove connessioni consente alle sessioni su connessioni esistenti di continuare fino alla loro fine naturale. Quando tutte le sessioni esistenti sono terminate, il server è pronto per essere portato offline.

Quando si impediscono nuove connessioni a un Front End Server, alcune funzionalità e servizi di Skype for Business Server si basano sul bilanciamento del carico DNS per garantire il corretto funzionamento. Se non si utilizza il bilanciamento del carico DNS nel pool, le connessioni tramite questi servizi potrebbero non essere instradati nuovamente ad altri server durante il periodo in cui il server impedisce nuove connessioni e pertanto, quando il server viene portato offline, alcune sessioni e chiamate potrebbero essere interrotte. Le funzionalità che si basano sul bilanciamento del carico DNS per garantire il corretto funzionamento di questa opzione sono le seguenti:

  - Attendant

  - Applicazione Annuncio conferenza

  - Applicazione Response Group

  - Applicazione Annuncio

  - Applicazione Parcheggio di chiamata

Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [Load balancing requirements.](../../plan-your-deployment/network-requirements/load-balancing.md)

Oltre a impedire nuove connessioni per tutti i servizi in un server che esegue Skype for Business Server, è anche possibile impedire nuove connessioni per i singoli servizi di Skype for Business Server. Ad esempio, questo metodo è utile in una situazione in cui è necessario applicare un aggiornamento di Skype for Business Server che non richiede l'arresto dell'intero server. Si noti che quando si impediscono le connessioni per un servizio, è necessario selezionare un servizio nel modo in cui è raggruppato e visualizzato nell'elenco dei servizi di Windows. Ad esempio, il servizio Front-End di Skype for Business Server e l'agente di raccolta dati per il monitoraggio sono servizi Skype for Business Server separati, ma nell'elenco dei servizi di Windows vengono consolidati e visualizzati come servizio Front End di Skype for Business Server. È possibile impedire nuove connessioni per il servizio Front End di Skype for Business Server, ma non è possibile impedire nuove connessioni per questi due singoli servizi Skype for Business Server sottostanti separatamente.

> [!IMPORTANT]
> Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Per impedire nuove connessioni a Skype for Business Server

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Aprire la console snap-in Servizi: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** Strumenti di **amministrazione** e quindi **Servizi.**

3.  Nell'elenco, fare doppio clic sul servizio Windows di Skype for Business Server a cui si desidera impedire nuove connessioni.

4.  In **Stato servizio: In sospeso** nella finestra di dialogo Proprietà fare clic su **Pausa**.

5.  Accanto a **Tipo di avvio** fare clic su **Manuale**. Questa operazione è facoltativa, ma consigliata.
    
    > [!IMPORTANT]
    > Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.
