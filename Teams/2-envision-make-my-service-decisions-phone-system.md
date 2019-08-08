---
title: Impostare il sistema telefonico con le decisioni di servizio per i piani di chiamata-Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scegliere tra piani di chiamata e licenze, configurare le posizioni di emergenza e le caratteristiche come la segreteria telefonica e l'ID chiamante, acquisire o trasferire numeri di telefono.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc618a4b68c8a620568eba5ae2ed52d17096b30
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233080"
---
# <a name="make-my-service-decisions"></a>Prendere le decisioni del servizio

Per pianificare l'implementazione tecnica del sistema telefonico con i piani di chiamata, è necessario effettuare una serie di decisioni di servizio prima del tempo per preparare meglio l'organizzazione per implementare una soluzione che soddisfi i requisiti aziendali definiti.

## <a name="calling-in-teams"></a>Chiamata in teams

Con Microsoft teams gli utenti possono effettuare e ricevere telefonate da o verso la rete PSTN (Public Switched Telephone Network). Gli utenti possono usare i propri numeri di telefono dedicati per l'immissione e la ricezione di chiamate telefoniche nazionali e internazionali dalle applicazioni client di teams, con funzionalità avanzate che includono la segreteria telefonica.

> [!NOTE]
> La roadmap per i team più recenti per identificare il sistema telefonico delle squadre con le caratteristiche del piano chiamante in ambito <https://aka.ms/O365Roadmap>per la distribuzione è disponibile all'indirizzo.

## <a name="phone-system-in-teams"></a>Sistema telefonico in teams

Affinché gli utenti di teams possano effettuare e ricevere chiamate PSTN, devono essere abilitati per il sistema telefonico, una funzionalità di Office 365.

Per abilitare la connettività alla rete PSTN, l'organizzazione può usare Microsoft come provider di servizi di telecomunicazioni. Alla fine si avrà anche la possibilità di "portare il proprio provider di servizi di telecomunicazioni" per abilitare la connettività alla rete PSTN per il sistema telefonico.

> [!IMPORTANT]
> La possibilità di usare il proprio provider di servizi di telecomunicazioni per il sistema telefonico con la distribuzione di teams è disponibile anche con routing diretto del sistema telefonico. Per altre informazioni sul routing diretto, vedere le [indicazioni](2-envision-make-my-service-decisions-direct-routing.md)per il routing diretto.

## <a name="phone-system-with-calling-plans"></a>Sistema telefonico con piani di chiamata

Per usare Microsoft come provider di servizi di telecomunicazioni, è necessario ottenere le licenze per il piano di chiamata e assegnarle agli utenti del sistema telefonico.

Esistono due tipi principali di piani di chiamata:

-   Piano per chiamate nazionali

-   Piano per chiamate nazionali e internazionali

Ogni tipo di piano chiamante assegna un certo numero di minuti di chiamata per mese a ogni utente a cui è stata assegnata la licenza. Quando l'allocazione dei minuti di chiamata è esaurita, l'utente non potrà inserire le chiamate in uscita, ad eccezione delle chiamate di emergenza, fino al ciclo di fatturazione del mese successivo. Se si vuole che gli utenti possano continuare a inserire la chiamata in uscita anche dopo aver esaurito l'allocazione dei minuti di chiamata oppure per consentire agli utenti che hanno un piano per chiamate nazionali di effettuare telefonate internazionali, è possibile configurare i crediti per le comunicazioni per l'organizzazione.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilità dei piani per le chiamate

Prima di pianificare l'implementazione dei piani per le chiamate in team, verificare che il servizio piani di chiamata sia disponibile nella propria area, rivedendo la disponibilità per i servizi di [audioconferenza e le chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> A causa di vincoli legali, per consentire alle chiamate di essere disponibili per le organizzazioni multinazionali, il contratto per gli abbonamenti a Office 365 deve essere basato in un paese o in un'area geografica in cui il servizio piani di chiamata è disponibile o in cui il servizio piani di chiamata può essere acquistato.

