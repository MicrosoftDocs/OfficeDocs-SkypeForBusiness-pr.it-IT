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
ms.openlocfilehash: 92b28a00e1737b533c17cf3f1f670bc23561620d
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689794"
---
# <a name="plan-your-teams-voice-solution"></a>Pianificare la soluzione Teams vocale 

Questo articolo consente di decidere quale soluzione vocale Microsoft è ideale per l'organizzazione. Dopo aver deciso, l'articolo fornisce una roadmap per il contenuto che consente di implementare la soluzione scelta.

> [!NOTE]
> Per indicazioni sulla pianificazione di una soluzione vocale Teams come parte del piano generale per l'aggiornamento a Teams da Skype for Business Server, vedere Considerazioni [su PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)per l'aggiornamento a Teams da Skype for Business locale.

È consigliabile usare la soluzione più &mdash; semplice Sistema telefonico piano per chiamate. Si tratta della soluzione all-in-the-cloud di Microsoft che fornisce funzionalità PBX (Private Branch Exchange) e chiamate alla rete PSTN (Public Switched Telephone Network), come illustrato nel diagramma seguente. Con questa soluzione, Microsoft è il gestore PSTN.

![Il diagramma 1 mostra Sistema telefonico piano per chiamate](media/voice-solutions-simple.png)

Se si risponde sì a quanto segue, Sistema telefonico piano per chiamate è la soluzione giusta per te:

- Piano chiamate è disponibile nella tua area geografica.
- Non è necessario conservare il gestore PSTN corrente.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Tuttavia, la situazione potrebbe essere più complessa. Ad esempio, potresti avere uffici in località in cui il piano per chiamate non è disponibile. In caso contrario, potrebbe essere necessaria una soluzione combinata che supporti una distribuzione complessa e nazionale, con requisiti diversi per posizioni geografiche diverse. Microsoft supporta una combinazione di soluzioni: 

- Sistema telefonico piano chiamate
- Sistema telefonico con il proprio gestore PSTN con operatore Connessione (attualmente disponibile solo in **anteprima pubblica)**
- Sistema telefonico con il proprio gestore PSTN con Routing diretto
- Una soluzione combinata che usa Sistema telefonico piano per chiamate, Sistema telefonico con operatore Connessione e/o Sistema telefonico con Routing diretto


## <a name="what-do-you-need-to-read"></a>Cosa è necessario leggere?

**Obbligatorio per tutti.** Alcune delle sezioni di questo articolo riguardano tutte le organizzazioni. Ad esempio, tutti dovrebbero leggere le informazioni Sistema telefonico e comprendere le opzioni per la connessione alla rete PSTN (Public Switched Telephone Network). 


