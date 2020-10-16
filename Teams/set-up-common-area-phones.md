---
title: Configurare la licenza telefonica per l'area comune
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
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
- Phone System
- seo-marvel-mar2020
description: "Informazioni su come configurare i telefoni per l'area comune per atri, aree di ricezione e sale conferenze "
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476711"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurare la licenza telefonica per l'area comune per Microsoft Teams
> [!NOTE]
> I telefoni delle aree comuni non supportano la segreteria telefonica.

Un telefono con area comune viene in genere posizionato in un'area come una sala d'attesa o in un'altra area disponibile per molti utenti per effettuare una chiamata; ad esempio, un'area di ricezione, una sala d'attesa o un telefono per conferenze. I telefoni delle aree comuni sono connessi con gli account collegati a una licenza telefonica per l'area comune. Anche il criterio TeamsIPPhone deve essere impostato in modo appropriato per consentire al telefono di avere un'esperienza utente nell'area comune.

Nei passaggi seguenti ti aiuteremo a configurare un account per il sistema telefonico per la distribuzione dei telefoni delle aree comuni per l'organizzazione. Per un'esperienza di sala riunioni più completa, inclusi i servizi di audioconferenza, valutare l'acquisto della licenza dedicata sala riunioni con un dispositivo della sala riunioni. 

Prima di tutto, è necessario acquistare una licenza per un telefono con area comune (CAP) e assicurarsi di avere un telefono certificato. Per cercare e ottenere ulteriori informazioni sui telefoni certificati, vedere [dispositivi Microsoft teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze

1. Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Billing**  >  **servizi di acquisto** fatturazione e quindi espandere **altri piani**.

    ![Screenshot che mostra il riquadro Telefono area comune](media/set-up-common-area-phone-image1.png)

2. Selezionare Acquista **telefono area comune**  >  **ora**.

3. Nella pagina estrazione fare clic su **Acquista ora**.

4. Espandere **abbonamenti a componenti aggiuntivi** e quindi fare clic per acquistare un piano per le chiamate. Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.

> [!NOTE]
> Se si usa il routing diretto di Microsoft Phone System, non è necessaria una licenza per il piano di chiamata.

> [!NOTE]
> Non è necessario aggiungere una licenza per il sistema telefonico. È inclusa con la licenza per il Telefono di area comune.

Per altre informazioni sulle licenze, vedere [licenze per i componenti aggiuntivi Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

La licenza telefonica per l'area comune supporta: 


|   |  Telefono di area comune  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema telefonico |    &#x2714; |
|Audioconferenza |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilità mondiale |       &#x2718; &sup2;  |
|Disponibilità del canale |    EA, EAS, CSP, GCC, SEO, Web Direct  |
|      |         |

&sup1; I telefoni per l'area comune possono partecipare a conferenze audio tramite il numero di accesso esterno fornito dall'organizzatore della riunione

&sup2; Non disponibile in nubi sovrane  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze

1. Nell'interfaccia di amministrazione di Microsoft 365, passa **a utenti**attivi gli utenti che  >  **active users**  >  **aggiungono un utente**.

2. Immettere un nome utente come "Main" per il nome e la "ricezione" per il secondo nome.

3. Immettere un nome visualizzato se non genera automaticamente uno come "ricezione principale".

4. Immettere un nome utente come "MainReception" o "Mainlobby".

5. Per i telefoni delle aree comuni, è possibile impostare una password manualmente o avere la stessa password per tutti i telefoni delle aree comuni. Inoltre, potresti pensare di deselezionare la casella di controllo **imposta l'utente come modificarne la password al primo accesso** .

6. Assegnare le licenze all'utente. Nella stessa pagina, fai clic per espandere **Licenze di prodotto**. Attivare il telefono per l'area comune e selezionare un **piano per chiamate nazionali** o un **piano per chiamate nazionali e internazionali**. 

    ![Schermata che mostra l'assegnazione delle licenze](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Se si usa il routing diretto di Microsoft Phone System, non è necessario assegnare una licenza per il piano di chiamata.

Per altre informazioni, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune

Usare l'interfaccia di amministrazione di teams per assegnare un numero all'utente.

1. Nell'interfaccia di amministrazione di teams **Voice**selezionare  >  **numeri di telefono**vocali.

3.    Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.

4. Nella casella utente vocale della pagina **assegna** Digitare il nome dell'utente che utilizzerà il telefono e quindi selezionare l'utente nell'elenco a discesa **selezionare un utente vocale** .

5. Devi quindi aggiungere un indirizzo di emergenza. Scegliere **Cerca**in base alla città, **ricerca per Descrizione**o **Cerca in base alla posizione** dall'elenco a discesa e quindi immettere la città, la descrizione o la posizione nella casella di testo. Una volta eseguita la ricerca, Cerca in **selezionare l'indirizzo di emergenza per selezionarne** uno giusto.

6. Clicca su **Salvare** e il tuo utente dovrebbe apparire così:

   ![Schermata che mostra l'assegnazione delle licenze](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Gli utenti verranno visualizzati solo se è stata applicata una licenza per il sistema telefonico. Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.

Per altre informazioni, vedere [recupero di numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md).

È anche possibile prendere il numero di telefono che si ha con un altro vettore e "porta" oppure trasferirlo in Microsoft 365 o Office 365. Vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