> [!NOTE]
> Se i piani per le chiamate non sono disponibili nell'area, è possibile usare il [routing diretto del sistema telefonico](2-envision-make-my-service-decisions-direct-routing.md) per consentire agli utenti di usare teams con funzionalità PSTN.

Dopo aver confermato che l'organizzazione può ottenere il servizio piani di chiamata, compilare l'elenco delle posizioni o degli uffici degli utenti in cui verrà implementato il servizio piani di chiamata, in base all'elenco di paesi e aree geografiche disponibili.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Scegliere le posizioni o gli uffici degli utenti a cui implementare il servizio piani di chiamata.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le posizioni degli utenti o gli uffici da abilitare per il servizio piani di chiamata.</li></ul>|

> [!TIP]
> Di seguito è riportato un esempio di sistema telefonico con l'elenco di abilitazione del sito piani di chiamata.
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

Con i piani per le chiamate in Office 365, ogni utente dell'organizzazione deve avere un numero di telefono univoco diretto (DID) e un indirizzo di emergenza convalidato corrispondente. Revisione [gestire i numeri di telefono Cloud Voice](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers) per pianificare l'acquisizione del numero di telefono per l'implementazione dei piani di chiamata.

Quando si configurano i numeri di telefono per i piani di chiamata, è necessario assegnare un indirizzo di emergenza a ogni numero di telefono prima di assegnare il numero a un utente. Questa operazione è necessaria per supportare le chiamate di emergenza. L'indirizzo di emergenza deve essere convalidato per assicurarsi che sia nel formato corretto da usare per i servizi di risposta di emergenza.

> [!IMPORTANT]
> I servizi di emergenza che chiamano funzionano in modo diverso nel servizio piani di chiamata rispetto ai servizi telefonici tradizionali. È importante comprendere queste differenze e comunicarle a tutti gli utenti. Per altre informazioni, Vedi [termini e condizioni per le chiamate di emergenza](emergency-calling-terms-and-conditions.md) .

Oltre a fornire un indirizzo di emergenza convalidato, è possibile definire i percorsi di emergenza e associarli all'indirizzo di emergenza convalidato per ottenere una posizione più precisa all'interno di un indirizzo. Una posizione di emergenza è in genere un numero di edificio, un piano, un'ala da costruzione o un numero di ufficio in cui si trova l'utente.

Per ulteriori informazioni sulle posizioni di emergenza in relazione ai piani di chiamata, vedere gli articoli seguenti:

-   [Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?](what-are-emergency-locations-addresses-and-call-routing.md)

