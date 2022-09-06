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
description: Scopri come configurare la funzionalità chiamate di emergenza dinamiche Piani per chiamate Microsoft e Routing diretto sistema telefonico.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9109f26abc953fd131e96440bd62d147cac8114f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606035"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Pianificare e configurare chiamate di emergenza dinamiche 

Chiamate di emergenza dinamiche per i piani per chiamate Microsoft, Operator Connect, Connessione con operatore di telefonia mobile (versione di anteprima pubblica) e Routing diretto offrono la possibilità di configurare e instradare le chiamate di emergenza e avvisare il personale di sicurezza in base alla posizione corrente del client Teams.  

In base alla topologia di rete (elementi di rete associati agli indirizzi di emergenza) definita dall'amministratore del tenant, il client Teams fornisce informazioni sulla connettività di rete in una richiesta al servizio LIS (Location Information Service). Se esiste una corrispondenza, LIS restituisce una posizione al client.

Il client Teams include i dati sulla posizione come parte di una chiamata di emergenza. Questi dati vengono quindi utilizzati dal provider dei servizi di emergenza per determinare il punto di risposta per la sicurezza pubblica appropriato (PSAP) e per instradare la chiamata al PSAP, il che consente al dispatcher del PSAP di ottenere la posizione del chiamante.  

Per le chiamate di emergenza dinamiche, è necessario che si verifichi quanto segue:

1. L'amministratore di rete configura le impostazioni di rete e liS per creare una mappa della posizione di rete/emergenza.

