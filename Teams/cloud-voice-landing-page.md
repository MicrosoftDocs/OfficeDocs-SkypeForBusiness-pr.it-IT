---
title: Pianificare la soluzione vocale in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Altre informazioni sulle funzionalità vocali Microsoft Teams cloud e sulle decisioni di distribuzione che verranno prese per l'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f6d857e11545df9c338dd2c75b089d8bef0247e
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518798"
---
# <a name="plan-your-teams-voice-solution"></a>Pianificare la soluzione Teams vocale

Questo articolo consente di decidere quale soluzione vocale Microsoft è ideale per l'organizzazione. Dopo aver deciso, l'articolo fornisce una roadmap per il contenuto che consente di implementare la soluzione scelta.

Potresti volere la soluzione più semplice Sistema telefonico&mdash; piano per chiamate. Questa opzione è la soluzione all-in-the-cloud di Microsoft che fornisce funzionalità PBX (Private Branch Exchange) e chiamate alla rete PSTN (Public Switched Telephone Network), come illustrato nel diagramma seguente. Con questa soluzione, Microsoft è il gestore PSTN.

![Il diagramma 1 mostra Sistema telefonico piano chiamate.](media/voice-solutions-simple.png)

Se si risponde sì a quanto segue, Sistema telefonico piano per chiamate è la soluzione giusta per te:

- Piano chiamate è disponibile nella tua area geografica.
- Non è necessario conservare il gestore PSTN corrente.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Tuttavia, la situazione potrebbe essere più complessa. Ad esempio, potresti avere uffici in località in cui il piano per chiamate non è disponibile. In caso contrario, potrebbe essere necessaria una soluzione combinata che supporti una distribuzione complessa e nazionale, con requisiti diversi per posizioni geografiche diverse. Microsoft supporta una combinazione di soluzioni:

- Sistema telefonico piano chiamate
- Sistema telefonico con il proprio gestore PSTN con Connessione con operatore
- Sistema telefonico con il proprio gestore PSTN con Routing diretto
- Una soluzione combinata che usa Sistema telefonico piano per chiamate, Sistema telefonico con Connessione con operatore e/o Sistema telefonico con Direct Routing

>[!NOTE]
>Se sei una piccola e media impresa (300 o meno persone), Microsoft ora include Sistema telefonico piano per chiamate nazionali. Per altre informazioni[, vedere le](/microsoftteams/business-voice/whats-business-voice) Sistema telefonico per le piccole e medie imprese che consentono di pianificare, configurare e gestire la soluzione vocale.

## <a name="what-do-you-need-to-read"></a>Cosa è necessario leggere?

**Obbligatorio per tutti.** Alcune delle sezioni di questo articolo riguardano tutte le organizzazioni. Ad esempio, tutti dovrebbero leggere le informazioni Sistema telefonico e comprendere le opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).


