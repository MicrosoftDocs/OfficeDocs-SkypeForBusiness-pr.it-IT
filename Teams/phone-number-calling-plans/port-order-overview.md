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
description: Ottenere una panoramica degli ordini di trasferimento e su come trasferire i numeri di telefono dal provider di servizi a Teams.
ms.openlocfilehash: f30bdc825caf7feadbb09bd4bbe65a4d5771a6a6
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278649"
---
# <a name="whats-a-port-order"></a>Cos'è un ordine di portabilità?

Se attualmente si ha un provider di servizi di telefonia o un gestore telefonico e si hanno già numeri di telefono per gli utenti o i servizi, è necessario creare un *"* ordine di trasferimento " per trasferire tali numeri di telefono in Microsoft Teams. Quando i numeri vengono esportati, è possibile assegnarli agli utenti e ai servizi, ad esempio audioconferenze (per bridge di conferenza), operatori automatici e code di chiamata.
  
Dopo aver portato i numeri di telefono in Teams, Microsoft diventa il provider di servizi ed è possibile disconnettere il servizio con il provider di servizi o il gestore precedente.

Leggere le informazioni contenute in questo articolo per acquisire familiarità con la portabilità dei numeri. Dopo di che, si dovrebbe essere pronti per creare un ordine di trasferimento e trasferire i numeri di telefono. Vedere [Trasferire numeri di telefono Teams](transfer-phone-numbers-to-teams.md) per istruzioni dettagliate.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quali paesi o aree geografiche supportano la portabilità dei numeri?

È possibile trasferire o trasferire numeri di telefono in tutti i paesi o aree geografiche supportati, ma la modalità di invio di una richiesta di ordine di trasferimento dipende dal paese o dall'area geografica da cui provengono i numeri di telefono. Per un elenco dei paesi e delle aree geografiche che supportano la portabilità dei numeri, vedere [Gestire i numeri di telefono per l'organizzazione.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

Attualmente, [la procedura guidata di porting](transfer-phone-numbers-to-teams.md) nell'interfaccia Microsoft Teams di amministrazione supporta il recupero di numeri di telefono per Regno Unito, Stati Uniti e Canada. Per ottenere numeri di telefono per altri paesi e aree geografiche, è possibile [inviare manualmente un ordine di trasferimento.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>Quali numeri possono essere trasferiti?

 **È possibile trasferire**
  
In generale, è possibile trasferire qualsiasi numero di telefono di un provider supportato, tra cui:
  
- Numeri di telefono della rete terrestre.

- Numeri di telefono del dispositivo mobile, ad esempio quelli usati per telefoni cellulari e tablet.

    > [!NOTE]
    > Il trasferimento di numeri di cellulare è disponibile solo negli Stati Uniti e portorico.
  
- Numeri di telefono a pedaggio.

- Numeri di telefono gratuiti.

    > [!NOTE]
    > L'UIFN (Universal International Freephone Number) non può essere trasferito a Microsoft. 
  
- Numeri di telefono di servizio, ad esempio quelli usati per i ponti conferenza, gli operatori automatici e così via.

- I numeri di telefono fax, ma non possono essere usati per l'invio di fax. Devono essere assegnate a un utente.

- Numeri di telefono VoIP di un provider di telefonia, ad esempio Vonage o RingCentral.

- Skype for Business numeri di telefono ibridi. Se vuoi trasferire questi numeri, inviaci un'e-mail all'indirizzo <ptn@microsoft.com> .

  **Non è possibile trasferire:**
  
    > [!NOTE]
    > Al momento, non è possibile trasferire numeri di telefono o numeri non provenienti da un paese o un'area geografica supportata, inclusi i numeri di telefono di un provider di telefonia VoIP. Per un elenco dei paesi/aree geografiche supportati, vedere Disponibilità di paesi e aree geografiche [per audioconferenze e piani per chiamate](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Telefono numeri usati per le connessioni dati, ad esempio per le linee DSL o le connessioni Internet a banda larga.