2. Durante l'avvio e periodicamente in seguito, o quando viene modificata una connessione di rete, il client Teams invia una richiesta di posizione che contiene le informazioni sulla connettività di rete alle impostazioni di rete e al LIS.

   - Se esiste una corrispondenza del sito delle impostazioni di rete, i criteri per le chiamate di emergenza vengono restituiti al client Teams da quel sito. Per altre informazioni sui criteri, vedere [Configurare i criteri di emergenza](#configure-emergency-policies).

   - Se c'è una corrispondenza LIS: una posizione per gli interventi di emergenza dall'elemento di rete a cui è connesso il client Teams viene restituita al client teams. La corrispondenza viene eseguita nell'ordine seguente con il primo risultato corrispondente restituito:
       - Wap
       - Switch/porta Ethernet
       - Interruttore Ethernet
       - Subnet

3. Quando il client Teams effettua una chiamata di emergenza, la posizione per gli interventi di emergenza viene comunicata alla rete PSTN.

La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica (PSAP) appropriato varia a seconda del paese di utilizzo dell'utente di Teams.

I Piani per chiamate Microsoft, i partner Operator Connect e i partner Connessione con operatore di telefonia mobile includono servizi di routing di emergenza dinamici per gli utenti del Stati Uniti e del Canada.

Per il routing diretto, tuttavia, è necessaria una configurazione aggiuntiva per il routing delle chiamate di emergenza ed eventualmente per la connettività dei partner. L'amministratore deve assicurarsi che il gateway PSTN instradare la chiamata di emergenza sia stato configurato per aggiungere informazioni sulla posizione all'invito in uscita (impostando il parametro PidfloSupported su True nell'oggetto gateway PSTN online. Inoltre, l'amministratore deve configurare la connessione a un provider del servizio di routing di emergenza (ERS) (Stati Uniti e Canada) **OPPURE** configurare il controller dei confini della sessione (SBC) per un'applicazione ELIN (Emergency Location Identification Number). Per informazioni sui provider ERS, vedere [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).

Questo articolo contiene le sezioni seguenti.

- [Assegnare indirizzi per gli interventi di emergenza](#assign-emergency-addresses)
- [Configurare le impostazioni di rete](#configure-network-settings)
- [Configurare il servizio informazioni sulla posizione](#configure-location-information-service)
- [Configurare i criteri di emergenza](#configure-emergency-policies)
- [Abilitare utenti e siti](#enable-users-and-sites)
- [Testare le chiamate di emergenza](#test-emergency-calling)

Per ulteriori informazioni sulle chiamate di emergenza, incluse informazioni sugli indirizzi di emergenza e sul routing delle chiamate di emergenza, informazioni specifiche per i paesi e informazioni sulle impostazioni di rete e sulla topologia della rete, vedi quanto segue:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire le impostazioni di rete per le funzionalità vocali cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)

Per altre informazioni sulle funzionalità disponibili nei cloud per enti pubblici, vedere [Supporto](#government-support) per enti pubblici alla fine di questo articolo.


## <a name="supported-clients"></a>Client supportati

Attualmente sono supportati i client seguenti.  Ricontrollare spesso per vedere gli aggiornamenti a questo elenco.

- Client desktop di Teams per Microsoft Windows
- Client desktop di Teams per Apple macOS
- Client teams mobile per client Apple iOS versione 1.0.92.2019121004 e App Store versione 1.0.92 e successive
- Client teams mobile per client Android e Google Play Store versione 1416/1.0.0.2019121201 e versioni successive
- Telefono Teams versione 1449/1.0.94.2019110802 e versioni successive
- Teams Rooms versione 4.4.25.0 e successive

> [!NOTE]
> Le posizioni subnet e basate su WiFi sono supportate in tutti i client Teams supportati. <br><br>
> Ethernet/Switch (LLDP) è supportato in:
> - Versioni di Windows 10.0 e successive in questo momento.<br>
> - Mac OS, che richiede [il software di abilitazione LLDP](https://www.microsoft.com/download/details.aspx?id=103383).<br>
> - Telefono Teams con l'app Teams versione 1449/1.0.94.2021110101 e successive.

> [!NOTE]
> Le chiamate di emergenza dinamiche, incluse le notifiche di security desk, non sono supportate nel client Web di Teams. Per impedire agli utenti di usare il client Web di Teams per chiamare i numeri PSTN, è possibile impostare un criterio per le chiamate di Teams e disattivare l'impostazione **Consenti chiamate PSTN Web** . Per ulteriori informazioni, vedi [Criteri per le chiamate in Teams](teams-calling-policy.md) e [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). 

> [!NOTE]
> I telefoni 3PIP non supportano le chiamate di emergenza dinamiche. 



## <a name="assign-emergency-addresses"></a>Assegnare indirizzi per gli interventi di emergenza

Puoi assegnare gli indirizzi per gli interventi di emergenza come segue:

- A Utenti del Piano per chiamate.

- Per Operator Connect e Connessione con operatore di telefonia mobile gli utenti&mdash;in base alle funzionalità assegnate al numero quando il gestore li carica nell'inventario di un cliente.

- Agli identificatori di rete necessari per ottenere dinamicamente una posizione. 

Per supportare il routing automatico delle chiamate di emergenza all'interno del Stati Uniti, è necessario assicurarsi che le posizioni per gli interventi di emergenza assegnate agli identificatori di rete includano i codici geografici associati. Gli indirizzi di emergenza senza codici geografici non possono essere assegnati agli identificatori di rete necessari per le posizioni dinamiche.

Mappe di Azure viene utilizzato per i servizi basati sulla posizione. Quando si immette un indirizzo per gli interventi di emergenza tramite l'interfaccia di amministrazione di Microsoft Teams, Teams verifica Mappe di Azure l'indirizzo:

- Se viene trovata una corrispondenza, i codici geografici vengono inclusi automaticamente.

- Se non viene trovata una corrispondenza, avrai la possibilità di creare manualmente un indirizzo per gli interventi di emergenza. A tale scopo, è possibile usare la funzionalità di rilascio del PIN. 

> [!NOTE]
> Gli indirizzi di emergenza che hanno più di un paio di anni non possono essere assegnati agli identificatori di rete. Sarà necessario ricreare gli indirizzi meno recenti.

Aggiungi e assegna indirizzi per gli interventi di emergenza nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell. Per altre informazioni, vedi [Aggiungere una posizione per gli interventi di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md) e [Assegnare una posizione per gli interventi di emergenza per un utente](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Configurare le impostazioni di rete

Le impostazioni di rete vengono usate per determinare la posizione di un client di Teams e per ottenere dinamicamente criteri per le chiamate di emergenza e una posizione per gli interventi di emergenza. È possibile configurare le impostazioni di rete in base al funzionamento delle chiamate di emergenza dell'organizzazione.

Le impostazioni di rete includono siti che includono una raccolta di subnet, usati esclusivamente per l'assegnazione di criteri dinamici agli utenti. Ad esempio, al "sito Redmond" potrebbero essere assegnati criteri per le chiamate di emergenza e routing delle chiamate di emergenza, in modo che qualsiasi utente che effettua il roaming da casa o da un'altra posizione Microsoft sia configurato con numeri di emergenza, routing e security desk specifici di Redmond.  

Gli indirizzi IP attendibili contengono una raccolta di indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Un tentativo di ottenere un criterio dinamico o una posizione verrà effettuato solo se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP nell'indirizzo IP attendibile.

Per altre informazioni su indirizzi IP, aree geografiche di rete, siti e indirizzi subnet, vedi [Impostazioni di rete per le funzionalità vocali nel cloud](cloud-voice-network-settings.md).

È possibile configurare le impostazioni di rete nell'interfaccia di amministrazione di Microsoft Teams o usando PowerShell. Per altre informazioni, vedere [Gestire la topologia di rete per le funzionalità vocali nel cloud](manage-your-network-topology.md).

Si noti che la propagazione di alcune modifiche alle impostazioni di rete (ad esempio un nuovo indirizzo, un identificatore di rete e così via) può richiedere del tempo (fino a un paio di ore).  

> [!Note]
> Le subnet possono anche essere definite in LIS e possono essere associate a una posizione di emergenza.  Le subnet LIS devono essere definite dall'ID di rete corrispondente all'intervallo IP subnet assegnato ai client. Ad esempio, l'ID di rete per un IP/maschera client 10.10.10.150/25 è 10.10.10.128. Per altre informazioni, vedere [Informazioni di base sull'indirizzamento TCP/IP e la subnetting](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

> [!Important]
> Le ricerche delle impostazioni di configurazione di rete non sono supportate nelle distribuzioni dei servizi proxy cloud che modificano gli indirizzi IP di origine dai client di Teams.



**Per gli utenti con piano per chiamate, Operator Connect e Connessione con operatore di telefonia mobile:**

- Se è necessaria la configurazione dinamica della notifica security desk, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili; non è necessario configurare le impostazioni di rete.

- Se nessuna delle due impostazioni è necessaria, non è necessario configurare le impostazioni di rete. 

**Per gli utenti di Direct Routing:**

- Se è necessaria l'abilitazione dinamica delle chiamate di emergenza o la configurazione dinamica della notifica security desk, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili; non è necessario configurare le impostazioni di rete.

- Se nessuna delle due impostazioni è necessaria, non è necessario configurare le impostazioni di rete.


## <a name="configure-location-information-service"></a>Configurare il servizio informazioni sulla posizione

Un client Teams ottiene gli indirizzi per gli interventi di emergenza dalle posizioni associate a diversi identificatori di rete. 

Affinché un client ottenga una posizione, è necessario popolare il LIS con identificatori di rete (subnet, WAP, switch, porte) e posizioni per gli interventi di emergenza. È possibile farlo nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro vai a **Percorsi** > **rete & posizioni**.
2. Fare clic sulla scheda che rappresenta l'identificatore di rete da aggiungere. Ad esempio, fare clic su **Subnet**, **punti di accesso Wi-Fi**, **commutatori** o **porte**. Quindi fare clic su **Aggiungi**.
3. Completa i campi, aggiungi una posizione per gli interventi di emergenza e quindi fai clic su **Applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Utilizza i cmdlet seguenti per aggiungere porte, switch, subnet e WAP al LIS.

- [Ottenere](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [impostare](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [rimuovere](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Ottenere](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [impostare](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [rimuovere](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Ottenere](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [impostare](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [rimuovere](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Scarica](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [imposta](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [rimuovi](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Se le subnet vengono usate come parte di siti di rete, devono essere ridefinite nel servizio informazioni sulla posizione per il rendering di posizioni dinamiche.

## <a name="configure-emergency-policies"></a>Configurare i criteri di emergenza

Utilizza i criteri seguenti per configurare le chiamate di emergenza. È possibile gestire questi criteri nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.

- **Criteri di routing delle chiamate di emergenza: si applica solo al routing diretto**. Questo criterio configura i numeri di emergenza, le maschere per numero, se lo si desidera, e la route PSTN per numero. È possibile assegnare questo criterio agli utenti, ai siti di rete o a entrambi. Per altre informazioni, vedere [Gestire i criteri di routing delle chiamate di emergenza per il routing diretto](manage-emergency-call-routing-policies.md).  

   (Gli utenti di Piani per chiamate, Operator Connect e Connessione con operatore di telefonia mobile vengono automaticamente abilitati per le chiamate di emergenza con i numeri di emergenza del paese in base alla loro posizione di utilizzo di Microsoft 365 o Office 365.

- **Criteri per le chiamate di emergenza: si applica ai piani per chiamate, a Operator Connect, a Connessione con operatore di telefonia mobile e al routing diretto.** Questo criterio configura l'esperienza di notifica del security desk quando viene effettuata una chiamata di emergenza. È possibile impostare le persone a cui inviare la notifica e la relativa modalità di notifica. Ad esempio, per informare automaticamente il security desk dell'organizzazione e fare in modo che ascoltino le chiamate di emergenza.  Questo criterio può essere assegnato agli utenti o ai siti di rete o a entrambi. Per altre informazioni, vedere [Gestire i criteri per le chiamate di emergenza in Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Abilitare utenti e siti

È possibile assegnare criteri di routing delle chiamate di emergenza e criteri per le chiamate di emergenza agli utenti e ai siti. Tenere presente che i criteri di routing delle chiamate di emergenza si applicano solo al routing diretto. Anche se è possibile assegnare questo criterio a un piano per chiamate, a Una connessione operatore o a un utente Connessione con operatore di telefonia mobile, il criterio non avrà alcun effetto.

I criteri vengono assegnati nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell. Per altre informazioni, vedere:

- [Gestire i criteri di routing delle chiamate di emergenza per il routing diretto](manage-emergency-call-routing-policies.md)
- [Gestire i criteri per le chiamate di emergenza in Teams](manage-emergency-calling-policies.md)

Ecco alcuni esempi di PowerShell:

Per abilitare una notifica di security desk a un utente specifico, usare il comando seguente:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Per assegnare un criterio denominato "Criterio chiamate di emergenza Contoso 1" al sito 1, usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Per abilitare uno specifico utente di routing diretto per le chiamate di emergenza, utilizza il comando seguente:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Per assegnare un criterio denominato "Routing chiamate di emergenza Contoso New York" al sito 1, usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se è stato assegnato un criterio di chiamata di emergenza a un sito di rete e a un utente e tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sovrascrive il criterio assegnato all'utente.

## <a name="test-emergency-calling"></a>Testare le chiamate di emergenza

Alcuni provider di servizi di routing di emergenza (ERSP) nel Stati Uniti offrono un bot per il test di chiamata di emergenza.

- **Gli utenti di Piani per chiamate, Operator Connect e Connessione con operatore di telefonia mobile nel Stati Uniti o in Canada** possono utilizzare il numero di emergenza predefinito 933 per convalidare la configurazione delle chiamate di emergenza. Questo numero viene instradato a un bot, che quindi richiama il numero di telefono del chiamante (ID della linea di chiamata), l'indirizzo o la posizione per gli interventi di emergenza e indica se la chiamata verrebbe instradata automaticamente al PSAP o prima visualizzata.

- **I clienti di Direct Routing nel Stati Uniti** devono coordinarsi con il proprio ERSP per un servizio di test.

## <a name="government-support"></a>Supporto governativo

La tabella seguente mostra il supporto per le chiamate di emergenza dinamiche nei cloud governativi:

| Cloud | Disponibilità |
| :------------|:-------|
| World Wide Multi Tenant | Disponibile in tutti i client di Teams |
| Gcc | Disponibile in tutti i client di Teams |
| GCCH | -Disponibile su Teams desktop <br> -Disponibile nei client mobili di Teams <br> -Disponibile sui telefoni Teams, versione dell'app: 1449/1.0.94.2022061702 |
| Dod | In sospeso |

 ## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza ](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione per gli interventi di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Impostazioni di rete per le funzionalità vocali del cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)
