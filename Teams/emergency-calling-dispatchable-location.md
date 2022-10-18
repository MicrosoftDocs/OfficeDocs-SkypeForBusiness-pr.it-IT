---
title: Indirizzi di emergenza per posizioni remote
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
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Scopri come Microsoft supporta le informazioni sulla posizione inviabili per supportare le chiamate di emergenza.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d7fd3111991c4a2e5e0d16e5d46aba411b1553c3
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584579"
---
# <a name="emergency-addresses-for-remote-locations"></a>Indirizzi di emergenza per posizioni remote

Questo articolo descrive il supporto di Microsoft per le informazioni sulla posizione delle chiamate di emergenza 911 nel Stati Uniti. Questo supporto garantisce che le informazioni sulla posizione di emergenza più precise possibili vengano fornite agli utenti di Teams che effettuano chiamate di emergenza. Indipendentemente dalla posizione del chiamante, in loco o da casa, le informazioni sulla posizione del chiamante inviate al PSAP (Public Safety Answering Point) devono essere accurate.

Questo articolo include informazioni sulla conformità di Microsoft alla legge RAY BAUM per i sistemi mlts (Multi Line Telephone Systems). La legge RAY BAUM estende i requisiti di Legge di Kari, entrati in vigore all'inizio del 2021. Per ulteriori informazioni sulla LEGGE DI RAY BAUM e sulla Legge Kari, vedi [Località di recapito per 911 chiamate](https://www.fcc.gov/911-dispatchable-location) e [sistemi telefonici multiriga - Legge di Kari e Ray BAUM's Act 911 Direct Dialing, Notification, and Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements). 

Gli utenti che lavorano a casa possono ora impostare il proprio indirizzo per gli interventi di emergenza, se applicabile. Questo articolo descrive come configurare i criteri utente in modo che gli utenti finali possano impostare gli indirizzi per gli interventi di emergenza.

Anche se queste informazioni si applicano alle chiamate di emergenza 911 nel Stati Uniti, le posizioni immesse dall'utente verranno comunicate anche al centro di screening in Canada.

Questo articolo contiene le sezioni seguenti:

- [Supporto per le informazioni sulla posizione delle chiamate di emergenza](#support-for-emergency-calling-location-information)
- [Precedenza delle posizioni](#location-precedence)
- [Classificazione e instradamento degli indirizzi di emergenza](#emergency-address-classification-and-routing)
- [Consentire agli utenti finali di configurare l'indirizzo per gli interventi di emergenza](#enable-end-users-to-configure-their-emergency-address)
- [Note e restrizioni](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Supporto per le informazioni sulla posizione delle chiamate di emergenza

Per supportare questi requisiti, Teams usa i servizi di posizione forniti dal rispettivo sistema operativo per suggerire un indirizzo, se concesso dall'amministratore o dall'utente. L'utente finale può confermare la posizione di un indirizzo suggerito, modificarlo o immetterne manualmente uno nuovo. Un indirizzo confermato, modificato o immesso manualmente viene quindi salvato nel client di Teams in modo che l'indirizzo confermato dall'utente venga utilizzato automaticamente quando il client è connesso a tale rete. Gli indirizzi salvati dall'utente vengono cancellati automaticamente quando il client Teams viene disconnesse.


## <a name="location-precedence"></a>Precedenza delle posizioni

Gli indirizzi di emergenza per Teams possono essere classificati in base a diversi tipi. L'elenco seguente mostra la precedenza delle posizioni utilizzata per la chiamata di un numero di emergenza:

1. Indirizzo acquisito dinamicamente definito dal tenant che amministra nel servizio informazioni sulla posizione.

2. Indirizzo a cui l'utente finale ha confermato, modificato o immesso manualmente e che è associato alla rete locale a cui è connesso il client Teams.

3. Un indirizzo suggerito automaticamente dal sistema operativo.

4. Un indirizzo che l'amministratore assegna staticamente all'utente.


## <a name="emergency-address-classification-and-routing"></a>Classificazione e instradamento degli indirizzi di emergenza

La tabella seguente mostra i tipi di indirizzi per gli interventi di emergenza e i metodi di routing associati per ogni tipo: se la chiamata viene automaticamente instradata al PSAP che serve o schermata per accuratezza prima del trasferimento al PSAP che serve. Questo comportamento di routing è supportato nel Stati Uniti per tutti gli utenti del piano per chiamate, i partner Operator Connect e i provider di servizi di chiamata di emergenza certificati per Direct Routing.


| Tipo di indirizzo per gli interventi di emergenza | Metodo di instradamento di emergenza |
| :------------| :-------|
| Indirizzo di emergenza acquisito dinamicamente, definito dall'amministratore. | Diretto al PSAP. |
| Indirizzo di emergenza ottenuto dal sistema operativo **senza conferma dell'accuratezza** da parte dell'utente. | Schermate e trasferite al PSAP. |
| Indirizzo di emergenza ottenuto dal sistema operativo **con conferma dell'accuratezza** da parte dell'utente.| Diretto al PSAP. |
| Indirizzo di emergenza ottenuto dal sistema operativo e modificato e confermato dall'utente. | Schermate e trasferite al PSAP. |
| Indirizzo di emergenza immesso e confermato dall'utente. | Schermate e trasferite al PSAP. |
| Indirizzo di emergenza assegnato staticamente all'utente/numero. | Schermate e trasferite al PSAP. |
| Null | Schermate e trasferite al PSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Consentire agli utenti finali di configurare l'indirizzo per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Criteri di emergenza** **vocale** > .
2. Selezionare **Aggiungi**.
3. Immetti un nome per i criteri per le chiamate di emergenza, ad esempio "E911WFH".
4. Attivare la **modalità di ricerca della posizione esterna**.
5. Selezionare **Applica**.

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Assegnare criteri personalizzati per le chiamate di emergenza agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>Utilizzo di PowerShell

Per abilitare questa funzionalità per gli utenti finali, usare il cmdlet New-CsTeamsEmergencyCallingPolicy PowerShell e impostare il parametro ExternalLocationLookupMode su Enabled. Vedere l'esempio seguente: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Dopo aver abilitato questa funzionalità per gli utenti finali, nella scheda Chiamate l'utente può aggiungere, modificare o confermare un indirizzo per gli interventi di emergenza e visualizzare l'indirizzo dopo averlo impostato. Per altre informazioni su come gli utenti finali possono impostare i servizi di posizione, vedi [Emergenza domestica 911: abilitare i servizi di posizione](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

In Windows è possibile gestire il servizio di posizione di Windows e verificare se le applicazioni hanno accesso alla posizione, tramite Criteri di gruppo o tramite [gestione di dispositivi mobili](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation).

Per altre informazioni sui servizi di posizione di Windows, vedi [Servizi di posizione di Windows e privacy](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Note e restrizioni

Tenere presente quanto segue:

- L'esperienza di lavoro da casa descritta è per teams desktop su Windows e Mac.

- I telefoni di Teams non supportano l'esperienza di lavoro da casa.

- Teams Mobile supporta il rilevamento automatico della posizione, ma non l'esperienza immessa dall'utente descritta.

- Le impostazioni di privacy possono essere in conflitto con il rilevamento automatico della posizione: è possibile usare sistemi di Gestione dispositivi per dispositivi mobili.


## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)

- [Lavoro da casa Emergenza 911: abilitare i servizi di posizione](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

