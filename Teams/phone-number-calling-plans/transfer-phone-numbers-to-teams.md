---
title: Trasferire i numeri di telefono in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: ''
ms.openlocfilehash: b87684b6fbb73115540e20c72636200e61ca0e88
ms.sourcegitcommit: c4f13aa4947df606d38694a7e544b08be7ce20d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42370415"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Trasferire i numeri di telefono in Microsoft Teams

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Usare la conversione guidata nell'interfaccia di amministrazione di Microsoft teams per trasferire i numeri di telefono dal provider di servizi corrente in teams. Dopo aver convertito i numeri di telefono in teams, Microsoft diventerà il proprio provider di servizi e gli verrà addebitato il numero di telefono.

Prima di iniziare, è consigliabile rivedere le informazioni in [un ordine di trasferimento?](port-order-overview.md) Se si hanno numeri di servizio per i Bridge di conferenza telefonica con accesso esterno, gli operatori automatici o altri numeri di servizio, i numeri verdi 999 o i numeri di telefono degli utenti (abbonati) che è necessario trasferire in teams, vedere [gestire i numeri di telefono dell'organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per scaricare i moduli corretti e inviarli a noi.

  > [!NOTE]
  > Elaboriamo gli ordini di trasferimento per trasferire i numeri di telefono solo nei giorni lavorativi degli Stati Uniti e non in festività pubbliche o nei fine settimana.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Creare un ordine di trasferimento e trasferire i numeri di telefono in teams

> [!NOTE]
> **Attualmente, è possibile usare questa procedura guidata per ottenere numeri di telefono per il Regno Unito e il Canada**. Per ottenere i numeri di telefono per altri paesi e aree geografiche, è possibile [inviare manualmente un ordine di trasferimento](manually-submit-port-order.md). Per ottenere il modulo necessario per inviare manualmente un ordine di trasferimento, selezionare il paese o l'area geografica nell'elenco a discesa in [gestire i numeri di telefono per l'organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a**numeri di telefono** **vocale** > . Fare clic su **numeri**e quindi su **porta** per avviare la procedura guidata.
2. Esaminare **le informazioni nella pagina inizia** e quindi quando si è pronti, fare clic su **Avanti**.
3. Nella pagina **Selezione tipo di posizione e numero** specificare quanto segue e quindi fare clic su **Avanti**:

    - **Paese o area geografica**: paese o area geografica in cui si stanno ottenendo i numeri.
    - **Tipo di numero di telefono**: tipo di numero, ad esempio numeri geografici o verdi.
    - **Numeri assegnati a**: a cosa sono assegnati i numeri. Ad esempio, utenti o servizi di conferenza o voce.

4. Nella pagina **Aggiungi informazioni account** completare le operazioni seguenti e quindi fare clic su **Avanti**.

    > [!IMPORTANT]
    > Le informazioni visualizzate in questa pagina sono determinate in base al paese o all'area geografica e al tipo di numero. Ogni paese e area geografica hanno regole diverse sulle informazioni necessarie per i numeri di porta. Ciò che viene visualizzato in questa pagina può essere diverso da quello descritto qui.

    - **Dettagli ordine**: 
        - **Nome ordine**: nome dell'ordine
        - **Messaggi di notifica**: indirizzi di posta elettronica per ricevere notifiche degli ordini. Se si immettono più indirizzi di posta elettronica, separare ognuno di essi con un punto e virgola.
        - **Data trasferita**: data di trasferimento emessa dal provider di servizi corrente.
    - **Dettagli numero di telefono**
        - **Tipo di porta**: se si sta eseguendo una porta completa per trasferire tutti i numeri o una porta parziale per trasferire alcuni numeri.
    - **Persona che richiede dettagli**  
        - Il nome dell'organizzazione e i dettagli di contatto della persona che richiede il trasferimento.
    - **Dettagli del provider corrente**
        - **Numero di telefono di fatturazione (BTN)**: il proprio BTN nel formato e. 164, che richiede un segno + per anteporre il numero. Ad esempio, per un numero Nord America usare il formato + 1XXXYYYZZZZ.
        - Altri dettagli, tra cui il nome del provider di servizi corrente, il numero di account e l'indirizzo del servizio.
            
5. Nella pagina **Aggiungi numeri** fare clic su **Seleziona un file**, individuare e selezionare il file CSV contenente i numeri di telefono che si desidera trasferire e quindi fare clic su **Avanti**.  

    > [!NOTE]
    > Il file CSV deve avere una sola colonna con un'intestazione denominata PhoneNumber. Ogni numero di telefono deve trovarsi in una riga distinta e può essere costituito solo da cifre o in formato E. 164.

6. Nella pagina **completa l'ordine** fare clic su **carica una lettera di autorizzazione firmata** per caricare una copia digitalizzata della lettera di autorizzazione firmata (LOA).

    Se non è già stato scaricato e firmato il LOA, eseguire le operazioni seguenti:
    
    1. Fare clic su **Scarica il modello** per scaricare la LOA per il paese o l'area geografica. 
    2. Stampare il LOA.
    3. Avere il LOA firmato dalla persona autorizzata a apportare modifiche all'account.
    4. Digitalizzare la LOA con segno e quindi fare clic su **carica una lettera di autorizzazione firmata** per caricarla.

    > [!NOTE]
    > Dopo aver caricato il tuo LOA, invia il tuo ordine. Basta caricare la LOA non è sufficiente. È inoltre necessario inviare l'ordine per l'elaborazione.

7. Esaminare i dettagli dell'ordine e quindi fare clic su **Invia**.


## <a name="what-happens-next"></a>Cosa succede ora?

Quando riceviamo l'ordine di trasferimento, riceverai un messaggio di posta elettronica che verifica la tua richiesta. La tua richiesta viene selezionata e aggiornata giornalmente e verrai avvisato dello stato di avanzamento e dello stato nella posta elettronica. Se la richiesta di porta viene rifiutata dal vettore perdente, contattare il [servizio di assistenza PSTN](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

Per visualizzare lo stato dell'ordine di trasferimento, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai a >**ordini di porta** **vocale** > e quindi fai clic su **cronologia**ordini. Ogni stato dell'ordine di porta è elencato nella colonna **stato** . Per altre informazioni, vedere [Qual è lo stato degli ordini di trasferimento?](port-order-status.md)

## <a name="related-topics"></a>Argomenti correlati

- [Cos'è un ordine di portabilità?](port-order-overview.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
