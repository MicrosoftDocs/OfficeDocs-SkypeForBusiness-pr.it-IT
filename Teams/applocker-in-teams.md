---
title: Criteri di controllo AppLocker
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
description: Informazioni su come abilitare l'applicazione client desktop di Teams con i criteri di controllo dell'applicazione AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526692"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Criteri di controllo delle applicazioni AppLocker in Microsoft Teams

Questo articolo spiega come abilitare l'app client desktop di Teams con i criteri di controllo delle applicazioni AppLocker. L'uso di AppLocker è progettato per limitare l'esecuzione di programmi e script da parte di utenti non amministrativi. Per altre informazioni e indicazioni su AppLocker, vedere [Che cos'è AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Il processo per abilitare Teams con AppLocker richiede la creazione di criteri di inserimento degli elementi consentiti basati su AppLocker. I criteri vengono creati con il software di gestione di Criteri di gruppo e/o con l'uso di cmdlet di Windows PowerShell per AppLocker (per altre informazioni, vedere il riferimento tecnico su [AppLocker).](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) Il criterio AppLocker viene salvato in formato XML e può essere modificato con qualsiasi editor di testo o XML.

## <a name="teams-allow-list-with-applocker"></a>Elenco di team consentiti con AppLocker

Le regole di AppLocker sono organizzate in raccolte di regole. Le regole di AppLocker si applicano all'app di destinazione e sono i componenti che costituiscono i criteri di AppLocker.  

Per consentire Teams, è consigliabile usare le regole delle condizioni di publisher [perché](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) tutti i file delle app di Teams sono firmati digitalmente.
  
Non è consigliabile usare regole per i percorsi perché la directory di installazione di Teams è scrivibile dall'utente. Non è inoltre consigliato l'uso di regole hash perché è necessario aggiornare le regole ogni volta che si aggiorna l'app client teams.

Poiché i file eseguibili desktop di Teams sono firmati digitalmente, la condizione dell'autore identifica un file dell'app in base alla firma digitale e agli attributi di versione incorporati. La firma digitale contiene informazioni sulla società che ha creato il file dell'app (l'autore). Le informazioni sulla versione, ottenute dalla risorsa binaria, includono il nome del prodotto di cui fa parte il file e il numero di versione del file dell'applicazione.

### <a name="example-of-publisher-condition-rules"></a>Esempio di regole delle condizioni dell'autore

Per l'app client Teams (tutti i file, tutte le versioni) aggiungere quanto segue alle regole eseguibili & DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Argomenti correlati
[Che cos'è AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Informazioni di riferimento tecnico su AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
