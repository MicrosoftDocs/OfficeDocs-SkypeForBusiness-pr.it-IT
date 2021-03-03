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
description: Altre informazioni sulle funzionalità vocali cloud di Microsoft Teams e sulle decisioni di distribuzione che verranno prese per l'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd7ebfd4542c38bd56900c1e414dadec09bf246
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50408192"
---
# <a name="plan-your-teams-voice-solution"></a>Pianificare la soluzione vocale di Teams 

Questo articolo ti aiuta a decidere quale soluzione Microsoft Voice è giusta per la tua organizzazione. Dopo aver deciso, l'articolo fornisce una roadmap per i contenuti che consentono di implementare la soluzione scelta.

> [!NOTE]
> Per indicazioni sulla pianificazione di una soluzione voce di Teams come parte del piano complessivo per l'aggiornamento a Teams da Skype for Business Server, consulta considerazioni su PSTN per l'aggiornamento a Teams dalla distribuzione locale di [Skype for Business.](upgrade-to-teams-on-prem-pstn-considerations.md)

Potresti volere la soluzione più semplice sistema telefonico &mdash; con piano per chiamate. Si tratta della soluzione cloud all-in-the-cloud di Microsoft che offre funzionalità PBX (Private Branch Exchange) e chiamate alla rete PSTN (Public Switched Telephone Network), come illustrato nel diagramma seguente. Con questa soluzione, Microsoft è il tuo gestore PSTN.

![Diagramma 1 che mostra Sistema telefonico con Piano per chiamate](media/voice-solutions-simple.png)

Se rispondi sì a quanto segue, allora Sistema telefonico con Piano per chiamate è la soluzione giusta per te:

- Il Piano per chiamate è disponibile nella tua area geografica.
- Non è necessario conservare l'attuale gestore PSTN.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Tuttavia, la situazione potrebbe essere più complessa. Ad esempio, potresti avere uffici in luoghi in cui il Piano per chiamate non è disponibile. Oppure potrebbe essere necessaria una soluzione combinata che supporti una distribuzione complessa e nazionale, con requisiti diversi per diverse aree geografiche. Microsoft supporta una combinazione di soluzioni: 

- Sistema telefonico con piano per chiamate
- Sistema telefonico con il proprio gestore PSTN con instradamento diretto
- Una soluzione combinata che utilizza sia Sistema telefonico con Piano per chiamate che Sistema telefonico con instradamento diretto

## <a name="what-do-you-need-to-read"></a>Cosa occorre leggere?

**Obbligatorio per tutti.** Alcune delle sezioni di questo articolo sono relative a tutte le organizzazioni. Ad esempio, tutti dovrebbero conoscere il Sistema telefonico e comprendere le opzioni di connessione alla rete PSTN (Public Switched Telephone Network). 


