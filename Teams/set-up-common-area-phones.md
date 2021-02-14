---
title: Configurare la licenza Common Area Phone
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
description: 'Informazioni su come configurare Common Area Phones per lobbies, le aree di ricezione e le sale riunioni '
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476711"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurare la licenza Common Area Phone per Microsoft Teams
> [!NOTE]
> I telefoni nell'area comune non supportano la segreteria telefonica.

Un telefono ad area comune viene in genere inserito in un'area, ad esempio una sala d'attesa o un'altra area disponibile a molte persone per effettuare una chiamata; ad esempio un'area della reception, una sala d'attesa o un telefono da conferenza. I telefoni dell'area comune sono connessi con account collegati a una licenza Common Area Phone. Anche il criterio TeamsIPPhone deve essere impostato in modo appropriato perché il telefono abbia un'esperienza utente nell'area comune.

Nei passaggi seguenti verrà illustrato come configurare un account per Sistema telefonico per distribuire i telefoni dell'area comune per l'organizzazione. Per un'esperienza di sala riunioni più completa, compresa l'audioconferenza, valutare l'acquisto della licenza dedicata per la sala riunioni con un dispositivo per la sala riunioni. 

Prima di tutto, è necessario acquistare una licenza Common Area Phone (CAP) e assicurarsi di avere un telefono certificato. Per cercare e ottenere altre informazioni sui telefoni certificati, vai ai [dispositivi Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Acquisto** di fatturazione  >  **e** quindi espandere **Altri piani.**

    ![Screenshot che mostra il riquadro Telefono area comune](media/set-up-common-area-phone-image1.png)

2. Seleziona **Acquista telefono area comune**  >  **ora.**

3. Nella pagina Cassa fare clic **su Acquista ora.**

4. Espandi **gli abbonamenti a componenti aggiuntivi** e quindi fai clic per acquistare un piano per chiamate. Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.

> [!NOTE]
> Se si utilizza l'instradamento diretto del Sistema telefonico Microsoft, non è necessaria una licenza per il Piano per chiamate.

> [!NOTE]
> Non è necessario aggiungere una licenza Sistema telefonico. È inclusa con la licenza per il Telefono di area comune.

Per altre informazioni sulle licenze, vedere [licenze per i componenti aggiuntivi di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)

La licenza Common Area Phone supporta: 


|   |  Telefono di area comune  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Phone System |    &#x2714; |
|Audioconferenza |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilità in tutto il mondo |       &#x2718; &sup2;  |
|Disponibilità dei canali |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; I telefoni dell'area comune possono accedere alle audioconferezioni tramite un numero di telefono fornito dall'organizzatore della riunione

&sup2; Non disponibile nei cloud sovereign  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze

1. Nell'interfaccia di amministrazione di Microsoft 365 passare **agli** utenti attivi e  >    >  **aggiungere un utente.**

2. Immettere un nome utente come "Principale" per il nome e "Ricezione" per il secondo nome.

3. Immettere un nome visualizzato se non viene rigenerato automaticamente, ad esempio "Ricezione principale".

4. Immettere un nome utente, ad esempio "MainReception" o "Mainlobby".

5. Per i telefoni dell'area comune, può essere necessario impostare manualmente una password o avere la stessa password per tutti i telefoni dell'area comune. È anche consigliabile deselezionare la casella di controllo Imposta questo utente per cambiare **la password** al primo accesso.

6. Assegnare le licenze all'utente. Nella stessa pagina, fai clic per espandere **Licenze di prodotto**. Attiva il Common Area Phone e scegli un Piano **per** chiamate nazionali o Un Piano per chiamate nazionali **e internazionali.** 

    ![Screenshot che mostra l'assegnazione di licenze](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Se si utilizza l'instradamento diretto del Sistema telefonico Microsoft, non è necessario assegnare una licenza per un Piano per chiamate.

Per altre informazioni, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune

Usare l'interfaccia di amministrazione di Teams per assegnare un numero all'utente.

1. Nell'interfaccia di amministrazione di Teams selezionare **Numeri**  >  **di telefono vocali.**

3.    Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.

4. Nella casella **Utente** vocale della pagina Assegna digita il nome dell'utente che usa il telefono e quindi seleziona l'utente nell'elenco **a** discesa Seleziona un utente vocale.

5. Successivamente, è necessario aggiungere un indirizzo per gli interventi di emergenza. Scegliere **Cerca per città,** Cerca  per descrizione o Cerca per località nell'elenco a discesa e quindi immettere la città, la descrizione o il luogo nella casella di testo.  Dopo aver cercato, cerca in **Seleziona l'indirizzo per** gli interventi di emergenza e scegli quello giusto per te.

6. Clicca su **Salvare** e il tuo utente dovrebbe apparire così:

   ![Screenshot che mostra l'assegnazione di licenze](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Gli utenti verranno visualizzati solo se hanno una licenza Sistema telefonico applicata. Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.

Per ulteriori informazioni, consulta [Recupero di numeri di telefono per gli utenti.](getting-phone-numbers-for-your-users.md)

Puoi anche trasferire il tuo numero di telefono con un altro gestore e la "porta" oppure trasferirlo a Microsoft 365 o Office 365. Vedi [Trasferire numeri di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
