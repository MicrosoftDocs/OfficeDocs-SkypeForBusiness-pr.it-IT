---
title: Cos'è un ordine di portabilità?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Panoramica degli ordini di trasferimento e di come trasferire i numeri di telefono dal provider di servizi a Teams.
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.openlocfilehash: f4160d8e5fac5ec1f706bb7c82a881248d092a59
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584917"
---
# <a name="whats-a-port-order"></a>Cos'è un ordine di portabilità?

Se attualmente hai un gestore o provider di servizi telefonici e hai già numeri di telefono per i tuoi utenti o servizi, devi creare un "*ordine di trasferimento*" per trasferire tali numeri di telefono a Microsoft Teams. Dopo aver convertito i numeri, puoi assegnarli agli utenti e ai servizi, ad esempio i servizi di audioconferenza (per i bridge delle conferenze), gli operatori automatici e le code di chiamata.
  
Dopo aver convertito i numeri di telefono in Teams, Microsoft diventa il tuo provider di servizi e puoi disconnettere il servizio dal gestore o provider di servizi precedente.

Esaminare le informazioni contenute in questo articolo per acquisire familiarità con la portabilità del numero. In seguito, dovresti essere pronto per creare un ordine di trasferimento e trasferire i numeri di telefono. Per istruzioni dettagliate, vedere [Trasferire numeri di telefono in Teams](transfer-phone-numbers-to-teams.md) .
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quali paesi o aree geografiche supportano la portabilità del numero?

Puoi trasferire o trasferire numeri di telefono in tutti i paesi o le aree geografiche supportati, ma il modo in cui invii una richiesta di ordine di trasferimento dipende dal paese o dall'area geografica da cui provengono i numeri di telefono. Per un elenco dei paesi e delle aree geografiche che supportano la portabilità dei numeri, vedi [Gestire i numeri di telefono per l'organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

Attualmente, [la procedura guidata di portabilità](transfer-phone-numbers-to-teams.md) nell'interfaccia di amministrazione di Microsoft Teams supporta il recupero di numeri di telefono per il Regno Unito, Stati Uniti e il Canada. Per ottenere numeri di telefono per altri paesi e aree geografiche, puoi [inviare manualmente un ordine di trasferimento](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>Quali numeri possono essere trasferiti?

 **Puoi trasferire**
  
In generale, puoi trasferire qualsiasi numero di telefono da un provider supportato, tra cui:
  
- Numeri di rete fissa.

- Numeri di telefono cellulare, ad esempio quelli utilizzati per i telefoni cellulari e tablet.

    > [!NOTE]
    > Il trasferimento di numeri di cellulare è disponibile solo nel Stati Uniti e a Portorico.
  
- Numeri a pagamento.

- Numeri verdi.

    > [!NOTE]
    > Il numero uifn (Universal International Freephone Number) non può essere trasferito a Microsoft.
    > La disponibilità per la portabilità dei numeri verdi può variare in base al paese e all'area geografica. Per saperne di più, fai riferimento ai documenti specifici del paese o dell'area geografica per vedere il supporto disponibile per il servizio di trasferimento. 
  
- Numeri di telefono di servizio, ad esempio quelli utilizzati per i ponti conferenza, gli operatori automatici e così via.

- I numeri di telefono fax, ma non possono essere usati per inviare fax. Devono essere assegnate a un utente.

- Numeri di telefono VoIP di un provider di telefonia, ad esempio Vonage o RingCentral.

- Se trasferisci numeri di telefono ibridi (eseguendo la migrazione da Direct Routing o Operator Connect a Piani per chiamate), contatta il [team dei servizi](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) di numeri di telefono, assicurati di includere una nota che indichi che si tratta di numeri di telefono ibridi.

**Non è possibile trasferire:**
  
> [!NOTE]
> Al momento, non è possibile trasferire numeri di telefono o numeri non provenienti da un paese o un'area geografica supportati, inclusi i numeri di telefono di un provider di telefonia VoIP. Per un elenco dei paesi/aree geografiche supportati, vedi [Disponibilità di Paesi e aree geografiche per i piani per audioconferenze e chiamate](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Numeri di telefono utilizzati per le connessioni dati, ad esempio per le linee DSL o le connessioni Internet a banda larga.

