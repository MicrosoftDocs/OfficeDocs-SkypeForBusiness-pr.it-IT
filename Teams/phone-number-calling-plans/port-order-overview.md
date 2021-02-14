---
title: Cos'è un ordine di portabilità?
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Panoramica degli ordini di trasferimento e di come trasferire i numeri di telefono dal provider di servizi a Teams.
ms.openlocfilehash: 4f1f8ca843db8c2b27eaa467b0014befe6f2b519
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802506"
---
# <a name="whats-a-port-order"></a>Cos'è un ordine di portabilità?

Se attualmente hai un gestore o provider di servizi telefonici e hai già i numeri di telefono per i tuoi utenti o servizi, devi creare un *"* ordine di trasferimento " per trasferire quei numeri di telefono in Microsoft Teams. Quando i numeri vengono traslati, puoi assegnarli agli utenti e a servizi come l'audioconferenza (per i bridge conferenza), gli operatori automatici e le code di chiamata.
  
Dopo aver porta i numeri di telefono in Teams, Microsoft diventa il tuo provider di servizi e puoi disconnettere il servizio dal gestore o provider di servizi precedente.

Esaminare le informazioni in questo articolo per acquisire familiarità con la portabilità del numero. In seguito, dovresti essere pronto per creare un ordine di trasferimento e trasferire i numeri di telefono. Per [istruzioni dettagliate, vedere](transfer-phone-numbers-to-teams.md) Trasferire numeri di telefono in Teams.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quali paesi o aree geografiche supportano la portabilità del numero?

Puoi trasferire numeri di telefono in tutti i paesi o aree geografiche supportati, ma il modo in cui invii la richiesta di un ordine di trasferimento dipende dal paese o dall'area geografica da cui provengono i numeri di telefono. Per un elenco di paesi e aree geografiche che supportano la portabilità del numero, vedi [Gestire i numeri di telefono per l'organizzazione.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

Attualmente, [la procedura guidata di](transfer-phone-numbers-to-teams.md) portabilità nell'interfaccia di amministrazione di Microsoft Teams supporta la ricezione di numeri di telefono per Regno Unito, Stati Uniti e Canada. Per ottenere numeri di telefono per altri paesi e aree geografiche, puoi [inviare manualmente un ordine di trasferimento.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>Quali numeri possono essere trasferiti?

 **Puoi trasferire**
  
In generale, puoi trasferire qualsiasi numero di telefono di un provider supportato, tra cui:
  
- Numeri di telefono land line.

- Numeri dei dispositivi mobili, ad esempio quelli utilizzati per i cellulari e tablet.

    > [!NOTE]
    > Il trasferimento di numeri di cellulare è disponibile solo negli Stati Uniti e a Portorico.
  
- Numeri a numero verde.

- Numeri verde.

    > [!NOTE]
    > Il numero UIFN (Universal International Freephone Number) non può essere trasferito a Microsoft. 
  
- Numeri di servizio, ad esempio quelli utilizzati per il bridge di conferenza, gli operatori automatici e così via.

- Numeri di fax, ma non possono essere utilizzati per inviare fax. Devono essere assegnate a un utente.

- Numeri VoIP di un provider di telefonia come Vonage o RingCentral.

- Numeri di telefono ibridi Skype for Business. Se vuoi trasferire questi numeri, inviaci un'e-mail all'indirizzo <ptn@microsoft.com> .

  **Non è possibile trasferire:**
  
    > [!NOTE]
    > Al momento, non puoi trasferire numeri di telefono o numeri che non siano di un paese o un'area geografica supportati, inclusi i numeri di telefono di un provider di telefonia VoIP. Per un elenco dei paesi/aree geografiche supportati, consulta la disponibilità dei Paesi e delle aree geografiche [per audioconferenze e piani per chiamate](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Numeri di telefono utilizzati per le connessioni dati, ad esempio per linee DSL o connessioni Internet a banda larga.

