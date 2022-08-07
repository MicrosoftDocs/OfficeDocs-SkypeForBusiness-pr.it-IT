---
title: Configurare Telefono di Microsoft Teams sistema con i numeri di telefono del piano per chiamate
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come configurare il sistema Telefono di Microsoft Teams con i numeri di telefono del piano per chiamate per utenti e servizi nell'organizzazione.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
- M365initiative-voice
ms.openlocfilehash: fe94987e4abf8c98c32428f608a19db46aacd4c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268011"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Passaggio 2: Configurare i numeri di telefono del sistema telefonico di Teams

Prima di poter configurare utenti o operatori automatici nella tua organizzazione, devi ottenere i numeri di telefono per loro. Esistono diversi tipi di numeri di telefono, ma di seguito sono elencati i due tipi di numeri che è necessario aggiungere in questo passaggio:

- **Numeri di servizio** Questi numeri vengono utilizzati per operatori automatici, audioconferenze e code di chiamata. Possono essere numeri verdi o a pagamento e gestire grandi quantità di chiamate contemporaneamente. Il numero di telefono dell'azienda deve essere un numero di servizio perché verrà assegnato a un operatore automatico in un passaggio successivo.
- **Numeri abbonati** Questi numeri vengono utilizzati per gli utenti normali in modo che possano effettuare e ricevere chiamate telefoniche.

> [!IMPORTANT]
> Anche se vuoi usare i numeri di telefono esistenti, devi creare e assegnare numeri di telefono temporanei alla linea telefonica principale della tua azienda e ai tuoi utenti. Potrai sostituire questi numeri temporanei con i numeri di telefono esistenti in un passaggio successivo.

> [!NOTE]
> Potrebbero essere richieste diverse ore prima che i nuovi numeri di telefono diventino disponibili in Teams.

## <a name="set-up-a-service-number"></a>Configurare un numero di servizio

Il numero di servizio configurato verrà usato in un passaggio successivo per il numero di telefono principale dell'azienda.

1. Aprire l'interfaccia di amministrazione di Microsoft Teams e accedere con un utente amministratore globale (in genere è l'account usato per iscriversi a Microsoft 365).
2. Nel riquadro di spostamento sinistro passa a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Numeri di telefono** **vocale** > </a> e quindi fai clic su **Aggiungi**.
3. Immettere un nome per l'ordine e aggiungere una descrizione.
4. Nella pagina Posizione e quantità eseguire le operazioni seguenti:
    1. In **Paese o area geografica** selezionare un paese o un'area geografica.
    2. In **Tipo di numero** selezionare una delle opzioni seguenti:

        - **Operatore automatico (a pagamento)** Numero di telefono normale non verde. Le tariffe per le interurbane vengono addebitate al chiamante.
        - **Operatore automatico (numero verde)** Numero verde (Stati Uniti e Canada) o numero verde (Regno Unito). Le tariffe per le lunghe distanze vengono addebitate alla tua azienda. Prima di selezionare questa opzione, è necessario acquistare Crediti comunicazioni. Per altre informazioni, vedi [Cosa devo acquistare per ottenere funzionalità vocali per la mia piccola o media azienda?](whats-business-voice.md).

    3. In **Quantità** selezionare **1**.
        > [!NOTE]
        > Se viene visualizzato il messaggio **Non hai licenze sufficienti per richiedere più numeri di questo tipo**, assicurati di aver acquistato Teams Phone con licenze bundle per il piano per chiamate. Per altre informazioni, vedi [Cosa devo acquistare per ottenere funzionalità vocali per la mia piccola o media azienda?](whats-business-voice.md).
    4. Scegli **Località** o **Prefisso**, a seconda che tu voglia cercare numeri di telefono usando la città di un luogo o se vuoi cercare numeri in un prefisso specifico.
    5. Se si seleziona **Posizione**:

        1. Digita la città in cui si trova l'indirizzo per gli [interventi di emergenza nel passaggio Imposta posizioni per gli interventi di emergenza](set-up-emergency-locations.md) oppure, se devi creare una nuova posizione per un altro ufficio o un ufficio domestico, fai clic su **Aggiungi una posizione**.
        2. In **Prefisso** seleziona un prefisso e quindi seleziona **Avanti** per prenotare il tuo numero.

    6. Se selezioni **Prefisso**, digita il prefisso che vuoi cercare e quindi seleziona **Avanti** per prenotare il numero.

5. Selezionare il numero desiderato. Hai 10 minuti per selezionare il numero di telefono ed effettuare l'ordine. Se l'operazione richiede più di 10 minuti, il numero di telefono verrà restituito al pool di numeri.
6. Quando sei pronto per effettuare l'ordine, fai clic su **Effettua ordine** e quindi **su Fine**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurare i numeri di telefono per gli utenti

1. Aprire l'interfaccia di amministrazione di Microsoft Teams e accedere con un utente amministratore globale. Si tratta in genere dell'account usato per iscriversi a Microsoft 365.
2. Nel riquadro di spostamento sinistro passa a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Numeri di telefono** **vocale** > </a> e quindi fai clic su **Aggiungi**.
3. Immettere un nome per l'ordine e aggiungere una descrizione.
4. Nella pagina Posizione e quantità eseguire le operazioni seguenti:

    1. In **Paese o area geografica** selezionare un paese o un'area geografica.
    2. In **Tipo di numero** selezionare **Utente (abbonato).**
    3. In **Quantità** immettere il numero di numeri desiderato per l'organizzazione.
    4. Scegli **Località** o **Prefisso**, a seconda che tu voglia cercare numeri di telefono usando la città di un luogo o se vuoi cercare numeri in un prefisso specifico.
    5. Se si seleziona **Posizione**:

        1. Digita la città in cui si trova l'indirizzo per gli [interventi di emergenza nel passaggio Imposta posizioni per gli interventi di emergenza](set-up-emergency-locations.md) oppure, se devi creare una nuova posizione per un altro ufficio o un ufficio domestico, fai clic su **Aggiungi una posizione**.
        2. In **Prefisso** seleziona un prefisso e quindi seleziona **Avanti** per prenotare il tuo numero.

    6. Se selezioni **Prefisso**, digita il prefisso che vuoi cercare e quindi seleziona **Avanti** per prenotare il numero.
5. Selezionare i numeri desiderati. Hai 10 minuti di tempo per selezionare i numeri di telefono ed effettuare l'ordine. Se si impiegano più di 10 minuti, i numeri di telefono verranno restituiti nel pool di numeri.
6. Quando sei pronto per effettuare l'ordine, fai clic su **Effettua ordine** e quindi **su Fine**.

> [!div class="nextstepaction"]
> [Passaggio successivo: Assegnare licenze agli utenti di Teams](set-up-licenses.md)
