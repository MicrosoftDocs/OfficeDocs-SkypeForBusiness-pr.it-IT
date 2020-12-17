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
description: Guida dettagliata in dettaglio come configurare il sistema telefonico (cloud PBX) per l'organizzazione in Microsoft 365 o Office 365.
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701214"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurare il sistema telefonico nell'organizzazione

Di seguito è riportata una guida dettagliata per configurare il sistema telefonico in Microsoft 365 o Office 365. I collegamenti ad altre informazioni dettagliate sono disponibili alla fine di ogni passaggio.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Passaggio 1: Verificare che Sistema telefonico sia disponibile nel tuo paese

1.    Innanzitutto passare alla [Disponibilità paese e area geografica per le Audioconferenze e i Piani di chiamata](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)e selezionare il proprio paese dall'elenco nella parte superiore della pagina. 
2.    In **Sistema telefonico**, esaminare l'elenco delle caratteristiche e i dettagli. 
3.    Se il Sistema telefonico è disponibile, andare al passaggio 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Passaggio 2: acquistare e assegnare licenze relative a Sistema telefonico e Piani di chiamata

Per assegnare un sistema telefonico e una licenza per un piano di chiamata a un singolo utente, la procedura è uguale all'assegnazione di una licenza Microsoft 365 o Office 365.  È anche possibile assegnare licenze a più utenti in blocco. Per altre informazioni, vedere [assegnare licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).

Se i piani per le chiamate non sono disponibili per il proprio paese o area geografica, è consigliabile usare il routing diretto per connettere l'infrastruttura di telefonia locale al sistema telefonico.  Per altre informazioni, Vedi [routing diretto del sistema telefonico](direct-routing-landing-page.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Passaggio 3: ottenere i numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono.

Sono disponibili tre modi per ottenere i numeri per gli utenti:
- Ottenere nuovi numeri tramite l'interfaccia di amministrazione di teams.
- Ottenere nuovi numeri che non sono disponibili nell'interfaccia di amministrazione di teams.
- Trasferire i numeri esistenti dal provider di servizi o dal gestore di telefonia corrente a Microsoft 365 o Office 365.

È necessario usare la pagina **Aggiungi numeri** per visualizzare, cercare, acquisire e prenotare i numeri. Puoi eseguire una ricerca in base a Paese/Area geografica, Stato e Città e inserire i numeri di telefono necessari per gli utenti.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Ottenere nuovi numeri di telefono degli utenti con l'interfaccia di amministrazione di Teams

1. Accedere a Microsoft 365 con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di **amministrazione di teams**.
    
3. Nella barra di spostamento sinistra, Vai a  >  **numeri di telefono** vocale, fai clic su **Aggiungi** e quindi segui le istruzioni.
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Ottenere nuovi numeri non disponibili nell'interfaccia di amministrazione di Teams
  
A volte, a seconda del paese o dell'area geografica, non potrai ottenere i nuovi numeri usando l'interfaccia di amministrazione di teams. In questo caso, è necessario scaricare un modulo e inviarlo di nuovo a noi. Per informazioni su come richiedere nuovi numeri di utente, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Trasferire numeri di telefono dal provider di servizi o dal gestore di telefonia
  
- Se sono necessari 999 o meno numeri di telefono per gli utenti, è possibile usare la procedura guidata **nuovo ordine di trasferimento dei numeri locali nell'interfaccia** di amministrazione di teams. Seguire i passaggi descritti in [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) per trasferire i numeri di telefono.
    
- Se è necessario trasferire più di 999 numeri di telefono, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) in modo da inviare una richiesta o un ordine di servizio per la porta. 

Per informazioni dettagliate sull'acquisizione di nuovi numeri di telefono o il trasferimento di numeri esistenti, consultare [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 4: ottenere numeri di telefono di servizio (audioconferenza, le code di chiamata, gli operatori automatici)

Oltre a ottenere i numeri di telefono per gli utenti da Microsoft 365 o Office 365, è possibile cercare e acquisire numeri di telefono a pedaggio o a numero verde per servizi come l'audioconferenza (per i Bridge di conferenza), gli operatori automatici e le code di chiamata. I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo alcune chiamate contemporaneamente.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Ottenere nuovi numeri di servizio con l'interfaccia di amministrazione di Teams


1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di **amministrazione di teams**.

3. Nel riquadro di spostamento sinistro passa a   >  **numeri di telefono** vocale  >  **Aggiungi nuovo numero** e quindi fai clic su **nuovi numeri di servizio**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione **vocale** nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di teams, è necessario prima acquistare almeno una licenza **Enterprise E5**, una licenza per il componente aggiuntivo per il **sistema telefonico** o una licenza per il componente aggiuntivo per i servizi di **audioconferenza** .

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Ottenere nuovi numeri non disponibili nell'interfaccia di amministrazione di Teams
  