- Telefono numeri dedicati al fax.

    Se sono già presenti numeri di telefono dedicati usati  per l'invio di fax, è possibile trasferire questi numeri in Teams, ma i servizi fax non continueranno a funzionare come previsto. I servizi fax non sono disponibili per Teams clienti, anche se si hanno licenze per Sistema telefonico, piano per chiamate nazionali o piano per chiamate internazionali.

    Se si porta il numero di telefono in Teams, è possibile assegnarlo a un utente dell'organizzazione invece di usarlo per l'invio di fax.

    > [!NOTE]
    > In questo momento nel Regno Unito, attualmente non è possibile trasferire numeri non geografici del Regno Unito, inclusi i numeri di costo condiviso per i codici area 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quali informazioni è necessario fornire?

È necessario avere tutte le informazioni sull'account per il gestore corrente. Le informazioni immesse nell'ordine di trasferimento si trovano principalmente nella fattura o nella fattura più recente del provider di servizi corrente. È anche necessario sapere il nome dell'account e i numeri da convertire.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Che cosa sono i trasferimenti full-port e partial-port?

Quando si trasferiscono i numeri di telefono in Teams, è possibile trasferire tutti i numeri o alcuni di essi.
  
- **Porta completa** Questo è il momento in cui trasferisci tutti i tuoi numeri dal provider di servizi corrente a Teams. Quando viene chiesto di specificare i numeri di  telefono da trasferire, è necessario includere il numero di telefono di fatturazione (BTN) insieme a tutti gli altri numeri di telefono dell'account.

    Si supponga ad esempio che il numero BTN sia *+1 425-555-1234* e che si vogliano eseguire il port di tutti i 25 numeri di telefono (*+1 425-555-1235-1259).* Quando si seguono le istruzioni seguenti per trasferire i numeri, immettere: **+14255551234 - +14255551259**.

- **Porta parziale** Questo è il momento in cui trasferisci solo alcuni dei tuoi numeri di telefono dal provider di servizi corrente a Teams. Per convertire alcuni dei numeri di telefono collegati allo stesso BTN, **** non deve includere ** il BTN insieme a tutti gli altri numeri di telefono dell'account.

    Si supponga ad esempio che il numero BTN sia *+1 425-555-1234* e che si desideri eseguire il port solo 5 dei 25 numeri di telefono (*+1 425-555-1235-1259).* Quando si seguono le istruzioni seguenti per trasferire i numeri, immettere: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>È possibile inviare una richiesta di portabilità di un singolo numero per tutti i numeri contemporaneamente?
<a name="bkmk_type_1"> </a>

È necessaria una richiesta univoca per ogni vettore e tipo di numero da convertire.
  
Ad esempio, è necessario inviare una richiesta di portabilità di numeri univoca per ognuno dei tipi di numeri seguenti:
  
- Numeri a pedaggio locali, noti anche come numeri abbonati o numeri geografici

- Numeri a numero verde con codici area come: 800, 844, 855, 866, 877 e 888

- Numeri di cellulare

- Numeri di servizio che possono essere usati per le audioconferenze in Microsoft 365 o Office 365.

Ecco altre informazioni su come inviare richieste di portabilità dei numeri per ognuno di questi tipi di numeri:
  
- **Telefono numeri forniti** da corrieri diversi richiedono una richiesta di portabilità univoca per i numeri con ogni gestore.

-  I numeri a numero verde con codici area come: 800, 844, 855, 866, 877 e 888 non possono essere inclusi in una richiesta di portabilità con altri tipi di numeri. Per il trasferimento di questi numeri verde, è necessario [inviare manualmente un ordine di trasferimento.](manually-submit-port-order.md) Non è possibile eseguire il port di questi numeri nell'Microsoft Teams di amministrazione. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    È importante usare la lettera di autorizzazione (LOA) corretta per il paese e il tipo di numeri di telefono da convertire. È possibile [scaricare il file LOA necessario qui.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **I numeri di** cellulare richiedono un codice PIN per autorizzare il trasferimento. Pertanto, hanno bisogno di una richiesta di portabilità del numero separata.