- Numeri di telefono dedicati a inviare fax.

    Se si hanno numeri di telefono dedicati utilizzati per  inviare fax, è possibile trasferire tali numeri in Teams, ma i servizi fax non continueranno a funzionare come previsto. I servizi fax non sono disponibili per i clienti di Teams, anche se si hanno licenze per Sistema telefonico, Piano per chiamate nazionali o Piano per chiamate internazionali.

    Se si porta il numero di telefono in Teams, è possibile assegnarlo a un utente dell'organizzazione invece di usarlo per inviare fax.

    > [!NOTE]
    > Al momento nel Regno Unito non supportiamo il trasferimento di numeri non geografici del Regno Unito, inclusi i numeri di costo condiviso per codici di area 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quali informazioni è necessario fornire?

Devi disporre di tutte le informazioni dell'account per il gestore corrente. Le informazioni immesse nell'ordine di trasferimento si trovano principalmente nella fattura più recente del provider di servizi corrente. È anche necessario sapere di quale nome si trova nell'account e di quali numeri si vuole eseguire il portabilità.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Cosa sono i trasferimenti completi o parziali?

Quando trasferisci numeri di telefono in Teams, hai la possibilità di trasferire tutti i tuoi numeri o alcuni di essi.
  
- **Portabilità completa** Si verifica quando trasferisci tutti i tuoi numeri dal provider di servizi corrente a Teams. Quando ti vengono chieti i numeri di  telefono che desideri trasferire, devi includere il numero di telefono di fatturazione (BTN) insieme a tutti gli altri numeri di telefono del tuo account.

    Si supponga ad esempio che il numero BTN sia *+1 425-555-1234* e che si vogliano eseguire il portabilità di tutti i 25 numeri di telefono (da *+1 425-555-1235 a 1259).* Seguendo le istruzioni riportate di seguito per trasferire i numeri, immettere: **+14255551234 - +14255551259.**

- **Porta parziale** Si verifica quando trasferisci solo alcuni dei tuoi numeri di telefono dal provider di servizi corrente a Teams. Quando vuoi eseguire il portabilità di alcuni numeri di telefono collegati allo stesso BTN, **** non devi includere ** il BTN insieme a tutti gli altri numeri di telefono del tuo account.

    Si supponga ad esempio che il numero BTN sia *+1 425-555-1234* e che si voglia eseguire il portabilità solo di 5 dei 25 numeri di telefono *(+1 425-555-1235-1259).* Seguendo le istruzioni riportate di seguito per trasferire i numeri, immettere: **+1 425 555 1235 - +1 425 555 1239.**
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Posso inviare una singola richiesta di portabilità del numero per tutti i numeri in una sola volta?
<a name="bkmk_type_1"> </a>

È necessaria una richiesta univoca per ogni gestore e tipo di numero da portare.
  
Ad esempio, devi inviare una richiesta di portabilità numero univoca per ognuno dei seguenti tipi di numeri:
  
- Numeri a verde locali, noti anche come numeri dell'abbonato o numeri geografici

- Numeri gratuiti con codici di area come 800, 844, 855, 866, 877 e 888

- Numeri di cellulare

- Numeri di servizio che possono essere utilizzati per le audioconferenze in Microsoft 365 o Office 365.

Ecco altre informazioni su come inviare richieste di portabilità del numero per ognuno di questi tipi di numeri:
  
- **I numeri di** telefono forniti da diversi gestori richiedono una richiesta di portabilità univoca per i numeri di ciascun gestore.

-  I numeri gratuiti con codici di area come 800, 844, 855, 866, 877 e 888 non possono essere inclusi in una richiesta di portabilità del numero con altri tipi di numeri. Per il trasferimento di questi numeri verde, devi inviare [manualmente un ordine di trasferimento.](manually-submit-port-order.md) Non è possibile eseguire il portabilità di questi numeri nell'interfaccia di amministrazione di Microsoft Teams. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    È importante usare la lettera di autorizzazione (LOA, Letter of Authorization) corretta per il paese e il tipo di numeri di telefono che si vuole convertire. Puoi scaricare [il loa che ti serve qui.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **I numeri di** cellulare richiedono un codice PIN per autorizzare il trasferimento. Pertanto, è necessario numerazione separata richiesta di portabilità.

