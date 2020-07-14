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
description: Informazioni su come abilitare l'applicazione client teams desktop con i criteri di controllo dell'applicazione AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cbccede3ca2d114b7bffa81b669a06a519f6b4e6
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121666"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Criteri di controllo delle applicazioni di AppLocker in Microsoft Teams

Questo articolo spiega come abilitare l'app client desktop teams con i criteri di controllo dell'applicazione AppLocker. L'uso di AppLocker è progettato per limitare l'esecuzione di programmi e script da parte di utenti non amministrativi. Per altre informazioni e indicazioni su AppLocker, vedere [che cos'è AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Il processo per l'attivazione di teams con AppLocker richiede la creazione di criteri di whitelist basati su AppLocker. I criteri vengono creati con il software di gestione di criteri di gruppo e/o l'uso dei cmdlet di Windows PowerShell per AppLocker (per altre informazioni, vedere la [documentazione di riferimento tecnico di AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) ). I criteri di AppLocker vengono salvati in formato XML e possono essere modificati con qualsiasi testo o editor XML.

## <a name="teams-whitelisting-with-applocker"></a>Whitelist delle squadre con AppLocker

Le regole di AppLocker sono organizzate in insiemi di regole. Le regole di AppLocker si applicano all'app di destinazione e sono i componenti che costituiscono i criteri di AppLocker.  

Per i team whitelist, ti consigliamo di usare le [regole della condizione di Publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , poiché tutti i file dell'app teams sono firmati digitalmente.
  
Non è consigliabile usare le regole di percorso perché la directory di installazione di teams è scrivibile dall'utente. Non è inoltre consigliabile usare le regole hash perché le regole devono essere aggiornate ogni volta che viene aggiornata l'app client teams.

Dato che i file eseguibili desktop di teams sono firmati digitalmente, la condizione di Publisher identifica un file dell'app in base alla firma digitale e agli attributi della versione incorporata. La firma digitale contiene informazioni sulla società che ha creato il file dell'app (l'editore). Le informazioni sulla versione, ottenute dalla risorsa binaria, includono il nome del prodotto in cui il file fa parte e il numero di versione del file dell'applicazione.

### <a name="example-of-publisher-condition-rules"></a>Esempio di regole della condizione di Publisher

Per l'app client Teams (tutti i file, tutte le versioni) aggiungere quanto segue alle regole eseguibili & regole della DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Argomenti correlati
[Che cos'è AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 Informazioni di [riferimento tecnico su AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
