---
title: Cos'è un ordine di portabilità?
ms.author: v-lanac
author: lanachin
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
description: Informazioni generali sugli ordini di trasferimento e su come trasferire i numeri di telefono dal provider di servizi in teams.
ms.openlocfilehash: 0102adfd53dba3ff455ddbdbc3678e625fd978de
ms.sourcegitcommit: 2d44f1a673316daf0aca3149571b24a63ca72772
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "43227540"
---
# <a name="whats-a-port-order"></a>Cos'è un ordine di portabilità?

Se si ha un provider o un gestore di servizi telefonici e si hanno già numeri di telefono per gli utenti o i servizi, è necessario creare un "*ordine*di trasferimento" per trasferire i numeri di telefono a Microsoft teams. Quando i numeri vengono convertiti, è possibile assegnare i numeri di telefono agli utenti e ai servizi, ad esempio le conferenze audio (per i Bridge di conferenza), gli operatori automatici e le code di chiamata.
  
Dopo aver convertito i numeri di telefono in teams, Microsoft diventa il proprio provider di servizi ed è possibile disconnettere il servizio con il vecchio gestore o provider di servizi.

Esaminare le informazioni contenute in questo articolo per familiarizzare con la portabilità dei numeri. Dopo di che, dovresti essere pronto per creare un ordine di trasferimento e trasferire i numeri di telefono. Per istruzioni dettagliate, vedere [trasferire numeri di telefono in teams](transfer-phone-numbers-to-teams.md) .
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quali paesi o aree geografiche supportano la portabilità del numero?

È possibile convertire o trasferire i numeri di telefono in tutti i paesi o le aree geografiche supportati, ma come inviare una richiesta di un ordine di trasferimento dipende dal paese o dall'area geografica in cui provengono i numeri di telefono. Per un elenco di paesi e aree geografiche che supportano la conversione del numero, vedere [gestire i numeri di telefono per l'organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

