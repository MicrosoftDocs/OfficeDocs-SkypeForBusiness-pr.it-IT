---
title: Coda Response Group Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Le code di Response Group contengono le chiamate a un Response Group finché un agente non risponde alla chiamata.
ms.openlocfilehash: 194fd2f0660c4aaf8447ff692bf964719ad0b2e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587720"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Coda dei Response Group: crearne una nuova o modificarne una esistente

Le code di Response Group contengono le chiamate a un Response Group finché un agente non risponde alla chiamata.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Ogni coda deve avere un nome. Digitare un nome descrittivo per la coda.

- **Descrizione** Questo campo è facoltativo. Usarlo per specificare ulteriori informazioni sulla coda.

- **Gruppi** Selezionare i gruppi di agenti che si desidera assegnare alla coda. Fare clic su **Seleziona** per aggiungere gruppi di agenti all'elenco. Fare clic su **Rimuovi** per eliminare il gruppo di agenti selezionato dall'elenco.

    Le frecce rivolte verso l'alto e verso il basso spostano un gruppo di agenti selezionato verso l'alto e verso il basso nell'elenco. L'ordine dei gruppi di agenti influisce sull'ordine in Skype for Business Server ricerca di un agente disponibile. In altre parole, viene prima cercato un agente disponibile nel primo gruppo nell'elenco, quindi nel secondo gruppo e così via.

- **Abilitare il timeout della coda** Selezionare questa casella di controllo per specificare un periodo di tempo massimo per cui un chiamante deve attendere il blocco prima che un agente risponde alla chiamata. Se si seleziona questa opzione, è anche necessario specificare quanto segue:

  - **Periodo di timeout (secondi)** Selezionare o digitare il numero massimo di secondi che un chiamante può attendere prima che un agente possa rispondere alla chiamata.

  - **Azione chiamata** Selezionare l'azione che si verifica quando si verifica il timeout di una chiamata. Le opzioni disponibili sono:

  - **Disconnect**

  - **Inoltra alla segreteria telefonica** Se si seleziona questa opzione, in **Indirizzo SIP** digitare un indirizzo del sistema di caselle vocali nel formato sip: <username> @ <domainname> (ad esempio, sip:bob@contoso.com).

  - **Inoltra al numero di telefono** Se si seleziona questa opzione, in **Indirizzo SIP** digitare il numero di telefono nel formato sip: <number> @ <domainname> (ad esempio, sip:+14255550121@contoso.com).

  - **Inoltra a indirizzo SIP** Selezionare questa opzione per inoltrare la chiamata a un altro utente. In **Indirizzo SIP** digitare l'URI dell'utente nel formato sip: <username> @ <domainname> .

  - **Inoltra a un'altra coda** Se si seleziona questa opzione, passare alla coda che deve ricevere le chiamate al timeout delle chiamate.

- **Abilitare l'overflow della coda** Selezionare questa casella di controllo per specificare il numero massimo di chiamate che la coda può contenere. Se si seleziona questa opzione, è anche necessario specificare quanto segue:

  - **Numero massimo di chiamate** Selezionare o digitare il numero massimo di chiamate che la coda può contenere.

  - **Inoltrare la chiamata** Selezionare la chiamata da eseguire quando viene raggiunta la soglia di overflow della coda.

  - **Azione chiamata** Selezionare l'azione che viene eseguita quando viene raggiunta la soglia di overflow della coda. Le opzioni sono:

  - **Disconnect**

  - **Inoltra alla segreteria telefonica** Se si seleziona questa opzione, in **Indirizzo SIP** digitare un indirizzo del sistema di caselle vocali nel formato sip: <username> @ <domainname> (ad esempio, sip:bob@contoso.com).

  - **Inoltra al numero di telefono** Se si seleziona questa opzione, in **Indirizzo SIP** digitare il numero di telefono nel formato sip: <number> @ <domainname> (ad esempio, sip:+14255550121@contoso.com).

  - **Inoltra a indirizzo SIP** Selezionare questa opzione per inoltrare la chiamata a un altro utente. In **Indirizzo SIP** digitare l'URI dell'utente nel formato sip: <username> @ <domainname> .

  - **Inoltra a un'altra coda** Se si seleziona questa opzione, passare alla coda che deve ricevere le chiamate quando viene raggiunta la soglia di overflow della coda.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità di Response Group, vedere [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle code, vedere [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) nella documentazione relativa alle operazioni.