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
- m365initiative-voice
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come configurare la funzionalità di chiamata di emergenza dinamica Microsoft Calling Plans e Sistema telefonico Direct Routing dinamico per le chiamate di emergenza.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a243d8d2cf0447bbad78a4b1644fb9e3f1120ea
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465836"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Pianificare e configurare chiamate di emergenza dinamiche 

Le chiamate di emergenza dinamiche per Piani per chiamate Microsoft, Connessione con operatore e Routing diretto forniscono la possibilità di configurare e instradare le chiamate di emergenza e di inviare notifiche al personale di sicurezza in base alla posizione corrente del client Teams.  

In base alla topologia di rete (elementi di rete associati agli indirizzi di emergenza) definita dall'amministratore tenant, il client Teams fornisce informazioni sulla connettività di rete in una richiesta al servizio lis (Location Information Service). Se c'è una corrispondenza, liS restituisce una posizione al client.

Il Teams client include i dati sulla posizione come parte di una chiamata di emergenza. Questi dati vengono quindi usati dal provider del servizio di emergenza per determinare il punto di risposta per la sicurezza pubblica (PSAP) appropriato e per instradare la chiamata a tale PSAP, che consente al dispatcher PSAP di ottenere la posizione del chiamante.  

Per le chiamate di emergenza dinamiche, deve verificarsi quanto segue:

1. L'amministratore di rete configura le impostazioni di rete e liS per creare una mappa della posizione di rete/emergenza.

