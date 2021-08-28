---
title: Regola versione client
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
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: I criteri versione client sono composti da una serie di regole versione client, che definiscono le azioni che dovrebbero essere eseguite quando gli utenti tentano di eseguire l'accesso con specifici client o versioni client.
ms.openlocfilehash: 5f952c1a1c04e98a2635876d3746e828a086daf9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609543"
---
# <a name="client-version-rule"></a>Regola versione client

I criteri versione client sono composti da una serie di regole versione client, che definiscono le azioni che dovrebbero essere eseguite quando gli utenti tentano di eseguire l'accesso con specifici client o versioni client.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:

- Aggiungere nuove regole a un criterio versione client.

- Modificare le regole che costituiscono un criterio versione client esistente

## <a name="ui-reference"></a>Informazioni sull'interfaccia utente

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Agente utente** È possibile selezionare un tipo di client dall'elenco. Nella tabella seguente vengono definiti i codici agente utente.

|**Nome client**|**Agente utente**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Telefono Edition, Office Communicator Telefono  <br/> |OCPhone  <br/> |
|Piattaforma Communicator Phone Edition  <br/> |CPE  <br/> |
|Piattaforma Unified Communications  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
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

- **Numero di versione** È possibile specificare i numeri di versione per i campi seguenti oppure utilizzare caratteri jolly per indicare il numero di versione del client.

  - **Versione principale** Specifica il numero corrispondente alla versione principale del client.

  - **Versione secondaria** Specifica il numero corrispondente alla versione secondaria del client.

  - **Build** Specifica il numero di build corrispondente alla versione principale e secondaria del client.

  - **Aggiornamento** Specifica il numero corrispondente alla versione aggiornata del client.

- **Operazione di confronto** È possibile specificare l'operazione di corrispondenza per la versione client specificata nei passaggi precedenti. Sono disponibili le operazioni seguenti:

  - **Corrispondente a**

  - **Diverso da**

  - **Più recente di**

  - **Più recente di o corrispondente a**

  - **Meno recente di**

  - **Meno recente di o corrispondente a**

- **Azione** È possibile specificare l'azione da eseguire quando vengono soddisfatti i criteri nei passaggi precedenti. Sono disponibili le azioni seguenti:

  - **Consenti** Consente al client di accedere.

  - **Consenti e aggiorna** Consente al client di accedere e ricevere aggiornamenti da Windows Server Update Service o Microsoft Update. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.

    > [!NOTE]
    > Se si seleziona questa azione, viene visualizzata una notifica al successivo accesso degli utenti Skype for Business. La notifica indica che è disponibile un aggiornamento, anche se non sono stati ancora rilasciati aggiornamenti per Windows Server Update Service o Microsoft Update. Per evitare confusione, è consigliabile scegliere questa azione solo quando vengono resi disponibili gli aggiornamenti.

  - **Consenti con URL** Consente al client di eseguire l'accesso e visualizza un messaggio che indica dove scaricare un'altra versione client. L'URL viene specificato nel campo **URL**.

  - **Blocco** Impedisce al client di accedere.

  - **Blocco e aggiornamento** Impedisce al client di eseguire l'accesso e consente al client di ricevere gli aggiornamenti da Windows Server Update Service o Microsoft Update. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.

  - **Blocca con URL** Impedisce al client di eseguire l'accesso e visualizza un messaggio sulla posizione da cui scaricare un'altra versione client. L'URL viene specificato nel campo **URL**.

Per informazioni dettagliate sull'interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di configurazioni della versione client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) nella documentazione relativa alle operazioni.