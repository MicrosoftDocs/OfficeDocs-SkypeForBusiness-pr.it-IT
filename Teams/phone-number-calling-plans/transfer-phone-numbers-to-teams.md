---
title: Trasferire i numeri di telefono Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: Informazioni su come usare la procedura guidata di porting per trasferire il numero di telefono dal provider di servizi corrente a Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b487249e9a3744c2f83a9bece04a17e7e2948f01
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861953"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Trasferire i numeri di telefono Microsoft Teams

Usare la procedura guidata di porting nell'Microsoft Teams di amministrazione per trasferire i numeri di telefono dal provider di servizi corrente a Teams. Dopo aver portato i numeri di telefono in Teams, Microsoft diventerà il provider di servizi e ti addebiterà tali numeri di telefono.

Prima di iniziare, è consigliabile esaminare le informazioni in [Che cos'è un ordine di trasferimento?](port-order-overview.md) Se hai numeri di servizio per bridge di conferenza telefonica con accesso esterno, operatori automatici o altri numeri di servizio, numeri a numero verde o hai [](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) più di 999 numeri di telefono per utenti (abbonati) che devi trasferire a Teams, vedi Gestire i numeri di telefono dell'organizzazione per scaricare i moduli corretti e inviarli a Microsoft.

  > [!NOTE]
  > Microsoft elabora gli ordini di trasferimento per il trasferimento di numeri di telefono solo nei giorni lavorativi degli Stati Uniti e non nei giorni festivi o nei fine settimana.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Creare un ordine di trasferimento e trasferire i numeri di telefono in Teams

> [!NOTE]
> **Attualmente, è possibile usare questa procedura guidata per ottenere** i numeri di telefono per Regno Unito, Stati Uniti e Canada. Per ottenere numeri di telefono per altri paesi e aree geografiche, è possibile [inviare manualmente un ordine di trasferimento.](manually-submit-port-order.md) Per ottenere il modulo necessario per inviare manualmente un ordine di trasferimento, selezionare il proprio paese o area geografica nell'elenco a discesa in Gestire i numeri di telefono [per l'organizzazione.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Numeri  >  **Telefono vocali.** Fare **clic su** Numeri e quindi su **Porta** per avviare la procedura guidata di porting.
2. Esaminare le informazioni nella **pagina Introduzione** e quindi, quando si è pronti, fare clic su **Avanti.**
3. Nella pagina **Selezione località e tipo di numero** specificare quanto segue e quindi fare clic su **Avanti:**

    - **Paese o area geografica:** Paese o area geografica in cui si stanno ricevendo i numeri.
    - **Telefono tipo di** numero: tipo di numero, ad esempio numeri geografici o a numero verde.
    - **Numeri assegnati a:** a cosa sono assegnati i numeri. Ad esempio, utenti, conferenze o funzionalità vocali.

4. Nella pagina **Aggiungi informazioni account** completare le operazioni seguenti e quindi fare clic su **Avanti.**

    > [!IMPORTANT]
    > Le informazioni visualizzate in questa pagina sono determinate dal paese o dall'area geografica e dal tipo di numero. Ogni paese e area geografica ha normative diverse sulle informazioni necessarie per il porto dei numeri. Gli elementi visualizzati in questa pagina potrebbero essere diversi da quelli descritti di seguito.

    - **Dettagli ordine:** 
        - **Nome ordine:** nome dell'ordine
        - **Messaggi di posta elettronica di notifica:** indirizzi di posta elettronica per ricevere le notifiche degli ordini. Se si immettono più indirizzi di posta elettronica, separa ognuno con un punto e virgola.
        - **Data trasferimento:** data di trasferimento emessa dal provider di servizi corrente.
    - **Telefono numero**
        - **Tipo di** porta: se si sta eseguendo una porta completa per trasferire tutti i numeri o una porta parziale per trasferire alcuni numeri.
    - **Persona che richiede dettagli**  
        - Nome dell'organizzazione e dettagli di contatto della persona che richiede il trasferimento.
    - **Dettagli del provider corrente**
        - Numero di telefono di fatturazione **(BTN):** il tuo BTN in formato E.164, che richiede un segno + per anteporre il numero. Ad esempio, per un numero nordamericano, usare il formato +1XXXYYYZZZZ.
        - Altri dettagli, tra cui il nome del provider di servizi corrente, il numero dell'account e l'indirizzo del servizio.
            
5. Nella pagina **Aggiungi numeri** fare clic su Seleziona **un file,** individuare e selezionare il file CSV contenente i numeri di telefono da trasferire e quindi fare clic su **Avanti.**  

    > [!NOTE]
    > Il file CSV deve contenere una sola colonna con un'intestazione denominata NumeroFono. Ogni numero di telefono deve essere in una riga separata e può contenere solo cifre o in formato E.164.

6. Nella pagina **Completa l'ordine** fare clic Upload una lettera di autorizzazione firmata per caricare una copia digitalizzata della lettera di autorizzazione (LOA) firmata. 

    Se non è già stato scaricato e firmato il contratto di accesso, eseguire le operazioni seguenti:
    
    1. Fare **clic su Scarica il modello** per scaricare la loa per il proprio paese o area geografica. 
    2. Stampare il file LOA.
    3. Impostare la firma LOA da parte della persona autorizzata a apportare modifiche all'account.
    4. Analizzare la firma LOA e quindi fare clic Upload **una lettera** di autorizzazione firmata per caricarla.

    > [!NOTE]
    > Dopo aver caricato il tuo LOA, invia l'ordine. Il caricamento della loa non è sufficiente. Devi anche inviare l'ordine per poterlo elaborare.

7. Esaminare i dettagli dell'ordine e quindi fare clic su **Invia.**


## <a name="what-happens-next"></a>Cosa succede dopo?

Quando riceviamo l'ordine di trasferimento, riceverai un messaggio di posta elettronica che verifica la tua richiesta. La richiesta viene controllata e aggiornata quotidianamente e si verrà informati dello stato e dello stato dell'utente tramite posta elettronica. Se la richiesta di portabilità viene rifiutata dal gestore in perdita, contattare [il service desk TNS.](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

Per visualizzare lo stato dell'ordine di trasferimento, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare > **Ordini** di trasferimento vocale e quindi fare clic su Cronologia  >   **ordini.** Ogni stato dell'ordine di trasferimento è elencato nella **colonna** Stato. Per altre informazioni, vedere Qual è lo stato [degli ordini di trasferimento?](port-order-status.md)

## <a name="related-topics"></a>Argomenti correlati

- [Cos'è un ordine di portabilità?](port-order-overview.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