2. Durante l'avvio e periodicamente in un secondo momento o quando viene modificata una connessione di rete, il client di Teams invia una richiesta di posizione che contiene le informazioni sulla connettività di rete alle impostazioni di rete e al lis.

   - Se è presente una corrispondenza del sito delle impostazioni di rete: i criteri per le chiamate di emergenza vengono restituiti al client Teams dal sito. Per altre informazioni sui criteri, vedere [Configurare i criteri di emergenza.](#configure-emergency-policies)

   - Se c'è una corrispondenza LIS: una posizione di emergenza dall'elemento di rete a cui il client Teams è connesso viene restituita al client Teams locale. La corrispondenza viene eseguita nell'ordine seguente con il primo risultato corrispondente restituito:
       - WAP
       - Switch/porta Ethernet
       - Switch Ethernet
       - Subnet

3. Quando il Teams effettua una chiamata di emergenza, la posizione di emergenza viene comunicata alla rete PSTN.

La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica (PSAP) appropriato varia a seconda del paese di utilizzo dell'Teams utente.

Piani per chiamate Microsoft e Connessione con operatore partner includono servizi di routing dinamico per gli interventi di emergenza per gli utenti negli Stati Uniti e in Canada.

Per il routing diretto, tuttavia, è necessaria una configurazione aggiuntiva per l'instradamento delle chiamate di emergenza e, eventualmente, per la connettività dei partner. L'amministratore deve configurare la connessione a un provider del servizio di routing di emergenza (ERS) (Stati Uniti e **Canada)** oppure configurare il Session Border Controller (SBC) per un'applicazione Emergency Location Identification Number (ELIN). Per informazioni sui provider ERS, vedere [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).

Questo articolo contiene le sezioni seguenti.

- [Assegnare indirizzi di emergenza](#assign-emergency-addresses)
- [Configurare le impostazioni di rete](#configure-network-settings)
- [Configurare il servizio informazioni sulla posizione](#configure-location-information-service)
- [Configurare i criteri di emergenza](#configure-emergency-policies)
- [Abilitare utenti e siti](#enable-users-and-sites)
- [Testare le chiamate di emergenza](#test-emergency-calling)

Per altre informazioni sulle chiamate di emergenza, incluse informazioni su indirizzi di emergenza e routing delle chiamate di emergenza, informazioni specifiche per i paesi e informazioni sulle impostazioni di rete e sulla topologia di rete, vedere quanto segue:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire le impostazioni di rete per le funzionalità vocali cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)

Per altre informazioni sulle funzionalità disponibili nei cloud per enti pubblici, vedere Supporto per enti pubblici [alla](#government-support) fine di questo articolo.


## <a name="supported-clients"></a>Client supportati

Attualmente sono supportati i client seguenti.  Torna spesso per vedere gli aggiornamenti a questo elenco.

- Teams client desktop per Microsoft Windows
- Teams desktop per Apple macOS
- Teams client per dispositivi mobili Apple iOS versione 1.0.92.2019121004 e App Store versione 1.0.92 e successive
- Teams client per dispositivi mobili Android e Google Play Store versione 1416/1.0.0.2019121201 e successive
- Teams telefono 1449/1.0.94.2019110802 e successive
- Teams Rooms versione 4.4.25.0 e successive

> [!NOTE]
> I telefoni 3PIP non supportano chiamate di emergenza dinamiche. 

> [!NOTE]
> Le chiamate di emergenza dinamiche, inclusa la notifica del security desk, non sono supportate nel client Teams Web. Per impedire agli utenti di usare il client Web Teams per chiamare i numeri PSTN, è possibile impostare un criterio di chiamata Teams e disattivare l'impostazione Consenti chiamate **PSTN** Web. Per altre informazioni, vedere Criteri di [chiamata in Teams](teams-calling-policy.md) e [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 

> [!NOTE]
> Le località basate su subnet e WiFi sono supportate in tutti Teams client. <br>
> Ethernet/Switch (LLDP) è supportato in:
> - Windows versioni 8.1 e successive al momento.<br>
> - Mac OS, che richiede [il software di abilitazione llDP.](https://www.microsoft.com/download/details.aspx?id=103383)

## <a name="assign-emergency-addresses"></a>Assegnare indirizzi di emergenza

È possibile assegnare gli indirizzi di emergenza nel modo seguente:

- Agli utenti del Piano chiamate.

- Per Connessione con operatore utenti in base alle funzionalità assegnate al numero quando il gestore li carica &mdash; nell'inventario di un cliente.

- Per gli identificatori di rete necessari per ottenere dinamicamente un percorso. 

Per supportare l'instradamento automatico delle chiamate di emergenza negli Stati Uniti, è necessario assicurarsi che le posizioni di emergenza assegnate agli identificatori di rete includano i codici geografici associati. Gli indirizzi di emergenza senza codici geografici non possono essere assegnati agli identificatori di rete necessari per le posizioni dinamiche.

Azure Mappe viene usato per i servizi basati sulla posizione. Quando si immette un indirizzo per gli interventi di emergenza usando l'interfaccia di amministrazione Microsoft Teams, Teams l'indirizzo Mappe azure:

- Se viene trovata una corrispondenza, i codici geografici vengono inclusi automaticamente.

- Se non viene trovata una corrispondenza, sarà possibile creare manualmente un indirizzo per gli interventi di emergenza. A questo scopo, è possibile usare la funzionalità di rilascio del PIN. 

> [!NOTE]
> Gli indirizzi di emergenza che hanno più di un paio di anni non possono essere assegnati agli identificatori di rete. Sarà necessario creare di nuovo gli indirizzi meno recenti.

È possibile aggiungere e assegnare indirizzi di emergenza nell'Microsoft Teams di amministrazione o usando PowerShell. Per altre informazioni, vedere Aggiungere una posizione per gli interventi di emergenza [per l'organizzazione](add-change-remove-emergency-location-organization.md) e Assegnare una posizione [per gli interventi di emergenza per un utente.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Configurare le impostazioni di rete

Le impostazioni di rete vengono usate per determinare la posizione di un client Teams e per ottenere dinamicamente i criteri per le chiamate di emergenza e una posizione di emergenza. È possibile configurare le impostazioni di rete in base al modo in cui l'organizzazione vuole che le chiamate di emergenza funzionino.

Le impostazioni di rete includono siti che includono una raccolta di subnet e vengono usate esclusivamente per l'assegnazione dinamica dei criteri agli utenti. Ad esempio, un criterio per le chiamate di emergenza e un criterio di routing delle chiamate di emergenza potrebbero essere assegnati al "sito Redmond" in modo che qualsiasi utente che effettua il roaming da casa o da un'altra posizione Microsoft sia configurato con numeri di emergenza, routing e desk di sicurezza specifici di Redmond.  

Gli indirizzi IP attendibili contengono una raccolta di indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Il tentativo di ottenere un criterio o un percorso dinamico verrà eseguito solo se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP nell'indirizzo IP attendibile.

Per altre informazioni sugli indirizzi IP, le aree di rete, i siti e gli indirizzi subnet, vedere [Impostazioni di rete per le funzionalità vocali cloud.](cloud-voice-network-settings.md)

È possibile configurare le impostazioni di rete nell'Microsoft Teams di amministrazione o usando PowerShell. Per altre informazioni, vedere [Gestire la topologia di rete per le funzionalità vocali cloud.](manage-your-network-topology.md)

Si noti che la propagazione e la disponibilità di alcune modifiche alle impostazioni di rete , ad esempio un nuovo indirizzo, un identificatore di rete e così via, possono richiedere del tempo (fino a un paio di ore) per la propagazione e la disponibilità Teams client.  

> [!Note]
> Le subnet possono anche essere definite in LIS e possono essere associate a una posizione di emergenza.  Le subnet LIS devono essere definite dall'ID di rete corrispondente all'intervallo IP subnet assegnato ai client. Ad esempio, l'ID di rete per un IP/mask client di 10.10.10.150/25 è 10.10.10.128. Per altre informazioni, vedere [Informazioni di base sull'indirizzamento TCP/IP e la subnetting.](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)

> [!Important]
> Le ricerche delle impostazioni di configurazione di rete non sono supportate nelle distribuzioni del servizio proxy cloud che modificano gli indirizzi IP di origine Teams client.



**Per gli utenti del piano Connessione con operatore chiamate:**

- Se è necessaria la configurazione dinamica della notifica di Security Desk, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessari solo percorsi dinamici, è necessario configurare solo gli indirizzi IP attendibili. non è necessaria la configurazione delle impostazioni di rete.

- Se nessuna delle due opzioni è necessaria, non è necessario configurare le impostazioni di rete. 

**Per gli utenti di Routing diretto:**

- Se è richiesta l'abilitazione dinamica delle chiamate di emergenza o la configurazione dinamica della notifica del security desk, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessari solo percorsi dinamici, è necessario configurare solo gli indirizzi IP attendibili. non è necessaria la configurazione delle impostazioni di metwork.

- Se nessuna delle due opzioni è necessaria, non è necessario configurare le impostazioni di rete.


## <a name="configure-location-information-service"></a>Configurare il servizio informazioni sulla posizione

Un Teams client ottiene gli indirizzi di emergenza dalle posizioni associate a diversi identificatori di rete. 

Per ottenere una posizione da un client, è necessario popolare il LIS con identificatori di rete (subnet, WAP, switch, porte) e posizioni di emergenza. È possibile farlo nell'interfaccia Microsoft Teams di amministrazione o usando PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Percorsi**  >  **reti & posizioni**.
2. Fare clic sulla scheda che rappresenta l'identificatore di rete da aggiungere. Ad esempio, fare clic **su Subnet,** **punti di accesso Wi-Fi,** **Switch** o **Porte.** Quindi fare clic **su Aggiungi**.
3. Completare i campi, aggiungere una posizione per gli interventi di emergenza e quindi fare clic su **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Usare i cmdlet seguenti per aggiungere porte, switch, subnet e WAP al lis.

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Se le subnet vengono usate come parte dei siti di rete, devono essere ridefinite nel servizio informazioni sulla posizione per eseguire il rendering delle posizioni dinamiche.

## <a name="configure-emergency-policies"></a>Configurare i criteri di emergenza

Usare i criteri seguenti per configurare le chiamate di emergenza. È possibile gestire questi criteri nell'interfaccia Microsoft Teams di amministrazione o usando PowerShell.

- **Criteri di routing delle chiamate di emergenza: si applica solo a Routing diretto.** Questo criterio configura i numeri di emergenza, le maschere per numero, se necessario, e la route PSTN per numero. È possibile assegnare questo criterio agli utenti, ai siti di rete o a entrambi. Per altre informazioni, vedere [Gestire i criteri di routing delle chiamate di emergenza per Routing diretto.](manage-emergency-call-routing-policies.md)  

   Gli utenti di Piano chiamate e Connessione con operatore sono abilitati automaticamente per le chiamate di emergenza con i numeri di emergenza del paese in base alla località di Microsoft 365 o Office 365 di utilizzo.

- **Criteri per le chiamate di emergenza: si applica ai piani per chiamate, Connessione con operatore e al routing diretto.** Questo criterio configura l'esperienza di notifica del security desk quando viene effettuata una chiamata di emergenza. È possibile impostare gli utenti a cui inviare la notifica e la modalità di notifica. Ad esempio, per informare automaticamente il desk di sicurezza dell'organizzazione e fare in modo che ascoltino le chiamate di emergenza.  Questo criterio può essere assegnato a utenti o siti di rete o a entrambi. Per altre informazioni, vedere [Gestire i criteri per le chiamate](manage-emergency-calling-policies.md)di emergenza in Teams .

## <a name="enable-users-and-sites"></a>Abilitare utenti e siti

È possibile assegnare criteri di routing delle chiamate di emergenza e criteri per le chiamate di emergenza agli utenti e ai siti. Tenere presente che i criteri di routing delle chiamate di emergenza si applicano solo al routing diretto. Anche se è possibile assegnare questo criterio a un piano per chiamate o a un Connessione con operatore utente, il criterio non avrà alcun effetto.

È possibile assegnare criteri nell'Microsoft Teams di amministrazione o usando PowerShell. Per altre informazioni, vedere:

- [Gestire i criteri di routing delle chiamate di emergenza per il routing diretto](manage-emergency-call-routing-policies.md)
- [Gestire i criteri per le chiamate di emergenza in Teams](manage-emergency-calling-policies.md)

Di seguito sono riportati alcuni esempi di PowerShell:

Per abilitare un utente specifico per la notifica di security desk, usare il comando seguente:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Per assegnare un criterio denominato "Criterio chiamate di emergenza Contoso 1" al sito 1, usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Per abilitare uno specifico utente di Routing diretto per le chiamate di emergenza, usare il comando seguente:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Per assegnare un criterio denominato "Contoso New York Emergency Call Routing" al sito 1, usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e l'utente si trova in tale sito di rete, i criteri assegnati al sito di rete sostituiscono i criteri assegnati all'utente.

## <a name="test-emergency-calling"></a>Testare le chiamate di emergenza

Alcuni provider di servizi di routing di emergenza (ESP) negli Stati Uniti offrono un bot di prova per le chiamate di emergenza.

- **Piano chiamate e Connessione con operatore** utenti negli Stati Uniti o in Canada possono usare il numero di emergenza di prova predefinito 933 per convalidare la configurazione delle chiamate di emergenza. Questo numero viene instradato a un bot, che riecheggia quindi il numero di telefono chiamante (ID linea chiamante), l'indirizzo di emergenza o la posizione e indica se la chiamata verrà instradata automaticamente al PSAP o visualizzata per prima.

- **I clienti di Direct Routing negli Stati Uniti** devono coordinarsi con l'ERSP per un servizio di test.

## <a name="government-support"></a>Supporto per enti pubblici

La tabella seguente mostra il supporto per le chiamate di emergenza dinamiche nei cloud governativi:

| Cloud | Disponibilità |
| :------------|:-------|
| World Wide Multi Tenant | Disponibile in tutti i Teams client |
| GCC | Disponibile in tutti i Teams client |
| GCCH | Disponibile su Teams desktop |
| DoD | In sospeso |

 ## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza ](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione per gli interventi di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Impostazioni di rete per le funzionalità vocali del cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)
