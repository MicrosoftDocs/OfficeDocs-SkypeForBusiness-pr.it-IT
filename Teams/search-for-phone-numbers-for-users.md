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
description: Informazioni su come cercare numeri di telefono che è possibile assegnare agli utenti, in base al paese o all'area geografica e alla città, e specificare la quantità di numeri necessaria.
ms.openlocfilehash: b44a25865f58dcabd8876f0e4bfa6732cd4cde54
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046332"
---
# <a name="search-for-telephone-numbers-for-users"></a>Cercare numeri di telefono per gli utenti

Quando si configurano gli utenti dell'organizzazione per effettuare e ricevere chiamate telefoniche tramite numeri di telefono forniti da Microsoft, è necessario prima di tutto usare l'interfaccia di amministrazione di **Microsoft Teams** e acquisire i numeri di telefono da assegnare agli utenti. Il numero di telefono assegnato a un utente sarà un numero di telefono acquistato in precedenza per l'organizzazione. il numero verrà elencato nell'elenco a discesa quando si modificano le proprietà dell'utente e si fa clic su **Assegna**.
  
Prima di poter assegnare numeri di telefono forniti da  Microsoft agli utenti, è necessario usare la pagina Ottieni nuovi numeri per cercare i numeri di telefono disponibili. È possibile eseguire ricerche **in base al paese (mercato),** al tipo **di** numero e alla **posizione.** Verrà quindi visualizzato un elenco di operatori che forniscono numeri in quel paese. 

Se si seleziona Microsoft come operatore, è possibile acquisire i numeri dall'interfaccia di amministrazione di Teams immettendo la quantità di numeri di telefono necessari per gli utenti.La pagina limiterà automaticamente la quantità in base al numero di elementi ancora disponibili per l'acquisizione. Se si seleziona un operatore Connessione con operatore, si verrà indirizzati alla pagina di destinazione dell'operatore selezionato per completare l'ordine dei numeri. 

La modalità di acquisizione e gestione dei numeri di telefono varia a seconda dell'opzione di connettività PSTN: Piani per chiamate Microsoft, Connessione con operatore o Routing diretto. 

Questo articolo si applica ai [Piani per chiamate Microsoft](#search-for-telephone-numbers-for-microsoft-calling-plans) e [Connessione con operatore.](#search-for-telephone-numbers-for-operator-connect) Per altre informazioni su tutte le opzioni, vedere [Gestire i numeri di telefono per l'organizzazione.](/microsoftteams/manage-phone-numbers-landing-page)

  
## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Cercare numeri di telefono per Piani per chiamate Microsoft

Per cercare numeri di telefono per gli utenti: 
  
1. Passare **all'Microsoft Teams di amministrazione.**

2. Nel riquadro di spostamento sinistro selezionare **Voce**  >  **Telefono numeri** Ottieni nuovi  >  **numeri**.
  
    > [!IMPORTANT]
    > Per visualizzare l'opzione Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Teams, è necessario prima acquistare almeno una licenza di  Enterprise E5 o **E3,** una licenza per componenti aggiuntivi  **Sistema telefonico** o una licenza per i componenti aggiuntivi per audioconferenze.  

3. Nella pagina **Seleziona posizione e quantità** selezionare una località nell'elenco a discesa Paese **(mercato).**

4. Selezionare **Utente** **nell'elenco a** discesa Tipo di numero.

5. A seconda del Paese (mercato) selezionato, ora sono disponibili diverse opzioni da usare per individuare i numeri di telefono necessari.  

6. In **Quantità** immettere il numero di numeri di telefono desiderato per l'organizzazione e quindi fare clic su **Avanti.** Hai 10 minuti di tempo per selezionare i numeri di telefono. Se superi i 10 minuti, i numeri di telefono verranno restituiti nel pool di numeri.

    > [!NOTE]
    > È possibile visualizzare il numero di numeri di telefono disponibili (in base al numero di licenze), elencato accanto a **Quantità**. 
  
8. Nella pagina **Ottieni numeri** selezionare i numeri di telefono desiderati, fare clic su **Acquisisci numeri** e quindi su **Avanti.**

    > [!IMPORTANT]
    > È possibile acquisire più numeri di telefono rispetto alle licenze Microsoft. Per determinare il numero di numeri di telefono che è possibile acquisire, prendere il numero di licenze del piano per chiamate Microsoft, aggiungere il 10% del numero di licenze, quindi aggiungere 10 e quindi rimuovere tutte le licenze già acquistate. Ad esempio, se si hanno 100 licenze **Per** chiamate nazionali Microsoft e/o **Piano** per chiamate internazionali Microsoft, è possibile prenotare 120 numeri di telefono, presupponendo che alcuni numeri di telefono non siano già stati acquistati per quei 100 utenti. Per altre informazioni, vedere [Quanti numeri di telefono è possibile ottenere?](./how-many-phone-numbers-can-you-get.md)

9. Nella pagina **Conferma** verificare le scelte effettuate e quindi fare clic su **Ordina.**

10. Quando si torna alla pagina **Telefono** numeri di telefono, selezionare il numero di telefono o i numeri da assegnare e quindi fare clic **su** Modifica per assegnarlo a un utente.  


## <a name="search-for-telephone-numbers-for-operator-connect"></a>Cercare numeri di telefono per Connessione con operatore

1. Passare **all'Microsoft Teams di amministrazione.**

2. Nel riquadro di spostamento sinistro selezionare **Voce**  >  **Telefono numeri** Ottieni nuovi  >  **numeri**.
  
    > [!IMPORTANT]
    > Per visualizzare l'opzione Voce nel riquadro di spostamento sinistro nell'interfaccia di amministrazione di Teams, è necessario prima acquistare almeno una licenza di  Enterprise E5 o **E3,** una licenza per componenti aggiuntivi  **Sistema telefonico** o una licenza per i componenti aggiuntivi per audioconferenze.  

3. Nella pagina **Seleziona posizione e quantità** selezionare una località nell'elenco a discesa Paese **(mercato).**

4. Selezionare **Utente** **nell'elenco a** discesa Tipo di numero.

5. A seconda del Paese (mercato) selezionato, ora sono disponibili diverse opzioni da usare per individuare i numeri di telefono necessari. È possibile filtrare per visualizzare solo gli operatori aggiunti selezionando **Mostra operatori.**

6. Se hai già fornito il consenso all'operatore, ti verrà indirizzato alla pagina di destinazione dell'operatore per completare il processo di ordine. 

7. Se non hai fornito il consenso all'operatore, ti verrà indicato di abilitare l'operatore nella pagina dell'operatore scelto nell'Teams di amministrazione. Per altre informazioni, vedere [Abilitare un operatore.](operator-connect-configure.md#enable-an-operator)

8. Al termine dell'ordine, l'operatore carica i numeri di telefono nel tenant ed è possibile assegnarli agli utenti.  

## <a name="related-topics"></a>Argomenti correlati

[Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)