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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Altre informazioni sulle funzionalità vocali cloud di Microsoft Teams e sulle decisioni di distribuzione che verranno prese per l'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a159a6e2c5f532205c8e0cdadf744a2e6e6f3c0a
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551670"
---
# <a name="plan-your-teams-voice-solution"></a>Pianificare la soluzione vocale di Teams

Questo articolo aiuta a decidere quale soluzione microsoft voice è adatta per la propria organizzazione. Dopo aver deciso, l'articolo fornisce una roadmap per il contenuto che consentirà di implementare la soluzione scelta.

Potresti volere la soluzione&mdash;più semplice Sistema telefonico con piano per chiamate. Questa opzione è la soluzione all-in-the-cloud di Microsoft che fornisce la funzionalità PBX (Private Branch Exchange) e le chiamate alla rete PSTN (Public Switched Telephone Network), come illustrato nel diagramma seguente. Con questa soluzione, Microsoft è il tuo gestore PSTN.

![Il diagramma 1 mostra sistema telefonico con piano per chiamate.](media/voice-solutions-simple.png)

Se rispondi sì a quanto segue, sistema telefonico con piano per chiamate è la soluzione giusta per te:

- Il piano per chiamate è disponibile nella tua area geografica.
- Non è necessario conservare l'attuale gestore PSTN.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Tuttavia, la situazione potrebbe essere più complessa. Ad esempio, potresti avere uffici in posizioni in cui il Piano per chiamate non è disponibile. Oppure potrebbe essere necessaria una soluzione combinata che supporti una distribuzione complessa e multinazionale, con requisiti diversi per diverse aree geografiche. Microsoft supporta una combinazione di soluzioni:

- Sistema telefonico con piano per chiamate
- Sistema telefonico con il tuo operatore PSTN con Operator Connect
- Sistema telefonico con il proprio operatore di telefonia mobile PSTN con Teams Phone Mobile 
- Sistema telefonico con il tuo operatore PSTN con Direct Routing
- Una soluzione combinata che usa sistema telefonico con piano per chiamate, sistema telefonico con Operator Connect e/o sistema telefonico con routing diretto

Per un riepilogo visivo di tutte le opzioni della soluzione vocale, vedere il poster delle soluzioni vocali.

