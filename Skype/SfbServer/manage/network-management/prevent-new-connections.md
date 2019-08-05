---
title: Impedire nuove connessioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188549"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Prevenzione di nuove connessioni a Skype for Business Server per la manutenzione del server


Skype for Business Server consente di prendere un server offline (ad esempio, per applicare aggiornamenti software o hardware) senza perdita di servizio agli utenti.

Quando si specifica l'opzione per impedire le nuove connessioni o le chiamate a un server in un pool, smette di accettare nuove connessioni e chiamate non appena si implementa questa opzione. Queste nuove connessioni e chiamate vengono instradate tramite altri server nel pool. Un server che impedisce le nuove connessioni consente di continuare le sessioni sulle connessioni esistenti finché non terminano naturalmente. Quando tutte le sessioni esistenti sono terminate, il server è pronto per essere preso offline.

Quando si impediscono nuove connessioni a un server front-end, alcune caratteristiche e servizi di Skype for Business Server si basano sul bilanciamento del carico DNS per verificare che funzioni correttamente. Se non si usa il bilanciamento del carico DNS sul pool, le connessioni tramite questi servizi potrebbero non essere reindirizzate ad altri server durante il periodo in cui il server impedisce le nuove connessioni e quindi quando il server viene disconnesso alcune sessioni e le chiamate possono essere interrotti. Le caratteristiche che si basano sul bilanciamento del carico DNS per verificare che questa opzione funzioni correttamente sono le seguenti:

  - Operatore

  - Applicazione per l'annuncio di conferenza

  - Response Group Application

  - Applicazione annuncio

  - Applicazione Parcheggio di chiamata

Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [requisiti di bilanciamento del carico](../../plan-your-deployment/network-requirements/load-balancing.md).

Oltre a impedire nuove connessioni per tutti i servizi in un server che gestisce Skype for Business Server, puoi anche evitare nuove connessioni per i singoli servizi di Skype for Business Server. Ad esempio, questo metodo è utile in una situazione in cui è necessario applicare un aggiornamento di Skype for Business Server che non richiede l'arresto dell'intero server. Si noti che quando si impediscono le connessioni per un servizio, è necessario selezionare un servizio mentre viene raggruppato e visualizzato nell'elenco di servizi di Windows. Ad esempio, il servizio front-end di Skype for Business Server e l'agente di raccolta dati per il monitoraggio sono servizi distinti per Skype for Business Server, ma nell'elenco dei servizi Windows vengono consolidati e visualizzati come front-end di Skype for Business Server servizio. Puoi impedire le nuove connessioni per il servizio front-end di Skype for Business Server, ma non puoi impedire le nuove connessioni per questi due singoli servizi Skype for Business Server separatamente.

> [!IMPORTANT]
> Quando si imposta un server per impedire nuove connessioni e quindi riavviare il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitare questo problema, imposta il server solo per sospendere e riprendere manualmente, prima di riavviare il server.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Per evitare nuove connessioni a Skype for Business Server

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Aprire la console snap-in Servizi: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Servizi**.

3.  Nell'elenco fare doppio clic sul servizio Windows Skype for Business Server a cui si vogliono impedire le nuove connessioni.

4.  Nella finestra di dialogo Proprietà, in **stato del servizio: avviato**, **** fare clic su Sospendi.

5.  Facoltativamente, ma consigliato, accanto a **tipo di avvio**, fare clic su **manuale**.
    
    > [!IMPORTANT]
    > Quando si imposta un server per impedire nuove connessioni e quindi riavviare il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitare questo problema, imposta il server solo per sospendere e riprendere manualmente, prima di riavviare il server.