- **Le richieste di** portabilità del numero di servizio devono essere inviate da sole. Non possono essere inviati con altri tipi di numeri.

## <a name="how-long-does-it-take-to-port-numbers"></a>Quanto tempo è necessario per la portabilità dei numeri?
<a name="bkmk_type_1"> </a>

Dopo aver completato la richiesta di ordine di trasferimento, l'elaborazione richiede da 7 a 14 giorni. Tuttavia, a seconda del provider di servizi, l'operazione può richiedere fino a 30 giorni. Dopo aver inviato i numeri di telefono, si otterrà un messaggio di posta elettronica da Microsoft per insodinviare l'invito.
  
Per controllare lo stato dell'ordine di trasferimento, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Numeri Telefono vocali e quindi fare clic su Cronologia  >   **ordini.** Ogni stato dell'ordine di trasferimento è elencato nella **colonna** Stato.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>I numeri di telefono degli utenti (abbonati) possono essere convertiti in numeri di servizio?
<a name="bkmk_type_1"> </a>

Sì, possono. È solo necessario inviare una richiesta di servizio che includa il GUID del tenant dell'organizzazione e i numeri di telefono da convertire. A questo scopo, vedere [Gestire i numeri di telefono per l'organizzazione.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>È possibile eseguire il port out dei numeri da Teams a un altro gestore o provider di servizi telefonici?

Per inviare i numeri da Teams a un altro gestore, è necessario inviare una richiesta con il nuovo gestore. È anche necessario impostare un PIN di portabilità nell'Microsoft Teams di amministrazione.

Per definire il PIN di portabilità, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Numeri Telefono vocali , nell'angolo in alto a destra della pagina selezionare Gestisci PIN di portabilità e quindi immettere un PIN di  >  10 cifre.

Quando il tuo nuovo gestore ci contatta con la richiesta di portabilità, ti chiederemo di fornire il PIN che hai definito.

## <a name="common-mistakes-to-watch-out-for"></a>Errori comuni da controllare
<a name="bkmk_type_1"> </a>

La portabilità dei numeri è facile. Il tuo ordine può essere incasinato, tuttavia, se c'è un problema con il provider di servizi telefonici, l'ordine è incompleto e mancano di informazioni o ci sono errori di digitazione.
  
Ecco gli errori più comuni che i clienti commettono quando effettuano la portabilità dei numeri. È possibile effettuare una chiamata al supporto tecnico ed effettuare un doppio controllo per verificare la presenza di questi errori.
  
- Assicurarsi che le informazioni dell'account fornite corrispondano esattamente a quanto registrato dal gestore telefonico. Le informazioni non corrispondenti sono la causa più comune di errori e ritardano l'ordine di trasferimento. Verificare che quanto segue sia vero:

  - Il nome o la persona autorizzata a apportare modifiche all'account è corretta.

  - L'indirizzo è corretto.

  - Il numero dell'account è corretto.

  - BTN è corretto.

- Assicurarsi che non siano disponibili funzionalità avanzate di controllo delle chiamate, ad esempio Risposta chiamata, Anello distintivo, abilitate su questi numeri di telefono.

- Assicurarsi di non aver effettuato nuovi ordini di assistenza o di disconnettersi con il provider di servizi corrente.

- Assicurati che tutti i numeri siano dello stesso gestore e dello stesso account.

- Assicurarsi che il servizio sia attivo. Il blocco dell'account impedisce la modifica dei gestori dell'account. La persona autorizzata a apportare modifiche all'account deve inviare un ordine al gestore corrente per rimuovere il blocco. Questo processo può richiedere da una a tre settimane, a seconda del gestore.

## <a name="related-topics"></a>Argomenti correlati

- [Qual è lo stato degli ordini di portabilità?](port-order-status.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Etichetta di esclusione di responsabilità per chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
