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
f1.keywords:
- NOCSH
description: Informazioni su come configurare i piani di chiamata Microsoft e il sistema telefonico Direct routing funzionalità di chiamata di emergenza dinamica.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27ee8dd17b3948d373b5a6c13a210d298ee10d8c
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083156"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Pianificare e configurare chiamate di emergenza dinamiche 

Le chiamate di emergenza dinamiche per i piani per chiamate Microsoft e per il routing diretto del sistema telefonico offrono la possibilità di configurare e instradare telefonate di emergenza e informare il personale di sicurezza in base alla posizione corrente del client teams.  

In base alla topologia di rete definita dall'amministratore del tenant, il client teams fornisce informazioni di connettività di rete in una richiesta al servizio informazioni sulla posizione. Se c'è una corrispondenza, la LIS restituirà una posizione al client. Questi dati della posizione vengono trasmessi al client.  

Il client teams include i dati della posizione nell'ambito di una chiamata di emergenza. Questi dati vengono quindi usati dal provider di servizi di emergenza per determinare il punto di risposta appropriato per la sicurezza pubblica (PSAP) e per instradare la chiamata a tale PSAP, che consente al dispatcher di PSAP di ottenere la posizione del chiamante.  

Per le chiamate di emergenza dinamiche, è necessario che vengano eseguite le operazioni seguenti:

1. L'amministratore di rete configura le impostazioni di rete e la LIS per creare una mappa della posizione di rete/emergenza.

   Per il routing diretto, è necessaria una configurazione aggiuntiva per il routing delle chiamate di emergenza e possibilmente per la connettività dei partner. L'amministratore deve configurare la connessione a un provider ERS (Emergency Routing Service) (Stati Uniti) **o** configurare il session border controller (SBC) per un'applicazione Elin (Emergency Location Identification Number).

