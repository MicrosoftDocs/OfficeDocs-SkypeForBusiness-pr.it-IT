---
title: Configurare la licenza Telefono area comune
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: "Informazioni su come configurare i telefoni dell'area comune per le lobby, le aree di ricezione e le sale riunioni "
ms.openlocfilehash: ad38f753b109aefd0e7628efe3e61472e7149597
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733755"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurare la licenza dell'area Telefono per Microsoft Teams
> [!NOTE]
> I telefoni dell'area comune non supportano la segreteria telefonica.

Un telefono dell'area comune è in genere posizionato in un'area come una sala d'attesa o un'altra area che è disponibile a molte persone per effettuare una chiamata; ad esempio un'area di ricezione, una sala d'attesa o un telefono per conferenze. I telefoni dell'area comune sono connessi con account collegati a una licenza di area Telefono comune. Anche il criterio TeamsIPPhone deve essere impostato in modo appropriato perché il telefono abbia un'esperienza utente nell'area comune.

Nei passaggi seguenti verrà illustrato come configurare un account per Sistema telefonico per distribuire telefoni ad area comune per l'organizzazione. Per un'esperienza più completa nella sala riunioni, inclusa l'audioconferenza, è consigliabile acquistare la licenza Sala riunioni con un dispositivo della sala riunioni. 

Prima di tutto, è necessario acquistare una licenza di Common Area Telefono (CAP) e assicurarsi di avere un telefono certificato. Per cercare e altre informazioni sui telefoni certificati, vai a Microsoft Teams [dispositivi.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze

1. Nel interfaccia di amministrazione di Microsoft 365, passare a **Servizi di** acquisto  >  **fatturazione** e quindi espandere Altri **piani**.

    ![Screenshot che mostra il riquadro Telefono area comune.](media/set-up-common-area-phone-image1.png)

2. Selezionare **Area comune Telefono** Acquista  >  **ora**.

3. Nella pagina Checkout fare clic su **Acquista ora.**

4. Espandere **Abbonamenti ai componenti aggiuntivi e** quindi fare clic per acquistare un piano per chiamate. Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.

> [!NOTE]
> Se si usa Telefono Microsoft sistema di routing diretto, non è necessaria una licenza per il piano di chiamata.

> [!NOTE]
> Non è necessario aggiungere una licenza Sistema telefonico licenza. È inclusa con la licenza per il Telefono di area comune.

Per altre informazioni sulle licenze, vedere Microsoft Teams [licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

La licenza common area Telefono supporta: 


| &nbsp;  |  Telefono di area comune  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema telefonico |    &#x2714; |
|Audioconferenza |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilità in tutto il mondo |       &#x2718; &sup2;  |
|Disponibilità del canale |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Area comune I telefoni possono partecipare a conferenze audio tramite il numero di accesso fornito dall'organizzatore della riunione

&sup2; Non disponibile nei cloud sovrani  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze

1. Nella finestra interfaccia di amministrazione di Microsoft 365 passare a **Utenti**  >  **utenti attivi che**  >  **aggiungono un utente.**

2. Immettere un nome utente come "Principale" per il nome e "Ricezione" per il secondo nome.

3. Immettere un nome visualizzato se non lo rigenera automaticamente, ad esempio "Ricezione principale".

4. Immettere un nome utente come "MainReception" o "Mainlobby".

5. Per i telefoni dell'area comune, è consigliabile impostare manualmente una password o avere la stessa password per tutti i telefoni dell'area comune. Inoltre, è consigliabile deselezionare la casella di controllo Imposta come utente la **modifica della password** al primo accesso.

6. Assegnare le licenze all'utente. Nella stessa pagina, fai clic per espandere **Licenze di prodotto**. Attiva l'area comune Telefono e scegli un **piano** per chiamate nazionali o un piano per chiamate nazionali **e internazionali.** 

    ![Screenshot che mostra l'assegnazione delle licenze con il piano per le chiamate nazionali e le opzioni del piano nazionale e internazionale evidenziate.](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Se si usa Telefono Microsoft sistema di routing diretto, non è necessario assegnare una licenza per il piano di chiamata.

Per altre informazioni, vedere [Assegnare licenze agli utenti.](/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune

Usare l Teams di amministrazione per assegnare un numero all'utente.

1. Nell'Teams di amministrazione selezionare **Numeri**  >  **Telefono vocali**.

3.    Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.

4. Nella **casella** Utente vocale della pagina Assegna digitare il nome dell'utente che usa il telefono e quindi selezionarlo nell'elenco **a** discesa Selezionare un utente vocale.

5. Successivamente, è necessario aggiungere un indirizzo per gli interventi di emergenza. Scegliere **Cerca per città,** Cerca  per descrizione o Cerca per posizione nell'elenco a discesa e quindi immettere la città, la descrizione o la posizione nella casella di testo.  Dopo aver cercato, cerca in **Seleziona l'indirizzo per gli interventi** di emergenza per scegliere quello giusto per te.

6. Clicca su **Salvare** e il tuo utente dovrebbe apparire così:

   ![Screenshot che mostra l'assegnazione di licenze utente di esempio.](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Gli utenti verranno visualizzati solo se è applicata una Sistema telefonico licenza. Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.

Per altre informazioni, vedere [Ottenere numeri di telefono per gli utenti.](getting-phone-numbers-for-your-users.md)

Puoi anche prendere il tuo numero di telefono che hai con un altro gestore e "porta" o trasferirlo a Microsoft 365 o Office 365. Vedere [Trasferire numeri di telefono Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
