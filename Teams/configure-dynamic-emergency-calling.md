---
title: Configurare chiamate di emergenza dinamiche
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurare chiamate di emergenza dinamiche
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "37639484"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>Pianificare e configurare chiamate di emergenza dinamiche per i piani di chiamata
Le chiamate di emergenza dinamiche per i piani per le chiamate Microsoft offrono la possibilità di configurare e instradare telefonate di emergenza in base alla posizione corrente del client teams.  La possibilità di eseguire il routing automatico al punto di risposta di sicurezza pubblica appropriato (PSAP) o di informare il personale del servizio di sicurezza varia a seconda del paese di utilizzo dell'utente teams.  

> [!Note] 
> Le chiamate di emergenza dinamiche sono attualmente disponibili solo negli Stati Uniti. La notifica di Security desk, tuttavia, è supportata in tutti i confini nazionali.

**All'interno degli Stati Uniti**è possibile configurare il routing dinamico delle chiamate di emergenza come indicato di seguito:
  
- Se un client teams si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza provenienti da tale client vengono automaticamente indirizzate al PSAP che serve tale posizione geografica.  

- Se un client teams non si trova in una posizione di emergenza dinamica definita dall'inquilino, le chiamate di emergenza provenienti da tale client vengono visualizzate da un Call Center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP al servizio della posizione geografica.

È possibile configurare la notifica di Security desk come indicato di seguito:

- Se un client teams si trova in un sito di rete definito dal tenant, verranno comunicati i membri del gruppo di sicurezza configurati per il sito.

- Se un client teams non si trova in un sito di rete definito dal tenant, verranno comunicati i membri del gruppo di sicurezza configurati per l'utente.

Al **di fuori degli Stati Uniti**, le chiamate di emergenza vengono instradate al PSAP mappato al numero di telefono assegnato all'utente.  Alcuni paesi, ad esempio la Gran Bretagna e il Canada, schermano le chiamate a livello nazionale prima di trasferire il chiamante all'appropriato PSAP, mentre altri si instradano direttamente al PSAP indipendentemente dalla posizione in cui si trova attualmente l'utente. 

Tieni presente che puoi configurare la notifica di Security desk dinamico per tutti gli utenti del piano chiamante.


## <a name="supported-clients"></a>Client supportati

I client seguenti sono attualmente supportati.  Controlla spesso per vedere gli aggiornamenti di questo elenco.

- Client desktop teams per Windows
- Client desktop teams per Mac

## <a name="configure-dynamic-emergency-calling"></a>Configurare chiamate di emergenza dinamiche

Per configurare le chiamate di emergenza dinamiche, è necessario eseguire le attività seguenti:

- [Configurare gli indirizzi di emergenza](#configure-emergency-addresses)
- [Configurare le impostazioni di rete](#configure-network-settings)
- [Configurare il servizio informazioni sulla posizione](#configure-location-information-service)
- [Configurare i criteri di emergenza](#configure-emergency-policies)
- [Abilitare utenti e siti](#enable-users-and-sites)
- [Verificare le chiamate di emergenza](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>Configurare gli indirizzi di emergenza

Per supportare il routing automatizzato negli Stati Uniti, è necessario configurare completamente l'indirizzo civico che fa parte delle posizioni di emergenza assegnate agli identificatori di rete e includere i codici Geo associati. Gli indirizzi di emergenza senza Geo-codici non possono essere assegnati agli identificatori di rete necessari per le posizioni dinamiche.

- Se si immette un indirizzo di emergenza tramite l'interfaccia di amministrazione di Microsoft teams, i codici Geo vengono automaticamente inclusi se viene trovata una corrispondenza.

- Se non viene trovata automaticamente una corrispondenza, si avrà la possibilità di creare manualmente un indirizzo di emergenza.  

Questo significa che se è configurato un indirizzo di emergenza esistente per le chiamate di emergenza, è necessario ricreare lo stesso indirizzo per includere i codici Geo.  Per distinguere tra i due indirizzi, è necessario includere una descrizione diversa. Il nuovo indirizzo di emergenza può essere assegnato agli utenti che hanno l'indirizzo precedente. Quando è stata eseguita la migrazione completa, è possibile eliminare l'indirizzo precedente. 

Per altre informazioni sulla configurazione degli indirizzi di emergenza, vedere [quali sono le posizioni di emergenza, i luoghi e il routing delle chiamate?](what-are-emergency-locations-addresses-and-call-routing.md).

### <a name="configure-network-settings"></a>Configurare le impostazioni di rete

È necessario configurare le impostazioni di rete per ottenere in modo dinamico un percorso di emergenza usato per il routing delle chiamate di emergenza e, facoltativamente, per garantire la configurazione dinamica delle notifiche di Security desk. L'esperienza di chiamata in caso di emergenza desiderata indicherà quali impostazioni di rete devono essere configurate. 

Tieni presente le definizioni seguenti:

- Gli IP attendibili contengono una raccolta di indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. I percorsi dinamici verranno abilitati solo se l'IP esterno dell'utente corrisponde a un IP nella raccolta IP attendibile.  Una corrispondenza può essere eseguita in base agli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete.

- Un'area di rete contiene una raccolta di siti di rete. 

- Un sito di rete rappresenta un percorso in cui l'organizzazione ha un valore fisico, ad esempio un ufficio, un set di edifici o un campus. Questi siti sono definiti come una raccolta di subnet IP.

- Una subnet di rete deve essere associata a un sito di rete specifico. La posizione di un cliente viene determinata in base alla subnet della rete e al sito di rete associato.  


Per gli utenti del piano chiamante:

- Se è necessaria la configurazione dinamica della notifica del servizio di sicurezza, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili. 

- Se non sono necessarie, la configurazione delle impostazioni di rete non è obbligatoria. 

Per altre informazioni, vedere [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md), che descrive come configurare le impostazioni di rete. Le informazioni contenute in questo articolo sono valide sia per i piani di chiamata che per il routing diretto.


### <a name="configure-location-information-service"></a>Configurare il servizio informazioni sulla posizione

Un client teams ottiene gli indirizzi di emergenza dai percorsi di emergenza associati a identificatori di rete diversi.  Le subnet e i punti di accesso wireless sono entrambi supportati. Il supporto per switch/porta Ethernet è in sospeso.

Per configurare il servizio LIS (Location Information Service) con gli identificatori di rete e le posizioni di emergenza, usare i cmdlet seguenti:

- Ottieni, imposta, Rimuovi-CsOnlineLisPort
- Ottieni, imposta, Rimuovi-CsOnlineLisSwitch
- Ottieni, imposta, Rimuovi-CsOnlineLisSubnet
- Ottieni, imposta, Rimuovi-CsOnlineLisWirelessAccessPoint 

> [!Important] 
> Se le subnet vengono usate come parte dei siti di rete, devono essere ridefinite nel servizio informazioni sulla posizione per il rendering di posizioni dinamiche.


### <a name="configure-emergency-policies"></a>Configurare i criteri di emergenza

I criteri di emergenza determinano cosa succede quando un utente dell'organizzazione effettua una chiamata di emergenza.  Puoi impostare gli utenti che notificano e come vengono informati quando un utente chiama i servizi di emergenza. Ad esempio, è possibile configurare le impostazioni dei criteri per comunicare automaticamente al banco di sicurezza dell'organizzazione e farli ascoltare in caso di chiamate di emergenza.

Puoi gestire i criteri di emergenza usando i cmdlet New-, set-e Grant-CsTeamsEmergencyCalling Policy.  Per altre informazioni, vedere [gestire i criteri per le chiamate di emergenza in teams](manage-emergency-calling-policies.md).


### <a name="enable-users-and-sites"></a>Abilitare utenti e siti

Quando gli utenti del piano chiamante vengono abilitati automaticamente per le chiamate di emergenza, è necessario abilitare gli utenti per la notifica del servizio di sicurezza configurando il criterio delle chiamate di emergenza, come illustrato nell'esempio seguente:


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

È anche possibile assegnare i criteri delle chiamate di emergenza a un sito di rete, come illustrato nell'esempio seguente, che assegna un criterio denominato "criteri di chiamata di emergenza contoso 1" al sito 1:

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e, se l'utente è in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.


### <a name="test-emergency-calling"></a>Verificare le chiamate di emergenza

Per testare le chiamate di emergenza negli Stati Uniti, usare il numero di emergenza predefinito per il test 933.  Questo numero viene indirizzato a un bot, che riprende il numero di telefono chiamante (ID linea chiamante), l'indirizzo o la posizione di emergenza e se la chiamata viene indirizzata automaticamente al PSAP o prima schermata.  