2. Durante l'avvio e periodicamente dopo, o quando viene modificata una connessione di rete, il client teams invia una richiesta di posizione che contiene le informazioni sulla connettività di rete alle impostazioni di rete e alla LIS.

   - Se è presente una corrispondenza del sito delle impostazioni di rete, i criteri di chiamata di emergenza vengono restituiti al client Teams da tale sito. Per altre informazioni sui criteri, vedere [configurare i criteri di emergenza](#configure-emergency-policies).

   - Se c'è una corrispondenza LIS: una posizione di emergenza dall'elemento Network a cui è connesso il client teams viene restituita al client teams.

3. Quando il client Team effettua una chiamata di emergenza, la posizione di emergenza viene trasmessa alla rete PSTN.

   Per il routing diretto, l'amministratore deve configurare l'SBC per inviare chiamate di emergenza al provider ERS o configurare l'applicazione ELIN SBC.

Questo articolo contiene le sezioni seguenti.

- [Configurare gli indirizzi di emergenza](#assign-emergency-addresses)
- [Configurare le impostazioni di rete](#configure-network-settings)
- [Configurare il servizio informazioni sulla posizione](#configure-location-information-service)
- [Configurare i criteri di emergenza](#configure-emergency-policies)
- [Abilitare utenti e siti](#enable-users-and-sites)
- [Verificare le chiamate di emergenza](#test-emergency-calling)

La possibilità di eseguire il routing automatico all'appropriato PSAP (Public Safety Answering Point) varia a seconda del paese di utilizzo dell'utente teams.

Per altre informazioni sulle chiamate di emergenza, incluse informazioni su indirizzi di emergenza e routing delle chiamate di emergenza, informazioni specifiche per i paesi e informazioni sulle impostazioni di rete e la topologia di rete, vedere quanto segue:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire le impostazioni di rete per le caratteristiche vocali cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)

## <a name="supported-clients"></a>Client supportati

I client seguenti sono attualmente supportati.  Controlla spesso per vedere gli aggiornamenti di questo elenco.

- Client desktop teams per Microsoft Windows
- Client desktop teams per Apple macOS
- Client di teams mobile per Apple iOS Client versione 1.0.92.2019121004 e App Store versione 1.0.92 e versioni successive
- Client di teams per dispositivi mobili per client Android e Google Play Store versione 1416/1.0.0.2019121201 e versioni successive
- Telefono teams versione 1449/1.0.94.2019110802 e versioni successive
- Teams Rooms versione 4.4.25.0 e versioni successive

## <a name="assign-emergency-addresses"></a>Assegnare indirizzi di emergenza

È possibile assegnare indirizzi di emergenza sia agli utenti del piano chiamante che agli identificatori di rete necessari per ottenere in modo dinamico una posizione. (La subnet e il WiFi AP sono supportati; il supporto per switch Ethernet/porta è in sospeso).

Per supportare il routing automatizzato delle chiamate di emergenza negli Stati Uniti, è necessario assicurarsi che i percorsi di emergenza assegnati agli identificatori di rete includano i codici Geo associati. Gli indirizzi di emergenza senza codici Geo non possono essere assegnati agli identificatori di rete necessari per le posizioni dinamiche.

Azure Maps viene usato per i servizi basati sulla posizione.  Quando si immette un indirizzo di emergenza tramite l'interfaccia di amministrazione di Microsoft teams, teams controlla le mappe di Azure per l'indirizzo:

- Se viene trovata una corrispondenza, i codici Geo vengono automaticamente inclusi.

- Se non viene trovata una corrispondenza, si avrà la possibilità di creare manualmente un indirizzo di emergenza. Per eseguire questa operazione, è possibile usare la caratteristica drop PIN. 

Questo significa che se una posizione di emergenza esistente creata per l'assegnazione agli utenti del piano chiamante è destinata a una posizione dinamica, è necessario ricreare lo stesso indirizzo per includere i codici Geo. Per distinguere tra le due posizioni, è necessario includere una descrizione diversa. La nuova posizione di emergenza può essere assegnata agli utenti che hanno la posizione precedente. Quando è stata eseguita la migrazione completa, la posizione precedente può essere eliminata.

È possibile aggiungere e assegnare indirizzi di emergenza nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell. Per altre informazioni, vedere [aggiungere un percorso di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md) e [assegnare una posizione di emergenza per un utente](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Configurare le impostazioni di rete

Le impostazioni di rete vengono usate per determinare la posizione di un client di teams e per ottenere dinamicamente criteri per le chiamate di emergenza e una posizione di emergenza. È possibile configurare le impostazioni di rete in base alle modalità di funzionamento dell'organizzazione per le chiamate di emergenza.

Le impostazioni di rete includono i siti che includono una raccolta di subnet e questi vengono usati esclusivamente per l'assegnazione di criteri dinamici agli utenti. Ad esempio, un criterio di chiamata di emergenza e un criterio di routing delle chiamate di emergenza potrebbero essere assegnati al "sito Redmond" in modo che tutti gli utenti che si spostano da casa o da un'altra posizione Microsoft siano configurati con numeri di emergenza, routing e Security desk specifici di Redmond.  

>[!Note]
>Le subnet possono essere definite anche in LIS e possono essere associate a una posizione di emergenza.  

Tieni presente le definizioni seguenti. Per altre informazioni, vedere [impostazioni di rete per le caratteristiche vocali del cloud](cloud-voice-network-settings.md).

- Gli indirizzi IP attendibili contengono una raccolta degli indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Un tentativo di ottenere un criterio dinamico o una posizione verrà eseguito solo se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP nell'indirizzo IP attendibile. Una corrispondenza può essere eseguita in base agli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete.  Se un indirizzo IP pubblico include sia IPv4 che IPv6, è necessario aggiungere entrambi come indirizzi IP attendibili.

- Un'area di rete contiene una raccolta di siti di rete. 

- Un sito di rete rappresenta un percorso in cui l'organizzazione ha un valore fisico, ad esempio un ufficio, un set di edifici o un campus. Questi siti sono definiti come una raccolta di subnet IP.

- Una subnet di rete deve essere associata a un sito di rete specifico. La posizione di un cliente viene determinata in base alla subnet della rete e al sito di rete associato.  

Le impostazioni di rete vengono configurate nell'interfaccia di amministrazione di Microsoft teams o tramite PowerShell. Per altre informazioni, vedere [gestire la topologia di rete per le caratteristiche vocali del cloud](manage-your-network-topology.md).

Tieni presente che può essere necessario un po' di tempo (fino a un paio di ore) per alcune modifiche apportate alle impostazioni di rete, ad esempio un nuovo indirizzo, un identificatore di rete e così via, per propagarsi e essere disponibile per i client del team.  

**Per gli utenti del piano chiamante:**

- Se è necessaria la configurazione dinamica della notifica del servizio di sicurezza, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili.

- Se non sono necessarie, la configurazione delle impostazioni di rete non è necessaria. 

**Per gli utenti di routing diretto:**

- Se è necessaria l'abilitazione dinamica delle chiamate di emergenza o della configurazione dinamica della notifica per il servizio di sicurezza, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili.

- Se non sono necessarie, la configurazione delle impostazioni di rete non è necessaria.


## <a name="configure-location-information-service"></a>Configurare il servizio informazioni sulla posizione

Un client teams ottiene gli indirizzi di emergenza dalle posizioni associate a identificatori di rete diversi. Sono supportate sia le subnet che i punti di accesso wireless (WAP). Il supporto per switch/porta Ethernet è in sospeso.

Affinché un client ottenga una posizione, è necessario popolare la LIS con gli identificatori di rete (subnet, WAP, Switch, porte) e le posizioni di emergenza. Puoi eseguire questa operazione nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra, Vai **a posizioni**  >  **Networks & posizioni**.
2. Fare clic sulla scheda che rappresenta l'identificatore di rete che si vuole aggiungere. Ad esempio, fare clic su **subnet**, **punti di accesso Wi-Fi**, **interruttori**o **porte**. Quindi fare clic su **Aggiungi**.
3. Completare i campi, aggiungere un percorso di emergenza e quindi fare clic su **applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Usare i cmdlet seguenti per aggiungere porte, Switch, subnet e WAP alla LIS.

- [Ottieni](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [imposta](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Ottieni](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [imposta](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Ottieni](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [imposta](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Ottieni](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [imposta](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Se le subnet vengono usate come parte dei siti di rete, devono essere ridefinite nel servizio informazioni sulla posizione per il rendering di posizioni dinamiche.

## <a name="configure-emergency-policies"></a>Configurare i criteri di emergenza

Usare i criteri seguenti per configurare le chiamate di emergenza. Puoi gestire questi criteri nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.

- **Criteri di routing delle chiamate di emergenza** : si applica solo al routing diretto. Questo criterio Configura i numeri di emergenza, le maschere per numero, se necessario, e la route PSTN per numero.  È possibile assegnare questo criterio agli utenti, ai siti di rete o a entrambi. (Piani di chiamata i client teams vengono abilitati automaticamente per le chiamate di emergenza con i numeri di emergenza provenienti dal paese in base alla posizione di utilizzo di Microsoft 365 o Office 365.)  Per altre informazioni, vedere [gestire i criteri di routing delle chiamate di emergenza per il routing diretto](manage-emergency-call-routing-policies.md).

- **Criteri** per le chiamate di emergenza: si applica ai piani di chiamata e al routing diretto. Questo criterio configura l'esperienza di notifica di Security desk quando viene effettuata una chiamata di emergenza. È possibile impostare gli utenti che notificano e come vengono notificati. Ad esempio, per informare automaticamente il proprio banco di sicurezza dell'organizzazione e farli ascoltare in caso di chiamate di emergenza.  Questo criterio può essere assegnato a utenti o siti di rete o entrambi. Per altre informazioni, vedere [gestire i criteri per le chiamate di emergenza in teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Abilitare utenti e siti

È possibile assegnare criteri di routing delle chiamate di emergenza e criteri di chiamata di emergenza agli utenti e ai siti. Tieni presente che i criteri di routing delle chiamate di emergenza si applicano solo al routing diretto. Anche se è possibile assegnare questo criterio a un utente del piano chiamante, il criterio non avrà alcun effetto.

Si assegnano i criteri nell'interfaccia di amministrazione di Microsoft teams o tramite PowerShell. Per altre informazioni, vedere:

- [Gestire i criteri di routing delle chiamate di emergenza per il routing diretto](manage-emergency-call-routing-policies.md)
- [Gestire i criteri delle chiamate di emergenza in teams](manage-emergency-calling-policies.md)

Ecco alcuni esempi di PowerShell.

Per abilitare un utente specifico per la notifica di un servizio di sicurezza, usare il comando seguente:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Per assegnare un criterio denominato "criteri di chiamata di emergenza contoso 1" al sito 1, usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Per abilitare un utente di routing diretto specifico per le chiamate di emergenza, usare il comando seguente:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Per assegnare un criterio denominato "routing delle chiamate di emergenza di Contoso New York" al sito 1, usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e, se l'utente è in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.

## <a name="test-emergency-calling"></a>Verificare le chiamate di emergenza

Alcuni provider di servizi di routing di emergenza (ERSPs) negli Stati Uniti offrono un bot di test delle chiamate di emergenza.

- **Gli utenti del piano chiamante negli Stati Uniti** possono usare il numero di emergenza predefinito per il test 933 per convalidare la configurazione delle chiamate di emergenza. Questo numero viene indirizzato a un bot, che riprende il numero di telefono chiamante (ID linea chiamante), l'indirizzo o la posizione di emergenza e se la chiamata viene indirizzata automaticamente al PSAP o prima schermata.

- **Il routing diretto clienti negli Stati Uniti** deve coordinarsi con il proprio ERSP per un servizio di test.

 ## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Impostazioni di rete per le funzionalità vocali del cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)