| Obbligatorio per tutti | Descrizione |
| :------------|:-------|
| [**Phone System**](#phone-system) | La tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 con Microsoft Teams. |
| [**Opzioni di connettività PSTN (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Scelta tra l'uso di Microsoft come gestore telefonico o la connessione del proprio gestore telefonico a Microsoft Teams tramite l'instradamento diretto. Combinate con Sistema telefonico, le opzioni di connettività PSTN consentono agli utenti di effettuare telefonate in tutto il mondo.|

**A seconda dei requisiti.** Alcune sezioni di questo articolo sono pertinenti a seconda della distribuzione e dei requisiti esistenti. Ad esempio, il Location-Based di distribuzione è necessario solo per i clienti con routing diretto in aree geografiche che non consentono il bypass a pedaggio.

Considerare quali di queste configurazioni aggiuntive potrebbero essere necessarie:

![Il diagramma 2 mostra altri componenti vocali, come i numeri di telefono di Microsoft, i piani di chiamata e l'instradamento delle chiamate e così via.](media/voice-consider-additional-components.png)

| A seconda dei requisiti | Descrizione |
| :------------|:-------|
| [**Numeri di telefono di Microsoft**](#phone-numbers-from-microsoft) | Come ottenere e gestire i numeri di telefono da Microsoft e come trasferire i numeri esistenti in Microsoft. Leggi questa guida se hai bisogno di ottenere numeri di telefono per il Piano per chiamate Microsoft, trasferire numeri esistenti, ottenere numeri di servizio e così via. |
| [**Piani di chiamata e routing delle chiamate**](#dial-plans-and-call-routing) | Come configurare e gestire piani di chiamata che traducono i numeri di telefono composto in un formato alternativo (in genere formato E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate. Leggere questa pagina per informazioni su quali sono i piani di chiamata e se è necessario specificare i piani di chiamata per l'organizzazione.|
| [**Chiamate d'emergenza**](#emergency-calling) | Come gestire e configurare le chiamate di emergenza &mdash; in base all'opzione di connettività PSTN. Leggere questa sezione se si utilizza il Piano per chiamate Microsoft o l'instradamento diretto e occorre sapere come gestire le chiamate di emergenza per l'organizzazione. |
| [**Routing basato sulla posizione per il routing diretto**](#location-based-routing-for-direct-routing) |Come usare il Location-Based (LBR) per limitare il bypass a pedaggio per gli utenti di Microsoft Teams in base alla loro posizione geografica. Leggere questa sezione se l'organizzazione usa il routing diretto in una località che non consente il bypass a numero verde.
| [**Topologia di rete per le caratteristiche vocali nel cloud**](#network-topology-for-voice-features) | Se la tua organizzazione sta distribuendo Location-Based Routing (LBR) per il routing diretto o chiamate di emergenza dinamiche, devi configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams. Leggere questa sezione se stai implementando l'LBR per il routing diretto o se stai implementando chiamate di emergenza dinamiche con Piano per chiamate o Instradamento diretto. |
| [**Eseguire la migrazione della soluzione voce esistente**](#migrate-your-existing-voice-solution-to-teams) | Cosa occorre pensare quando si esegue la migrazione della soluzione vocale a Teams.  Se si esegue la migrazione da una soluzione voce esistente a Teams, leggere questa sezione. 



> [!Important]
> Questo articolo è in particolare sulle soluzioni vocali con Microsoft Teams. Anche se le soluzioni con Skype for Business online sono ancora disponibili (come descritto nelle soluzioni di telefonia [Microsoft),](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)è importante sapere che Skype for Business online verrà ritirato il 31 luglio 2021.  Dopo tale data, il servizio Skype for Business online non sarà più accessibile. Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non &mdash; &mdash; sarà più supportata. Questo articolo presenta le soluzioni vocali di Teams e su come connettere la rete telefonica locale, se necessario, a Teams usando il routing diretto.


## <a name="phone-system"></a>Phone System

Sistema telefonico è la tecnologia microsoft per abilitare il controllo delle chiamate e le funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 o Office 365 con Microsoft Teams.

Sistema telefonico funziona con i client Teams o Skype for Business e i dispositivi certificati. Sistema telefonico consente di sostituire il sistema PBX esistente con una serie di funzionalità direttamente da Microsoft 365 o Office 365. 

Le chiamate tra gli utenti dell'organizzazione vengono gestite internamente al Sistema telefonico e non passano mai alla rete PSTN (Public Switched Telephone Network). Si applica alle chiamate tra gli utenti dell'organizzazione che si trovano in aree geografiche diverse, rimuovendo i costi a distanza lunga per queste chiamate interne.

Questo articolo presenta le caratteristiche e le funzionalità principali del Sistema telefonico e le decisioni di distribuzione che è necessario prendere in considerazione:

- [Operatori automatici e code delle chiamate](#auto-attendants-and-call-queues)
- [Cloud Voicemail](#cloud-voicemail)
- [Identità delle chiamate](#calling-identity)

![Diagramma 3 mostra che il sistema telefonico contiene operatori automatici e query di chiamata, segreteria telefonica cloud e identità di chiamata](media/phone-system-contains.png)

Per informazioni su tutte le funzionalità del Sistema telefonico e su come configurare il Sistema telefonico, vedere gli articoli seguenti:

- [Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)
- [Configurare il Sistema telefonico nell'organizzazione](setting-up-your-phone-system.md)<br>
  Descrive come acquistare e assegnare licenze di Sistema telefonico, gestire i numeri di telefono e impostare i crediti comunicazioni per i numeri verde. 

Per informazioni sulla gestione dei dispositivi supportati, vedere [Gestire i dispositivi in Microsoft Teams](devices/device-management.md) e Teams [Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Operatori automatici e code di chiamata

Gli operatori automatici consentono di impostare opzioni di menu per instradare le chiamate in base all'input del chiamante. Le code di chiamata sono aree di attesa per i chiamanti. Usati insieme, gli operatori automatici e le code di chiamata possono facilmente instradare i chiamanti alla persona o al reparto appropriato dell'organizzazione.

Per informazioni sugli operatori automatici e le code di chiamata, vedere gli articoli seguenti:

- [Pianificare gli operatori automatici e le code di chiamata di Teams](plan-auto-attendant-call-queue.md)
- [Impostare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md) 
- [Case study contoso: Operatori automatici e code di chiamata](voice-case-study-call-queues.md)<br>
  Descrive in che modo una multinazionale fittizia, Contoso, ha implementato operatori automatici e code di chiamata per la propria soluzione vocale.

### <a name="cloud-voicemail"></a>Cloud Voicemail

La segreteria telefonica cloud, con tecnologia Azure Voicemail, supporta i depositi di segreteria telefonica solo nelle cassette postali di Exchange. Non supporta i sistemi di posta elettronica di terze parti. 

La Cloud Voicemail include la trascrizione della segreteria telefonica che è abilitata di default per tutti gli utenti dell’organizzazione. Le esigenze aziendali potrebbero richiedere la disabilitazione della trascrizione segreteria telefonica per utenti specifici o per tutti gli utenti dell'organizzazione.

Solo per gli utenti online, la segreteria telefonica cloud viene automaticamente impostata ed eseguita il provisioning per gli utenti dopo l'assegnazione di una licenza Sistema telefonico. Per gli utenti di Sistema telefonico con una cassetta postale di Exchange, è necessario eseguire passaggi di configurazione aggiuntivi. 

Per altre informazioni su Cloud Voicemail e la relativa configurazione, vedere gli articoli seguenti:

- [Configurare Cloud Voicemail](set-up-phone-system-voicemail.md)
- [Impostare i criteri della segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identità delle chiamate

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante). Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata. Per informazioni sulla configurazione dell'ID chiamante o su come modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opzioni di connettività di Public Switched Telephone Network

Sistema telefonico offre funzionalità PBX complete per l'organizzazione. Tuttavia, per consentire agli utenti di effettuare chiamate esterne all'organizzazione, è necessario collegare il Sistema telefonico alla rete PSTN (Public Switched Telephone Network). Per connettere il Sistema telefonico alla rete PSTN, è possibile scegliere una delle opzioni seguenti:

- [**Sistema telefonico con Piano per chiamate.**](#phone-system-with-calling-plan) Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- [**Sistema telefonico con il proprio gestore PSTN**](#phone-system-with-own-pstn-carrier-with-direct-routing) utilizzando l'instradamento diretto per connettere l'ambiente locale a Teams.

È anche possibile scegliere una combinazione di opzioni, che consente di progettare una soluzione per un ambiente complesso, o gestire una migrazione in più passaggi (altre informazioni sulla migrazione in un secondo momento).

### <a name="phone-system-with-calling-plan"></a>Sistema telefonico con piano per chiamate 

Come descritto in precedenza in questo articolo, Sistema telefonico con piano per chiamate è la soluzione vocale all-in-the-cloud di Microsoft per gli utenti di Teams. Questa è l'opzione più semplice che connette il Sistema telefonico Microsoft alla rete PSTN (Public Switched Telephone Network) per consentire le chiamate a telefoni fissi e cellulari in tutto il mondo. Con questa opzione, Microsoft offre funzionalità PBX (Private Branch Exchange) per l'organizzazione e funge da gestore PSTN, come illustrato nel diagramma seguente:

![Diagramma 4 mostra Sistema telefonico con operatori automatici, code di chiamata, ID chiamante e altro ancora e Microsoft come gestore PSTN](media/voice-solution-microsoft-complete.png)

Se rispondi sì a quanto segue, allora Sistema telefonico con Piano per chiamate è la soluzione giusta per te:

- Il Piano per chiamate è disponibile nella tua area geografica.
- Non è necessario conservare l'attuale gestore PSTN.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Con questa opzione: 

- Si ottiene il Sistema telefonico Microsoft con l'aggiunta di piani per chiamate nazionali o internazionali che consentono di chiamare telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza).

- Non è necessaria la distribuzione o la manutenzione di una distribuzione locale perché il Piano per chiamate opera da &mdash; Microsoft 365 o Office 365.

- Nota: se necessario, è possibile scegliere di connettere un controller SBC (Session Border Controller) supportato tramite routing diretto per l'interoperabilità con PCX di terze parti, dispositivi analogici e altri dispositivi di telefonia di terze parti supportati dal controller SBC.

Questa opzione richiede una connessione senza interruzioni a Microsoft 365 o Office 365.

Per ulteriori informazioni sul Piano per chiamate, consulta i seguenti articoli:

- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Come acquistare un piano di chiamata](calling-plans-for-office-365.md)
- [Disponibilità di Piano di chiamata in Paesi e aree geografiche](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Imposta piano per chiamate](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema telefonico con gestore PSTN con instradamento diretto

Questa opzione connette il Sistema telefonico Microsoft alla rete telefonica tramite l'instradamento diretto, come illustrato nel diagramma seguente: 

![Diagramma 5 che mostra Sistema telefonico con instradamento diretto](media/voice-solution-with-direct-routing.png)

Se rispondi sì alle seguenti domande, il Sistema telefonico con instradamento diretto è la soluzione giusta per te:

- Si vuole usare Teams con Sistema telefonico.
- È necessario conservare l'attuale gestore PSTN.
- Vuoi combinare il routing, con alcune chiamate che passano attraverso il Piano per chiamate, altre attraverso il gestore.
- È necessario interoperabilità con pc e/o apparecchiature di terze parti, ad esempio paginer di costi, dispositivi analogici e così via.

Con questa opzione:

- È possibile connettere il proprio SBC supportato al Sistema telefonico Microsoft senza la necessità di software locale aggiuntivo.

- È possibile utilizzare praticamente qualsiasi gestore telefonico del Sistema telefonico Microsoft.

- Puoi scegliere di configurare e gestire questa opzione oppure configurarla e gestirla dal gestore o dal partner (chiedi se il gestore o il partner fornisce questa opzione).

- È possibile configurare l'interoperabilità tra i dispositivi di telefonia, ad esempio pbx e dispositivi analogici di terze &mdash; &mdash; parti, e il Sistema telefonico Microsoft.


Questa opzione richiede quanto segue:

- Connessione senza interruzioni a Microsoft 365 o Office 365.

- Distribuzione e gestione di un SBC supportato.

- Un contratto con un gestore di terze parti.
  (A meno che non sia distribuita come opzione per fornire la connessione a PBX di terze parti, dispositivi analogici o altri dispositivi di telefonia per gli utenti di Sistema telefonico con Piano per chiamate).)

Per altre informazioni sul routing diretto, vedere gli articoli seguenti:

- [Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)
- [Pianificare Instradamento diretto](direct-routing-plan.md)
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Gestire i criteri di routing vocale per l'uso con l'instradamento diretto](manage-voice-routing-policies.md)
- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Numeri di telefono di Microsoft

Microsoft ha a disposizione due tipi di numeri *di* telefono: i numeri abbonati  (utente), che possono essere assegnati agli utenti della tua organizzazione, e i numeri di servizio, disponibili come numeri di servizio a numero verde e a numero verde. I numeri di servizio hanno una capacità di chiamata simultanea superiore rispetto ai numeri abbonati e possono essere assegnati a servizi come Audioconferenze, Operatori automatici o Code di chiamata.

Sarà necessario decidere:

- Quali località utente hanno bisogno di nuovi numeri di telefono da Microsoft?
- Quale tipo di numero di telefono (abbonato o servizio) è necessario? 
- Come si portano i numeri di telefono esistenti in Teams?

Per altre informazioni sulla gestione dei numeri di telefono nella tua organizzazione, inclusi il recupero di nuovi numeri o il trasferimento di numeri in uscita, consulta gli articoli seguenti:

- [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Diversi tipi di numeri di telefono utilizzati per il Piano per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Recuperare numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md)
- [Trasferire numeri di telefono in Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Piani di chiamata e routing delle chiamate

Un piano di chiamata è un insieme di regole di normalizzazione che traducono i numeri di telefono composto in un formato alternativo (in genere formato E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate.

È necessario decidere quanto segue: 

- L'organizzazione ha bisogno di un dial plan personalizzato?
- Quali utenti richiedono un piano di chiamata personalizzato?
- Quale piano di chiamata tenant deve essere assegnato a ogni utente?

Per altre informazioni, vedere gli articoli seguenti: 

- [Che cosa sono i piani di chiamata?](what-are-dial-plans.md)
- [Pianificare piani di chiamata tenant](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Creare e impostare piani di chiamata](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Chiamate di emergenza

La modalità di configurazione delle chiamate di emergenza varia in base all'opzione di connettività PSTN: Piano per chiamate Microsoft o Instradamento diretto. Le chiamate di emergenza dinamiche per il Piano per chiamate Microsoft e il routing diretto del sistema telefonico forniscono la possibilità di configurare e instradare le chiamate di emergenza e avvisare il personale addetto alla sicurezza in base alla posizione corrente del client teams. Per ulteriori informazioni sui concetti e sulla terminologia delle chiamate di emergenza e su come configurare le chiamate di emergenza dinamiche, consulta gli articoli seguenti:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
- [Case study Contoso: Chiamate di emergenza](voice-case-study-emergency-calling.md)<br>
  Descrive come una multinazionale fittizia, Contoso, ha implementato le chiamate di emergenza per l'organizzazione.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based routing diretto

In alcuni paesi e aree geografiche, è illegale bypassare il provider PSTN (Public Switched Telephone Network) per ridurre i costi per le chiamate a distanza. Location-Based routing diretto consente di limitare il bypass a numero verde per gli utenti di Microsoft Teams in base alla loro posizione geografica. Per altre informazioni su come pianificare e configurare il Location-Based routing dei dati (LBR), vedere gli articoli seguenti:

- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Configurare le impostazioni di rete per l'instradamento basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Case study Contoso: Location-Based distribuzione](voice-case-study-location-based-routing.md)<br>
  Descrive in che modo una multinazionale fittizia, Contoso, ha implementato Location-Based routing per l'organizzazione.

## <a name="network-topology-for-voice-features"></a>Topologia di rete per le funzionalità vocali

Se stai distribuendo chiamate di emergenza dinamiche o Location-Based routing diretto, devi configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams. Per informazioni su come configurare le impostazioni di rete per aree geografiche, siti di rete, subnet di rete e indirizzi IP attendibili, vedere gli articoli seguenti:

- [Impostazioni di rete per le funzionalità vocali sul cloud in Microsoft Teams - Concetti e terminologia](cloud-voice-network-settings.md)
- [Gestire la topologia della rete per le funzionalità vocali nel cloud in Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Eseguire la migrazione della soluzione voce esistente a Teams

Per un'organizzazione che sta aggiornando a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly. L'uso di Sistema telefonico con Teams è supportato solo quando l'utente è in modalità TeamsOnly. Se hai bisogno di informazioni di base sull'aggiornamento a Teams, inizia da qui:

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Informazioni sul framework di aggiornamento](upgrade-framework.md)
- [Strategie di aggiornamento per gli amministratori IT](upgrade-to-teams-on-prem-implement.md)

Quando si esegue la migrazione della soluzione vocale, il passaggio alla modalità TeamsOnly può avere quattro scenari di chiamata:

- [**Un utente in Skype for Business online, con un Piano per chiamate Microsoft.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) Al momento dell'aggiornamento, l'utente continuerà a disporre di un Piano per chiamate Microsoft.

- **[Un utente in Skype for Business online,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per garantire che l'utente TeamsOnly abbia funzionalità PSTN.

- **[Un utente in Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** locale con VoIP aziendale , che si locerà online mantenendo la connettività PSTN locale. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento del trasferimento con la migrazione dell'utente al routing diretto. 

- **[Un utente in Skype for Business locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** con VoIP aziendale , che si locerà online e utilizzando un piano per le chiamate Microsoft.  La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento del trasferimento con A) il trasferimento del numero di telefono dell'utente a un piano per chiamate Microsoft o B) l'assegnazione di un nuovo numero di abbonato dalle aree geografiche disponibili.

Per altre informazioni su come implementare la migrazione vocale per ognuno di questi scenari, incluse informazioni su quando è necessario configurare la connettività ibrida e su come eseguire la migrazione degli utenti con funzionalità vocali locali al routing diretto, vedere gli articoli &mdash; &mdash; seguenti:

- [Considerazioni su PSTN durante l'aggiornamento a Teams - per gli amministratori IT](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Case study sulla migrazione vocale di Contoso](voice-case-study-overview.md)<br>
  Il case study descrive in che modo una multinazionale fittizia, Contoso, ha implementato una soluzione voce di Teams per l'organizzazione. Contiene gli articoli seguenti:

  - [Piano di aggiornamento di Teams](voice-case-study-migration-plan.md)
  - [Opzioni di connettività Sistema telefonico e PSTN](voice-case-study-phone-system.md)
  - [Implementazione del routing basato sulla posizione](voice-case-study-location-based-routing.md)
  - [Chiamate d'emergenza](voice-case-study-emergency-calling.md)
  - [Operatori automatici e code delle chiamate](voice-case-study-call-queues.md)
  - [Audioconferenza](voice-case-study-audio-conferencing.md)