-   [Condizioni per le chiamate di emergenza](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere la granularità delle informazioni sulla posizione di emergenza da raccogliere per le posizioni degli utenti o gli uffici nell'ambito dell'implementazione dei piani di chiamata.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare l'indirizzo di emergenza dettagliato e le posizioni di emergenza per ogni posizione utente o Office in ambito per l'implementazione dei piani di chiamata.</li></ul>|

> [!TIP]
> È possibile usare il modello seguente per documentare i dettagli dei numeri di telefono e della posizione di emergenza.
> 
> |Utente |Posizione e indirizzo di emergenza |Numero di telefono |
> |-----|-------------------------------|-------------|
> |Emily Braun |1034/32 London Bridge Street, Londra, SE1, Regno Unito |+ 44 23 4567 8901 |
> |Lidia Holloway |1065/32 London Bridge Street, Londra, SE1, Regno Unito |+ 44 23 4567 89112 |
> |Luigi Lahr |1023/32 London Bridge Street, Londra, SE1, Regno Unito |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | TBA |
> |Rachelle Cormier |07N15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | TBA |
> |Isabell Potvin |07F05E/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Casella vocale

Cloud voicemail, alimentato da servizi di Azure voicemail, supporta i depositi della segreteria telefonica solo alle cassette postali di Exchange e non supporta sistemi di posta elettronica di terze parti.

Per impostazione predefinita, cloud Voicemail funziona con Exchange Online; Tuttavia, ha una versione di Exchange locale e un modello di distribuzione supportati minimi per consentire il recapito dei messaggi della segreteria telefonica alle cassette postali degli utenti nella distribuzione locale di Exchange.

Cloud Voicemail include la trascrizione della segreteria telefonica, che è abilitata per tutti gli utenti dell'organizzazione per impostazione predefinita. Le esigenze aziendali potrebbero richiedere la disattivazione della trascrizione della segreteria telefonica per utenti specifici o tutti nell'organizzazione. Se l'organizzazione ha deciso di tenere attivata la trascrizione della segreteria telefonica, è necessario considerare anche se la trascrizione della segreteria telefonica deve essere abilitata. Per altre informazioni, vedere [impostazione di criteri per la segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md) .

>[!NOTE]
> È stato implementato un meccanismo di fallback in modo che cloud Voicemail possa rinviare i messaggi tramite SMTP, ovvero gli utenti che dispongono di una cassetta postale in un sistema di posta elettronica di terze parti riceveranno i messaggi della segreteria telefonica. Questo meccanismo non include l'uptime del servizio garantito o altre caratteristiche della segreteria telefonica, ad esempio la modifica del saluto della segreteria telefonica.

Per altre informazioni sulla segreteria telefonica in un'implementazione di sistema telefonico, vedere [sistema telefonico con piani di chiamata](calling-plan-landing-page.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se abilitare il messaggio vocale cloud nell'implementazione dei piani di chiamata.</li><li>Se l'uso di Exchange locale e la distribuzione esistente non soddisfano i requisiti per il supporto della segreteria telefonica cloud, scegliere tra le opzioni disponibili (aggiornamento e configurazione per il supporto di cloud voicemail, migrazione a Exchange Online o sfruttare il fallback meccanismo descritto in precedenza).</li><li>Decidere se abilitare o disabilitare la trascrizione della segreteria telefonica e la trascrizione della segreteria telefonica in tutta l'organizzazione o per utenti specifici.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Se applicabile, documentare i punti decisionali di Exchange per il supporto della segreteria telefonica cloud.</li><li>Se si Abilita/Disabilita la segreteria telefonica, la trascrizione della segreteria telefonica e la trascrizione della segreteria telefonica solo per utenti specifici, documenta l'elenco degli utenti.</li></ul>|

> [!TIP]
> I dettagli della segreteria telefonica cloud per il sistema telefonico con l'implementazione di piani di chiamata possono essere documentati come segue.
> 
> |Utente |Cassetta postale di Exchange |Abilitare la segreteria telefonica? |Trascrizione della segreteria telefonica |Mascheramento profanità trascrizione della segreteria telefonica |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |Sì |Abilitata |Abilitata |
> |Lidia Holloway   |Online      |Sì |Abilitata |Disabilitata |
> |Luigi Lahr       |Locale |Sì |Abilitata |Abilitata |
> |Marcel Beauchamp |Locale |Sì |Disabilitata |N/D |
> |Rachelle Cormier |Online      |Sì |Disabilitata |N/D |
> |Isabell Potvin   |Locale |Sì |Disabilitata |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Chiamata dell'identità

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante). Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata. In alcuni casi, esistono requisiti aziendali legittimi per nascondere l'ID chiamante per proteggere l'identità dei chiamanti tramite il numero di riga principale di Office, in genere un numero di servizio servito dalla configurazione dell'operatore automatico, come ID chiamante o per bloccare l'ID chiamante presentazione del tutto.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se è necessaria la manipolazione dell'ID chiamante per l'implementazione dei piani di chiamata.</li><li>Se applicabile, decidere i tipi di manipolazione dell'ID chiamante (maschera con numero di servizio o anonimizzare) da implementare.</li><li>Se applicabile, decidere quali utenti richiedono la manipolazione dell'ID chiamante e il tipo di manipolazione dell'ID chiamante da assegnare a ogni utente.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare gli utenti come assegnati alla manipolazione dell'ID chiamante e il tipo di manipolazione dell'ID chiamante da assegnare.</li></ul>|