| Obbligatorio per tutti | Descrizione |
| :------------|:-------|
| [**Sistema telefonico**](#phone-system) | Tecnologia Microsoft per l'abilitazione del controllo delle chiamate e delle funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 con Microsoft Teams. |
| [**Opzioni di connettività PSTN (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Scegliere Microsoft come gestore di telefonia o connettere il proprio gestore di telefonia a Microsoft Teams tramite Connessione con operatore o Routing diretto. In combinazione con Sistema telefonico, le opzioni di connettività PSTN consentono agli utenti di effettuare chiamate telefoniche in tutto il mondo.|

**A seconda dei requisiti.** Alcune delle sezioni di questo articolo e degli articoli correlati sono pertinenti a seconda della distribuzione e dei requisiti esistenti. Ad esempio, Location-Based routing diretto è necessario solo per i clienti di Routing diretto in posizioni geografiche che non consentono il bypass a pedaggio.

Valutare quali di queste altre configurazioni potrebbero essere necessarie:

![Il diagramma 2 mostra altri componenti vocali, ad esempio i numeri Telefono microsoft, i piani di chiamata e il routing delle chiamate e così via.](media/voice-consider-additional-components.png)

| A seconda dei requisiti | Descrizione |
| :------------|:-------|
| [**Telefono gestione dei numeri**](pstn-connectivity.md#phone-number-management) | Come ottenere e gestire i numeri di telefono varia a seconda dell'opzione di connettività PSTN. Leggere questa sezione se è necessario ottenere numeri di telefono, trasferire numeri esistenti, ottenere numeri di servizio e così via. |
| [**Routing delle chiamate e dial plan**](pstn-connectivity.md#call-routing-and-dial-plans) | Come configurare e gestire i piani di chiamata che traducono i numeri di telefono dialed in un formato alternativo (in genere formato E.164) per l'autorizzazione delle chiamate e il routing delle chiamate. Leggere questa sezione se è necessario comprendere quali sono i piani di chiamata e se è necessario specificare i piani di chiamata per l'organizzazione.|
| [**Chiamate di emergenza**](pstn-connectivity.md#emergency-calling) | Le modalità di gestione e configurazione delle chiamate di emergenza variano a seconda dell'opzione di connettività PSTN. Leggere questa sezione per informazioni su come gestire le chiamate di emergenza per l'organizzazione. |
| [**Routing in base alla posizione per il routing diretto**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Come usare il routing Location-Based (LBR) per limitare il bypass a pedaggio per Microsoft Teams utenti in base alla loro posizione geografica. Leggere questa sezione se l'organizzazione usa Il routing diretto in una posizione che non consente il bypass a pedaggio.
| [**Topologia di rete per le funzionalità vocali cloud**](pstn-connectivity.md#network-topology-for-voice-features) | Se l'organizzazione distribuisce Location-Based Routing (LBR) per il routing diretto o le chiamate di emergenza dinamiche, è necessario configurare le impostazioni di rete per queste funzionalità in Microsoft Teams. Leggere questa sezione se si sta implementando LBR per il routing diretto o se si stanno implementando chiamate di emergenza dinamiche con piano chiamate o routing diretto. |
| [**Eseguire la migrazione della soluzione vocale esistente**](#migrate-your-existing-voice-solution-to-teams) | Cosa occorre pensare quando si esegue la migrazione della soluzione vocale a Teams.  Leggere questa sezione se si esegue la migrazione da una soluzione vocale esistente a Teams. 

> [!Important]
> Questo articolo è in particolare sulle soluzioni vocali con Microsoft Teams. A causa del ritiro di Skype for Business Online il 31 luglio 2021, la connettività PSTN&mdash; tra l'ambiente locale e Skype for Business Server o Cloud Connector Edition&mdash; e Skype for Business Online non è più supportata. Questo articolo illustra Teams e come connettere la rete di telefonia locale, se necessario, a Teams usando Connessione con operatore o Routing diretto.


## <a name="phone-system"></a>Sistema telefonico

Sistema telefonico è la tecnologia Microsoft per l'abilitazione del controllo delle chiamate e delle funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 con Microsoft Teams.

Sistema telefonico funziona con Teams client e dispositivi certificati. Sistema telefonico consente di sostituire il sistema PBX esistente con un set di funzionalità direttamente Microsoft 365. 

Le chiamate tra utenti dell'organizzazione, indipendentemente dall'area geografica, vengono gestite internamente all'interno Sistema telefonico. Queste chiamate interne non passano mai alla rete PSTN (Public Switched Telephone Network), quindi l'azienda evita addebiti a lunga distanza.

In questo articolo vengono presentate le Sistema telefonico caratteristiche e funzionalità principali e le decisioni di distribuzione da prendere in considerazione:

- [Operatori automatici e code delle chiamate](#auto-attendants-and-call-queues)
- [Cloud Voicemail](#cloud-voicemail)
- [Identità chiamante](#calling-identity)

![Il diagramma 3 mostra Telefono sistema contiene operatori automatici e query di chiamata, segreteria telefonica cloud e identità di chiamata.](media/phone-system-contains.png)

Per informazioni su tutte le Sistema telefonico e su come configurare Sistema telefonico, vedere gli articoli seguenti:

- [Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)
- [Configurare Sistema telefonico nell'organizzazione](setting-up-your-phone-system.md)<br>
  Descrive come acquistare e assegnare Sistema telefonico licenze, gestire i numeri di telefono e impostare i crediti di comunicazione per i numeri verde. 

Per informazioni sulla gestione dei dispositivi supportati, vedere [Gestire i dispositivi in Microsoft Teams](devices/device-management.md) e [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Operatori automatici e code di chiamata

Gli operatori automatici consentono di configurare le opzioni di menu per instradare le chiamate in base all'input del chiamante. Le code di chiamata sono aree di attesa per i chiamanti. Usati insieme, gli operatori automatici e le code di chiamata possono instradare facilmente i chiamanti alla persona o al reparto appropriato dell'organizzazione.

Per informazioni sugli operatori automatici e sulle code di chiamata, vedere gli articoli seguenti:

- [Pianificare Teams operatori automatici e code di chiamata](plan-auto-attendant-call-queue.md)
- [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md) 
- [Case study contoso: Operatori automatici e code di chiamata](voice-case-study-call-queues.md)<br>
  Descrive come un'azienda multinazionale fittizia, Contoso, ha implementato operatori automatici e code di chiamata per la soluzione vocale.

### <a name="cloud-voicemail"></a>Cloud Voicemail

Cloud Voicemail, basato sui servizi di segreteria telefonica di Azure, supporta i depositi di segreteria telefonica solo Exchange cassette postali. Non supporta sistemi di posta elettronica di terze parti. 

La Cloud Voicemail include la trascrizione della segreteria telefonica che è abilitata di default per tutti gli utenti dell’organizzazione. Le esigenze aziendali potrebbero richiedere la disabilitazione della trascrizione della segreteria telefonica per utenti specifici o per tutti gli utenti dell'organizzazione.

Cloud Voicemail viene configurato ed eseguito automaticamente il provisioning per Teams utenti.  

Per altre informazioni sulle Cloud Voicemail e sulla relativa configurazione, vedere gli articoli seguenti:

- [Configurare Cloud Voicemail](set-up-phone-system-voicemail.md)
- [Impostare i criteri della segreteria telefonica nell'organizzazione](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Identità chiamante

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante). Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata. Per informazioni sulla configurazione dell'ID chiamante o per modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opzioni di connettività rete telefonica a commutazione pubblica

Sistema telefonico offre funzionalità PBX complete per l'organizzazione. Tuttavia, per consentire agli utenti di effettuare chiamate all'esterno dell'organizzazione, è necessario connettersi Sistema telefonico rete PSTN (Public Switched Telephone Network). Per connettersi Sistema telefonico alla rete PSTN, è possibile scegliere una delle opzioni seguenti:

- [**Sistema telefonico piano chiamate**](pstn-connectivity.md#phone-system-with-calling-plan). Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- [**Sistema telefonico con il proprio gestore PSTN usando Connessione con operatore**](operator-connect-plan.md). Con Connessione con operatore, se l'operatore esistente partecipa al programma Microsoft Connessione con operatore, può gestire il servizio per portare le chiamate PSTN in Teams. Per informazioni sui vantaggi e i requisiti di Connessione con operatore[, vedere Pianificare](operator-connect-plan.md) Connessione con operatore.

- [**Sistema telefonico con il proprio gestore PSTN usando Il**](pstn-connectivity.md#phone-system-with-direct-routing) routing diretto per connettere l'ambiente locale a Teams.

È possibile scegliere una combinazione di opzioni, che consente di progettare una soluzione per un ambiente complesso o di gestire una migrazione in più passaggi. Leggere altre informazioni sulla migrazione in un secondo momento.

La Sistema telefonico caratteristiche sono le stesse indipendentemente dall'opzione di connettività PSTN scelta. Esistono tuttavia alcune differenze di funzionalità che influiscono sulla configurazione di alcune funzionalità Sistema telefonico, ad esempio il routing delle chiamate e le chiamate di emergenza. Per altre informazioni sulle opzioni di connettività PSTN e sulle considerazioni sulla configurazione, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Eseguire la migrazione della soluzione vocale esistente a Teams

> [!NOTE]
> Per indicazioni sulla pianificazione di una soluzione vocale Teams come parte del piano generale per l'aggiornamento a Teams da Skype for Business Server, vedere Considerazioni [su PSTN](upgrade-to-teams-on-prem-pstn-considerations.md) per l'aggiornamento a Teams da Skype for Business locale.

Per un'organizzazione che esegue l'aggiornamento a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly. L Sistema telefonico è supportato solo quando l'utente è in modalità TeamsOnly. Per informazioni di base sull'aggiornamento a Teams, iniziare da qui:

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Informazioni sul framework di aggiornamento](upgrade-framework.md)
- [Strategie di aggiornamento per gli amministratori IT](upgrade-to-teams-on-prem-implement.md)

Quando si esegue la migrazione della soluzione vocale, ci sono quattro possibili scenari di chiamata quando si attiva la modalità TeamsOnly:

- [**Un utente in Skype for Business Online, con un piano per chiamate Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Al momento dell'aggiornamento, questo utente continuerà a disporre di un piano per chiamate Microsoft.

- **[Un utente in Skype for Business Online,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente Teams deve essere coordinato con la migrazione dell'utente al routing diretto per assicurarsi che l'utente TeamsOnly abbia la funzionalità PSTN.

- **[Un utente in Skype for Business locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** con VoIP aziendale, che si trasferirà online e mantiene la connettività PSTN locale. La migrazione di questo utente a Teams richiede lo spostamento dell'account di Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con la migrazione dell'utente al routing diretto. 

- **[Un utente in Skype for Business locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** con VoIP aziendale, che si trasferirà online e usa un piano per chiamate Microsoft.  La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con A) la porta del numero di telefono dell'utente a un piano per chiamate Microsoft o B) assegnando un nuovo numero di abbonato dalle aree geografiche disponibili.

Per altre informazioni su come implementare la migrazione vocale per ognuno di questi scenari, vedere gli articoli seguenti:

- [Considerazioni su PSTN durante l'aggiornamento a Teams, per gli amministratori IT](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Case study sulla migrazione vocale di Contoso](voice-case-study-overview.md)<br>
  Il case study descrive in che modo una multinazionale fittizia, Contoso, ha implementato una soluzione vocale Teams per l'organizzazione. Contiene gli articoli seguenti:

  - [Teams di aggiornamento](voice-case-study-migration-plan.md)
  - [Sistema telefonico di connettività PSTN](voice-case-study-phone-system.md)
  - [Implementazione del routing in base alla posizione](voice-case-study-location-based-routing.md)
  - [Chiamate di emergenza](voice-case-study-emergency-calling.md)
  - [Operatori automatici e code delle chiamate](voice-case-study-call-queues.md)
  - [Audioconferenza](voice-case-study-audio-conferencing.md)
