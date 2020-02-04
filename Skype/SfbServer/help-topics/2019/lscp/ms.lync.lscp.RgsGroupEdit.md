---
title: Gruppi di risposte creare nuovi o modificare il gruppo di agenti esistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: I gruppi di agenti definiscono quali utenti possono rispondere alle chiamate a un Response Group (anche definito agenti) e le impostazioni che si applicano a tutti gli agenti del gruppo.
ms.openlocfilehash: 2fde88426c659492cff350007b7e88a53581c67d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690911"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Response Group: creare un nuovo gruppo di agenti o modificarne uno esistente

I gruppi di agenti definiscono quali utenti possono rispondere alle chiamate a un Response Group (anche definito agenti) e le impostazioni che si applicano a tutti gli agenti del gruppo.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Ogni gruppo di agenti richiede un nome univoco. Usa un nome descrittivo che identifichi la funzione del gruppo. Ad esempio, help desk.

- **Descrizione** Questo campo è facoltativo. Usarlo per fornire maggiori dettagli sul gruppo.

- **Criteri di partecipazione** Specificare il modo in cui gli agenti devono eseguire l'accesso al gruppo di risposte:

  - Selezionare **Informale** per specificare che gli agenti del gruppo non devono connettersi e disconnettersi dal gruppo. L'accesso al gruppo viene eseguito automaticamente quando gli agenti informali accedono. L'impostazione predefinita è **Informale**.

  - Selezionare **formale** per specificare che gli agenti del gruppo devono accedere e disconnettersi. Quando si seleziona questa opzione, gli agenti fanno clic su una voce di menu nel client per aprire un browser e visualizzare una console per la pagina Web per l'accesso e la disconnessione.

- **Tempo di avviso (secondi)** Specificare il numero di secondi per chiamare un agente prima di offrire la chiamata al successivo agente disponibile. Il valore deve essere compreso tra 10 e 180 secondi. Il valore predefinito è 20 secondi.

- **Metodo di routing** Selezionare il metodo per determinare l'ordine in cui gli agenti ricevono chiamate:

  - Selezionare **Inattività più lunga** per inoltrare una nuova chiamata prima all'agente che è stato inattivo (ha avuto una presenza **Disponibile** o **Inattivo**) più a lungo.

  - Per inoltrare una nuova chiamata a tutti gli agenti disponibili contemporaneamente, selezionare **Parallelo**. La chiamata verrà inviata al primo agente che la accetta.

  - Per inoltrare una nuova chiamata a ogni agente a turno, selezionare **Round robin**.

  - Per inoltrare sempre una nuova chiamata agli agenti in base all'ordine con cui sono elencati nell'elenco **Agente**, selezionare **Seriale**.

  - Selezionare **Attendant** per offrire una nuova chiamata a tutti gli agenti che hanno effettuato l'accesso e l'applicazione Response Group contemporaneamente, indipendentemente dalla presenza corrente. Gli addetti e gli utenti client configurati come agenti possono vedere tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine. La chiamata viene inviata al primo agente che la accetta e gli altri operatori e utenti non la visualizzeranno più.

- **Agenti** Selezionare gli utenti che devono essere agenti per il gruppo di risposte in uno dei modi seguenti:

  - Selezionare **Usa una lista di distribuzione di posta elettronica esistente** per usare una lista di distribuzione di Exchange. Immettere l'indirizzo di posta elettronica della lista di distribuzione in **Indirizzo lista di distribuzione**.

    > [!NOTE]
    > È possibile selezionare solo una lista di distribuzione per ogni gruppo di agenti e, se tale lista include liste di distribuzione nidificate, queste ultime non verranno incluse nel gruppo di agenti.

    > [!NOTE]
    > L'ordine in cui sono elencati gli agenti nella lista di distribuzione determina l'ordine in cui riceveranno le chiamate per il routing di tipo round robin e seriale.

    > [!NOTE]
    > Le appartenenze nascoste o gli elenchi nascosti potrebbero diventare visibili per gli amministratori o gli utenti di Response Group. Per informazioni dettagliate, vedere [creare o modificare un gruppo di agenti in Skype for business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Selezionare **Definisci un gruppo di agenti personalizzato** per selezionare gli utenti da assegnare come agenti per il Response Group. Fare clic su **Seleziona** per aggiungere un agente all'elenco oppure su **Rimuovi** per eliminare un agente selezionato dall'elenco.

    Le frecce su e giù consentono di spostare un agente selezionato verso l'alto e verso il basso nell'elenco di agenti. L'ordine degli agenti nell'elenco determina l'ordine in cui ricevono le chiamate per il routing di tipo round robin e seriale.

Per informazioni dettagliate sulle funzionalità e le caratteristiche dei gruppi di risposta, vedere [pianificare l'applicazione Response Group in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei gruppi di agenti, vedere [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) nella documentazione relativa alle operazioni.