> [!TIP]
> Di seguito è riportato un esempio di documentazione relativa alla mascheratura dei dettagli dell'ID chiamante.
> 
> |Utente  |Abilitare la mascheratura dell'ID chiamante in uscita  |Tipo di mascheramento ID chiamante  |Consenti override utente  | Abilitare la mascheratura dell'ID chiamante in ingresso  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|No|N/D|Sì|No|
> |Lidia Holloway|Sì|Numero di servizio (OrgAA + 44 20 7946 0000)|No|Sì|
> |Luigi Lahr|No|N/D|Sì|No|
> |Marcel Beauchamp|Sì|Numero di servizio (OrgAA, TBA)|No|Sì|
> |Rachelle Cormier|Sì|Anonimizzare|Sì|No|
> |Isabell Potvin|Sì|Numero di servizio (OrgAA, TBA)|No|Sì|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Licenze per funzionalità cloud Voice

I servizi di audioconferenza e il sistema telefonico sono funzionalità in Office 365. Possono essere concessi in licenza separatamente come servizi per i componenti aggiuntivi per clienti esistenti che hanno piani di abbonamento a Office 365 E3 o E1; sono già inclusi nell'ambito del piano di sottoscrizione di Office 365 E5.

I piani di chiamata sono un componente aggiuntivo della funzionalità di sistema telefonico in Office 365, quindi è necessario disporre di un sistema telefonico abilitato per l'uso di piani di chiamata.

Per supportare altri servizi di audioconferenza e piani di chiamata, è possibile impostare i crediti per le comunicazioni per l'organizzazione, ad uso dei casi di chiamate internazionali, chiamate esterne dopo l'esaurimento delle assegnazioni del piano di chiamata.

## <a name="licensing-for-calling-plans"></a>Licenze per i piani di chiamata

Se l'organizzazione intende usare Microsoft come provider di servizi di telecomunicazioni, è necessario ottenere i componenti aggiuntivi per il piano di chiamata appropriati per i requisiti aziendali degli utenti. In generale, non tutti gli utenti di un'organizzazione devono effettuare chiamate internazionali, in modo da poter eseguire il provisioning della maggior parte dei clienti con licenze per le chiamate nazionali.

Esistono due tipi di licenze per il piano di chiamata:

-   Piano per chiamate nazionali

-   Piano per chiamate internazionali e nazionali

> [!NOTE]
> Ciò che viene considerato "domestico" per un utente specifico è determinato dal percorso di utilizzo di Office 365 assegnato dall'utente.

Ogni tipo di piano chiamante offre un'assegnazione di minuti di chiamata che gli utenti possono usare per mese, per effettuare chiamate nazionali o chiamate internazionali. Il piano per le chiamate nazionali costa meno rispetto al piano di chiamate internazionali e nazionali.

La flessibilità di sottoscrizione e assegnazione del tipo di piano chiamante più appropriato per i singoli requisiti aziendali per gli utenti consente all'organizzazione di controllare i costi dell'implementazione dei piani di chiamata.

Per ogni tenant di Office 365, il numero combinato di minuti per le chiamate viene riunito per paese o area geografica e per tipo di piano chiamante. Quando viene raggiunto il limite di minuti per le chiamate mensili per il tenant, il servizio piani di chiamata (ad eccezione delle chiamate di emergenza) verrà sospeso per il resto del mese. Il servizio piani di chiamata viene ripreso automaticamente il primo giorno del mese successivo del calendario.

È possibile configurare i crediti per le comunicazioni per le organizzazioni per consentire agli utenti di effettuare chiamate in uscita dopo che l'allocazione dei minuti di chiamata viene esaurita senza dover attendere il ciclo di fatturazione del mese successivo. Inoltre, i crediti per le comunicazioni conferiscono agli utenti il piano per le chiamate nazionali la possibilità di effettuare telefonate internazionali, che vengono quindi addebitate usando un modello "pay-per-minute".

Per altre informazioni sul sistema telefonico e sui piani di chiamata, vedere gli articoli seguenti:

