---
title: Configurare le Teams Telefono nell'organizzazione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Guida dettagliata che illustra come configurare Teams Sistema telefonico per l'organizzazione in Microsoft 365.
ms.openlocfilehash: 305cb9874ed7d14a647d984dfc36586a16004d71
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625797"
---
# <a name="set-up-teams-phone-in-your-organization"></a>Configurare le Teams Telefono nell'organizzazione

Di seguito è riportata una guida dettagliata per la configurazione di Teams Telefono in Microsoft 365. Collegamenti a ulteriori informazioni maggiormente dettagliate sono disponibili alla fine di ogni passaggio.

## <a name="step-1-make-sure-that-teams-phone-is-available-in-your-country-or-region"></a>Passaggio 1: Verificare che il Teams Telefono sia disponibile nel proprio paese o area geografica

1.    Innanzitutto passare alla [Disponibilità paese e area geografica per le Audioconferenze e i Piani di chiamata](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)e selezionare il proprio paese dall'elenco nella parte superiore della pagina. 
2.    In **Sistema telefonico**, esaminare l'elenco delle caratteristiche e i dettagli. 
3.    Se il Sistema telefonico è disponibile, andare al passaggio 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Passaggio 2: acquistare e assegnare licenze relative a Sistema telefonico e Piani di chiamata

Per assegnare una licenza Sistema telefonico piano di chiamata a un singolo utente, i passaggi sono gli stessi dell'assegnazione di una licenza Microsoft 365 chiamata.  È anche possibile assegnare licenze a più utenti in blocco. Per altre informazioni, vedere [Assegnare Microsoft Teams licenze per i componenti aggiuntivi](teams-add-on-licensing/assign-teams-add-on-licenses.md).

Se Piani per chiamate non sono disponibili per il proprio paese o area geografica, sono disponibili altre opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).  Per altre informazioni, vedere [Opzioni di connettività PSTN.](pstn-connectivity.md)

## <a name="step-3-get-phone-numbers-for-your-users"></a>Passaggio 3: Ottenere i numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono.

Sono disponibili tre modi per ottenere numeri per gli utenti:

- Ottenere nuovi numeri usando l'Teams di amministrazione.
- Ottenere nuovi numeri non disponibili nell'interfaccia Teams di amministrazione.
- Trasferire o trasferire i numeri esistenti dal provider di servizi o dal gestore telefonico corrente Microsoft 365.

È necessario usare la **pagina Aggiungi numeri** per visualizzare, cercare, acquisire e prenotare tali numeri. Puoi eseguire una ricerca in base a Paese/Area geografica, Stato e Città e inserire i numeri di telefono necessari per gli utenti.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Ottenere nuovi numeri di telefono degli utenti tramite l'interfaccia Teams di amministrazione

1. Accedere a Microsoft 365 con l'account aziendale o dell'istituto di istruzione.

2. Passare all'**interfaccia di amministrazione di Teams**.
    
3. Nel riquadro di spostamento sinistro passare **a Numeri** Telefono vocali, fare clic  >  su **Aggiungi** e quindi seguire le istruzioni visualizzate.
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Ottenere nuovi numeri non disponibili nell'interfaccia Teams di amministrazione
  
A volte (a seconda del paese/area geografica) non è possibile ottenere i nuovi numeri usando l'interfaccia di amministrazione Teams. In questo caso, è necessario scaricare un modulo e inviarlo di nuovo a Microsoft. Per informazioni su come richiedere nuovi numeri utente, vedere [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Trasferire numeri di telefono dal provider di servizi o dal gestore di telefonia
  
- Se sono necessari 999 o meno numeri di  telefono per gli utenti, è possibile usare la procedura guidata Nuovo ordine di trasferimento numeri locali nell'interfaccia di amministrazione Teams locale. Seguire la procedura descritta in [Trasferire numeri di telefono per Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) trasferire i numeri di telefono.
    
