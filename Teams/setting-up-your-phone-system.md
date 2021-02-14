---
title: Configurazione di Sistema telefonico nella tua organizzazione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Guida dettagliata che illustra come configurare il Sistema telefonico (Cloud PBX) per l'organizzazione in Microsoft 365 o Office 365.
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701214"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurare il Sistema telefonico nell'organizzazione

Di seguito è riportata una guida dettagliata per la configurazione del Sistema telefonico in Microsoft 365 o Office 365. Alla fine di ogni passaggio sono disponibili collegamenti ad altre informazioni dettagliate.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Passaggio 1: Verificare che Sistema telefonico sia disponibile nel tuo paese

1.    Innanzitutto passare alla [Disponibilità paese e area geografica per le Audioconferenze e i Piani di chiamata](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)e selezionare il proprio paese dall'elenco nella parte superiore della pagina. 
2.    In **Sistema telefonico**, esaminare l'elenco delle caratteristiche e i dettagli. 
3.    Se il Sistema telefonico è disponibile, andare al passaggio 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Passaggio 2: acquistare e assegnare licenze relative a Sistema telefonico e Piani di chiamata

Per assegnare una licenza Sistema telefonico e Piano per chiamate a un singolo utente, i passaggi sono gli stessi di assegnazione di una licenza di Microsoft 365 o Office 365.  È anche possibile assegnare licenze a più utenti in blocco. Per altre informazioni, vedere [Assegnare le licenze per i componenti aggiuntivi di Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

Se i Piani per chiamate non sono disponibili per il proprio paese o area geografica, è consigliabile usare l'instradamento diretto per connettere l'infrastruttura telefonica locale al Sistema telefonico.  Per ulteriori informazioni, consulta [Instradamento diretto sistema telefonico.](direct-routing-landing-page.md)

## <a name="step-3-get-phone-numbers-for-your-users"></a>Passaggio 3: Ottenere i numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono.

È possibile ottenere numeri per gli utenti in tre modi:
- Ottenere nuovi numeri utilizzando l'interfaccia di amministrazione di Teams.
- Ottieni nuovi numeri che non sono disponibili nell'interfaccia di amministrazione di Teams.
- Trasferire i numeri esistenti dal gestore o provider di servizi corrente a Microsoft 365 o Office 365.

Devi utilizzare la pagina Aggiungi **numeri** per visualizzare, cercare, acquisire e prenotare quei numeri. Puoi eseguire una ricerca in base a Paese/Area geografica, Stato e Città e inserire i numeri di telefono necessari per gli utenti.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Ottenere nuovi numeri di telefono utente utilizzando l'interfaccia di amministrazione di Teams

1. Accedere a Microsoft 365 con l'account aziendale o dell'istituto di istruzione.

2. Accedere **all'interfaccia di amministrazione di Teams.**
    
3. Nella barra di spostamento sinistra passa **a Numeri**  >  **di telefono,** fai clic su **Aggiungi** e quindi segui le istruzioni visualizzate.
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Ottenere nuovi numeri che non sono disponibili nell'interfaccia di amministrazione di Teams
  
A volte (a seconda del paese/area geografica) non potrai ottenere nuovi numeri utilizzando l'interfaccia di amministrazione di Teams. In questo caso, dovrai scaricare un modulo e inviarci il modulo. Per informazioni su come richiedere nuovi numeri utente, vedi [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Trasferire numeri di telefono dal provider di servizi o dal gestore di telefonia
  
- Se hai bisogno di un massimo di 999  numeri di telefono per i tuoi utenti, puoi utilizzare la procedura guidata Nuovo ordine di portabilità numero locale nell'interfaccia di amministrazione di Teams. Seguire la procedura descritta in Trasferire [numeri di telefono in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) per trasferire i numeri di telefono.
    
- Se devi eseguire il trasferimento di più di [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 999 numeri di telefono, consulta Gestisci i numeri di telefono per l'organizzazione per inviare una richiesta o un ordine di servizio per un ordine di trasferimento. 

Per informazioni dettagliate sull'acquisizione di nuovi numeri di telefono o il trasferimento di numeri esistenti, consultare [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 4: ottenere numeri di telefono di servizio (audioconferenza, le code di chiamata, gli operatori automatici)

Oltre a ottenere numeri di telefono per gli utenti da Microsoft 365 o Office 365, è possibile cercare e acquisire numeri di telefono a numero verde o a numero verde per servizi come le audioconferenze (per il bridge di conferenza), gli operatori automatici e le code di chiamata. I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo poche chiamate contemporaneamente.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Ottenere nuovi numeri di servizio utilizzando l'interfaccia di amministrazione di Teams


1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Accedere **all'interfaccia di amministrazione di Teams.**

3. Nel riquadro di spostamento sinistro passa a **Numeri** di telefono vocali Aggiungi nuovo numero e quindi fai clic  >    >  su **Nuovi numeri di servizio.**

    > [!IMPORTANT]
    > Per visualizzare l'opzione Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Teams, devi prima acquistare almeno una licenza **Enterprise E5,** una licenza per un componente aggiuntivo Sistema telefonico o una licenza per i componenti aggiuntivi   **audioconferenza.**

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Ottenere nuovi numeri che non sono disponibili nell'interfaccia di amministrazione di Teams
  
A volte (a seconda del paese/area geografica) non potrai ottenere nuovi numeri utilizzando l'interfaccia di amministrazione di Teams. In questo caso, è necessario scaricare un modulo e inviarlo a Microsoft. Per informazioni su come richiedere nuovi numeri, vedi [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilità o trasferimento dei numeri di servizio

Se voi trasferire numeri di servizio esistenti dall'operatore o provider di servizio attuale, devi presentare manualmente un ordine di portabilità a Microsoft. Devi inviare ordini di trasferimento separati per ogni tipo di numero di servizio (a numero verde) che stai trasferendo utilizzando una lettera di autorizzazione (LOA, Letter of Authorization). Nella lettera di autorizzazione (LOA, Letter of Authorization), devi selezionare il tipo corretto di numero di servizio. Quando si contatta il supporto Microsoft, specificare che si sta trasferendo un numero di servizio *(e* non un numero utente o abbonato) oppure che la capacità di chiamata simultanea potrebbe non essere sufficiente per gestire volumi elevati di chiamate. Se si desidera trasferire i numeri di telefono o eseguire altre operazioni con i numeri di telefono, vedere [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Passaggio 5: se si desidera impostare i Piani di chiamata

Se avete seguito i passaggi precedenti, avete già acquistato il Sistema telefonico e assegnato le relative licenze, acquistato un Piano di chiamata (passaggio 2) e acquisito numeri di telefono per gli utenti (passaggio 3), pertanto il Piano di chiamata è parzialmente configurato. Per completare le procedure di configurazione del Piano per chiamate, consulta [Configurare i Piani per chiamate.](set-up-calling-plans.md)


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Passaggio 6: Se si desidera impostare Audioconferenze

A volte le persone all'interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Microsoft Teams include la funzionalità di audioconferenza proprio per queste situazioni. Le persone possono accedere alle riunioni di Teams usando un telefono, invece di usare l'app Teams su un dispositivo mobile o PC.
Per informazioni su come configurare le audioconferenze, vedere [Configurare le audioconferenze per Teams.](set-up-audio-conferencing-in-teams.md)

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Passaggio 7: Se desideri impostare una coda di chiamata Cloud

Le code di chiamata cloud includono i saluti che vengono utilizzati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di mettere automaticamente in attesa le chiamate e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano la musica di attesa. Puoi creare una o più code di chiamata per la tua organizzazione.

Per ulteriori informazioni sulle code di chiamata, consulta [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Passaggio 8: Se desideri impostare un operatore automatico Cloud

Gli operatori automatici consentono alle persone che chiamano la tua organizzazione di navigare in un sistema di menu per spostarli nel reparto, nella coda di chiamata, nella persona o nell'operatore giusto. Puoi creare un operatore automatico per la tua organizzazione utilizzando l'interfaccia di amministrazione di Teams.

Per informazioni sulla configurazione di un partecipante automatico cloud, consulta [Configurare un operatore](create-a-phone-system-auto-attendant.md)automatico Cloud.


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 9: assegnare i numeri di telefono di servizio (audioconferenza, code di chiamata, operatori automatici)

Dopo avere creato i numeri di servizio dal **passaggio 4 sopra**, è necessario assegnarli a ogni tipo di servizio che si desidera. Ad esempio, se vuoi assegnare un numero di telefono di servizio dedicato (a numero verde o a numero verde), devi assegnarlo al bridge di conferenza.

- Per le audioconferenze, puoi assegnare un numero dedicato a un bridge di conferenza dall'interfaccia di amministrazione **di Teams** e seguire le  >    >   istruzioni visualizzate.  Per ulteriori informazioni, consulta Modificare i numeri a verde o a numero verde [sul bridge per audioconferenze.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

- Per gli operatori automatici, puoi assegnare un numero dedicato a un operatore automatico andando agli operatori vocali dell'interfaccia di amministrazione **di Teams** e seguendo le  >    >   istruzioni visualizzate.  Per ulteriori informazioni, consulta [Configurare un operatore automatico Cloud.](create-a-phone-system-auto-attendant.md)

- Per le code di chiamata, è possibile assegnare un numero dedicato a una coda di chiamata andando nelle code di chiamata vocali dell'interfaccia di amministrazione **di Teams** e seguendo le  >    >   istruzioni visualizzate. Per ulteriori informazioni, consulta [Creare una coda di chiamata Cloud.](create-a-phone-system-call-queue.md)

Per informazioni dettagliate su come ottenere nuovi numeri di servizio oppure su come trasferire numeri di servizio esistenti, vedere [Ottenere numeri di telefono di servizio](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Passaggio 10: Configurare i Crediti comunicazioni per la propria organizzazione

Se desideri utilizzare i numeri verde con Microsoft Teams, devi impostare i Crediti comunicazioni. Microsoft consiglia di impostare i Crediti comunicazioni per i piani per chiamate (nazionali o internazionali) e per le audioconferenze che hanno bisogno di effettuare chiamate in uscita verso qualsiasi destinazione. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. 

Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. Per ulteriori informazioni, compresi gli importi consigliati per il pagamento, consulta Cosa sono i [Crediti comunicazioni?](what-are-communications-credits.md) e [Imposta i Crediti comunicazioni per la tua organizzazione.](set-up-communications-credits-for-your-organization.md)
  

## <a name="related-topics"></a>Argomenti correlati
[Ecco cosa si ottiene con Sistema telefonico in Microsoft 365 o Office 365](here-s-what-you-get-with-phone-system.md)

[Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
