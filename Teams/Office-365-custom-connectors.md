---
title: Usare i connettori personalizzati e di Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: I connettori mantengono il team aggiornato, fornendo contenuto e aggiornamenti provenienti dai servizi usati di frequente direttamente in un canale.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6726507b0dd6c0ca0067bf19a3f9a2c37f727c53
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136506"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usare Office 365 e connettori personalizzati in Microsoft Teams
=======================================================

I connettori mantengono la corrente del team consegnando i contenuti e gli aggiornamenti del servizio usati di frequente direttamente in un canale. Con i connettori, gli utenti di Microsoft teams possono ricevere gli aggiornamenti da servizi popolari come Twitter, Trello, Wunderlist, GitHub e Azure DevOps Services all'interno del flusso di chat del proprio team.

Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori se le autorizzazioni del team lo consentono e tutti i membri del team ricevono notifiche di attività da tale servizio. I connettori continueranno a funzionare anche dopo che il membro che ha inizialmente configurato il connettore ha lasciato. Qualsiasi membro del team con le autorizzazioni per Add\Remove può modificare la configurazione dei connettori da parte di altri membri.

I connettori di Office 365 possono essere usati sia con Microsoft teams che con i gruppi di Office 365, semplificando la sincronizzazione e la ricezione rapida delle informazioni rilevanti per tutti i membri. Sia Microsoft teams che Exchange usano lo stesso modello di connettore, che consente di usare gli stessi connettori in entrambe le piattaforme. È tuttavia importante notare che la disabilitazione dei connettori per il gruppo di Office 365 a cui un team dipende sarà in grado di disabilitare la possibilità di creare connettori anche per il team.

<a name="add-a-connector-to-a-channel"></a>Aggiungere un connettore a un canale
----------------------------

Attualmente è possibile aggiungere connettori usando i client desktop e Web di Microsoft teams. Tuttavia, le informazioni pubblicate da questi connettori possono essere visualizzate in **tutti i client** , inclusi i dispositivi mobili.

1. Per aggiungere un connettore a un canale, fare clic sui puntini di sospensione **(...),** a destra di un nome di canale, quindi fare clic su **connettori**.

    ![Screenshot dell'interfaccia teams con l'opzione Connectors selezionata.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. È possibile selezionare una varietà di connettori disponibili e quindi fare clic su **Aggiungi**.

    ![Screenshot della finestra di dialogo connettori che mostra i connettori disponibili.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Immettere le informazioni necessarie del connettore selezionato e fare clic su **Salva**. Ogni connettore richiede il corretto funzionamento di un set di informazioni diverso e alcuni potrebbero richiedere l'accesso al servizio usando i collegamenti forniti nella pagina di configurazione del connettore.

    ![Screenshot della pagina di configurazione per il connettore RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. I dati forniti dal connettore vengono automaticamente inseriti nel canale.

    ![Screenshot dell'interfaccia teams che mostra una conversazione in un canale.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Sviluppare connettori personalizzati
----------------------------

È anche possibile creare connettori personalizzati, oltre a webhook in entrata e in uscita. Per altre informazioni, vedere la [documentazione per sviluppatori](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