- Se è necessario inviare più di 999 numeri di telefono, vedere Gestire i numeri di telefono per l'organizzazione per inviare una richiesta o un ordine di servizio per l'ordine di trasferimento. [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

Per informazioni dettagliate sull'acquisizione di nuovi numeri di telefono o il trasferimento di numeri esistenti, consultare [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 4: ottenere numeri di telefono di servizio (audioconferenza, le code di chiamata, gli operatori automatici)

Oltre a ottenere numeri di telefono per gli utenti da Microsoft 365 o Office 365, è possibile cercare e acquisire numeri a numero verde o a numero verde per servizi come audioconferenza (per bridge di conferenza), operatori automatici e code di chiamata. I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo alcune chiamate contemporaneamente.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Ottenere nuovi numeri di servizio tramite l'Teams di amministrazione


1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'**interfaccia di amministrazione di Teams**.

3. Nel riquadro di spostamento sinistro passare a **Numeri** Telefono aggiungi nuovo numero e quindi fare  >    >  clic su **Nuovi numeri di servizio.**

    > [!IMPORTANT]
    > Per visualizzare l'opzione Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Teams, è necessario prima acquistare almeno una licenza Enterprise  **E5,** una licenza per componenti aggiuntivi **Sistema telefonico** o una licenza per i componenti aggiuntivi per audioconferenze. 

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Ottenere nuovi numeri non disponibili nell'interfaccia Teams di amministrazione
  
A volte (a seconda del paese/area geografica) non è possibile ottenere i nuovi numeri usando l'interfaccia di amministrazione Teams. In questo caso, è necessario scaricare un modulo e inviarlo di nuovo a Microsoft. Per informazioni su come richiedere nuovi numeri, vedere [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilità o trasferimento dei numeri di servizio

Se voi trasferire numeri di servizio esistenti dall'operatore o provider di servizio attuale, devi presentare manualmente un ordine di portabilità a Microsoft. È necessario inviare ordini di trasferimento separati per ogni tipo di numero di servizio (numero verde e numero verde) che verrà trasferito con una lettera di autorizzazione (LOA). Nella lettera di autorizzazione (LOA) è necessario selezionare il tipo corretto di numero di servizio. Quando si contatta il supporto Microsoft, specificare che si sta trasferendo un numero di servizio *(* e non un numero di utente o abbonato ) oppure che la capacità di chiamata simultanea potrebbe non essere sufficiente per gestire i volumi di chiamata. Se si desidera trasferire i numeri di telefono o eseguire altre operazioni con i numeri di telefono, vedere [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Passaggio 5: se si desidera impostare i Piani di chiamata

Se avete seguito i passaggi precedenti, avete già acquistato il Sistema telefonico e assegnato le relative licenze, acquistato un Piano di chiamata (passaggio 2) e acquisito numeri di telefono per gli utenti (passaggio 3), pertanto il Piano di chiamata è parzialmente configurato. Per completare le procedure per la configurazione del piano chiamate, vedere [Configurare i piani per chiamate.](set-up-calling-plans.md)


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Passaggio 6: Se si desidera impostare Audioconferenze

A volte le persone all'interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Microsoft Teams include la funzionalità di audioconferenza per questa situazione. Le persone possono accedere a Teams riunioni usando un telefono, invece di usare l'app Teams su un dispositivo mobile o un PC.
Per informazioni su come configurare le audioconferenze, vedere [Configurare le audioconferenze per](set-up-audio-conferencing-in-teams.md)Teams .

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Passaggio 7: Se si vuole configurare una coda di chiamata cloud

Le code di chiamata cloud includono i messaggi di saluto usati quando qualcuno chiama a un numero di telefono per l'organizzazione, la possibilità di mettere automaticamente in attesa le chiamate e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa. È possibile creare una o più code di chiamata per l'organizzazione.

Per altre informazioni sulle code di chiamata, vedere [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Passaggio 8: Se si vuole configurare un operatore automatico cloud

Gli operatori automatici consentono alle persone che chiamano l'organizzazione di spostarsi in un sistema di menu per accedervi al reparto, alla coda di chiamata, alla persona o all'operatore giusto. È possibile creare un operatore automatico per l'organizzazione usando l'Teams di amministrazione.

Per informazioni sulla configurazione di un partecipante automatico cloud, vedere [Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md)


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 9: assegnare i numeri di telefono di servizio (audioconferenza, code di chiamata, operatori automatici)

Dopo avere creato i numeri di servizio dal **passaggio 4 sopra**, è necessario assegnarli a ogni tipo di servizio che si desidera. Ad esempio, se si vuole un numero di telefono di servizio dedicato (a numero verde o a numero verde), è necessario assegnare il numero al bridge di conferenza.

- Per le audioconferenze, è possibile assegnare un numero dedicato a un **bridge** di conferenza Teams nell'interfaccia di amministrazione Bridge di conferenza riunioni e seguire  >    >   le istruzioni visualizzate.  Per altre informazioni, vedere Modificare i numeri a numero verde o a numero verde [nel bridge di audioconferenza.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

- Per gli operatori automatici, è possibile assegnare un numero dedicato a un operatore automatico andando **Teams** gli operatori vocali dell'interfaccia di amministrazione e seguendo  >    >   le istruzioni visualizzate.  Per altre informazioni, vedere [Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md)

- Per le code di chiamata, è possibile assegnare un numero dedicato **a** una coda di chiamata andando Teams code chiamate vocali dell'interfaccia di amministrazione e seguendo  >    >   le istruzioni visualizzate. Per altre informazioni, vedere [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)

Per informazioni dettagliate su come ottenere nuovi numeri di servizio oppure su come trasferire numeri di servizio esistenti, vedere [Ottenere numeri di telefono di servizio](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Passaggio 10: Configurare i crediti comunicazioni per l'organizzazione

Se si vuole usare numeri verde con Microsoft Teams, è necessario configurare Crediti comunicazioni. Microsoft consiglia di configurare i Crediti comunicazioni per i piani per chiamate (nazionali o internazionali) e gli utenti di audioconferenza che necessitano della possibilità di effettuare chiamate in uscita verso qualsiasi destinazione. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. 

Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. Per altre informazioni, inclusi gli importi di finanziamento consigliati, vedere Che cosa sono i crediti [comunicazioni?](what-are-communications-credits.md) e [Configurare i crediti comunicazioni per l'organizzazione.](set-up-communications-credits-for-your-organization.md)
  

## <a name="related-topics"></a>Argomenti correlati
[Ecco cosa si ottiene con Teams Telefono](here-s-what-you-get-with-phone-system.md)

[Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