| Obbligatorio per tutti | Descrizione |
| :------------|:-------|
| [**Sistema telefonico**](#phone-system) | Tecnologia Microsoft per l'abilitazione del controllo delle chiamate e delle funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 con Microsoft Teams. |
| [**Opzioni di connettività PSTN (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Scelta tra l'uso di Microsoft come gestore di telefonia o la connessione del proprio gestore di telefonia a Microsoft Teams tramite Routing diretto o Operatore Connessione. In combinazione con Sistema telefonico, le opzioni di connettività PSTN consentono agli utenti di effettuare chiamate telefoniche in tutto il mondo.|

**A seconda dei requisiti.** Alcune delle sezioni di questo articolo sono pertinenti a seconda della distribuzione e dei requisiti esistenti. Ad esempio, Location-Based routing diretto è necessario solo per i clienti di Routing diretto in posizioni geografiche che non consentono il bypass a pedaggio.

Valutare quali di queste configurazioni aggiuntive potrebbero essere necessarie:

![Il diagramma 2 mostra altri componenti vocali, ad esempio i numeri Telefono microsoft, i piani di chiamata e il routing delle chiamate e così via.](media/voice-consider-additional-components.png)

| A seconda dei requisiti | Descrizione |
| :------------|:-------|
| [**Telefono numeri da Microsoft**](#phone-numbers-from-microsoft) | Come ottenere e gestire i numeri di telefono da Microsoft e come trasferire i numeri esistenti a Microsoft. Leggi questo articolo se devi ottenere i numeri di telefono per il Piano chiamate Microsoft, trasferire i numeri esistenti, ottenere i numeri di servizio e così via. |
| [**Dial plan e routing delle chiamate**](#dial-plans-and-call-routing) | Come configurare e gestire i piani di chiamata che traducono i numeri di telefono dialed in un formato alternativo (in genere formato E.164) per l'autorizzazione delle chiamate e il routing delle chiamate. Leggere questa pagina se è necessario comprendere quali sono i piani di chiamata e se è necessario specificare i piani di chiamata per l'organizzazione.|
| [**Chiamate di emergenza**](#emergency-calling) | Come gestire e configurare le chiamate di emergenza &mdash; a seconda dell'opzione di connettività PSTN. Leggere questa sezione se si usa Microsoft Calling Plan o Direct Routing ed è necessario comprendere come gestire le chiamate di emergenza per l'organizzazione. |
| [**Routing in base alla posizione per il routing diretto**](#location-based-routing-for-direct-routing) |Come usare il routing Location-Based (LBR) per limitare il bypass a pedaggio per Microsoft Teams utenti in base alla loro posizione geografica. Leggere questa sezione se l'organizzazione usa Il routing diretto in una posizione che non consente il bypass a pedaggio.
| [**Topologia di rete per le funzionalità vocali cloud**](#network-topology-for-voice-features) | Se l'organizzazione distribuisce Location-Based Routing (LBR) per il routing diretto o le chiamate di emergenza dinamiche, è necessario configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams. Leggere questa sezione se si sta implementando LBR per il routing diretto o se si stanno implementando chiamate di emergenza dinamiche con piano chiamate o routing diretto. |
| [**Eseguire la migrazione della soluzione vocale esistente**](#migrate-your-existing-voice-solution-to-teams) | Cosa occorre pensare quando si esegue la migrazione della soluzione vocale a Teams.  Leggere questa sezione se si esegue la migrazione da una soluzione vocale esistente a Teams. 



> [!Important]
> Questo articolo è in particolare sulle soluzioni vocali con Microsoft Teams. Anche se le soluzioni con Skype for Business Online sono ancora disponibili (come descritto nelle soluzioni di telefonia [Microsoft),](/SkypeForBusiness/hybrid/msft-telephony-solutions)è importante tenere presente che Skype for Business Online verrà ritirato il 31 luglio 2021.  Dopo tale data, il Skype for Business online non sarà più accessibile. Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business Online non &mdash; &mdash; sarà più supportata. Questo articolo illustra Teams soluzioni vocali e illustra come connettere la rete di telefonia locale, se necessario, a Teams usando Routing diretto o Operatore Connessione.


## <a name="phone-system"></a>Sistema telefonico

Sistema telefonico è la tecnologia Microsoft per l'abilitazione del controllo delle chiamate e delle funzionalità PBX (Private Branch Exchange) nel cloud Microsoft 365 o Office 365 con Microsoft Teams.

Sistema telefonico funziona con Teams o Skype for Business client e dispositivi certificati. Sistema telefonico consente di sostituire il sistema PBX esistente con un set di funzionalità direttamente Microsoft 365 o Office 365. 

Le chiamate tra utenti dell'organizzazione vengono gestite internamente all'interno Sistema telefonico e non passano mai alla rete PSTN (Public Switched Telephone Network). Questo vale per le chiamate tra utenti dell'organizzazione che si trovano in aree geografiche diverse, rimuovendo i costi a lunga distanza per queste chiamate interne.

Questo articolo presenta le seguenti Sistema telefonico caratteristiche e funzionalità principali e le decisioni di distribuzione da prendere in considerazione:

- [Operatori automatici e code delle chiamate](#auto-attendants-and-call-queues)
- [Cloud Voicemail](#cloud-voicemail)
- [Identità chiamante](#calling-identity)

![Il diagramma 3 mostra Telefono sistema contiene operatori automatici e query di chiamata, segreteria telefonica cloud e identità di chiamata](media/phone-system-contains.png)

Per informazioni su tutte le Sistema telefonico e su come configurare Sistema telefonico, vedere gli articoli seguenti:

- [Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)
- [Configurare Sistema telefonico nell'organizzazione](setting-up-your-phone-system.md)<br>
  Descrive come acquistare e assegnare Sistema telefonico licenze, gestire i numeri di telefono e configurare i crediti di comunicazione per i numeri verde. 

Per informazioni sulla gestione dei dispositivi supportati, vedere Gestire i dispositivi [in Microsoft Teams](devices/device-management.md) e [Teams Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


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

Per gli utenti solo online, Cloud Voicemail viene automaticamente configurato ed eseguito il provisioning per gli utenti dopo l'assegnazione di una Sistema telefonico licenza. Per Sistema telefonico utenti con una Exchange cassetta postale, è necessario eseguire passaggi di configurazione aggiuntivi. 

Per altre informazioni su Cloud Voicemail configurazione, vedere gli articoli seguenti:

- [Configurare Cloud Voicemail](set-up-phone-system-voicemail.md)
- [Impostare i criteri della segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identità chiamante

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante). Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata. Per informazioni sulla configurazione dell'ID chiamante o per modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opzioni di connettività rete telefonica a commutazione pubblica

Sistema telefonico offre funzionalità PBX complete per l'organizzazione. Tuttavia, per consentire agli utenti di effettuare chiamate all'esterno dell'organizzazione, è necessario connettersi Sistema telefonico rete PSTN (Public Switched Telephone Network). Per connettersi Sistema telefonico alla rete PSTN, è possibile scegliere una delle opzioni seguenti:

- [**Sistema telefonico piano chiamate**](#phone-system-with-calling-plan). Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- [**Sistema telefonico con il proprio gestore PSTN usando Il**](#phone-system-with-own-pstn-carrier-with-direct-routing) routing diretto per connettere l'ambiente locale a Teams.

- [**Sistema telefonico con il proprio gestore PSTN**](operator-connect-plan.md)usando operatore Connessione , attualmente disponibile solo **nell'anteprima pubblica.**  Con Operator Connessione, se l'operatore esistente è un partecipante al programma Microsoft Operator Connessione, può gestire il servizio per portare le chiamate PSTN in Teams. Per informazioni sui vantaggi e i requisiti dell'operatore Connessione e per un elenco degli operatori che partecipano a questo programma, vedere Pianificare l'operatore [Connessione](operator-connect-plan.md).

È anche possibile scegliere una combinazione di opzioni, che consente di progettare una soluzione per un ambiente complesso o di gestire una migrazione in più passaggi (altre informazioni sulla migrazione in un secondo momento).

### <a name="phone-system-with-calling-plan"></a>Sistema telefonico piano chiamate 

Come descritto in precedenza in questo articolo, Sistema telefonico piano chiamate è la soluzione vocale all-in-the-cloud di Microsoft per Teams utenti. Questa è l'opzione più semplice che connette Telefono Microsoft System alla rete PSTN (Public Switched Telephone Network) per consentire le chiamate a telefoni fissi e cellulari in tutto il mondo. Con questa opzione, Microsoft fornisce funzionalità PBX (Private Branch Exchange) per l'organizzazione e funge da gestore PSTN, come illustrato nel diagramma seguente:

![Il diagramma 4 mostra Sistema telefonico operatori automatici, code di chiamata, ID chiamante e altro ancora e Microsoft come gestore PSTN](media/voice-solution-microsoft-complete.png)

Se si risponde sì a quanto segue, Sistema telefonico piano per chiamate è la soluzione giusta per te:

- Piano chiamate è disponibile nella tua area geografica.
- Non è necessario conservare il gestore PSTN corrente.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Con questa opzione: 

- Si ottiene Telefono Microsoft sistema con l'aggiunta di piani per chiamate nazionali o internazionali che consentono di chiamare verso telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza).

- Non è necessaria la distribuzione o la manutenzione di una distribuzione locale perché il piano per chiamate funziona Microsoft 365 &mdash; o Office 365.

- Nota: se necessario, è possibile scegliere di connettere un session border controller (SBC) supportato tramite Direct Routing per garantire l'interoperabilità con sistemi IPX di terze parti, dispositivi analogici e altre apparecchiature di telefonia di terze parti supportate da SBC.

Questa opzione richiede una connessione ininterrotta a Microsoft 365 o Office 365.

Per altre informazioni sul piano chiamate, vedere gli articoli seguenti:

- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Come acquistare un piano di chiamata](calling-plans-for-office-365.md)
- [Disponibilità di Piano di chiamata in Paesi e aree geografiche](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurare il piano per le chiamate](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema telefonico con un gestore PSTN con Routing diretto

Questa opzione connette Telefono Microsoft sistema alla rete di telefonia tramite Routing diretto, come illustrato nel diagramma seguente: 

![Il diagramma 5 mostra Sistema telefonico routing diretto](media/voice-solution-with-direct-routing.png)

Se si risponde sì alle domande seguenti, Sistema telefonico il routing diretto è la soluzione giusta:

- Si vuole usare le Teams con Sistema telefonico.
- È necessario conservare il gestore PSTN corrente.
- Vuoi combinare l'instradamento, con alcune chiamate che attraversano il Piano chiamate, altre tramite il tuo gestore.
- È necessario interagire con sistemi PBX e/o apparecchiature di terze parti, ad esempio test di paginazione, dispositivi analogici e così via.

Con questa opzione:

- È possibile connettere il proprio SBC supportato Telefono Microsoft sistema senza la necessità di software locale aggiuntivo.

- È possibile usare praticamente qualsiasi gestore di telefonia con Telefono Microsoft Sistema.

- È possibile scegliere di configurare e gestire questa opzione oppure può essere configurata e gestita dal gestore o dal partner (chiedere se il gestore o il partner fornisce questa opzione).

- È possibile configurare l'interoperabilità tra le apparecchiature di telefonia, ad esempio pbx di terze parti e dispositivi &mdash; analogici &mdash; e Telefono Microsoft sistema.


Questa opzione richiede quanto segue:

- Connessione ininterrotta a Microsoft 365 o Office 365.

- Distribuzione e gestione di un SBC supportato.

- Contratto con un gestore di terze parti.
  (A meno che non venga distribuita come opzione per fornire la connessione a PBX di terze parti, dispositivi analogici o altre apparecchiature di telefonia per gli utenti che Sistema telefonico con piano chiamate.

Per altre informazioni sul routing diretto, vedere gli articoli seguenti:

- [Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)
- [Pianificare Instradamento diretto](direct-routing-plan.md)
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Gestire i criteri di routing vocale per l'uso con Routing diretto](manage-voice-routing-policies.md)
- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Telefono numeri da Microsoft

Microsoft ha a disposizione due tipi di numeri di *telefono:* numeri abbonati (utente), che possono essere assegnati agli utenti dell'organizzazione, e numeri di servizio, disponibili come numeri di servizio a numero verde e a numero verde.  I numeri di servizio hanno una capacità di chiamata simultanea maggiore rispetto ai numeri degli abbonati e possono essere assegnati a servizi come audioconferenze, operatori automatici o code di chiamata.

Dovrai decidere:

- Quali posizioni degli utenti hanno bisogno di nuovi numeri di telefono da Microsoft?
- Quale tipo di numero di telefono (abbonato o servizio) è necessario? 
- Come faccio a eseguire il port di numeri di telefono esistenti Teams?

Per altre informazioni sulla gestione dei numeri di telefono nell'organizzazione, tra cui il recupero di nuovi numeri o il trasferimento di numeri in uscita, vedere gli articoli seguenti:

- [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Diversi tipi di numeri di telefono usati per il piano chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Recuperare numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md)
- [Trasferire i numeri di telefono Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Dial plan e routing delle chiamate

Un piano di chiamata è un set di regole di normalizzazione che traducono i numeri di telefono dialed in un formato alternativo (in genere formato E.164) per l'autorizzazione delle chiamate e il routing delle chiamate.

È necessario decidere quanto segue: 

- L'organizzazione ha bisogno di un dial plan personalizzato?
- Quali utenti richiedono un piano di chiamata personalizzato?
- Quale piano di chiamata tenant deve essere assegnato a ogni utente?

Per altre informazioni, vedere gli articoli seguenti: 

- [Che cosa sono i piani di chiamata?](what-are-dial-plans.md)
- [Pianificare i piani di chiamata del tenant](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Creare e impostare dial plan](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Chiamate di emergenza

La modalità di configurazione delle chiamate di emergenza varia a seconda dell'opzione di connettività PSTN: Piano chiamate Microsoft o Routing diretto. Le chiamate di emergenza dinamiche per Il piano chiamate Microsoft e Sistema telefonico Direct Routing forniscono la possibilità di configurare e instradare le chiamate di emergenza e di inviare notifiche al personale di sicurezza in base alla posizione corrente del client Teams. Per altre informazioni sui concetti e la terminologia delle chiamate di emergenza e su come configurare le chiamate di emergenza dinamiche, vedere gli articoli seguenti:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
- [Caso di studio Contoso: Chiamate di emergenza](voice-case-study-emergency-calling.md)<br>
  Descrive come una multinazionale fittizia, Contoso, ha implementato le chiamate di emergenza per l'organizzazione.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based routing diretto

In alcuni paesi e aree geografiche, è illegale ignorare il provider PSTN (Public Switched Telephone Network) per ridurre i costi delle chiamate a lunga distanza. Location-Based routing diretto consente di limitare il bypass a pedaggio per Microsoft Teams utenti in base alla loro posizione geografica. Per altre informazioni su come pianificare e configurare Location-Based Routing (LBR), vedere gli articoli seguenti:

- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Configurare le impostazioni di rete per l'instradamento basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Case study contoso: Location-Based Routing](voice-case-study-location-based-routing.md)<br>
  Descrive in che modo una multinazionale fittizia, Contoso, ha implementato Location-Based routing per l'organizzazione.

## <a name="network-topology-for-voice-features"></a>Topologia di rete per le funzionalità vocali

Se si distribuiscono chiamate di emergenza dinamiche o Location-Based routing per il routing diretto, è necessario configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams. Per informazioni su come configurare le impostazioni di rete per aree di rete, siti di rete, subnet di rete e indirizzi IP attendibili, vedere gli articoli seguenti:

- [Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams - Concetti e terminologia](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali cloud in Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Eseguire la migrazione della soluzione vocale esistente a Teams

Per un'organizzazione che esegue l'aggiornamento a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly. L'Sistema telefonico con Teams è supportato solo quando l'utente è in modalità TeamsOnly. Per informazioni di base sull'aggiornamento a Teams, iniziare da qui:

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Informazioni sul framework di aggiornamento](upgrade-framework.md)
- [Strategie di aggiornamento per gli amministratori IT](upgrade-to-teams-on-prem-implement.md)

Quando si esegue la migrazione della soluzione vocale, ci sono quattro possibili scenari di chiamata quando si attiva la modalità TeamsOnly:

- [**Un utente in Skype for Business Online, con un piano per chiamate Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Al momento dell'aggiornamento, questo utente continuerà a disporre di un piano per chiamate Microsoft.

- **[Un utente in Skype for Business Online,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente Teams deve essere coordinato con la migrazione dell'utente al routing diretto per assicurarsi che l'utente TeamsOnly abbia la funzionalità PSTN.

- **[Un utente in Skype for Business locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** con VoIP aziendale , che si trasferirà online e mantiene la connettività PSTN locale. La migrazione di questo utente a Teams richiede lo spostamento dell'account di Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con la migrazione dell'utente al routing diretto. 

- **[Un utente in Skype for Business locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** con VoIP aziendale , che si trasferirà online e con un piano per chiamate Microsoft .  La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con A) la porta del numero di telefono dell'utente a un piano per chiamate Microsoft o B) assegnando un nuovo numero di abbonato dalle aree geografiche disponibili.

Per altre informazioni su come implementare la migrazione vocale per ognuno di questi scenari, incluse le informazioni su quando è necessario configurare la connettività ibrida e su come eseguire la migrazione degli utenti con funzionalità vocali locali a Routing diretto, vedere gli articoli &mdash; &mdash; seguenti:

- [Considerazioni su PSTN durante l'aggiornamento a Teams, per gli amministratori IT](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Case study sulla migrazione vocale di Contoso](voice-case-study-overview.md)<br>
  Il case study descrive come una multinazionale fittizia, Contoso, ha implementato una Teams vocale per l'organizzazione. Contiene gli articoli seguenti:

  - [Teams di aggiornamento](voice-case-study-migration-plan.md)
  - [Sistema telefonico di connettività PSTN e pstn](voice-case-study-phone-system.md)
  - [Implementazione del routing in base alla posizione](voice-case-study-location-based-routing.md)
  - [Chiamate di emergenza](voice-case-study-emergency-calling.md)
  - [Operatori automatici e code delle chiamate](voice-case-study-call-queues.md)
  - [Audioconferenza](voice-case-study-audio-conferencing.md)