- Numeri di telefono dedicati ai fax.

    Se hai numeri di telefono dedicati che vengono utilizzati per inviare fax,  *puoi*  trasferire questi numeri a Teams, ma i servizi fax non continueranno a funzionare come previsto. I servizi fax non sono disponibili per i clienti di Teams, anche se si hanno licenze per Sistema telefonico, Piano per chiamate nazionali o Piano per chiamate internazionali.

    Se si porta il numero di telefono in Teams, è possibile assegnare questo numero di telefono a un utente dell'organizzazione invece di usarlo per inviare fax.

> [!NOTE]
> Attualmente, nel Regno Unito, il trasferimento di numeri non geografici del Regno Unito inclusi i numeri di costo condivisi non è supportto per i codici area 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quali informazioni devo fornire?

Devi avere tutte le informazioni dell'account per il gestore corrente. Le informazioni immesse nell'ordine di trasferimento si trovano principalmente nell'estratto conto o nella fattura più recente del provider di servizi corrente. Devi anche conoscere il nome dell'account e i numeri da trasferire.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Cosa sono i trasferimenti di trasferimento completo e parziale?

Quando trasferisci numeri di telefono in Teams, hai la possibilità di trasferire tutti i tuoi numeri o alcuni di essi.
  
- **Porta completa** Si verifica quando trasferisci tutti i tuoi numeri dal provider di servizi corrente a Teams. Quando ti vengono richiesti i numeri di telefono da trasferire, *devi includere* il numero di telefono di fatturazione (BTN) insieme a tutti gli altri numeri di telefono del tuo account.

    Si supponga ad esempio che la BTN sia  *+1 425-555-1234*  e che si voglia trasferire tutti i 25 numeri di telefono (*da +1 425-555-1235 a 1259*). Seguendo le istruzioni riportate di seguito per trasferire i numeri, si immetterà + **14255551234 - +14255551259**.

- **Porta parziale** Si verifica quando trasferisci solo alcuni numeri di telefono dal provider di servizi corrente a Teams. Se vuoi trasferire alcuni numeri di telefono collegati allo stesso BTN, ** *non devi includere* ** il BTN insieme a tutti gli altri numeri di telefono del tuo account.

    Si supponga ad esempio che la BTN sia  *+1 425-555-1234*  e che si voglia trasferire solo 5 dei 25 numeri di telefono (*da +1 425-555-1235 a 1259*). Seguendo le istruzioni riportate di seguito per trasferire i numeri, immettere: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Posso inviare una singola richiesta di portabilità del numero per tutti i miei numeri contemporaneamente?
<a name="bkmk_type_1"> </a>

È necessaria una richiesta univoca per ogni gestore telefonico e tipo di numero da trasferire.
  
Ad esempio, è necessario inviare una richiesta di portabilità del numero univoco per ognuno dei seguenti tipi di numeri:
  
- Numeri a pagamento locali, noti anche come numeri di abbonati o numeri geografici

- Numeri verdi gratuiti con prefisso di località come 800, 844, 855, 866, 877 e 888

- Numeri di cellulare

- Numeri di servizio che possono essere utilizzati per le audioconferenze in Microsoft 365 o Office 365.

Ecco altre informazioni su come inviare richieste di portabilità del numero per ognuno di questi tipi di numeri:
  
- **I numeri di telefono** forniti da diversi gestori richiedono una richiesta di trasferimento univoca per i numeri con ciascun vettore.

- **I numeri verdi** con prefisso di località come 800, 844, 855, 866, 877 e 888 non possono essere inclusi in una richiesta di trasferimento numeri con altri tipi di numeri. Per trasferire questi numeri verdi, devi [inviare manualmente un ordine di trasferimento](manually-submit-port-order.md). Non è possibile trasferire questi numeri nell'interfaccia di amministrazione di Microsoft Teams. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    È importante usare la lettera di autorizzazione (LOA) corretta per il paese e il tipo di numeri di telefono da trasferire. È possibile [scaricare qui la loa necessaria](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- **I numeri di cellulare** richiedono un codice PIN per autorizzare il trasferimento. Pertanto, è necessaria una richiesta di portabilità del numero separata.

