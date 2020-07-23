---
title: Recupero di numeri di telefono per gli utenti
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Informazioni su come ottenere nuovi numeri di telefono o di trasferimento di dati esistenti per i team e come visualizzare le modifiche apportate agli utenti. '
ms.openlocfilehash: ccc0baa1f4793967daa9520de1c9aaa9b56175ba
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372075"
---
# <a name="getting-phone-numbers-for-your-users"></a>Recupero di numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono.
  
Sono disponibili tre modi per ottenere i numeri degli utenti:

- **Usare l'interfaccia di amministrazione di Microsoft teams.** Per alcuni paesi e aree geografiche è possibile ottenere numeri per gli utenti tramite l'interfaccia di amministrazione di Microsoft teams. Vedere [ottenere nuovi numeri di telefono per gli utenti](#get-new-phone-numbers-for-your-users).

- **Importa i tuoi numeri esistenti.** È possibile convertire o trasferire i numeri esistenti dal provider di servizi o dal gestore di telefonia corrente. Per ulteriori informazioni su come eseguire questa operazione, vedere [Trasferire numeri di telefono in Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) o [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).  
  
- **Utilizzare un modulo di richiesta per nuovi numeri.** A volte, a seconda del paese o dell'area geografica, non potrai ottenere i nuovi numeri di telefono usando l'interfaccia di amministrazione di Microsoft teams oppure avrai bisogno di numeri di telefono o codici di area specifici. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> Per informazioni su come configurare i numeri di telefono per l'organizzazione, vedere contattare il contatto di supporto per i prodotti business-Guida per gli amministratori ( https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online .
  
## <a name="get-new-phone-numbers-for-your-users"></a>Ottenere numeri di telefono per gli utenti

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

Per apportare queste modifiche, è necessario essere un amministratore del servizio teams. Vedere [usare i ruoli di amministratore di team per gestire i team](https://docs.microsoft.com/microsoftteams/using-admin-roles) per leggere informazioni su come ottenere ruoli di amministratore e autorizzazioni.

1. Accedere all'interfaccia di amministrazione di Microsoft teams.
2. Nella barra di spostamento sinistra, Vai **Voice**a  >  **numeri di telefono**vocale e quindi fai clic su **Aggiungi**.
3. Immettere un nome per l'ordine e aggiungere una descrizione.
4. Nella pagina location and quantity eseguire le operazioni seguenti:
    1. In **paese o area geografica**selezionare un paese o un'area geografica.
    2. In **tipo di numero**selezionare **utente (abbonato)**.
    3. In **posizione**selezionare una posizione. Se è necessario creare una nuova posizione, fare clic su **Aggiungi una posizione**.
    4. In **prefisso geografica**selezionare un prefisso.
    5. In **quantità**immettere il numero di numeri desiderato per l'organizzazione e quindi fare clic su **Avanti** per selezionare i numeri.
5. Selezionare i numeri desiderati. Si hanno 10 minuti per selezionare i numeri di telefono e inserire l'ordine. Se si impiegano più di 10 minuti, i numeri di telefono vengono restituiti al pool di numeri.
6. Quando si è pronti per effettuare l'ordine, fare clic su **Inserisci ordine**.

    > [!IMPORTANT]
    > Il numero di numeri di telefono per gli utenti (abbonati) è uguale al numero totale di **piani per chiamate nazionali** e/o licenze per le **chiamate nazionali e internazionali** assegnate moltiplicato per 1,1, oltre a 10 numeri di telefono aggiuntivi. Ad esempio, se hai 50 utenti in totale con un piano per chiamate nazionali e/o un piano per chiamate nazionali e internazionali, puoi acquisire **65** numeri di telefono **(50 x 1,1 + 10)**. Per informazioni dettagliate, Vedi [quanti numeri di telefono puoi ottenere?](/microsoftteams/how-many-phone-numbers-can-you-get). Per ottenere più numeri di telefono, [contattare il contatto di supporto per i prodotti business-Guida per gli amministratori](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Trasferire numeri di telefono dal provider di servizi o dal gestore di telefonia
  
- Se sono necessari 999 o meno numeri di telefono per gli utenti, usare la procedura guidata per la conversione nell'interfaccia di amministrazione di Microsoft teams. Seguire i passaggi descritti in [trasferire i numeri di telefono in teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams). Se il paese o l'area geografica non è elencato nella procedura guidata di conversione, è possibile [inviare manualmente un ordine di trasferimento](phone-number-calling-plans/manually-submit-port-order.md) o vedere [gestire i numeri di telefono per l'organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization) per scaricare la lettera di autorizzazione (LOA, correct Letter of Authorization).

- Se è necessario trasferire più di 999 numeri di telefono, è possibile [inviare manualmente un ordine](phone-number-calling-plans/manually-submit-port-order.md) di trasferimento o vedere [gestire i numeri di telefono per l'organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization) per scaricare la lettera di autorizzazione corretta e quindi inviarla al [banco di servizio PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) per trasferire tutti i numeri.

## <a name="view-the-phone-numbers-for-your-organization"></a>Visualizzare i numeri di telefono per l'organizzazione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

Nella barra di spostamento sinistra dell'interfaccia di amministrazione, passa **Voice**a  >  **numeri di telefono** vocale per visualizzare i numeri per l'organizzazione, inclusi posizione, tipo di numero e informazioni sullo stato.
  
## <a name="assign-phone-numbers-to-users"></a>Assegnare numeri di telefono agli utenti

Dopo aver ottenuto i numeri di telefono, è necessario assegnare un numero a ogni utente. Per altre informazioni [, vedere assegnare, modificare o rimuovere un numero di telefono per un utente](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Per ottenere più numeri di telefono, [contattare il contatto di supporto per i prodotti business-Guida per gli amministratori](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).

## <a name="related-topics"></a>Argomenti correlati

[Domande comuni sul trasferimento dei numeri di telefono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
