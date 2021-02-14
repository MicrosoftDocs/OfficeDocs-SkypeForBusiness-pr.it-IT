---
title: Trasferire numeri di telefono in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare la procedura guidata di portabilità per trasferire il numero di telefono dal provider di servizi corrente a Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52dd8a2a1dcbc14930695efd52141ce3b1842458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812966"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Trasferire numeri di telefono in Microsoft Teams

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Usare la procedura guidata di portabilità nell'interfaccia di amministrazione di Microsoft Teams per trasferire i numeri di telefono dal provider di servizi corrente a Teams. Dopo il portabilità dei numeri di telefono in Teams, Microsoft diventa il tuo provider di servizi e ti addebita i numeri di telefono.

Prima di iniziare, ti consigliamo di esaminare le informazioni in [Che cos'è un ordine di trasferimento?](port-order-overview.md) Se hai numeri di servizio per bridge dei servizi di conferenza telefonica con accesso esterno, operatori automatici o altri numeri di servizio, numeri verde o [](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) più di 999 numeri di telefono per utenti (abbonati) che devi trasferire in Teams, vedi Gestire i numeri di telefono per la tua organizzazione per scaricare i moduli corretti e inviarli a Microsoft.

  > [!NOTE]
  > Gli ordini di trasferimento vengono elarati per il trasferimento di numeri di telefono solo nei giorni lavorativi negli Stati Uniti e non nei giorni festivi o nei fine settimana.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Creare un ordine di trasferimento e trasferire i numeri di telefono in Teams

> [!NOTE]
> Attualmente puoi utilizzare questa procedura guidata per ottenere numeri di telefono per Regno **Unito, Stati Uniti e Canada.** Per ottenere numeri di telefono per altri paesi e aree geografiche, puoi [inviare manualmente un ordine di trasferimento.](manually-submit-port-order.md) Per ottenere il modulo necessario per inviare manualmente un ordine di trasferimento, seleziona il tuo paese o area geografica nell'elenco a discesa in Gestisci i numeri di telefono [per l'organizzazione.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Numeri**  >  **di telefono vocali.** Fare **clic su** Numeri e quindi su **Porta** per avviare la procedura guidata di portabilità.
2. Esaminare le informazioni nella **pagina Introduzione** e quindi, quando si è pronti, fare clic su **Avanti.**
3. Nella pagina **Selezione località e tipo di** numero specificare quanto segue e quindi fare clic su **Avanti:**

    - **Paese o area geografica:** il paese o l'area geografica in cui si stanno ottenendo numeri.
    - **Tipo di numero di** telefono: tipo di numero, ad esempio numeri geografici o a numero verde.
    - **Numeri assegnati a:** a cosa vengono assegnati i numeri. Ad esempio, utenti, conferenze o funzionalità vocali.

4. Nella pagina **Aggiungi informazioni account** completare le operazioni seguenti e quindi fare clic su **Avanti.**

    > [!IMPORTANT]
    > Le informazioni visualizzate in questa pagina sono determinate dal paese o dall'area geografica e dal tipo di numero. Ogni paese e area geografica ha normative diverse sulle informazioni necessarie per il portabilità dei numeri. I dati visualizzati in questa pagina potrebbero essere diversi da quelli descritti qui.

    - **Dettagli ordine:** 
        - **Nome ordine:** nome dell'ordine
        - **Messaggi di posta elettronica di notifica:** indirizzi di posta elettronica per ricevere le notifiche degli ordini. Se si immettono più indirizzi di posta elettronica, separa ognuno con un punto e virgola.
        - **Data trasferimento:** data di trasferimento emessa dal provider di servizi corrente.
    - **Dettagli del numero di telefono**
        - **Tipo di** porta: se stai eseguendo una portabilità completa per trasferire tutti i tuoi numeri o una portabilità parziale per trasferire alcuni numeri.
    - **Persona che richiede dettagli**  
        - Nome dell'organizzazione e dettagli di contatto della persona che richiede il trasferimento.
    - **Dettagli del provider corrente**
        - **Numero di telefono di fatturazione (BTN):** il tuo numero BTN in formato E.164, che richiede l'anteporre il segno + al numero. Ad esempio, per un numero in America del Nord, usare il formato +1XXXYYYZZZZ.
        - Altri dettagli, tra cui il nome del provider di servizi corrente, il numero dell'account e l'indirizzo del servizio.
            
5. Nella pagina **Aggiungi numeri** fare clic su Seleziona un **file,** individuare e selezionare il file CSV contenente i numeri di telefono da trasferire e quindi fare clic su **Avanti.**  

    > [!NOTE]
    > Il file CSV deve contenere una sola colonna con un'intestazione denominata Numero Phone. Ogni numero di telefono deve essere in una riga separata e può contenere solo cifre o in formato E.164.

6. Nella pagina **Completa l'ordine,** fai clic su **Carica** una lettera di autorizzazione firmata per caricare una copia digitalizzata della lettera di autorizzazione (LOA, Signed Letter of Authorization).

    Se non hai ancora scaricato e firmato il contratto LOA, procedere come segue:
    
    1. Fai **clic su Scarica il modello** per scaricare la loA per il tuo paese o area geografica. 
    2. Stampare il file LOA.
    3. Firma il contratto LOA della persona autorizzata ad apportare modifiche all'account.
    4. Digitalizzare la loa firmata e quindi fare clic **su Carica una lettera di autorizzazione firmata** per caricarla.

    > [!NOTE]
    > Dopo aver caricato il modulo LOA, invia l'ordine. Non è sufficiente caricare il file LOA. Devi anche inviare l'ordine per poterlo elaborare.

7. Rivedere i dettagli dell'ordine e quindi fare clic su **Invia.**


## <a name="what-happens-next"></a>Cosa succede dopo?

Quando riceviamo il tuo ordine di trasferimento, riceverai un'e-mail di verifica della tua richiesta. La richiesta viene controllata e aggiornata quotidianamente e si verrà informati dell'avanzamento e dello stato tramite posta elettronica. Se la richiesta di portabilità viene rifiutata dal gestore perdente, contattare il [service desk PSTN.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)

Per visualizzare lo stato del tuo ordine di trasferimento, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams vai > Ordini di trasferimento vocale, quindi fai clic su  >   **Cronologia ordini.** Ogni stato dell'ordine di trasferimento è elencato nella **colonna** Stato. Per ulteriori informazioni, consulta Qual è lo stato [dei tuoi ordini di trasferimento?](port-order-status.md)

## <a name="related-topics"></a>Argomenti correlati

- [Cos'è un ordine di portabilità?](port-order-overview.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Etichetta della dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
