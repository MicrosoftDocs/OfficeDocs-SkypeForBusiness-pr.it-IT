---
title: Cercare numeri di telefono per gli utenti
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: cc22c49a-c644-4151-a2fc-a1474148f8ba
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Informazioni su come cercare numeri di telefono che è possibile assegnare agli utenti in base al paese o all'area geografica e alla città e specificare la quantità di numeri necessaria.
ms.openlocfilehash: 4cb30e6ef03e50c3524ccd9b5c36ae10fb8b5ab2
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681797"
---
# <a name="search-for-telephone-numbers-for-users"></a>Cercare numeri di telefono per gli utenti

Quando si impostano gli utenti dell'organizzazione per effettuare e ricevere chiamate telefoniche con numeri di telefono forniti da Microsoft, è necessario innanzitutto utilizzare l'interfaccia di amministrazione **di Microsoft Teams** e acquisire numeri di telefono da assegnare agli utenti. Il numero di telefono assegnato a un utente sarà un numero di telefono precedentemente acquisito per l'organizzazione; il numero verrà elencato nell'elenco a discesa quando si modificano le proprietà dell'utente e si fa clic su **Assegna**.
  
Prima di assegnare numeri di telefono forniti da Microsoft agli utenti, è necessario utilizzare la pagina **Ottieni nuovi numeri** per cercare i numeri di telefono disponibili. È possibile eseguire una ricerca per **Paese (mercato),** **tipo di numero** e **località**. Verrà quindi visualizzato un elenco di operatori che forniscono numeri in quel paese.

Se si seleziona Microsoft come operatore, è possibile acquisire i numeri dall'interfaccia di amministrazione di Teams immettendo la quantità di numeri di telefono necessari per gli utenti. La pagina limiterà automaticamente la quantità in base al numero ancora disponibile per l'acquisto. Se selezioni un operatore di Connessione con operatore, verrai indirizzato alla pagina di destinazione dell'operatore selezionato per completare l'ordine numerico.

La modalità di acquisizione e gestione dei numeri di telefono varia in base all'opzione di connettività PSTN: Piani per chiamate Microsoft, Connessione con operatore o Routing diretto.

Questo articolo si applica ai [Piani per chiamate Microsoft](#search-for-telephone-numbers-for-microsoft-calling-plans) e [ai Connessione con operatore](#search-for-telephone-numbers-for-operator-connect). Per altre informazioni su tutte le opzioni, vedere [Gestire i numeri di telefono per l'organizzazione](/microsoftteams/manage-phone-numbers-landing-page).

## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Cercare numeri di telefono per Piani per chiamate Microsoft

Per cercare i numeri di telefono degli utenti:
  
1. Passare **all'interfaccia di amministrazione di Microsoft Teams**.

2. Nel riquadro di spostamento sinistro seleziona **Voce** >  **Telefono numeri** > **Ottieni nuovi numeri**.
  
    > [!IMPORTANT]
    > Per visualizzare l'opzione **Voce** nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams, è necessario acquistare almeno una **licenza Enterprise E5 o E3**, una **Sistema telefonico** una licenza per i componenti aggiuntivi o una **Audioconferenza** licenza per i componenti aggiuntivi.  

3. Nella pagina **Seleziona località e quantità** selezionare una località dall'elenco a discesa **Paese (mercato** ).

4. Selezionare **Utente** nell'elenco a discesa **Tipo di numero** .

5. A seconda del paese (mercato) selezionato, avrai ora diverse opzioni disponibili per l'individuazione dei numeri di telefono di cui hai bisogno.  

6. In **Quantità** immettere il numero di numeri di telefono desiderati per l'organizzazione e quindi fare clic su **Avanti**. Hai 10 minuti di tempo per selezionare i numeri di telefono. Se superi i 10 minuti, i numeri di telefono verranno restituiti nel pool di numeri.

    > [!NOTE]
    > Puoi vedere il numero di numeri di telefono disponibili (in base al numero di licenze), elencato accanto a **Quantità**.
  
7. Nella pagina **Ottieni numeri** selezionare i numeri di telefono desiderati, fare clic su **Acquisisci numeri** e quindi su **Avanti**.

    > [!IMPORTANT]
    > Puoi acquisire un numero di numeri di telefono superiore a quello delle licenze Microsoft. Per determinare quanti numeri di telefono puoi acquisire, prendi il numero di licenze del Piano per chiamate Microsoft, aggiungi il 10% del numero di licenze, quindi aggiungi 10 e rimuovi il numero di licenze che hai già acquisito. Ad esempio, se disponi di 100 licenze **per Piano** per chiamate nazionali Microsoft, **Piano per chiamate internazionali** e/o **Piano per chiamate nazionali e internazionali** , puoi prenotare 120 numeri di telefono, presupponendo di non aver già acquisito alcuni numeri di telefono per tali 100 utenti. Per altri dettagli, vedi [Quanti numeri di telefono puoi ottenere?](./how-many-phone-numbers-can-you-get.md)

8. Nella pagina **Conferma** verifica le tue scelte e quindi fai clic su **Effettua ordine**.

9. Quando si torna alla pagina **Telefono numeri**, selezionare il numero di telefono o i numeri da assegnare e quindi fare clic su **Modifica** per assegnarli a un utente.

## <a name="search-for-telephone-numbers-for-operator-connect"></a>Cercare numeri di telefono per Connessione con operatore

1. Passare **all'interfaccia di amministrazione di Microsoft Teams**.

2. Nel riquadro di spostamento sinistro seleziona **Voce** >  **Telefono numeri** > **Ottieni nuovi numeri**.
  
    > [!IMPORTANT]
    > Per visualizzare l'opzione **Voce** nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams, è necessario acquistare almeno una **licenza Enterprise E5 o E3**, una **Sistema telefonico** una licenza per i componenti aggiuntivi o una **Audioconferenza** licenza per i componenti aggiuntivi.  

3. Nella pagina **Seleziona località e quantità** selezionare una località dall'elenco a discesa **Paese (mercato** ).

4. Selezionare **Utente** nell'elenco a discesa **Tipo di numero** .

5. A seconda del paese (mercato) selezionato, avrai ora diverse opzioni disponibili per l'individuazione dei numeri di telefono di cui hai bisogno. È possibile filtrare per mostrare solo gli operatori aggiunti selezionando **Mostra operatori personali**.

6. Se hai già fornito il consenso all'operatore, verrai indirizzato alla pagina di destinazione dell'operatore per completare il processo di ordine.

7. Se non hai fornito il consenso all'operatore, verrai indirizzato per abilitare il tuo operatore nella pagina dell'operatore scelto nell'interfaccia di amministrazione di Teams. Per altre informazioni, vedere [Abilitare un operatore](operator-connect-configure.md#enable-an-operator).

8. Una volta completato l'ordine, l'operatore caricherà i numeri di telefono nel tenant e potrai assegnarli agli utenti.  

## <a name="related-topics"></a>Argomenti correlati

[Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
