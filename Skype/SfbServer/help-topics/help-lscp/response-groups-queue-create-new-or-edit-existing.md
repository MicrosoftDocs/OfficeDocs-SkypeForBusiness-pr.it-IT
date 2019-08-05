---
title: Coda di Response Groups creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Le code dei gruppi di risposte contengono le chiamate a un gruppo di risposte finché un agente non risponde alla chiamata.
ms.openlocfilehash: 3eba4fbba662ecc1497b5c8d0aac14ce5083c1ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190403"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Coda dei Response Group: crearne una nuova o modificarne una esistente

Le code dei gruppi di risposte contengono le chiamate a un gruppo di risposte finché un agente non risponde alla chiamata.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Ogni coda deve avere un nome. Digitare un nome descrittivo per la coda.

- **Descrizione** Questo campo è facoltativo. Usarlo per specificare ulteriori informazioni sulla coda.

- **Gruppi** Selezionare i gruppi di agenti che si desidera assegnare alla coda. Fare clic su **Seleziona** per aggiungere gruppi di agenti all'elenco. Fare clic su **Rimuovi** per eliminare il gruppo di agenti selezionato dall'elenco.

    Le frecce rivolte verso l'alto e verso il basso spostano un gruppo di agenti selezionato verso l'alto e verso il basso nell'elenco. L'ordine dei gruppi di agenti influisce sull'ordine in cui Skype for Business Server cerca un agente disponibile. In altre parole, viene prima cercato un agente disponibile nel primo gruppo nell'elenco, quindi nel secondo gruppo e così via.

- **Abilitare il timeout della coda** Selezionare questa casella di controllo per specificare un periodo di tempo massimo per il chiamante in attesa in attesa prima che un agente risponda alla chiamata. Se si seleziona questa opzione, è anche necessario specificare quanto segue:

  - **Periodo di timeout (secondi)** Selezionare o digitare il numero massimo di secondi che il chiamante può attendere prima che un agente risponda alla chiamata.

  - **Azione chiamata** Selezionare l'azione che si verifica quando viene eseguito il timeout di una chiamata. Le opzioni disponibili sono:

  - **Disconnetti**

  - **Inoltra alla** segreteria telefonica Se si seleziona questa opzione, in **indirizzo SIP**Digitare un indirizzo di segreteria telefonica nel formato SIP:<username> @ <domainname> (ad esempio, SIP:bob@contoso.com).

  - **Inoltra al numero di telefono** Se si seleziona questa opzione, in **indirizzo SIP** Digitare il numero di telefono nel formato SIP:<number> @ <domainname> (ad esempio, SIP:+14255550121@contoso.com).

  - **Inoltra all'indirizzo SIP** Selezionare questa opzione per inoltrare la chiamata a un altro utente. In **indirizzo SIP**Digitare l'URI per l'utente nel formato SIP:<username>@<domainname>.

  - **Inoltra a un'altra coda** Se si seleziona questa opzione, passare alla coda che riceverà le chiamate quando il timeout delle chiamate.

- **Abilitare l'overflow delle code** Selezionare questa casella di controllo per specificare un numero massimo di chiamate che la coda può contenere. Se si seleziona questa opzione, è anche necessario specificare quanto segue:

  - **Numero massimo di chiamate** Selezionare o digitare il numero massimo di chiamate che la coda può contenere.

  - **Inoltrare la chiamata** Selezionare la chiamata che consente di intervenire quando viene soddisfatta la soglia di overflow della coda.

  - **Azione chiamata** Selezionare l'azione che si verifica quando viene soddisfatta la soglia di overflow della coda. Le opzioni sono:

  - **Disconnetti**

  - **Inoltra alla** segreteria telefonica Se si seleziona questa opzione, in **indirizzo SIP**Digitare un indirizzo di segreteria telefonica nel formato SIP:<username> @ <domainname> (ad esempio, SIP:bob@contoso.com).

  - **Inoltra al numero di telefono** Se si seleziona questa opzione, in **indirizzo SIP** Digitare il numero di telefono nel formato SIP:<number> @ <domainname> (ad esempio, SIP:+14255550121@contoso.com).

  - **Inoltra all'indirizzo SIP** Selezionare questa opzione per inoltrare la chiamata a un altro utente. In **indirizzo SIP**Digitare l'URI per l'utente nel formato SIP:<username>@<domainname>.

  - **Inoltra a un'altra coda** Se si seleziona questa opzione, passare alla coda che riceve le chiamate quando viene soddisfatta la soglia di overflow della coda.

Per informazioni dettagliate sulle funzionalità e le caratteristiche dei gruppi di risposta, vedere [pianificare l'applicazione Response Group in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle code, vedere [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) nella documentazione relativa alle operazioni.


