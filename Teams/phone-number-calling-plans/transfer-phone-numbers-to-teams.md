---
title: Trasferire numeri di telefono a Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare la procedura guidata di portabilità per trasferire il numero di telefono dal provider di servizi corrente a Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5b139d332026ffe0ec8338cbe54f6a5309e6e2df
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103253"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Trasferire numeri di telefono a Microsoft Teams

Usa la procedura guidata di portabilità nell'interfaccia di amministrazione di Microsoft Teams per trasferire i numeri di telefono dal provider di servizi corrente a Teams. Dopo il trasferimento dei numeri di telefono in Teams, Microsoft diventa il tuo provider di servizi e ti addebita i numeri di telefono.

Prima di iniziare, ti consigliamo di esaminare le informazioni in [Che cos'è un ordine di trasferimento?](port-order-overview.md) Se hai numeri di servizio per bridge dei servizi di conferenza telefonica con accesso esterno, operatori automatici o altri numeri di servizio, numeri verdi o più di 999 numeri utente (abbonato) che devi trasferire a Teams, vedi [Gestire i numeri di telefono per l'organizzazione per](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) scaricare i moduli corretti e inviarli a Microsoft.

  > [!NOTE]
  > Gli ordini di trasferimento per il trasferimento di numeri di telefono vengono elaborati solo nei Stati Uniti giorni lavorativi e non nei giorni festivi o nei fine settimana.
  > La disponibilità per la portabilità dei numeri verdi può variare in base al paese e all'area geografica. Per saperne di più, fai riferimento ai documenti specifici del paese o dell'area geografica per vedere il supporto disponibile per il servizio di trasferimento.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Crea un ordine di trasferimento e trasferisci i numeri di telefono a Teams

> [!NOTE]
> **Attualmente è possibile usare questa procedura guidata per ottenere i numeri di telefono per il Regno Unito, Stati Uniti e il Canada**. Per ottenere numeri di telefono per altri paesi e aree geografiche, puoi [inviare manualmente un ordine di trasferimento](manually-submit-port-order.md). Per ottenere il modulo necessario per inviare manualmente un ordine di trasferimento, seleziona il paese o l'area geografica nell'elenco a discesa in [Gestisci numeri di telefono per l'organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Numeri Telefono** **voce** > . Fare clic su **Numeri** e quindi su **Porta** per avviare la portabilità guidata.
2. Esaminare le informazioni nella pagina **Attività iniziali** e quindi, quando si è pronti, fare clic su **Avanti**.
3. Nella pagina **Seleziona posizione e tipo di numero** specificare quanto segue e quindi fare clic su **Avanti**:

    - **Paese o area geografica**: paese o area geografica in cui si ricevono numeri.
    - **Telefono tipo di numero**: tipo di numero, ad esempio numeri geografici o gratuiti.
    - **Numeri assegnati a**: a cosa sono assegnati i numeri. Ad esempio, utenti, servizi di conferenza o funzionalità vocali.

4. Nella pagina **Aggiungi informazioni account** completare le operazioni seguenti e quindi fare clic su **Avanti**.

    > [!IMPORTANT]
    > Le informazioni visualizzate in questa pagina dipendono dal paese o dall'area geografica e dal tipo di numero. Ogni paese e area geografica ha normative diverse sulle informazioni necessarie per trasferire i numeri. Gli elementi visualizzati in questa pagina potrebbero essere diversi da quanto descritto qui.

    - **Dettagli ordine**: 
        - **Nome ordine**: nome dell'ordine
        - **E-mail di notifica**: indirizzi e-mail per ricevere notifiche sugli ordini. Se si immettono più indirizzi di posta elettronica, separarli con un punto e virgola.
        - **Data trasferimento**: data di trasferimento emessa dal provider di servizi corrente.
    - **Telefono i dettagli dei numeri**
        - **Tipo di** portabilità: sia che tu stia eseguendo una portabilità completa per trasferire tutti i tuoi numeri o una portabilità parziale per trasferire alcuni dei tuoi numeri.
    - **Persona che richiede dettagli**  
        - Nome dell'organizzazione e dettagli di contatto della persona che richiede il trasferimento.
    - **Dettagli del provider corrente**
        - **Numero di telefono di fatturazione**: il tuo BTN in formato E.164, che richiede un segno + per anteporre il numero. Ad esempio, per un numero di America del Nord, usare il formato +1XXXYYYZZZZ.
        - Altri dettagli, tra cui il nome del provider di servizi corrente, il numero di account e l'indirizzo del servizio.
            
5. Nella pagina **Aggiungi numeri** fare clic su **Seleziona un file**, individuare e selezionare il file CSV contenente i numeri di telefono da trasferire e quindi fare clic su **Avanti**.  

    > [!NOTE]
    > Il file CSV deve avere una sola colonna con un'intestazione denominata Numero Phone. Ogni numero di telefono deve trovarsi in una riga separata e può essere di sola cifra o in formato E.164.

6. Nella pagina **Completa l'ordine**, fai clic su **Upload una lettera di autorizzazione firmata** per caricare una copia digitalizzata della lettera di autorizzazione (LOA) firmata.

    Se la loa non è ancora stata scaricata e firmata, eseguire le operazioni seguenti:
    
    1. Fare clic su **Scarica il modello** per scaricare il modulo LOA per il proprio paese o area geografica. 
    2. Stampare la LOA.
    3. Impostare la LOA firmata dalla persona autorizzata ad apportare modifiche all'account.
    4. Analizzare la LOA firmata e quindi fare clic su **Upload una lettera di autorizzazione firmata** per caricarla.

    > [!NOTE]
    > Dopo aver caricato il loa, invia il tuo ordine. Il solo caricamento della LOA non è sufficiente. Devi anche inviare l'ordine per l'elaborazione.

7. Controlla i dettagli dell'ordine e quindi fai clic su **Invia**.


## <a name="what-happens-next"></a>Cosa succede dopo?

Quando riceviamo il tuo ordine di trasferimento, riceverai un'e-mail di verifica della tua richiesta. La tua richiesta viene controllata e aggiornata quotidianamente e riceverai una notifica dello stato e dell'avanzamento della richiesta tramite e-mail. Se la richiesta di trasferimento viene rifiutata dal gestore precedente, contatta il [Service Desk di TNS](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md).

Per visualizzare lo stato dell'ordine di trasferimento, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams vai a >**Ordini di trasferimento** **vocali** >  e quindi fai clic su **Cronologia ordini**. Ogni stato dell'ordine di portabilità è elencato nella colonna **Stato** . Per ulteriori informazioni, vedi [Qual è lo stato dei tuoi ordini di trasferimento?](port-order-status.md)


## <a name="reporting-telephone-number-issues"></a>Segnalare problemi relativi al numero di telefono?
Se noti problemi con i numeri di portabilità entro le prime 24-48 ore dopo il completamento della porta, contatta il [TNS Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md). Per qualsiasi problema che supera le 48 ore, contatta il team di supporto tecnico Microsoft.

## <a name="related-topics"></a>Argomenti correlati

- [Cos'è un ordine di portabilità?](port-order-overview.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