- **Le** richieste di portabilità del numero di servizio devono essere inviate da sole. Non possono essere inviati con altri tipi di numeri.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo è necessario per trasferire i numeri?
<a name="bkmk_type_1"> </a>

Dopo aver completato la richiesta di ordine di trasferimento, l'elaborazione della richiesta richiede da 7 a 14 giorni. Tuttavia, a seconda del provider di servizi, potrebbero essere necessari fino a 30 giorni. Dopo aver effettuato il trasferimento dei numeri di telefono, riceverai un'e-mail da noi per farti sapere che sei pronto.
  
Per controllare lo stato dell'ordine di trasferimento, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Numeri di telefono** **vocale** >  e quindi fare clic su **Cronologia ordini**. Ogni stato dell'ordine di portabilità è elencato nella colonna **Stato** .
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>I numeri di telefono degli utenti (abbonati) possono essere convertiti in numeri di servizio?
<a name="bkmk_type_1"> </a>

Sì, possono. A tale scopo, vedi [Gestire l'uso di un numero di telefono](../manage-the-usage-of-a-phone-number.md).

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>È possibile trasferire i numeri da Teams a un altro gestore o provider di servizi telefonici?

Per trasferire i numeri da Teams a un altro gestore, è necessario inviare una richiesta al nuovo gestore. Dovrai anche impostare un PIN di portabilità nell'interfaccia di amministrazione di Microsoft Teams.

Per definire il PIN di portabilità, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, vai a **Numeri di telefono** **vocale** > , nell'angolo in alto a destra della pagina, seleziona **Gestisci PIN di portabilità**, quindi immetti un PIN di 10 cifre.

Quando il nuovo gestore telefonico contatta Microsoft con la richiesta di portabilità, gli chiederemo di fornire il PIN definito.

Se hai bisogno di ulteriore assistenza per la configurazione di un PIN, contatta il [team dei servizi di numeri di telefono](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="common-mistakes-to-watch-out-for"></a>Errori comuni a cui prestare attenzione
<a name="bkmk_type_1"> </a>

La portabilità del numero è facile da eseguire. Tuttavia, se si verifica un problema con il provider di servizi telefonici, l'ordine è incompleto e mancano informazioni o se si verificano errori di digitazione.
  
Ecco gli errori più comuni che i clienti fanno durante il trasferimento dei numeri. Salva una chiamata al supporto tecnico e verifica la presenza di questi errori.
  
- Assicurati che le informazioni dell'account fornite corrispondano esattamente a quanto registrato dal gestore telefonico. Le informazioni non corrispondenti sono la causa più comune di errori e ritardano l'ordine di trasferimento. Verifica che sia vero quanto segue:

  - Il nome o la persona autorizzata ad apportare modifiche all'account è corretta.

  - L'indirizzo è corretto.

  - Il numero di conto è corretto.

  - BTN è corretto.

- Assicurati che su questi numeri di telefono non siano abilitate funzionalità avanzate di controllo delle chiamate, ad esempio la risposta alle chiamate o l'anello distintivo.

- Assicurati di non aver inserito nuovi ordini di servizio o di disconnetterti dal provider di servizi corrente.

- Assicurati che tutti i numeri proveniano dallo stesso gestore e dallo stesso account.

- Verificare che il servizio sia attivo. Il blocco dell'account impedisce la modifica dei gestori dell'account. La persona autorizzata ad apportare modifiche all'account deve inviare un ordine al gestore corrente per rimuovere il blocco. Questo processo può richiedere da una a tre settimane a seconda del vettore.

## <a name="related-topics"></a>Argomenti correlati

- [Qual è lo stato degli ordini di portabilità?](port-order-status.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