Attualmente, [la conversione guidata nell'interfaccia](transfer-phone-numbers-to-teams.md) di amministrazione di Microsoft teams supporta l'ottenimento di numeri di telefono per Regno Unito, Stati Uniti e Canada. Per ottenere i numeri di telefono per altri paesi e aree geografiche, è possibile [inviare manualmente un ordine di trasferimento](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>Quali numeri possono essere trasferiti?

 **È possibile trasferire**
  
In generale, è possibile trasferire qualsiasi numero di telefono proveniente da un provider supportato, tra cui:
  
- Numeri di telefono della linea terrestre.

- Numeri di telefono per dispositivi mobili, ad esempio quelli usati per telefoni cellulari e tablet.

    > [!NOTE]
    > Il trasferimento di numeri per dispositivi mobili è disponibile solo negli Stati Uniti e in Puerto Rico.
  
- Numeri di telefono a pedaggio.

- Numeri verdi gratuiti.

    > [!NOTE]
    > Il numero verde internazionale universale (UIFN) non può essere trasferito a noi. 
  
- Numeri di telefono di servizio, ad esempio quelli usati per i Bridge di conferenza, gli operatori automatici e così via.

- Numeri di telefono fax, ma non possono essere usati per l'invio di fax. Devono essere assegnati a un utente.

- Numeri di telefono VoIP di un provider di telefonia, ad esempio Vonage o RingCentral.

- Numeri di telefono ibridi Skype for business. Se vuoi trasferire questi numeri, inviaci una e-mail all' <ptn@microsoft.com>indirizzo.

  **Non è possibile trasferire:**
  
    > [!NOTE]
    > In questo momento, non è possibile trasferire numeri di telefono o numerazioni che non si trovano in un paese o in un'area geografica supportata, inclusi i numeri di telefono di un provider di telefonia VoIP. Per un elenco dei paesi/aree geografiche supportati, vedere [disponibilità per i servizi di audioconferenza e per i piani di chiamata](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Numeri di telefono usati per le connessioni dati, come per le linee DSL o le connessioni Internet a banda larga.

- Numeri di telefono dedicati all'invio di fax.

    Se sono presenti numeri di telefono dedicati che vengono usati per l'invio di fax, è *possibile* trasferire questi numeri in teams, ma i servizi fax non continueranno a funzionare come previsto. I servizi di fax non sono disponibili per i clienti dei team, anche se si hanno licenze per il sistema telefonico, il piano per chiamate nazionali o il piano per chiamate internazionali.

    Se si trasferisce il numero di telefono in teams, è possibile assegnare questo numero di telefono a un utente dell'organizzazione invece di usarlo per l'invio di fax.

    > [!NOTE]
    > Attualmente nel Regno Unito non è supportato il trasferimento di numeri non geografici del Regno Unito, inclusi i numeri di costo condivisi per i codici di area 0843, 0844, 0845, 0870, 0871 e 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quali informazioni è necessario specificare?

È necessario disporre di tutte le informazioni sull'account per il vettore corrente. Le informazioni immesse nell'ordine di trasferimento si trovano principalmente nella fattura o fattura più recente del provider di servizi corrente. Devi anche sapere il cui nome è nell'account e i numeri che vuoi trasferire.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Che cosa sono i trasferimenti a piena porta e a porta parziale?

Quando si trasferiscono i numeri di telefono in teams, è possibile trasferire tutti i numeri o alcuni di essi.
  
- **Porta completa** Questo è il momento in cui si trasferiscono tutti i numeri dal provider di servizi corrente a teams. Quando vengono chiesti i numeri di telefono da trasferire, è *necessario includere* il numero di telefono di fatturazione (BTN) insieme a tutti gli altri numeri di telefono del proprio account.

    Supponiamo ad esempio che il BTN sia *+ 1 425-555-1234* e si voglia trasferire tutti i 25 numeri di telefono (*+ 1 425-555-1235 a 1259*). Quando si seguono le istruzioni riportate di seguito per trasferire i numeri, immettere: **+ 14255551234-+ 14255551259**.

- **Porta parziale** Questo è il momento in cui si trasferiscono solo alcuni numeri di telefono dal provider di servizi corrente a teams. Quando si vogliono trasferire alcuni numeri di telefono legati allo stesso BTN, *non è necessario includere* * * il BTN insieme a tutti gli altri numeri di telefono del proprio account.

    Supponiamo ad esempio che il BTN sia *+ 1 425-555-1234* e si voglia trasferire solo 5 dei 25 numeri di telefono (*+ 1 425-555-1235 a 1259*). Quando si seguono le istruzioni riportate di seguito per trasferire i numeri, immettere: **+ 1 425 555 1235-+ 1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>È possibile inviare una richiesta di conversione di un numero unico per tutti i numeri contemporaneamente?
<a name="bkmk_type_1"> </a>

È necessaria una richiesta univoca per ogni vettore e tipo di numero che viene convertito.
  
Ad esempio, è necessario inviare una richiesta di conversione numero univoco per ognuno dei tipi di numeri seguenti:
  
- Numeri a pedaggio locali, noti anche come numeri di abbonato o numeri geografici

- Numeri verdi con codici di area, ad esempio: 800, 844, 855, 866, 877 e 888

- Numeri per dispositivi mobili

- Numeri di servizio che possono essere usati per i servizi di audioconferenza in Office 365.

Ecco altre informazioni su come inviare richieste di conversione del numero per ognuno di questi tipi di numeri:
  
- I **numeri di telefono** forniti da diversi vettori richiedono una richiesta di conversione univoca per i numeri con ogni gestore.

- I **numeri verdi** con i codici di area, ad esempio: 800, 844, 855, 866, 877 e 888, non possono essere inclusi in una richiesta di trasferimento di numeri con altri tipi di numero. Per trasferire questi numeri verdi, è necessario [inviare manualmente un ordine di trasferimento](manually-submit-port-order.md). Non è possibile trasferire questi numeri nell'interfaccia di amministrazione di Microsoft teams. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    È importante usare la lettera di autorizzazione corretta per il paese e il tipo di numeri di telefono che si vuole trasferire. È possibile [scaricare il Loa di cui si ha bisogno](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- I **numeri di cellulare** richiedono un codice PIN per autorizzare il trasferimento. Di conseguenza, hanno bisogno di una richiesta separata per la portabilità del numero.

- Le richieste di portabilità del **numero di servizio** devono essere inviate da sole. Non possono essere inviati con altri tipi di numeri.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo è necessario per i numeri di porta?
<a name="bkmk_type_1"> </a>

Dopo aver completato la richiesta di un ordine di trasferimento, è necessario tra 7-14 giorni per l'elaborazione. Tuttavia, a seconda del provider di servizi, possono essere necessarie fino a 30 giorni. Dopo il trasferimento dei numeri di telefono, riceverai un messaggio di posta elettronica da parte dell'utente che ti permetterà di essere pronto.
  
Per controllare lo stato dell'ordine di trasferimento, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a**numeri di telefono** **vocale** > e quindi fai clic su **Cronologia ordini**. Ogni stato dell'ordine di porta è elencato nella colonna **stato** .
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>I numeri di telefono can User (Subscriber) possono essere convertiti in numeri di servizio?
<a name="bkmk_type_1"> </a>

Sì, è possibile. Tutto quello che devi fare è inviare una richiesta di servizio che includa il GUID del tenant dell'organizzazione e i numeri di telefono che vuoi convertire. Per eseguire questa operazione, vedere [gestire i numeri di telefono per l'organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="common-mistakes-to-watch-out-for"></a>Errori comuni a cui prestare attenzione
<a name="bkmk_type_1"> </a>

La portabilità del numero è facile da fare. Il tuo ordine può essere incasinato, tuttavia, se c'è un problema con il provider di servizi telefonici, l'ordine è incompleto e mancano informazioni o sono presenti errori di battitura.
  
Ecco gli errori più comuni che i clienti fanno quando i numeri di porta. Salvarsi una chiamata al supporto tecnico e verificare se sono presenti errori.
  
- Verificare che le informazioni sull'account fornite corrispondano esattamente a ciò che il gestore di telefonia ha registrato. Le informazioni non corrispondenti sono la causa più comune di errori e ritardano l'ordine di trasferimento. Verificare che il codice seguente sia vero:

  - Il nome o la persona autorizzata a apportare modifiche all'account è corretta.

  - Indirizzo è corretto.

  - Il numero di account è corretto.

  - BTN è corretto.

- Verificare che non siano presenti funzionalità avanzate per il controllo delle chiamate, ad esempio chiamata Hunt, anello distintivo, abilitati per questi numeri di telefono.

- Verificare che non siano stati inseriti nuovi ordini di servizio o che non siano stati disconnessi con il provider di servizi corrente.

- Assicurarsi che tutti i numeri siano dello stesso vettore e dello stesso account.

- Verificare che il servizio sia attivo. Il blocco dell'account impedisce la modifica dei vettori nell'account. La persona autorizzata a apportare modifiche all'account deve inviare un ordine al vettore corrente per rimuovere il blocco. Questo processo può richiedere da 1 a 3 settimane a seconda del vettore.

## <a name="related-topics"></a>Argomenti correlati

- [Qual è lo stato degli ordini di portabilità?](port-order-status.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)