[![Poster di Microsoft Voice Solutions.](media/microsoft-voice-solutions-thumb.png)](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br> [PDF](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br>[Visio](https://download.microsoft.com/download/7/5/c/75c13012-e20c-48bd-a6dd-ea49d1a3420d/microsoft-voice-solutions.vsdx) 
<br>

>[!NOTE]
>Se sei un'azienda di piccole e medie dimensioni (almeno 300 persone), Microsoft ora include sistema telefonico con un piano per chiamate nazionali. Per altre informazioni, vedi [Linee guida del sistema telefonico per piccole e medie imprese](/microsoftteams/business-voice/whats-business-voice) che consentono di pianificare, configurare e gestire la soluzione vocale.

## <a name="what-do-you-need-to-read"></a>Cosa è necessario leggere?

**Obbligatorio per tutti.** Alcune sezioni di questo articolo riguardano tutte le organizzazioni. Ad esempio, tutti devono leggere informazioni su Sistema telefonico e comprendere le opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).


| Obbligatorio per tutti | Descrizione |
| :------------|:-------|
| [**Sistema telefonico**](#phone-system) | La tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 con Microsoft Teams. |
| [**Opzioni di connettività PSTN (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Scegli Microsoft come gestore di telefonia o collega il tuo operatore di telefonia a Microsoft Teams utilizzando Operator Connect o Direct Routing. In combinazione con sistema telefonico, le opzioni di connettività PSTN consentono agli utenti di effettuare telefonate in tutto il mondo.|

**A seconda delle esigenze.** Alcune sezioni di questo articolo e gli articoli correlati sono pertinenti a seconda della distribuzione e dei requisiti esistenti. Ad esempio, Location-Based Routing è necessario solo per i clienti di Direct Routing in posizioni geografiche che non consentono il bypass a pagamento.

Considerare quali di queste altre configurazioni potrebbero essere necessarie:

![Il diagramma 2 mostra altri componenti vocali, ad esempio i numeri di telefono di Microsoft, i piani di chiamata e il routing delle chiamate e così via.](media/voice-consider-additional-components.png)

| A seconda dei requisiti | Descrizione |
| :------------|:-------|
| [**Gestione dei numeri di telefono**](pstn-connectivity.md#phone-number-management) | La procedura per ottenere e gestire i numeri di telefono varia in base all'opzione di connettività PSTN. Leggi questa sezione se devi ottenere numeri di telefono, trasferire numeri esistenti, ottenere numeri di servizio e così via. |
| [**Routing delle chiamate e piani di chiamata**](pstn-connectivity.md#call-routing-and-dial-plans) | Come configurare e gestire piani di chiamata che traducono numeri di telefono composizionati in un formato alternativo (in genere formato E.164) per l'autorizzazione delle chiamate e il routing delle chiamate. Leggere questa sezione se è necessario conoscere i piani di chiamata e specificare se è necessario specificare i piani di chiamata per l'organizzazione.|
| [**Chiamate di emergenza**](pstn-connectivity.md#emergency-calling) | La modalità di gestione e configurazione delle chiamate di emergenza varia in base all'opzione di connettività PSTN. Leggere questa sezione per informazioni su come gestire le chiamate di emergenza per l'organizzazione. |
| [**Routing basato sulla posizione per il routing diretto**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Come usare Location-Based Routing (LBR) per limitare il bypass a pagamento per gli utenti di Microsoft Teams in base alla loro posizione geografica. Leggi questa sezione se l'organizzazione usa l'instradamento diretto in una località che non consente il bypass a pagamento.
| [**Topologia di rete per le funzionalità di voce cloud**](pstn-connectivity.md#network-topology-for-voice-features) | Se l'organizzazione sta distribuendo Location-Based Routing (LBR) per il routing diretto o le chiamate di emergenza dinamiche, è necessario configurare le impostazioni di rete per queste funzionalità in Microsoft Teams. Leggi questa sezione se stai implementando LBR per il routing diretto o se stai implementando chiamate di emergenza dinamiche con il piano per chiamate o il routing diretto. |
| [**Eseguire la migrazione della soluzione vocale esistente**](#migrate-your-existing-voice-solution-to-teams) | Cosa occorre pensare quando si esegue la migrazione della soluzione vocale a Teams.  Leggi questa sezione se stai eseguendo la migrazione da una soluzione vocale esistente a Teams. 

> [!Important]
> Questo articolo è incentrato sulle soluzioni vocali con Microsoft Teams. A causa del ritiro di Skype for Business Online il 31 luglio 2021, la connettività PSTN tra l'ambiente&mdash;locale tramite Skype for Business Server o Cloud Connector Edition&mdash;e Skype for Business Online non è più supportata. Questo articolo introduce le soluzioni vocali di Teams e come collegare la rete telefonica locale, se necessario, a Teams usando Operator Connect o Direct Routing.


## <a name="phone-system"></a>Sistema telefonico

Phone System è la tecnologia microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 con Microsoft Teams.

Sistema telefonico funziona con i client di Teams e i dispositivi certificati. Sistema telefonico consente di sostituire il sistema PBX esistente con un set di funzionalità direttamente fornite da Microsoft 365. 

Le chiamate tra gli utenti dell'organizzazione, indipendentemente dall'area geografica, vengono gestite internamente all'interno del sistema telefonico. Queste chiamate interne non vengono mai recapitate nella rete PSTN (Public Switched Telephone Network), pertanto l'azienda non deve pagare costi per le chiamate interurbane.

Questo articolo presenta le caratteristiche e le funzionalità principali di Sistema telefonico seguenti e le decisioni di distribuzione che è necessario prendere in considerazione:

- [Operatori automatici e code delle chiamate](#auto-attendants-and-call-queues)
- [Cloud Voicemail](#cloud-voicemail)
- [Identità chiamante](#calling-identity)

![Il diagramma 3 mostra che il sistema telefonico contiene operatori automatici e query di chiamata, segreteria telefonica cloud e identità per le chiamate.](media/phone-system-contains.png)

Per informazioni su tutte le funzionalità di Sistema telefonico e su come configurare Sistema telefonico, vedi gli articoli seguenti:

- [Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)
- [Configurare Sistema telefonico nell'organizzazione](setting-up-your-phone-system.md)<br>
  Descrive come acquistare e assegnare licenze sistema telefonico, gestire numeri di telefono e configurare crediti comunicazioni per i numeri verdi. 

Per informazioni sulla gestione dei dispositivi supportati, vedere [Gestire i dispositivi in Microsoft Teams](devices/device-management.md) e [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Operatori automatici e code di chiamata

Gli operatori automatici consentono di impostare le opzioni di menu per instradare le chiamate in base all'input del chiamante. Le code di chiamata sono aree di attesa per i chiamanti. Usati insieme, gli operatori automatici e le code di chiamata possono facilmente instradare i chiamanti alla persona o al reparto appropriato dell'organizzazione.

Per informazioni sugli operatori automatici e le code di chiamata, vedi gli articoli seguenti:

- [Pianificare gli operatori automatici di Teams e le code di chiamata](plan-auto-attendant-call-queue.md)
- [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md) 
- [Case study di Contoso: Operatori automatici e code di chiamata](voice-case-study-call-queues.md)<br>
  Descrive in che modo una società multinazionale fittizia, Contoso, ha implementato operatori automatici e code di chiamata per la soluzione vocale.

### <a name="cloud-voicemail"></a>Cloud Voicemail

Cloud Voicemail, con tecnologia Azure Voicemail, supporta i depositi di messaggi vocali solo nelle cassette postali di Exchange. Non supporta i sistemi di posta elettronica di terze parti. 

La Cloud Voicemail include la trascrizione della segreteria telefonica che è abilitata di default per tutti gli utenti dell’organizzazione. Per le esigenze aziendali potrebbe essere necessario disabilitare la trascrizione della segreteria telefonica per utenti specifici o per tutti gli utenti dell'organizzazione.

Cloud Voicemail viene configurato e eseguito automaticamente il provisioning per gli utenti di Teams.  

Per altre informazioni su Cloud Voicemail e sulla relativa configurazione, vedere gli articoli seguenti:

- [Configurare Cloud Voicemail](set-up-phone-system-voicemail.md)
- [Impostare i criteri della segreteria telefonica nell'organizzazione](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Identità chiamante

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante). Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata. Per informazioni sulla configurazione dell'ID chiamante o sulla modifica o il blocco dell'ID chiamante, vedere [Impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opzioni di connettività public Switched Telephone Network

Sistema telefonico fornisce funzionalità PBX complete per la tua organizzazione. Tuttavia, per consentire agli utenti di effettuare chiamate all'esterno dell'organizzazione, è necessario connettere Sistema telefonico alla rete PSTN (Public Switched Telephone Network). Per connettere Sistema telefonico alla rete PSTN, è possibile scegliere una delle opzioni seguenti:

- [**Sistema telefonico con piano per chiamate**](pstn-connectivity.md#phone-system-with-calling-plan). Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- [**Sistema telefonico con il tuo operatore PSTN tramite Operator Connect**](operator-connect-plan.md). Con Operator Connect, se l'operatore esistente partecipa al programma Microsoft Operator Connect, può gestire il servizio per portare le chiamate PSTN in Teams. 

- [**Sistema telefonico con il tuo operatore di telefonia mobile PSTN usando Teams Phone Mobile**](operator-connect-mobile-plan.md). Con Teams Phone Mobile, se il tuo operatore esistente partecipa al programma Telefono di Microsoft Teams Mobile, può gestire il servizio per l'uso dei numeri di cellulare abilitati per la SIM con Teams. 

- [**Sistema telefonico con il proprio operatore PSTN tramite Direct Routing**](pstn-connectivity.md#phone-system-with-direct-routing) per connettere l'ambiente locale a Teams.


È possibile scegliere una combinazione di opzioni che consente di progettare una soluzione per un ambiente complesso o di gestire una migrazione in più passaggi. Leggere altre informazioni sulla migrazione in un secondo momento.

La maggior parte delle funzionalità di Sistema telefonico sono uguali indipendentemente dall'opzione di connettività PSTN scelta. Esistono tuttavia alcune differenze di funzionalità che influiscono sulla configurazione di determinate funzionalità di Sistema telefonico, ad esempio il routing delle chiamate e le chiamate di emergenza. Per altre informazioni sulle opzioni di connettività PSTN e considerazioni sulla configurazione, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Eseguire la migrazione della soluzione vocale esistente a Teams

> [!NOTE]
> Per indicazioni sulla pianificazione di una soluzione vocale di Teams come parte del piano generale per l'aggiornamento a Teams da Skype for Business Server, vedere [Considerazioni pstn per l'aggiornamento a Teams da Skype for Business locale](upgrade-to-teams-on-prem-pstn-considerations.md).

Per un'organizzazione che esegue l'aggiornamento a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly. L'uso di Sistema telefonico è supportato solo quando l'utente è in modalità TeamsOnly. Se hai bisogno di informazioni di base sull'aggiornamento a Teams, inizia da qui:

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Informazioni sul framework di aggiornamento](upgrade-framework.md)
- [Strategie di aggiornamento per gli amministratori IT](upgrade-to-teams-on-prem-implement.md)

Durante la migrazione della soluzione vocale, ci sono quattro possibili scenari di chiamata quando si passa alla modalità TeamsOnly:

- [**Un utente in Skype for Business online, con un piano per chiamate Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Al momento dell'aggiornamento, l'utente continuerà ad avere un piano per le chiamate Microsoft.

- **[Un utente in Skype for Business Online, con funzionalità vocali locali](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) tramite Skype for Business locale o Cloud Connector Edition**. L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per garantire che l'utente TeamsOnly disponga di funzionalità PSTN.

- **[Un utente in Skype for Business locale con VoIP aziendale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), che si sposterà online mantenendo la connettività PSTN locale**. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con la migrazione dell'utente al routing diretto. 

- **[Un utente in Skype for Business locale con VoIP aziendale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), che passa online e usa un piano per le chiamate Microsoft**.  La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento con A) la porta del numero di telefono dell'utente a un piano per chiamate Microsoft o B) l'assegnazione di un nuovo numero di abbonato dalle aree geografiche disponibili.

Per altre informazioni su come implementare la migrazione vocale per ognuno di questi scenari, vedere gli articoli seguenti:

- [Considerazioni SU PSTN per l'aggiornamento a Teams per gli amministratori IT](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Case study sulla migrazione vocale di Contoso](voice-case-study-overview.md)<br>
  Il case study descrive in che modo una società multinazionale fittizia, Contoso, ha implementato una soluzione vocale di Teams per l'organizzazione. Contiene gli articoli seguenti:

  - [Piano di aggiornamento di Teams](voice-case-study-migration-plan.md)
  - [Opzioni sistema telefonico e connettività PSTN](voice-case-study-phone-system.md)
  - [Implementazione del routing basato sulla posizione](voice-case-study-location-based-routing.md)
  - [Chiamate di emergenza](voice-case-study-emergency-calling.md)
  - [Operatori automatici e code delle chiamate](voice-case-study-call-queues.md)
  - [Audioconferenza](voice-case-study-audio-conferencing.md)
