---
title: Criteri versione client Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nel proprio ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.
ms.openlocfilehash: db463896426d8919776ba21532bbac04415c526d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829516"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Criteri versione client: crearne di nuovi o modificare quelli esistenti

È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nel proprio ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.

> [!IMPORTANT]
> I filtri sono elencati in ordine di precedenza. Se, ad esempio, è presente un filtro che consente ai client che eseguono la versione 1.5 di connettersi, seguito da un filtro che blocca i client che eseguono una versione precedente alla 2.0, il primo filtro ha la precedenza e i client che eseguono la versione 1.5 possono connettersi.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Crea nuovi criteri versione client** o **Modifica Criteri versione client** è possibile eseguire le attività seguenti:

- Aggiungere o modificare il nome o la descrizione dei criteri versione client.

- Aggiungere o modificare le regole per i criteri versione client.

## <a name="ui-reference"></a>Riferimenti UI

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (sito, pool o utente) dei criteri versione client.

- **Name** È possibile aggiungere o modificare il nome dei criteri versione client.

- **Descrizione** È possibile aggiungere una descrizione per identificare il criterio nell'elenco nella pagina Criteri versione client.

- **Nuovo** È possibile aggiungere una nuova regola della versione client al criterio.

- **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una regola della versione client.

- **Rimuovi** Questa opzione consente di rimuovere la regola della versione client selezionata dal criterio.

- **Frecce su e giù** Questa opzione sposta la regola della versione client selezionata verso l'alto o verso il basso in ordine di priorità. Le regole vengono elaborate nell'ordine in cui sono elencate.

Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) nella documentazione relativa alle operazioni.