-   [Sistema telefonico](https://products.office.com/en-us/skype-for-business/phone-system)

-   [Piani per chiamate](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Se l'organizzazione non ha la licenza necessaria per il sistema telefonico, decidere se acquisire la licenza per il sistema telefonico tramite l'aggiunta di abbonamenti a Office 365 o l'acquisizione del servizio di componente aggiuntivo per il sistema telefonico.</li><li>Decidere quali utenti richiedono una licenza per un piano per chiamate nazionali e che richiedono una licenza per il piano di chiamate nazionali e internazionali.</li><li>Decidere se è necessario disporre di crediti per le comunicazioni per l'implementazione dei piani di chiamata.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare i gruppi divisione, reparto, ufficio o utenti assegnare una licenza di sistema telefonico con piano per chiamate nazionali o piano per chiamate nazionali e internazionali.</li></ul>|

> [!TIP]
> Puoi usare l'esempio seguente per documentare l'assegnazione della licenza per il sistema telefonico con gli utenti dei piani di chiamata.
> 
> |Utente |Ufficio |Licenza di Office 365 |Piano per le chiamate |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Piano per chiamate internazionali e nazionali |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Piano per chiamate nazionali |
> |Luigi Lahr |32 London Bridge Street |Office 365 E5 |Piano per chiamate nazionali |
> |Marcel Beauchamp |39 Quai du Président Roosevelt |Office 365 E3, componente aggiuntivo per il sistema telefonico |Piano per chiamate nazionali |
> |Rachelle Cormier |39 Quai du Président Roosevelt |Office 365 E5 |Piano per chiamate internazionali e nazionali |
> |Isabell Potvin |39 Quai du Président Roosevelt |Office 365 E3, componente aggiuntivo per il sistema telefonico |Piano per chiamate nazionali |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Crediti comunicazioni

Usando i crediti per le comunicazioni, gli utenti possono effettuare la chiamata da una riunione di audioconferenza per aggiungere un altro utente da qualsiasi parte del mondo (al di fuori del paese di origine dell'organizzatore della riunione). È possibile configurare i crediti per le comunicazioni per l'organizzazione per consentire agli utenti di effettuare chiamate in uscita dopo aver esaurito l'assegnazione dei minuti di chiamata, senza dover attendere il ciclo di fatturazione del mese successivo. Inoltre, i crediti per le comunicazioni conferiscono agli utenti assegnati al piano per le chiamate nazionali la possibilità di effettuare telefonate internazionali, che vengono quindi addebitate usando un modello "pay-per-minute".

La prima considerazione da apportare quando si implementano i crediti per le comunicazioni consiste nel decidere l'importo iniziale dei fondi da acquistare. Se l'organizzazione sceglie di usare la ricarica automatica, si determinerà l'importo ottimale misurando l'utilizzo effettivo. Monitorare l'utilizzo dei crediti di comunicazione nel tempo e regolare l'importo della ricarica come richiesto.

Per l'implementazione di piani di chiamata, è possibile controllare l'uso dei crediti di comunicazione per ogni singolo utente, che ti aiuta a assicurarti di aver assegnato questi crediti in linea con le esigenze aziendali.

Per altre informazioni sui crediti per le comunicazioni, vedere [quali sono i crediti per le comunicazioni?](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se sono necessari crediti per comunicazioni per l'implementazione di servizi di audioconferenza o per i piani di chiamata.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare i gruppi divisione, reparto, Office o utenti per cui si consentiranno i crediti per le comunicazioni.</li><li>Documentare il piano per i crediti di comunicazione per l'implementazione di servizi di audioconferenza o piani di chiamata.</li></ul>|

> [!TIP]
> Puoi usare l'esempio seguente per documentare l'elenco di assegnazione crediti comunicazioni per gli utenti dei piani di chiamata.
> 
> |Utente |Ufficio |Piano per le chiamate |Crediti comunicazioni |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Piano per chiamate internazionali e nazionali |Abilitata |
> |Lidia Holloway |32 London Bridge Street |Piano per chiamate nazionali |Disabilitata |
> |Luigi Lahr |32 London Bridge Street |Piano per chiamate nazionali |Abilitata |
> |Marcel Beauchamp |39 Quai du Président Roosevelt |Piano per chiamate nazionali |Disabilitata |
> |Rachelle Cormier |39 Quai du Président Roosevelt |Piano per chiamate internazionali e nazionali |Abilitata |
> |Isabell Potvin |39 Quai du Président Roosevelt |Piano per chiamate nazionali |Disabilitata |

<br>

> [!TIP]
> I numeri di pianificazione per i crediti di comunicazione possono essere documentati come nell'esempio seguente.
>
> |         |         |
> |---------|---------|
> |Importo iniziale|$1.000|
> |Importo trigger|$400|
> |Importo di ricarica automatica|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gestire i numeri di telefono Cloud Voice

Se implementi il sistema telefonico portando il proprio provider di servizi di telecomunicazioni, la gestione dei numeri di telefono rimarrà così com'è.

Per le implementazioni di servizi di audioconferenza e per i piani di chiamata, è possibile scegliere di acquisire nuovi numeri di telefono o di trasferimento (porta) numeri di telefono esistenti.

Per consentire agli utenti di chiamare i numeri di telefono nel modo in cui sono abituati, ad esempio omettendo i codici di area per le chiamate locali, omettendo il codice paese per le chiamate nazionali o anche usando la chiamata a breve cifra durante l'esecuzione della chiamata in uscita o chiamando altri utenti nell'organizzazione, è possibile configurare un dial plan personalizzato e assegnarlo agli utenti.

## <a name="acquire-new-telephone-numbers"></a>Acquisire nuovi numeri di telefono

I due tipi di numeri di telefono nelle soluzioni Microsoft Cloud Voice sono i seguenti:

-   Numeri di abbonato (utente), che possono essere assegnati agli utenti dell'organizzazione.

-   Numeri di servizio, disponibili come numeri di servizio a pagamento e a pagamento, che hanno una maggiore capacità di chiamata simultanea rispetto ai numeri di abbonato e possono essere assegnati a servizi come audioconferenza, operatori automatici o code di chiamata.

Per altre informazioni sui tipi di numeri di telefono, vedere [diversi tipi di numeri di telefono usati per i piani di chiamata](different-kinds-of-phone-numbers-used-for-calling-plans.md).

Il numero totale di numeri di telefono che è possibile ottenere dipende dal tipo di telefono e dal numero di licenze acquistate e assegnate agli utenti.

Per altre informazioni sul numero totale di numeri di telefono ottenibili, vedere [quanti numeri di telefono si possono ottenere?](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere le posizioni o gli uffici degli utenti in cui verranno acquisiti nuovi numeri di telefono da Microsoft.</li><li>Decidere il tipo di numeri di telefono da acquisire da Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le posizioni degli utenti o gli uffici in cui verranno acquisiti nuovi numeri di telefono da Microsoft.</li><li>Documentare il tipo di numeri di telefono da acquisire da Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Trasferire i numeri di telefono esistenti

Se l'organizzazione vuole trasferire (o portare) i numeri di telefono esistenti a Microsoft, è possibile inviare una richiesta di ordine di trasferimento a Microsoft.

È possibile trasferire tutti i numeri di telefono esistenti contemporaneamente (porta completa) e, in alcuni mercati, è possibile trasferire un sottoinsieme dei numeri di telefono esistenti (porta parziale). Una porta parziale può essere utile nei casi in cui si vuole semplicemente trasferire gradualmente gli utenti nel sistema telefonico con i piani di chiamata.

Un singolo ordine di porta può solo trasferire i numeri di telefono a un singolo tipo di numero di telefono. Se è necessario trasferire alcuni numeri di telefono come numeri di abbonato e alcuni come numeri di servizio, è consigliabile completare prima il trasferimento a Microsoft e quindi eseguire la conversione non appena i numeri si trovano nel controllo di Microsoft.

In alternativa, se è supportata la porta parziale, è possibile inviare più richieste di porta, una richiesta di porta alla volta. Questo approccio alternativo prolungherà tuttavia il contratto con il provider di servizi di telecomunicazioni esistente.

La conversione di numeri di telefono è un argomento complesso e richiede pianificazione, coordinamento e gestione adeguati delle aspettative delle parti interessate. Per altre informazioni, vedere gli articoli seguenti:

-   [Trasferimento di numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md)

-   [Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere le posizioni o gli uffici degli utenti in cui i numeri di telefono esistenti verranno trasferiti a Microsoft.</li><li>Decidere il tipo di numeri di telefono da trasferire a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le posizioni o gli uffici degli utenti in cui i numeri di telefono esistenti verranno trasferiti a Microsoft.</li><li>Documentare il tipo di numeri di telefono da trasferire a Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Dial plan

Un dial plan nella caratteristica sistema telefonico di Office 365 è un set di regole di normalizzazione che traducono i numeri di telefono composti in un formato alternativo (in genere E. 164) per l'autorizzazione alle chiamate e il routing delle chiamate. Il servizio di audioconferenza sfrutta le stesse funzionalità usate dal sistema telefonico per tradurre i numeri di telefono compilati in scenari di chiamata in uscita per conferenze, ad esempio invitare i partecipanti tramite PSTN e effettuare la chiamata, "Chiamami".

Nella caratteristica sistema telefonico di Office 365 sono disponibili due tipi di dial plan:

-   **Dial plan di servizio:** Questo è il dial plan predefinito applicato agli utenti in base alla posizione di utilizzo di Office 365 e non può essere modificato.

-   **Dial plan tenant:** Si tratta di un dial plan personalizzabile all'interno di un tenant, che viene ulteriormente suddiviso in due tipi:

    -   **Tenant-dial plan globale:** Il dial plan che si applica a tutti gli utenti del tenant.

    -   **Tenant-dial plan per utenti:** Il dial plan che si applica solo a utenti specifici.

Il dial plan effettivo assegnato agli utenti è la combinazione del piano di chiamata di servizio (in base alla posizione di utilizzo di Office 365 dell'utente) e del dial plan tenant (che può essere un piano di dial plan globale o tenant-utente).

![Tabella mostra tre combinazioni di piani di servizio e di dial tenant.] (media/audio_conferencing_image8.png "Tabella mostra tre combinazioni di piani di servizio e di dial tenant.")

> [!IMPORTANT]
> In ogni dial plan del tenant può essere previsto un massimo di 25 regole di normalizzazione; per questo motivo, è importante evitare di duplicare le regole di normalizzazione già disponibili nell'ambito del piano di servizi di chiamata.

Per altre informazioni sui dial plan, vedere [cosa sono i dial plan?](what-are-dial-plans.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se l'organizzazione richiede piani di dial personalizzati (requisiti aziendali, requisiti di adozione e così via).</li><li>Se applicabile, decidere l'ambito del piano di chiamata del tenant (tenant-globale o tenant-utente) per supportare i requisiti per i dial plan personalizzati.</li><li>Se applicabile, decidere i piani di chiamata del tenant che verranno creati per supportare le posizioni degli utenti o gli uffici in ambito per l'implementazione di cloud Voice.</li><li>Se applicabile, decidere quali utenti richiedono un piano di chiamata personalizzato e il piano di chiamata del tenant da assegnare per ogni utente.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare i piani di chiamata personalizzati e le regole di normalizzazione associate da configurare come parte dell'implementazione di cloud Voice.</li><li>Documento a cui gli utenti devono assegnare un dial plan personalizzato e il piano di chiamata del tenant da assegnare per ogni utente.</li></ul>|

> [!TIP]
> Se è applicabile al progetto, è possibile usare il modello seguente per documentare le configurazioni di dial plan del tenant.
> 
> |Nome del piano di chiamata tenant<br>_Descrizione_  |Nome regole di normalizzazione<br>_Descrizione_  |Modello<br>Conversione<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, AU dial plan_|**AU-NSW-NorthRyde-OER-interno**<br>_Numero interno (X7000-x7999) per un ufficio stradale di Epping, North Ryde, NSW, Australia_|^ (7 \ d{3}) $<br>+ 6125550 $1<br>True|
> ||**AU-NSW-local**<br>_Normalizzazione dei numeri locali per NSW, Australia_|^ ([2-9] \d{7}) $<br>+ 612 $1<br>False|
> ||**AU-TollFree**<br>_Normalizzazione numeri verdi per l'Australia_|^ (1 [38] \d{4,8}) \d * $<br>+ 61 $1<br>False|
> ||**AU-Service**<br>_Normalizzazione dei numeri di servizio per l'Australia_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapore, SG dial plan_|**SG-OMB-interno**<br>_Numero interno (X8000 â € "x8999) per OMB Office, Singapore_|^ (8 \ d{3}) $<br>+ 656888 $1<br>True|
> ||**SG-TollFree**<br>_Normalizzazione numeri verdi per Singapore_|^ (1? 800 \ d{7}) \d * $<br>+ 65 $1<br>False|
> ||**SG-Service**<br>_Normalizzazione dei numeri di servizio per Singapore_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>False|
> |**FR-Parigi-Issy-39qdPR**<br>_39 Quai du Président Roosevelt Issy-les-Moulineaux, Francia dial plan_|**FR-39qdPR-Internal**<br>_Numero interno (X7000 â € "x7999) per 39 Quai du Président Roosevelt Office, Issy-les-Moulineaux, Francia_|^ (7 \ d{3}) $<br>+ 3319999 $1<br>True|
> ||**FR-TollFree**<br>_Normalizzazione numeri verdi per la Francia_|^ 0? (80 \ d{7}) \d * $<br>+ 33 $1<br>False|
> ||**FR-Service**<br>_Normalizzazione dei numeri di servizio per la Francia_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> Il modello di esempio seguente può essere sfruttato per le assegnazioni di dial plan per documenti per supportare il progetto:
>
> |Utente  |Ufficio  |Tipo di dial plan  |Nome del dial plan  |
> |---------|---------|---------|---------|
> |Adele Vance|Una strada di Epping|Dial plan tenant|AU-NSW-NorthRyde-OER|
> |Alex Wilber|Una strada di Epping|Dial plan tenant|AU-NSW-NorthRyde-OER|
> |Ben Walters|Una strada di Epping|Dial plan tenant|AU-NSW-NorthRyde-OER|
> |Christie Cline|Una Marina Boulevard|Dial plan tenant|SG-Singapore-OMB|
> |Debra Berger|Una Marina Boulevard|Dial plan tenant|SG-Singapore-OMB|
> |Lee GU|Una Marina Boulevard|Dial plan tenant|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Dial plan di servizio|N/D|
> |Lidia Holloway|32 London Bridge Street|Dial plan di servizio|N/D|
> |Luigi Lahr|32 London Bridge Street|Dial plan di servizio|N/D|
> |Marcel Beauchamp|39 Quai du Président Roosevelt|Dial plan tenant|FR-Parigi-Issy-30qdPR|
> |Rachelle Cormier|39 Quai du Président Roosevelt|Dial plan tenant|FR-Parigi-Issy-30qdPR|
> |Isabell Potvin|39 Quai du Président Roosevelt|Dial plan tenant|FR-Parigi-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisioni del servizio documenti 

Usare le informazioni delle sezioni precedenti di questo articolo per documentare le decisioni del servizio. In generale, questa documentazione conterrà le sezioni principali seguenti:

-   Sistema telefonico con l'elenco di abilitazione del sito piani di chiamata

-   Assegnazione di licenze per il sistema telefonico con gli utenti dei piani di chiamata

-   Numeri di pianificazione per i crediti comunicazioni

-   Acquisizione del numero di telefono, numeri di telefono e informazioni sulla posizione di emergenza

-   Dettagli della configurazione della segreteria telefonica

-   Informazioni sulla configurazione della mascheratura dell'ID chiamante

-   Piani di dial tenant

-   Assegnazioni di dial plan

<!--ENDOFSECTION-->