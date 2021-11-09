---
title: Criteri delle versioni client
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.
ms.openlocfilehash: 89547442d432f25cc132a296328fe27f734be402
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846649"
---
# <a name="client-version-policy"></a>Criteri delle versioni client

È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina Criteri versione **client** è possibile eseguire le attività seguenti:

- Modificare il criterio predefinito ( **Globale**) della versione client.

- Creare criteri versione client per un sito o un pool specifico.

- Creare criteri versione client che possono essere assegnati a singoli utenti.

> [!NOTE]
> Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.

## <a name="ui-reference"></a>Riferimenti UI

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Nuovo** È possibile creare uno o più dei criteri di versione client seguenti:

  - Criterio sito

  - Criteri pool

  - Criteri utente

- **Modifica** È possibile modificare le opzioni di uno qualsiasi dei criteri delle versioni client. Usando questa voce, è possibile scegliere tra le opzioni seguenti:

  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per un criterio versione client.

  - **Seleziona tutto** Questa opzione consente di selezionare tutti i criteri delle versioni client nell'elenco.

  - **Elimina** Questa opzione consente di eliminare tutti i criteri di versione client selezionati.

- **Aggiorna** È possibile aggiornare l'elenco dei criteri versione client per verificare lo stato delle opzioni di tutti i criteri versione client.

Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) nella documentazione relativa alle operazioni.