- **Le richieste di** portabilità del numero di servizio devono essere inviate da sole. Non possono essere inviati con altri tipi di numeri.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo è necessario per il portabilità dei numeri?
<a name="bkmk_type_1"> </a>

Dopo aver completato la richiesta di ordine di trasferimento, l'elaborazione dell'ordine di trasferimento richiede da 7 a 14 giorni. Tuttavia, a seconda del provider di servizi, potrebbero essere necessario fino a 30 giorni. Dopo aver inviato i numeri di telefono, ricevi un'e-mail per consentirti di iniziare.
  
Per controllare lo stato del tuo ordine di trasferimento, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Numeri di telefono vocali, quindi fai clic  >  su **Cronologia ordini.** Ogni stato dell'ordine di trasferimento è elencato nella **colonna** Stato.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>I numeri di telefono degli utenti (abbonati) possono essere convertiti in numeri di servizio?
<a name="bkmk_type_1"> </a>

Sì. Tutto quello che devi fare è inviare una richiesta di servizio che includa il GUID del tenant dell'organizzazione e i numeri di telefono che desideri convertire. Per farlo, vedi [Gestire i numeri di telefono per l'organizzazione.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Posso eseguire il port out dei miei numeri da Teams a un gestore o provider di servizi telefonici diverso?

Per il port out dei tuoi numeri da Teams a un altro gestore, devi inviare una richiesta al nuovo gestore. Dovrai anche impostare un PIN di portabilità nell'interfaccia di amministrazione di Microsoft Teams.

Per definire il PIN di portabilità, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Numeri di telefono vocali, nell'angolo in alto a destra della pagina, seleziona Gestisci PIN di portabilità, quindi immetti un PIN di  >  10 cifre.

Quando il nuovo gestore contatta Microsoft con la richiesta di portabilità, verrà chiesto di fornire il PIN definito.

## <a name="common-mistakes-to-watch-out-for"></a>Errori comuni da evitare
<a name="bkmk_type_1"> </a>

La portabilità del numero è un'operazione semplice. Tuttavia, se c'è un problema con il provider di servizi telefonici, se l'ordine è incompleto e non contiene informazioni o ci sono errori di digitazione.
  
Ecco gli errori più comuni commersi dai clienti durante il portabilità dei numeri. Risparmia una chiamata al servizio di assistenza clienti e verifica la presenza di questi errori.
  
- Assicurati che le informazioni dell'account fornite corrispondano esattamente a ciò che ha registrato il gestore telefonico. La mancata corrispondenza delle informazioni è una delle cause più comuni di errori e potrebbe comportare ritardi nell'ordine di trasferimento. Verificare che:

  - Il nome o la persona autorizzata ad apportare modifiche all'account è corretta.

  - L'indirizzo sia corretto.

  - Il numero di conto è corretto.

  - BTN sia corretto.

- Su questi numeri di telefono non siano attivate funzioni di controllo chiamate avanzate, ad esempio la risposta alle chiamate o la suoneria differenziata.

- Assicurati di non aver inserito nuovi ordini di servizio o di disconnetterti dal provider di servizi corrente.

- Assicurati che tutti i numeri siano dello stesso gestore e dello stesso account.

- Verificare che il servizio sia attivo. Il blocco dell'account impedisce la modifica dei corrieri sull'account. La persona autorizzata ad apportare modifiche all'account deve inviare un ordine al gestore corrente per rimuovere il blocco. Questo processo può richiedere da una a tre settimane a seconda del gestore.

## <a name="related-topics"></a>Argomenti correlati

- [Qual è lo stato degli ordini di portabilità?](port-order-status.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Etichetta della dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)