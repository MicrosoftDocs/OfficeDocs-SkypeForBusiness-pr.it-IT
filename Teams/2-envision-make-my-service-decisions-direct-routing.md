---
title: Prendere decisioni del servizio di routing diretto del sistema telefonico-Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Informazioni su routing diretto, licenze e sulle decisioni che è necessario apportare.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d3410616cf3e841ab6689ffd0fea772975b484c
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271436"
---
# <a name="make-my-service-decisions"></a>Prendere le decisioni del servizio

Per pianificare l'implementazione tecnica del routing diretto del sistema telefonico ("Direct routing"), è necessario eseguire una serie di decisioni di servizio prima del tempo per preparare meglio la propria organizzazione per implementare una soluzione che soddisfi i requisiti aziendali definiti.

## <a name="calling-in-teams"></a>Chiamata in teams

Con Microsoft teams gli utenti possono effettuare e ricevere telefonate da o verso la rete PSTN (Public Switched Telephone Network). Gli utenti possono usare i propri numeri di telefono dedicati per l'immissione e la ricezione di chiamate telefoniche nazionali e internazionali (inclusa la segreteria telefonica) dall'applicazione client teams.

## <a name="direct-routing"></a>Routing diretto

Affinché gli utenti di teams possano effettuare e ricevere chiamate PSTN, devono essere abilitati per il sistema telefonico, una funzionalità di Office 365.

Per abilitare la connettività alla rete PSTN, è possibile usare il routing diretto per offrire alle persone dell'organizzazione la possibilità di effettuare e ricevere chiamate telefoniche all'esterno dell'organizzazione tramite la rete PSTN.

Con il routing diretto, la connettività PSTN è facilitata da un provider di terze parti, che offre la possibilità di continuare a usare i trunk PSTN esistenti forniti dal provider di servizi PSTN. Ciò consente la distribuzione in paesi in cui il sistema telefonico con piani di chiamata ("piani di chiamata") non è disponibile o nelle distribuzioni in cui deve essere mantenuto un contratto di provider di servizi PSTN esistente o l'interoperabilità con determinati sistemi locali è Obbligatorio.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Disponibilità del routing diretto

