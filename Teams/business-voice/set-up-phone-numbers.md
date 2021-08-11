---
title: Configurare i Microsoft 365 Business Voice di telefono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare i numeri Microsoft 365 Business Voice di telefono per gli utenti e i servizi dell'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8c4201930866c844a967c1f236222f7e9611602e5f9990c986a9700b5191d19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306577"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a>Passaggio 2: Configurare i numeri di telefono di VoIP aziendale

Prima di configurare utenti o operatori automatici nell'organizzazione, è necessario ottenere i numeri di telefono. Esistono diversi tipi di numeri di telefono, tuttavia i due tipi di numeri da aggiungere in questo passaggio sono i seguenti:

- **Numeri di servizio** Questi numeri vengono usati per operatori automatici, audioconferenze e code di chiamata. Possono essere numeri a pagamento o a pagamento e possono gestire grandi quantità di chiamate contemporaneamente. Il numero di telefono dell'azienda deve essere un numero di servizio perché verrà assegnato a un operatore automatico in un passaggio successivo.
- **Numeri di abbonato** Questi numeri vengono usati per gli utenti normali in modo che possano effettuare e ricevere chiamate telefoniche.

> [!IMPORTANT]
> Anche se si vogliono usare i numeri di telefono esistenti, è necessario creare e assegnare numeri di telefono temporanei alla linea telefonica principale dell'azienda e agli utenti. Sarà possibile sostituire questi numeri temporanei con i numeri di telefono esistenti in un passaggio successivo.

> [!NOTE]
> Potrebbero essere necessario diverse ore prima che i nuovi numeri di telefono diventino disponibili in Teams.

Il video seguente mostra come completare questi passaggi nell'interfaccia Teams di amministrazione.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWENzQ]

## <a name="set-up-a-service-number"></a>Configurare un numero di servizio

Il numero di servizio configurato ora verrà usato in un passaggio successivo per il numero di telefono principale dell'azienda.

1. Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).
2. Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Numeri**  >  **Telefono**</a>vocali e quindi fare clic su **Aggiungi.**
3. Immettere un nome per l'ordine e aggiungere una descrizione.
4. Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:
    1. In **Paese o area geografica** selezionare un paese o un'area geografica.
    2. In **Tipo di numero** selezionare una delle opzioni seguenti:

        - **Operatore automatico (pedaggio)** Numero di telefono normale, senza numero verde. Le tariffe interurbane vengono addebitate al chiamante.
        - **Operatore automatico (numero verde)** Numero verde (Stati Uniti e Canada) o numero verde (Regno Unito). Le tariffe per le lunghe distanze vengono addebitate all'azienda. Prima di selezionare questa opzione, è necessario acquistare Crediti comunicazioni. Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).

    3. In **Quantità** selezionare **1.**
        > [!NOTE]
        > Se viene visualizzato il messaggio Non si hanno licenze **sufficienti** per richiedere più numeri di questo tipo, assicurarsi di aver acquistato le licenze di VoIP aziendale. Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).
    4. Scegliere Località **o** **Codice** area, a seconda che si vogliano cercare numeri di telefono usando la città di una località o se si vogliono cercare numeri in un codice di area specifico.
    5. Se si seleziona **Posizione**:

        1. Digitare la città in cui si [](set-up-emergency-locations.md) trova l'indirizzo per gli interventi di emergenza nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un home office, fare clic su Aggiungi **una posizione.**
        2. In **Codice area** selezionare un codice di area e quindi selezionare **Avanti** per prenotare il numero.

    6. Se si seleziona **Codice area,** digitare il codice area da cercare e quindi selezionare **Avanti** per prenotare il numero.

5. Selezionare il numero desiderato. Hai 10 minuti per selezionare il tuo numero di telefono e inserire l'ordine. Se si prendono più di 10 minuti, il numero di telefono verrà restituito al pool di numeri.
6. Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurare i numeri di telefono per gli utenti

1. Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).
2. Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Numeri**  >  **Telefono**</a>vocali e quindi fare clic su **Aggiungi.**
3. Immettere un nome per l'ordine e aggiungere una descrizione.
4. Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:

    1. In **Paese o area geografica** selezionare un paese o un'area geografica.
    2. In **Tipo di numero** selezionare Utente **(abbonato)**.
    3. In **Quantità** immettere il numero di numeri desiderato per l'organizzazione.
    4. Scegliere Località **o** **Codice** area, a seconda che si vogliano cercare numeri di telefono usando la città di una località o se si vogliono cercare numeri in un codice di area specifico.
    5. Se si seleziona **Posizione**:

        1. Digitare la città in cui si [](set-up-emergency-locations.md) trova l'indirizzo per gli interventi di emergenza nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un home office, fare clic su Aggiungi **una posizione.**
        2. In **Codice area** selezionare un codice di area e quindi selezionare **Avanti** per prenotare il numero.

    6. Se si seleziona **Codice area,** digitare il codice area da cercare e quindi selezionare **Avanti** per prenotare il numero.
5. Selezionare i numeri desiderati. Hai 10 minuti per selezionare i numeri di telefono e eseguire l'ordine. Se si prendono più di 10 minuti, i numeri di telefono verranno restituiti al pool di numeri.
6. Quando si è pronti per eseguire l'ordine, fare clic **su Ordina** e quindi su **Fine.**

> [!div class="nextstepaction"]
> [Passaggio successivo: Assegnare licenze agli Teams utenti](set-up-licenses.md)
