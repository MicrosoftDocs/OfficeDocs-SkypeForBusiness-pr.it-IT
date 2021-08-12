---
title: Response Group Crea nuovo o Modifica gruppo di agenti esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: I gruppi di agenti definiscono quali utenti possono rispondere alle chiamate a un Response Group (anche definito agenti) e le impostazioni che si applicano a tutti gli agenti del gruppo.
ms.openlocfilehash: 732aef1d5c4e6c23fc084e8f178705888d1fec0ef938f5aeef65eb250b48f42b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54291564"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Response Group: creare un nuovo gruppo di agenti o modificarne uno esistente

I gruppi di agenti definiscono quali utenti possono rispondere alle chiamate a un Response Group (anche definito agenti) e le impostazioni che si applicano a tutti gli agenti del gruppo.

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Ogni gruppo di agenti richiede un nome univoco. Utilizzare un nome descrittivo che identifichi la funzione del gruppo. Ad esempio, Help Desk.

- **Descrizione** Questo campo è facoltativo. Usarlo per fornire maggiori dettagli sul gruppo.

- **Criteri di partecipazione** Specificare la modalità di accesso degli agenti al Response Group:

  - Selezionare **Informale** per specificare che gli agenti del gruppo non devono accedere e disconnettersi. Gli agenti informali vengono connessi automaticamente all'accesso. L'impostazione predefinita è **Informale**.

  - Selezionare **Formal** per specificare che gli agenti del gruppo devono accedere e disconnettersi. Quando si seleziona questa opzione, gli agenti selezionano una voce di menu nel client per aprire un browser e visualizzare una console della pagina Web per l'accesso e la disconnessione.

- **Tempo di avviso (secondi)** Specificare il numero di secondi di squillo di un agente prima di offrire la chiamata al successivo agente disponibile. Il valore deve essere compreso tra 10 e 180 secondi. Il valore predefinito è 20 secondi.

- **Routing, metodo** Selezionare il metodo per determinare l'ordine in cui gli agenti ricevono le chiamate:

  - Selezionare **Inattività più lunga** per inoltrare una nuova chiamata prima all'agente che è stato inattivo (ha avuto una presenza **Disponibile** o **Inattivo**) più a lungo.

  - Per inoltrare una nuova chiamata a tutti gli agenti disponibili contemporaneamente, selezionare **Parallelo**. La chiamata verrà inviata al primo agente che la accetta.

  - Per inoltrare una nuova chiamata a ogni agente a turno, selezionare **Round robin**.

  - Per inoltrare sempre una nuova chiamata agli agenti in base all'ordine con cui sono elencati nell'elenco **Agente**, selezionare **Seriale**.

  - Selezionare **Operatore** per offrire una nuova chiamata a tutti gli agenti che hanno eseguito l'accesso e all'applicazione Response Group contemporaneamente, indipendentemente dalla presenza corrente. Gli operatori e gli utenti client configurati come agenti possono visualizzare tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine. La chiamata viene inviata al primo agente che la accetta e gli altri operatori e utenti non vedono più la chiamata.

- **Agenti** Selezionare gli utenti che devono essere agenti per il Response Group in uno dei modi seguenti:

  - Selezionare **Usa una lista di distribuzione di posta elettronica esistente** per usare una Exchange di distribuzione. Immettere l'indirizzo di posta elettronica della lista di distribuzione in **Indirizzo lista di distribuzione**.

    > [!NOTE]
    > È possibile selezionare solo una lista di distribuzione per ogni gruppo di agenti e, se tale lista include liste di distribuzione nidificate, queste ultime non verranno incluse nel gruppo di agenti.

    > [!NOTE]
    > L'ordine in cui sono elencati gli agenti nella lista di distribuzione determina l'ordine in cui riceveranno le chiamate per il routing di tipo round robin e seriale.

    > [!NOTE]
    > Le appartenenze nascoste o gli elenchi nascosti potrebbero diventare visibili agli amministratori o agli utenti di Response Group. Per informazioni dettagliate, vedere [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Selezionare **Definisci un gruppo di agenti personalizzato** per selezionare gli utenti da assegnare come agenti per il Response Group. Fare clic su **Seleziona** per aggiungere un agente all'elenco oppure su **Rimuovi** per eliminare un agente selezionato dall'elenco.

    Le frecce su e giù consentono di spostare un agente selezionato verso l'alto e verso il basso nell'elenco di agenti. L'ordine degli agenti nell'elenco determina l'ordine in cui ricevono le chiamate per il routing di tipo round robin e seriale.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità di [Response Group,](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) vedere Plan for the Response Group application in Skype for Business Server nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei gruppi di agenti, vedere [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) nella documentazione relativa alle operazioni.