Il routing diretto è disponibile in qualsiasi paese in cui è disponibile Office 365. Vedere [disponibilità internazionale](https://products.office.com/business/international-availability) per un elenco di questi paesi.

Dopo aver confermato che l'organizzazione può ottenere la funzionalità di sistema telefonico, compilare l'elenco delle posizioni degli utenti o degli uffici in cui si implementerà il sistema telefonico, in base all'elenco dei paesi e delle aree geografiche disponibili. Identifica inoltre gli utenti che userai per abilitare piani di chiamata o routing diretto per ogni posizione che hai.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Identificare le posizioni degli utenti o gli uffici in cui implementare il sistema telefonico.<li>Identificare gli utenti che hanno intenzione di abilitare i piani di chiamata o il routing diretto per ogni posizione.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le posizioni degli utenti o gli uffici da abilitare per il sistema telefonico.<li>Documentare l'elenco degli utenti che si intende abilitare i piani di chiamata o il routing diretto per ogni posizione</ul>|

> [!TIP]
> Di seguito è riportato un esempio di elenco di abilitazione del sito di routing diretto.
> 
> | **Ufficio**                     | **Posizione**   | **Servizio di sistema telefonico** |
> |--------------------------------|----------------|--------------------------|
> | Una strada di Epping                | Australia      | Servizio PSTN legacy |
> | 100 Cyberport Road             | Hong Kong SAR (香港特別行政區)  | Routing diretto del sistema telefonico |
> | Una Marina Boulevard           | Singapore      | Routing diretto del sistema telefonico |
> | 32 London Bridge Street        | Regno Unito | Sistema telefonico con piani di chiamata |
> | 39 Quai du Président Roosevelt | Francia         | Sistema telefonico con piani di chiamata |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Numeri di telefono e posizioni di emergenza

Il sistema telefonico richiede a tutti gli utenti dell'organizzazione di avere un numero di telefono univoco diretto (DID). Con il routing diretto, i numeri di telefono e i servizi di emergenza vengono forniti dal provider di servizi PSTN.

> [!NOTE]
> Con il routing diretto, gli utenti possono continuare a usare i propri numeri di telefono, forniti dal provider di servizi PSTN.
> 
> [!TIP]
> Per documentare i dettagli dei numeri di telefono, è possibile usare il modello seguente.
> 
> |Utente |Numero di telefono |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |Luigi Lahr | + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Casella vocale

Cloud voicemail, alimentato da servizi di Azure voicemail, supporta i depositi della segreteria telefonica solo alle cassette postali di Exchange e non supporta sistemi di posta elettronica di terze parti.

Cloud Voicemail include la trascrizione della segreteria telefonica, che è abilitata per tutti gli utenti dell'organizzazione per impostazione predefinita. Le esigenze aziendali potrebbero richiedere la disattivazione della trascrizione della segreteria telefonica per utenti specifici o tutti nell'organizzazione. Se l'organizzazione ha deciso di tenere attivata la trascrizione della segreteria telefonica, è necessario considerare anche se la trascrizione della segreteria telefonica deve essere abilitata. Per altre informazioni, vedere [impostazione di criteri per la segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md) .

Per altre informazioni sulla segreteria telefonica in un'implementazione di sistema telefonico, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se abilitare la segreteria telefonica cloud nell'implementazione di routing diretto.<li>Decidere se abilitare o disabilitare la trascrizione della segreteria telefonica e la trascrizione della segreteria telefonica in tutta l'organizzazione o per utenti specifici.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Se applicabile, documentare i punti di decisione per il supporto della segreteria telefonica cloud.<li>Se è possibile abilitare o disabilitare la segreteria telefonica, la trascrizione della segreteria telefonica e la trascrizione della segreteria telefonica solo per utenti specifici, documentare l'elenco degli utenti.</ul>|

> [!TIP]
> I dettagli della segreteria telefonica cloud per l'implementazione dei piani di chiamata possono essere documentati come nella tabella seguente.
> 
> | **Utente**         | **Cassetta postale di Exchange** | **Abilitare la segreteria telefonica?** | **Trascrizione della segreteria telefonica** | **Mascheramento profanità trascrizione della segreteria telefonica** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Sì                   | Abilitata                     | Abilitata                                       |
> | Lidia Holloway   | Online               | Sì                   | Abilitata                     | Disabilitata                                      |
> | Luigi Lahr       | Locale          | Sì                   | Abilitata                     | Abilitata                                       |
> | Marcel Beauchamp | Locale          | Sì                   | Disabilitata                    | N/D                                           |
> | Rachelle Cormier | Online               | Sì                   | Disabilitata                    | N/D                                           |
> | Isabell Potvin   | Locale          | Sì                   | Disabilitata                    | N/D                                           |
> 
> [!NOTE]
> Per usare team e segreteria telefonica, gli utenti devono avere cassette postali di Exchange. Per altre informazioni [, vedere come interagiscono Exchange e Microsoft teams](exchange-teams-interact.md) .

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Licenze per il routing diretto

Se l'organizzazione intende usare il routing diretto, è necessario ottenere le licenze necessarie. Gli utenti del routing diretto devono avere le licenze seguenti assegnate in Office 365:

-   Sistema telefonico Microsoft

-   Microsoft Teams

-   Audioconferenza

È necessaria una licenza di audioconferenza per l'aggiunta di partecipanti esterni alle riunioni pianificate, tramite chiamata in uscita o fornendo il numero di accesso esterno. Quando viene chiamato un partecipante esterno, il servizio di audioconferenza inserisce la chiamata tramite le funzionalità di chiamata online. La licenza per i servizi di audioconferenza è facoltativa e richiede solo agli utenti che organizzeranno conferenze di team che includono servizi di audioconferenza.


> [!NOTE]
> Per ottenere numeri di telefono a ponte per conferenze senza pedaggio e per supportare l'accesso esterno ai numeri di telefono internazionali, è necessario configurare i crediti per le [comunicazioni](what-are-communications-credits.md) per l'organizzazione.

I servizi di audioconferenza e i sistemi telefonici possono essere concessi in licenza separatamente per i componenti aggiuntivi per i clienti esistenti che hanno piani di abbonamento a Office 365 E3 o E1; sono già inclusi nell'ambito del piano di sottoscrizione di Office 365 E5.

> [!TIP]
> È anche possibile usare il routing diretto per gli utenti abilitati per i piani di chiamata quando instradano le chiamate a sistemi PBX di terze parti. Per altre informazioni, Vedi [licenze e altri requisiti di routing diretto](direct-routing-plan.md#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Se l'organizzazione non ha la licenza necessaria per il sistema telefonico, decidere se acquisire la licenza per il sistema telefonico tramite l'aggiunta di abbonamenti a Office 365 o l'acquisizione del servizio di componente aggiuntivo per il sistema telefonico.<li>Decidere se è necessario disporre di crediti per comunicazioni per l'implementazione di routing diretto.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare la divisione, il reparto, l'ufficio o i gruppi di utenti assegnando una licenza per il sistema telefonico.<li>Se i servizi di audioconferenza con numeri verdi sono in ambito, documentare i gruppi divisione, reparto, Office o utenti che consentono di abilitare i crediti per le comunicazioni.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Considerazioni su Office 365

Qualsiasi utente abilitato per il routing diretto deve essere ospitato in Office 365. Per le distribuzioni ibride con Skype for Business Server locale o Lync Server, è necessario trasferire gli utenti in Skype for business online prima di configurarli per usare il routing diretto con i team.

Tutti gli utenti che hanno l'ambito di implementazioni di routing diretto devono essere abilitati per i team.

Il tenant di Office 365 deve essere abilitato con uno o più domini, perché il \*dominio default. onmicrosoft.com non può essere usato con il routing diretto. Per altre informazioni sui domini e i tenant di Office 365, vedere [domande frequenti sui domini](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se gli utenti devono essere migrati in Skype for business online per supportare il routing diretto.<li>Identificare gli utenti che devono essere abilitati per i team.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documenta l'elenco degli utenti che devono trasferirsi in Skype for business online ed essere abilitati per i team.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>Considerazioni su SBC

È necessario usare i controller di bordo della sessione certificati e supportati (SBCs) che devono essere associati al servizio di routing diretto per consentire la connettività PSTN per gli utenti. Per un elenco di SBCs certificati, vedere [controller di bordo della sessione supportati](direct-routing-plan.md#supported-session-border-controllers-sbcs).

A seconda dell'ambiente, del numero di posizioni e dei requisiti di routing vocale, potrebbe essere necessario distribuire più SBCs per supportare la base di utenti.

### <a name="sbc-domain-names"></a>Nomi di dominio SBC

Ogni SBC abbinato al routing diretto deve avere un nome DNS univoco. I nomi DNS di SBC devono essere provenienti da uno dei nomi di dominio registrati nel tenant di Office 365. Se al tenant sono stati assegnati più nomi di dominio, è possibile usare uno di questi nomi di dominio quando si pianificano i nomi DNS di SBCs.

> [!IMPORTANT]
> L'uso di *. onmicrosoft.com per il nome DNS SBC non è consentito.

### <a name="certificates"></a>Certificati

Ogni SBC distribuito con routing diretto richiede un certificato ottenuto da un elenco di autorità di certificazione supportate. Il certificato deve includere il nome DNS SBC nei campi oggetto, nome alternativo oggetto o nome comune.

> [!NOTE]
> È anche supportato l'uso di certificati con caratteri jolly con SBCs.

Per altre informazioni e un elenco delle autorità di certificazione supportate, vedere [certificato attendibile pubblico per SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>Indirizzi IP e porte SBC

Ogni SBC deve essere configurato usando un indirizzo IP pubblico accessibile dai Data Center di Office 365. È anche possibile configurare NAT (Network Address Translation) per pubblicare il proprio SBCs in datacenter di Office 365.

SBCs richiede connettività bidirezionale per comunicare con i servizi cloud per la segnalazione e l'elemento multimediale. La segnalazione viene gestita dal componente denominato *proxy SIP*e il supporto viene gestito dai *processori multimediali*.

È necessario definire numeri di porta specifici in ogni SBC per la segnalazione SIP e l'elemento multimediale e configurare i firewall per consentire il traffico bidirezionale verso queste porte e i relativi indirizzi IP associati.

Per altre informazioni, Vedi [segnalazione SIP: FQDN](direct-routing-plan.md#sip-signaling-fqdns) e [traffico multimediale: intervalli di porte](direct-routing-plan.md#media-traffic-port-ranges).


> [!NOTE]
> È consigliabile impostare un limite di sessione simultaneo massimo per ogni SBC, in base al modello SBC. Tale limite attiverà quindi una notifica quando il SBC viene eseguito in corrispondenza o in prossimità della sua capacità.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere in quali posizioni distribuire SBCs.<li>Decidere un nome DNS per ogni SBC che si sta pianificando di distribuire.<li>In base alla decisione relativa al nome di dominio SBC, decidere se utilizzare un certificato con caratteri jolly per supportare tutti i SBCs della distribuzione o un certificato dedicato per SBC.<li>Decidere di quale autorità di certificazione pubblica si otterranno i certificati per il proprio SBCs.<li>Definire una coppia indirizzo IP pubblico/porta per ogni SBC che verrà distribuito e decidere se assegnare gli indirizzi IP pubblici al SBCs o usare NAT.<li>Identificare il numero massimo di sessioni simultanee supportate da ogni SBC o in grado di gestire.<li>Decidere quali SBCs verranno configurati tramite il bypass multimediale.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare ogni decisione in corso per il SBCs usando la tabella di esempio seguente.</ul>|


> [!TIP]
> Usare il modello seguente per documentare i dettagli SBC per la distribuzione di routing diretto.
> 
> | **Nome DNS SBC (FQDN)** | **Creazione e modello di SBC** | **Certificato** | **Posizione**  | **Indirizzo IP** | **Porta di segnalazione SIP** | **NAT?** | **Sessioni simultanee max** | **Bypass multimediale abilitato?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | DA definire | \*. contoso.com | Amsterdam | DA definire | DA definire | Sì | DA definire | No |
> | SBC-Asia.contoso.com | DA definire | \*. contoso.com | Hong Kong SAR (香港特別行政區) | DA definire | DA definire | No | DA definire | Sì |
> | SBC-Africa.contoso.com | DA definire | \*. contoso.com | Johannesburg | DA definire | DA definire | Sì | DA definire | Sì |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>Routing vocale

È necessario configurare Microsoft Phone System per instradare le chiamate allo specifico SBCs per il routing diretto. È possibile configurare le route vocali in base a:

-   Chiamato pattern numerico.

-   Modello numerico denominato + l'utente che effettua la chiamata.


Il routing delle chiamate è costituito dagli elementi seguenti:

-   Criteri di routing vocale: contenitore per gli usi PSTN; può essere assegnato a un utente o a più utenti

-   Usi PSTN: contenitore per le route vocali ed usi PSTN; possono essere condivisi in criteri di routing vocale diversi

-   Route vocali: modello numerico e set di gateway PSTN online da usare per le chiamate in cui il numero chiamante corrisponde al modello

-   Il gateway PSTN online-puntatore su SBC, memorizza anche la configurazione applicata quando viene inserita una chiamata tramite SBC, ad esempio forward P-Asserted-Identity (PAI) o codec preferiti; può essere aggiunto alle route vocali

È possibile configurare le route vocali con routing diretto per coesistere con i piani di chiamata. Questa configurazione consente la chiamata dei piani per instradare alcune delle chiamate allo specifico SBCs tramite il routing diretto.

> [!TIP]
> SBCs può essere designato come *attivo* e *backup*. Questo significa che quando l'SBC configurato come attivo per questo modello di numero o modello numerico + utente specifico non è disponibile, le chiamate verranno instradate a un SBC di backup.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidi i criteri di routing vocale, gli usi PSTN e le route vocali che creerai per supportare le posizioni degli utenti o gli uffici in ambito per l'implementazione del routing diretto.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Criteri di routing vocale per documenti, usi PSTN e route vocali per l'organizzazione.<li>Documentare gli utenti da assegnare per ogni criterio di routing vocale definito.</ul>|

> [!TIP]
> Usare il modello seguente per documentare i criteri vocali per la distribuzione del routing diretto.
> 
> | **Utilizzo PSTN** | **Route vocale** | **Schema numerico** | **Priorità** | **SBC** | **Descrizione** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | Solo Stati Uniti | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Route attiva per i numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX |
> | Solo Stati Uniti | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | Percorso di backup per numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX |
> | Solo Stati Uniti | "Altro + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Route per i numeri chiamati + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX) |
> | Internazionale | Internazionale | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | Route per qualsiasi modello di numero |
> 
> [!IMPORTANT]
> Gli usi PSTN nei criteri di routing vocale vengono applicati in ordine e se viene trovata una corrispondenza nel primo utilizzo, gli altri usi non vengono mai valutati.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Criteri di chiamata e di interoperabilità

Il routing diretto è supportato solo con Microsoft teams. Per effettuare o ricevere chiamate PSTN tramite routing diretto, è necessario configurare i criteri necessari per garantire che le chiamate in arrivo vengano ricevute in teams.

> [!NOTE]
> Gli utenti abilitati per il routing diretto non possono inserire o ricevere chiamate di routing dirette tramite Skype for business e quindi devono essere distribuiti dal client teams.

Puoi configurare gli utenti per impostare teams come client preferito per le chiamate tramite uno dei due metodi seguenti:

-   Configurare l'utente per la modalità solo Teams

-   Configura teams come client chiamante preferito assegnando TeamsCallingPolicy e TeamsInteropPolicy.

Per altre informazioni, Vedi [impostare Microsoft teams come client chiamante preferito per gli utenti](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidi l'approccio che userai per impostare teams come client preferito per le chiamate.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare gli utenti per essere configurati con i criteri di interoperabilità e chiamata.</ul>|

> [!IMPORTANT]
> Quando un utente è configurato per la modalità solo teams, l'utente non potrà più accedere a Skype for business.

Per consentire agli utenti di visualizzare la scheda chiamate nel client teams, è necessario abilitare la chiamata privata a livello di organizzazione per il tenant. Per altre informazioni su come abilitare le chiamate private, vedere [abilitare la chiamata a Microsoft teams](direct-routing-configure.md) .


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisioni del servizio documenti

Usare le informazioni delle sezioni precedenti di questo articolo per documentare le decisioni del servizio. In generale, questa documentazione conterrà le sezioni principali seguenti:

-   Sistema telefonico con l'elenco di abilitazione del sito piani di chiamata

-   Dettagli della configurazione della segreteria telefonica

-   Assegnazione di licenze per il sistema telefonico Direct routing degli utenti

-   Dettagli della configurazione di SBC

-   Criteri di routing vocale e dettagli di routing

-   Dettagli dei criteri di interoperabilità e chiamata

<!--ENDOFSECTION-->