A volte, a seconda del paese o dell'area geografica, non potrai ottenere i nuovi numeri usando l'interfaccia di amministrazione di teams. In questo caso dovrai scaricare un modulo e inviarlo di nuovo a noi. Per informazioni su come richiedere nuovi numeri, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilità o trasferimento dei numeri di servizio

Se voi trasferire numeri di servizio esistenti dall'operatore o provider di servizio attuale, devi presentare manualmente un ordine di portabilità a Microsoft. È necessario inviare ordini di porta distinti per ogni tipo di numero di servizio (a pagamento o a pagamento) che verrà trasferito con una lettera di autorizzazione (LOA). Nella lettera di autorizzazione (LOA) è necessario selezionare il tipo di numero di servizio corretto. Quando si contatta il supporto Microsoft, specificare che si sta trasferendo un numero di servizio (*e non un utente o un numero di abbonato*) oppure che la capacità chiamante simultanea potrebbe non essere sufficiente per gestire i volumi delle chiamate. Se si desidera trasferire i numeri di telefono o eseguire altre operazioni con i numeri di telefono, vedere [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Passaggio 5: se si desidera impostare i Piani di chiamata

Se avete seguito i passaggi precedenti, avete già acquistato il Sistema telefonico e assegnato le relative licenze, acquistato un Piano di chiamata (passaggio 2) e acquisito numeri di telefono per gli utenti (passaggio 3), pertanto il Piano di chiamata è parzialmente configurato. Per completare le procedure per la configurazione del piano per le chiamate, vedere [configurare i piani](set-up-calling-plans.md)per le chiamate.


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Passaggio 6: Se si desidera impostare Audioconferenze

A volte le persone all'interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Microsoft teams include la funzionalità per i servizi di audioconferenza solo per questa situazione. Gli utenti possono chiamare riunioni di teams usando un telefono, invece di usare l'app teams in un dispositivo mobile o un PC.
Per informazioni su come configurare i servizi di audioconferenza, vedere [configurare le conferenze audio per i team](set-up-audio-conferencing-in-teams.md).

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Passaggio 7: se si vuole configurare una coda di chiamata cloud

Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare l'agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa. È possibile creare code di chiamata singole o multiple per l'organizzazione.

Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Passaggio 8: se si vuole configurare un operatore automatico cloud

Gli operatori automatici consentono agli utenti che chiamano l'organizzazione e spostano un sistema di menu per accedervi al reparto di destra, alla coda di chiamata, alla persona o all'operatore. Puoi creare un operatore automatico per l'organizzazione usando l'interfaccia di amministrazione di teams.

Per informazioni sulla configurazione di un cloud auto attendendant, vedere [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 9: assegnare i numeri di telefono di servizio (audioconferenza, code di chiamata, operatori automatici)

Dopo avere creato i numeri di servizio dal **passaggio 4 sopra**, è necessario assegnarli a ogni tipo di servizio che si desidera. Ad esempio, se si vuole un numero di telefono del servizio dedicato (a pagamento o a pagamento), è necessario assegnare il numero al Bridge di conferenza.

- Per i servizi di audioconferenza, è possibile assegnare un numero dedicato a un Bridge di conferenza accedendo ai ponti conferenza delle riunioni dell'interfaccia di **amministrazione di teams**  >    >   e seguendo le istruzioni.  Per altre informazioni, vedere  [modificare i numeri a pagamento o a numero verde nel Bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Per gli operatori automatici, è possibile assegnare un numero dedicato a un operatore automatico passando agli operatori automatici vocali dell'interfaccia di **amministrazione di teams**  >    >   e seguire le istruzioni.  Per altre informazioni, vedere [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).

- Per le code di chiamata, è possibile assegnare un numero dedicato a una coda di chiamata accedendo alle code delle chiamate vocali dell'interfaccia di **amministrazione di teams**  >    >   e seguire le istruzioni. Per altre informazioni, vedere [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).

Per informazioni dettagliate su come ottenere nuovi numeri di servizio oppure su come trasferire numeri di servizio esistenti, vedere [Ottenere numeri di telefono di servizio](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Passaggio 10: configurare i crediti per le comunicazioni per l'organizzazione

Se si vuole usare i numeri verdi con Microsoft teams, è necessario configurare i crediti per le comunicazioni. Microsoft consiglia di configurare i crediti per le comunicazioni per i piani di chiamata (nazionali o internazionali) e per gli utenti di servizi di audioconferenza che hanno la possibilità di effettuare chiamate in uscita a qualsiasi destinazione. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. 

Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. Per altre informazioni, inclusi gli importi dei finanziamenti consigliati, vedere [quali sono i crediti per le comunicazioni?](what-are-communications-credits.md) e [configurare i crediti per le comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>Argomenti correlati
[Ecco cosa si ottiene con il sistema telefonico in Microsoft 365 o Office 365](here-s-what-you-get-with-phone-system.md)

[Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
