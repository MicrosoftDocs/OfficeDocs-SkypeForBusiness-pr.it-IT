---
title: I criteri di versione client creano nuovi o modificano esistenti
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
ms.openlocfilehash: c2d6dc4f68a7c40668db9042d420f2f341e35ca0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824896"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Criteri versione client: crearne di nuovi o modificare quelli esistenti

È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per sfruttare al meglio le funzionalità incluse in Skype for Business Server e per migliorare l'esperienza complessiva degli utenti, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.

> [!IMPORTANT]
> I filtri sono elencati in ordine di precedenza. Se, ad esempio, è presente un filtro che consente ai client che eseguono la versione 1.5 di connettersi, seguito da un filtro che blocca i client che eseguono una versione precedente alla 2.0, il primo filtro ha la precedenza e i client che eseguono la versione 1.5 possono connettersi.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Crea nuovi criteri versione client** o **Modifica Criteri versione client** è possibile eseguire le attività seguenti:

- Aggiungere o modificare il nome o la descrizione dei criteri versione client.

- Aggiungere o modificare le regole per i criteri versione client.

## <a name="ui-reference"></a>Riferimenti UI

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (sito, pool o utente) dei criteri versione client.

- **Nome** È possibile aggiungere o modificare il nome dei criteri versione client.

- **Descrizione/Controlli** È possibile aggiungere una descrizione per identificare i criteri nell'elenco nella pagina Criteri versione client.

- **Nuovo** È possibile aggiungere una nuova regola versione client al criterio.

- **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una regola versione client.

- **Rimuovi** Questa opzione consente di rimuovere la regola di versione client selezionata dal criterio.

- **Frecce verso l'alto e verso il basso** Questa opzione consente di spostare in alto o in basso la regola della versione client selezionata. Le regole vengono elaborate nell'ordine in cui sono elencate.

Per informazioni dettagliate sull'interoperabilità tra client e versioni client, vedere [interoperabilità client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) nella documentazione relativa alle operazioni.

