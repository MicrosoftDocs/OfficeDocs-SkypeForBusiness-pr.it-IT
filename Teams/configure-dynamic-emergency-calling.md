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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Scopri come configurare la funzione Piani per chiamate Microsoft e Routing diretto sistema telefonico per le chiamate di emergenza dinamiche.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06153eccd343ef8731af38ff4e3b45cea334fcb2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031012"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Pianificare e configurare chiamate di emergenza dinamiche 

Le chiamate di emergenza dinamiche per i Piani per chiamate Microsoft e il routing diretto del sistema telefonico forniscono la possibilità di configurare e instradare le chiamate di emergenza e avvisare il personale addetto alla sicurezza in base alla posizione corrente del client teams.  

In base alla topologia di rete definita dall'amministratore del tenant, il client di Teams fornisce informazioni sulla connettività di rete in una richiesta al servizio LIS (Location Information Service). Se esiste una corrispondenza, liS restituisce una posizione al client. Questi dati sulla posizione vengono trasmessi al client.  

Il client Teams include i dati sulla posizione come parte di una chiamata di emergenza. Questi dati vengono quindi utilizzati dal provider dei servizi di emergenza per determinare il punto di risposta per la sicurezza pubblica (PSAP) appropriato e per instradare la chiamata a tale PSAP, in modo che l'asta del servizio di emergenza PSAP sia in grado di ottenere la posizione del chiamante.  

Per le chiamate di emergenza dinamiche, devono verificarsi le condizioni seguenti:

1. L'amministratore di rete configura le impostazioni di rete e il servizio LIS per creare una mappa della posizione di rete/emergenza.

   Per l'instradamento diretto, è necessaria una configurazione aggiuntiva per l'instradamento delle chiamate di emergenza e probabilmente per la connettività del partner. L'amministratore deve configurare la connessione a un provider del servizio di instradamento di emergenza (Stati **Uniti)** O configurare il controller dei confini della sessione (SBC) per un'applicazione ELIN (Emergency Location Identification Number).

2. Durante l'avvio e periodicamente in seguito o quando viene modificata una connessione di rete, il client Teams invia una richiesta di posizione che contiene le informazioni sulla connettività di rete alle impostazioni di rete e al sistema LIS.

   - Se c'è una corrispondenza tra un sito delle impostazioni di rete e un sito, da quel sito vengono restituiti criteri per le chiamate di emergenza al client Teams. Per altre informazioni sui criteri, vedere [Configurare i criteri di emergenza.](#configure-emergency-policies)

   - Se c'è una corrispondenza LIS: una posizione per gli interventi di emergenza dall'elemento di rete a cui è connesso il client di Teams viene restituita al client Teams. La corrispondenza viene eseguita nell'ordine seguente, con il primo risultato corrispondente restituito:
       - WAP
       - Switch/porta Ethernet
       - Interruttore Ethernet
       - Subnet

3. Quando il client Teams effettua una chiamata di emergenza, la posizione di emergenza viene comunicata alla rete PSTN.

   Per l'instradamento diretto, l'amministratore deve configurare SBC per l'invio di chiamate di emergenza al provider ERS o l'applicazione SBC ELIN.

Questo articolo contiene le sezioni seguenti.

