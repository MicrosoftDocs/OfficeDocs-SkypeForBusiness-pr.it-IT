---
title: Regola versione client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: I criteri versione client sono composti da una serie di regole versione client, che definiscono le azioni che dovrebbero essere eseguite quando gli utenti tentano di eseguire l'accesso con specifici client o versioni client.
ms.openlocfilehash: ab67f926f7a2e0ddc91f33bc9657d8fd4104e3a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195188"
---
# <a name="client-version-rule"></a>Regola versione client

I criteri versione client sono composti da una serie di regole versione client, che definiscono le azioni che dovrebbero essere eseguite quando gli utenti tentano di eseguire l'accesso con specifici client o versioni client.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:

- Aggiungere nuove regole a un criterio versione client.

- Modificare le regole che costituiscono un criterio versione client esistente

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Agente utente** Puoi selezionare un tipo di client nell'elenco. Nella tabella seguente vengono definiti i codici agente utente. Questo elenco include i tipi di client legacy, alcuni dei quali non sono più supportati.

|**Nome client**|**Agente utente**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator Phone  <br/> |OCPhone  <br/> |
|Piattaforma Communicator Phone Edition  <br/> |CPE  <br/> |
|Piattaforma Unified Communications  <br/> |UCCP  <br/> |
|Partecipante Lync 2010  <br/> |AOC  <br/> |
|Componente aggiuntivo Live Meeting  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client di comunicazione in tempo reale  <br/> |RTC  <br/> |
|Lync 2010 per iPad  <br/> |iPadLync  <br/> |
|Lync 2010 per iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 per Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 per Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 per Android  <br/> |AndroidLync  <br/> |
|Servizio Dispositivi mobili  <br/> |McxService  <br/> |

- **Numero di versione** Puoi specificare i numeri di versione per i campi seguenti oppure usare i caratteri jolly per indicare il numero di versione del client.

  - **Versione principale** Specifica il numero corrispondente alla versione principale del client.

  - **Versione secondaria** Specifica il numero corrispondente al rilascio secondario del client.

  - **Compilazione** Specifica il numero di build che corrisponde alla versione principale e secondaria del client.

  - **Aggiornamento** Specifica il numero corrispondente alla versione aggiornata del client.

- **Operazione di confronto** Puoi specificare l'operazione di corrispondenza per la versione client specificata nei passaggi precedenti. Sono disponibili le operazioni seguenti:

  - **Corrispondente a**

  - **Diverso da**

  - **Più recente di**

  - **Più recente di o corrispondente a**

  - **Meno recente di**

  - **Meno recente di o corrispondente a**

- **Azione** È possibile specificare l'azione da eseguire quando si soddisfano i criteri nei passaggi precedenti. Sono disponibili le azioni seguenti:

  - **Consenti** Consente al client di accedere.

  - **Consenti e aggiorna** Consente al client di accedere e ricevere gli aggiornamenti da Windows Server Update Service o Microsoft Update. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.

    > [!NOTE]
    > Selezionando questa azione, la notifica verrà visualizzata la volta successiva che gli utenti accederanno a Skype for business. Tale notifica comunica la disponibilità di un aggiornamento, anche se non sono stati ancora rilasciati aggiornamenti per Windows Server Update Service o per Microsoft Update. Per evitare confusione, scegliere questa azione solo dopo che gli aggiornamenti vengono resi disponibili.

  - **Consenti con URL** Consente al client di accedere e visualizza un messaggio che indica dove scaricare un'altra versione client. L'URL viene specificato nel campo **URL**.

  - **Blocco** Impedisce l'accesso al client.

  - **Bloccare e aggiornare** Impedisce al client di eseguire l'accesso e consente al client di ricevere gli aggiornamenti da Windows Server Update Service o Microsoft Update. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.

  - **Blocca con URL** Impedisce al client di eseguire l'accesso e visualizza un messaggio sulla posizione da cui scaricare un'altra versione client. L'URL viene specificato nel campo **URL**.

Per informazioni dettagliate sull'interoperabilità tra client e versioni client, vedere interoperabilità [client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) nella documentazione relativa alle operazioni.

