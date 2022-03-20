---
title: Indirizzi di emergenza per località remote
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Scopri come Microsoft supporta le informazioni sulla posizione inviabili per supportare le chiamate di emergenza.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d80854fc36e6914ba48e8993d298c75b136bd06f
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660711"
---
# <a name="emergency-addresses-for-remote-locations"></a>Indirizzi di emergenza per località remote

Questo articolo descrive il supporto microsoft per le informazioni sulla posizione delle chiamate di emergenza 911 negli Stati Uniti. Questo supporto assicura che le informazioni sulla posizione dispatchable più precise possibili siano fornite agli utenti Teams chiamate di emergenza. Indipendentemente dalla posizione del chiamante, in sede o da casa, le informazioni sulla posizione di un chiamante inviate al punto di risposta per la sicurezza pubblica (PSAP) devono essere accurate.

Questo articolo include informazioni sulla conformità di Microsoft al RAY BAUM'S Act for Multi Line Telephone Systems (MLTS). Il RAY BAUM'S Act estende i requisiti di legge di Kari, che sono stati in vigore all'inizio del 2021. Per altre informazioni sul Ray BAUM'S Act e sulla legge di Kari, vedere [Dispatchable Location for 911 Calls](https://www.fcc.gov/911-dispatchable-location) and [Multi-line Telephone Systems - Kari's Law e Ray BAUM's Act 911 Direct Dialing, Notification, and Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements). 

Gli utenti che lavorano a casa ora possono impostare i propri indirizzi di emergenza, se applicabile. Questo articolo descrive come configurare i criteri utente in modo che gli utenti finali possano impostare gli indirizzi di emergenza.

Anche se queste informazioni si applicano alle chiamate di emergenza 911 negli Stati Uniti, le località immesse dall'utente verranno comunicate anche al centro di screening in Canada.

Questo articolo contiene le sezioni seguenti:

- [Supporto per informazioni sulla posizione delle chiamate di emergenza](#support-for-emergency-calling-location-information)
- [Precedenza della posizione](#location-precedence)
- [Classificazione e routing degli indirizzi di emergenza](#emergency-address-classification-and-routing)
- [Consentire agli utenti finali di configurare l'indirizzo per gli interventi di emergenza](#enable-end-users-to-configure-their-emergency-address)
- [Note e restrizioni](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Supporto per informazioni sulla posizione delle chiamate di emergenza

Per supportare questi requisiti, Teams i servizi di posizione forniti dal rispettivo sistema operativo per suggerire un indirizzo, se l'amministratore o l'utente ha concesso l'autorizzazione. L'utente finale può confermare la posizione di un indirizzo suggerito, modificarlo o immetterne uno nuovo manualmente. Un indirizzo confermato, modificato o immesso manualmente viene quindi salvato nel client Teams in modo che l'indirizzo confermato dall'utente sia usato automaticamente quando il client è connesso a tale rete. Gli indirizzi salvati dall'utente vengono cancellati automaticamente quando Teams il client viene disconnesso.


## <a name="location-precedence"></a>Precedenza della posizione

Gli indirizzi di emergenza Teams possono essere categorizzati in base a tipi diversi. L'elenco seguente mostra la precedenza della posizione usata quando viene composto un numero di emergenza:

1. Indirizzo acquisito dinamicamente definito dal tenant amministrato nel servizio informazioni sulla posizione.

2. Indirizzo a cui l'utente finale ha confermato, modificato o immesso manualmente un indirizzo associato alla rete locale a cui è connesso Teams client.

3. Indirizzo suggerito automaticamente dal sistema operativo.

4. Indirizzo assegnato in modo statico dall'amministratore all'utente.


## <a name="emergency-address-classification-and-routing"></a>Classificazione e routing degli indirizzi di emergenza

La tabella seguente mostra i tipi di indirizzi di emergenza e i metodi di instradamento associati per ogni tipo: se la chiamata viene instradata automaticamente al PSAP di servizio o se viene schermata per verificarne l'accuratezza prima del trasferimento al PSAP di servizio. Questo comportamento di routing è supportato negli Stati Uniti per tutti gli utenti del piano di chiamata, i Connessione con operatore partner e i provider di servizi di chiamate di emergenza certificati Direct Routing.


| Tipo di indirizzo per gli interventi di emergenza | Metodo di routing per gli interventi di emergenza |
| :------------| :-------|
| Indirizzo di emergenza acquisito dinamicamente definito dall'amministratore. | Diretto a PSAP. |
| Indirizzo di emergenza ottenuto dal sistema operativo senza **conferma dell'accuratezza** da parte dell'utente. | Schermate e trasferite in PSAP. |
| Indirizzo di emergenza ottenuto dal sistema operativo con **conferma per l'accuratezza** da parte dell'utente.| Diretto a PSAP. |
| Indirizzo di emergenza ottenuto dal sistema operativo e modificato e confermato dall'utente. | Schermate e trasferite in PSAP. |
| Indirizzo di emergenza immesso e confermato dall'utente. | Schermate e trasferite in PSAP. |
| Indirizzo di emergenza assegnato staticamente all'utente/numero. | Schermate e trasferite in PSAP. |
| Null | Schermate e trasferite in PSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Consentire agli utenti finali di configurare l'indirizzo per gli interventi di emergenza

Per abilitare questa funzionalità per gli utenti finali, usare il cmdlet di PowerShell New-CsTeamsEmergencyCallingPolicy e impostare il parametro ExternalLocationLookupMode su Abilitato. Vedere l'esempio seguente: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Dopo aver abilitato questa funzionalità per gli utenti finali, nella scheda Chiamate l'utente può aggiungere, modificare o confermare un indirizzo di emergenza e visualizzare l'indirizzo dopo l'impostazione. Per altre informazioni su come gli utenti finali possono impostare i servizi di posizione, vedere Lavorare da [Home Emergency 911: abilitare i servizi di posizione](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

In Windows, è possibile gestire il servizio di posizione Windows e se le applicazioni hanno accesso alla posizione, usando Criteri di gruppo o gestione di dispositivi mobili [(MDM).](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

Per altre informazioni sul servizio Windows posizione, vedere Windows servizio di [posizione e privacy](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Note e restrizioni

Tenere presente quanto segue:

- L'esperienza di lavoro da casa descritta è per Teams desktop in Windows e Mac.

- Teams telefoni non supportano l'esperienza di lavoro da casa.

- Teams mobile supporta il rilevamento automatico della posizione, ma non l'esperienza immessa dall'utente descritta.

- Le impostazioni di privacy possono essere in conflitto con il rilevamento automatico della posizione: è possibile usare sistemi di gestione di dispositivi mobili.


## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)

- [Lavorare da Home Emergency 911: abilitare i servizi di posizione](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

