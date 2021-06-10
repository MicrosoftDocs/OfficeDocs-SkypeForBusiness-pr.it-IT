---
title: Criteri di controllo di AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come abilitare l'Teams client desktop con i criteri di controllo dell'applicazione AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120848"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Criteri di controllo dell'applicazione AppLocker in Microsoft Teams

Questo articolo spiega come abilitare l'app client desktop Teams con i criteri di controllo dell'applicazione AppLocker. L'uso di AppLocker è progettato per limitare l'esecuzione di programmi e script da parte di utenti non amministrativi. Per altre informazioni e indicazioni su AppLocker, vedere [Che cos'è AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Il processo per l'abilitazione Teams con AppLocker richiede la creazione di criteri di elenchi consentiti basati su AppLocker. I criteri vengono creati con il software di gestione di Criteri di gruppo e/o l'uso di cmdlet di Windows PowerShell per AppLocker (per altre informazioni, vedere le informazioni di riferimento tecnico su [AppLocker).](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) I criteri di AppLocker vengono salvati in formato XML e possono essere modificati con qualsiasi editor di testo o XML.

## <a name="teams-allow-list-with-applocker"></a>Teams elenco consenti con AppLocker

Le regole di AppLocker sono organizzate in raccolte di regole. Le regole di AppLocker si applicano all'app di destinazione e sono i componenti che costituiscono i criteri di AppLocker.  

Per consentire l Teams, è consigliabile [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) usare le regole delle condizioni dell'autore perché tutti i Teams dell'app sono firmati digitalmente.
  
Non è consigliabile usare regole percorso perché la directory Teams di installazione è scrivibile dall'utente. È anche sconsigliato l'uso di regole hash perché le regole devono essere aggiornate ogni volta che l'app client Teams viene aggiornata.

Poiché Teams file eseguibili desktop sono firmati digitalmente, la condizione dell'autore identifica un file dell'app in base alla firma digitale e agli attributi di versione incorporati. La firma digitale contiene informazioni sulla società che ha creato il file dell'app (l'autore). Le informazioni sulla versione, ottenute dalla risorsa binaria, includono il nome del prodotto di cui fa parte il file e il numero di versione del file dell'applicazione.

### <a name="example-of-publisher-condition-rules"></a>Esempio di regole delle condizioni dell'autore

Per l Teams app client (tutti i file, tutte le versioni) aggiungere quanto segue alle regole eseguibili & DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Argomenti correlati
[Che cos'è AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Informazioni di riferimento tecnico su AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)