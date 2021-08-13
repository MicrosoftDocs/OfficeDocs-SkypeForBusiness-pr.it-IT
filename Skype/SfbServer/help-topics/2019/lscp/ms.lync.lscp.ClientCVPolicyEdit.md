---
title: Criteri versione client Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client.
ms.openlocfilehash: d5bbbca5fcd937d177d839ed48f6feb6fcfc522ce38ddfbb30a013c9bad7392d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325303"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Criteri versione client: crearne di nuovi o modificare quelli esistenti

È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per utilizzare al massimo le funzionalità incluse in Skype for Business Server e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.

> [!IMPORTANT]
> I filtri sono elencati in ordine di precedenza. Se, ad esempio, è presente un filtro che consente ai client che eseguono la versione 1.5 di connettersi, seguito da un filtro che blocca i client che eseguono una versione precedente alla 2.0, il primo filtro ha la precedenza e i client che eseguono la versione 1.5 possono connettersi.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Crea nuovi criteri versione client** o **Modifica Criteri versione client** è possibile eseguire le attività seguenti:

- Aggiungere o modificare il nome o la descrizione dei criteri versione client.

- Aggiungere o modificare le regole per i criteri versione client.

## <a name="ui-reference"></a>Riferimenti UI

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (Sito, Pool o Utente) del criterio versione client.

- **Nome** È possibile aggiungere o modificare il nome del criterio versione client.

- **Descrizione** È possibile aggiungere una descrizione per identificare il criterio nell'elenco nella pagina Criteri versione client.

- **Nuovo** È possibile aggiungere una nuova regola della versione client al criterio.

- **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una regola della versione client.

- **Rimuovi** Questa opzione consente di rimuovere la regola della versione client selezionata dal criterio.

- **Frecce su e giù** Questa opzione sposta la regola della versione client selezionata verso l'alto o verso il basso in base alla priorità. Le regole vengono elaborate nell'ordine in cui sono elencate.

Per informazioni dettagliate sull'interoperabilità tra client e versioni client, vedere [Interoperabilità client](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013). Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) nella documentazione relativa alle operazioni.