- [Configurare gli indirizzi per gli interventi di emergenza](#assign-emergency-addresses)
- [Configurare le impostazioni di rete](#configure-network-settings)
- [Configurazione del servizio informazioni sulla posizione](#configure-location-information-service)
- [Configurare i criteri di emergenza](#configure-emergency-policies)
- [Abilitare utenti e siti](#enable-users-and-sites)
- [Testare le chiamate d'emergenza](#test-emergency-calling)

La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP, Public Safety Answering Point) varia a seconda del paese di utilizzo dell'utente di Teams.

Per ulteriori informazioni sulle chiamate di emergenza, incluse informazioni sugli indirizzi di emergenza e il routing delle chiamate di emergenza, informazioni specifiche per i paesi e informazioni sulle impostazioni di rete e la topologia di rete, vedere quanto segue:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire le impostazioni di rete per le funzionalità vocali nel cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)

## <a name="supported-clients"></a>Client supportati

Sono attualmente supportati i client seguenti.  Controllare spesso la disponibilità di aggiornamenti per questo elenco.

- Client desktop di Teams per Microsoft Windows
- Client desktop di Teams per Apple macOS
- Client teams per dispositivi mobili Apple iOS versione 1.0.92.2019121004 e App Store versione 1.0.92 e successive
- Client teams per dispositivi mobili Android e Google Play Store versione 1416/1.0.0.2019121201 e successive
- Telefono Teams versione 1449/1.0.94.2019110802 e versioni successive
- Teams Rooms versione 4.4.25.0 e successive

> [!NOTE]
> Le chiamate di emergenza dinamiche, tra cui le notifiche dei desk di sicurezza, non sono supportate nel client Web di Teams. Per impedire agli utenti di usare il client Web di Teams per chiamare i numeri PSTN, è possibile impostare un criterio di chiamata di Teams e disattivare l'impostazione Consenti chiamate **PSTN** Web. Per ulteriori informazioni, consulta [Criteri di chiamata in Teams](teams-calling-policy.md) e [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

## <a name="assign-emergency-addresses"></a>Assegnare indirizzi per gli interventi di emergenza

È possibile assegnare indirizzi di emergenza sia agli utenti del Piano per chiamate che agli identificatori di rete necessari per ottenere dinamicamente una posizione. Sono supportate le opzioni Subnet e WiFi. Al momento, il cambio/porta Ethernet è supportato in Windows 8.1 e versioni successive).

Per supportare il routing automatico delle chiamate di emergenza negli Stati Uniti, è necessario verificare che le posizioni di emergenza assegnate agli identificatori di rete includano i codici geografici associati. Gli indirizzi di emergenza senza codici geografici non possono essere assegnati agli identificatori di rete necessari per le posizioni dinamiche.

Mappe di Azure viene usato per i servizi basati sulla posizione.  Quando si immette un indirizzo per gli interventi di emergenza tramite l'interfaccia di amministrazione di Microsoft Teams, Teams verifica l'indirizzo in Azure Maps:

- Se viene trovata una corrispondenza, i codici geografici vengono inclusi automaticamente.

- Se non viene trovata una corrispondenza, potrai creare manualmente un indirizzo per gli interventi di emergenza. A questo scopo, è possibile usare la funzionalità di eliminazione dei PIN. 

Questo significa che se una posizione di emergenza esistente creata per l'assegnazione agli utenti del Piano per chiamate è destinata a una posizione dinamica, lo stesso indirizzo deve essere ri-creato per includere i codici geografici. Per distinguere le due posizioni, è necessario includere una descrizione diversa. La nuova posizione per gli interventi di emergenza può essere assegnata agli utenti che hanno la posizione precedente. Al termine della migrazione, la posizione precedente può essere eliminata.

È possibile aggiungere e assegnare indirizzi per gli interventi di emergenza nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell. Per ulteriori informazioni, consulta Aggiungere una posizione per gli interventi di emergenza per [l'organizzazione](add-change-remove-emergency-location-organization.md) e assegnare una posizione [per gli interventi di emergenza a un utente.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Configurare le impostazioni di rete

Le impostazioni di rete vengono usate per determinare la posizione di un client Teams e per ottenere dinamicamente i criteri per le chiamate di emergenza e una posizione per gli interventi di emergenza. È possibile configurare le impostazioni di rete in base al modo in cui l'organizzazione vuole che funzionino le chiamate di emergenza.

Le impostazioni di rete includono siti che includono una raccolta di subnet, che vengono usate esclusivamente per l'assegnazione dinamica dei criteri agli utenti. Ad esempio, un criterio per le chiamate di emergenza e un criterio di instradamento delle chiamate di emergenza potrebbero essere assegnati al "sito Redmond" in modo che tutti gli utenti che effettuano il roaming da casa o da un'altra sede Microsoft siano configurati con numeri di emergenza, instradamento e desk di sicurezza specifici di Redmond.  

>[!Note]
>Le subnet possono anche essere definite in LIS e possono essere associate a una posizione per gli interventi di emergenza.  

Tenere presenti le definizioni seguenti. Per ulteriori informazioni, consulta [Impostazioni di rete per le funzionalità vocali cloud.](cloud-voice-network-settings.md)

- Gli indirizzi IP attendibili contengono una raccolta di indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Il tentativo di ottenere un criterio o una posizione dinamica verrà eseguito solo se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP nell'indirizzo IP attendibile. Una corrispondenza può essere effettuata rispetto agli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete.  Se un indirizzo IP pubblico include sia IPv4 che IPv6, è necessario aggiungerli entrambi come indirizzi IP attendibili.

- Un'area di rete contiene una raccolta di siti di rete. 

- Un sito di rete rappresenta una posizione in cui l'organizzazione ha un valore fisico, ad esempio un ufficio, una serie di edifici o un campus. Questi siti sono definiti come una raccolta di subnet IP.

- Una subnet di rete deve essere associata a un sito di rete specifico. La posizione di un client viene determinata in base alla subnet di rete e al sito di rete associato.  

È possibile configurare le impostazioni di rete nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell. Per altre informazioni, vedere [Gestire la topologia di rete per le caratteristiche vocali nel cloud.](manage-your-network-topology.md)

Tenere presente che per la propagazione e la disponibilità di alcune modifiche alle impostazioni di rete (ad esempio un nuovo indirizzo, un identificatore di rete e così via) può essere necessario del tempo (fino a un paio di ore) per la propagazione e la disponibilità ai client di Teams.  

**Per gli utenti del Piano per chiamate:**

- Se è necessaria la configurazione dinamica della notifica security desk, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili.

- Se nessuna di queste opzioni è richiesta, non è necessario configurare le impostazioni di rete. 

**Per gli utenti con routing diretto:**

- Se è necessaria l'abilitazione dinamica delle chiamate di emergenza o la configurazione dinamica della notifica security desk, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.

- Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili.

- Se nessuna di queste opzioni è richiesta, non è necessario configurare le impostazioni di rete.


## <a name="configure-location-information-service"></a>Configurazione del servizio informazioni sulla posizione

Un client Teams ottiene gli indirizzi di emergenza dalle posizioni associate a diversi identificatori di rete. Sono supportati sia subnet che punti di accesso wireless (WAP). Al momento, il cambio/porta Ethernet è supportato in Windows 8.1 e versioni successive.

Per ottenere una posizione da un cliente, è necessario popolare il sistema LIS con identificatori di rete (subnet, WAP, switch, porte) e posizioni per gli interventi di emergenza. È possibile farlo nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare **a Percorsi**  >  **& percorsi.**
2. Fare clic sulla scheda che rappresenta l'identificatore di rete da aggiungere. Ad esempio, fare clic **su Subnet,** **punti di accesso #A0**, **Parametri** o **Porte.** Quindi fare clic **su Aggiungi.**
3. Completare i campi, aggiungere una posizione per gli interventi di emergenza e quindi fare clic **su Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Usare i cmdlet seguenti per aggiungere porte, switch, subnet e WAP al sistema LIS.

- [Ottieni,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps) [Imposta,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps) [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Ottieni,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps) [Imposta,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps) [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Ottieni,](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps) [Imposta,](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps) [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Ottieni,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps) [Imposta,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps) [Rimuovi](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLis Piùele

>[!Important]
>Se le subnet vengono usate come parte dei siti di rete, devono essere ridefinite nel servizio informazioni sulla posizione per il rendering delle posizioni dinamiche.

## <a name="configure-emergency-policies"></a>Configurare i criteri di emergenza

Utilizza i seguenti criteri per configurare le chiamate di emergenza. È possibile gestire questi criteri nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.

- **Criteri per l'instradamento delle chiamate** di emergenza- Si applica solo all'instradamento diretto. Questo criterio configura i numeri di emergenza, le maschere per numero, se necessario, e la route PSTN per numero.  È possibile assegnare questo criterio agli utenti, ai siti di rete o a entrambi. (I client di Teams dei piani per chiamate sono abilitati automaticamente per le chiamate di emergenza con i numeri di emergenza del Paese in base alla loro posizione di utilizzo di Microsoft 365 o Office 365.)  Per ulteriori informazioni, consulta [Gestire i criteri di instradamento delle chiamate di emergenza per l'instradamento diretto.](manage-emergency-call-routing-policies.md)

- **Criteri per le chiamate di emergenza** - Si applica ai piani per chiamate e all'instradamento diretto. Questo criterio configura l'esperienza di notifica al desk sicurezza durante una chiamata di emergenza. È possibile impostare le persone a cui inviare una notifica e la modalità di notifica. Ad esempio, per inviare automaticamente una notifica al desk sicurezza dell'organizzazione e fare in modo che ascolti le chiamate di emergenza.  Questo criterio può essere assegnato a utenti o siti di rete o a entrambi. Per ulteriori informazioni, consulta [Gestire i criteri per le chiamate di emergenza in Teams.](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>Abilitare utenti e siti

È possibile assegnare criteri di instradamento delle chiamate di emergenza e criteri per le chiamate di emergenza agli utenti e ai siti. Tenere presente che i criteri di instradamento delle chiamate di emergenza si applicano solo all'instradamento diretto. Sebbene sia possibile assegnare questo criterio a un utente di un Piano per chiamate, il criterio non avrà alcun effetto.

È possibile assegnare criteri nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell. Per altre informazioni, vedere:

- [Gestire i criteri di instradamento delle chiamate di emergenza per l'instradamento diretto](manage-emergency-call-routing-policies.md)
- [Gestire i criteri per le chiamate di emergenza in Teams](manage-emergency-calling-policies.md)

Ecco alcuni esempi di PowerShell.

Per abilitare una notifica di security desk a un utente specifico, usare il comando seguente:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Per assegnare al sito 1 un criterio denominato "Criterio chiamate di emergenza Contoso 1", usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Per abilitare uno specifico utente di instradamento diretto per le chiamate di emergenza, utilizza il seguente comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Per assegnare un criterio denominato "Instradamento chiamate di emergenza Contoso New York" al sito 1, usare il comando seguente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e tale utente è in quel sito di rete, il criterio assegnato al sito di rete sovrascrive il criterio assegnato all'utente.

## <a name="test-emergency-calling"></a>Testare le chiamate d'emergenza

Alcuni provider di servizi di emergenza (ESP) negli Stati Uniti offrono un bot di prova per le chiamate di emergenza.

- **Gli utenti del** Piano per chiamate negli Stati Uniti possono utilizzare il numero di emergenza di prova predefinito 933 per convalidare la configurazione delle chiamate di emergenza. Questo numero viene instradato a un bot, che poi fa eco al numero di telefono del chiamante (ID linea chiamante), all'indirizzo o alla posizione per gli interventi di emergenza e indica se la chiamata verrebbe automaticamente instradata al PSAP o prima schermata.

- **I clienti di routing diretto negli Stati Uniti** devono coordinarsi con la propria richiesta di assistenza per un servizio di test.

 ## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di instradamento delle chiamate di emergenza ](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione per gli interventi di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Impostazioni di rete per le funzionalità vocali del cloud](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud](manage-your-network-topology.md)
