---
title: Usare Microsoft 365 e connettori personalizzati
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076418"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Usare Microsoft 365 e connettori personalizzati in Microsoft Teams
=======================================================

I connettori mantengono la corrente del team consegnando i contenuti e gli aggiornamenti del servizio usati di frequente direttamente in un canale. Con i connettori, gli utenti di Microsoft teams possono ricevere gli aggiornamenti da servizi popolari come Trello, Wunderlist, GitHub e Azure DevOps Services all'interno del flusso di chat del proprio team.

Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori se le autorizzazioni del team lo consentono e tutti i membri del team ricevono notifiche di attività da tale servizio. I connettori continueranno a funzionare anche dopo che il membro che ha inizialmente configurato il connettore ha lasciato. Qualsiasi membro del team con le autorizzazioni per Add\Remove può modificare la configurazione dei connettori da parte di altri membri.

I connettori Microsoft 365 possono essere usati sia con Microsoft teams che con i gruppi Microsoft 365, semplificando la sincronizzazione e la ricezione rapida delle informazioni rilevanti per tutti i membri. Sia Microsoft teams che Exchange usano lo stesso modello di connettore, che consente di usare gli stessi connettori in entrambe le piattaforme. È comunque importante notare che la disabilitazione dei connettori per il gruppo Microsoft 365 a cui un team dipende sarà in grado di disabilitare la possibilità di creare connettori anche per il team.

<a name="add-a-connector-to-a-channel"></a>Aggiungere un connettore a un canale
----------------------------

Attualmente è possibile aggiungere connettori usando i client desktop e Web di Microsoft teams. Tuttavia, le informazioni pubblicate da questi connettori possono essere visualizzate in **tutti i client** , inclusi i dispositivi mobili.

1. Per aggiungere un connettore a un canale, fare clic sui puntini di sospensione **(...),** a destra di un nome di canale, quindi fare clic su **connettori**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot dell'interfaccia teams con l'opzione Connectors selezionata.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. È possibile selezionare una varietà di connettori disponibili e quindi fare clic su **Aggiungi**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot della finestra di dialogo connettori che mostra i connettori disponibili.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Immettere le informazioni necessarie del connettore selezionato e fare clic su **Salva**. Ogni connettore richiede il corretto funzionamento di un set di informazioni diverso e alcuni potrebbero richiedere l'accesso al servizio usando i collegamenti forniti nella pagina di configurazione del connettore.

    > [!div class="mx-imgBorder"]
    > ![Screenshot della pagina di configurazione per il connettore RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. I dati forniti dal connettore vengono automaticamente inseriti nel canale.

    > [!div class="mx-imgBorder"]
    > ![Screenshot dell'interfaccia teams che mostra una conversazione in un canale.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **Notifica aggiornamento URL connettore**
>
> I connettori teams stanno passando a un nuovo URL per migliorare la sicurezza. Durante il corso di questa transizione, riceverai alcune notifiche per aggiornare il connettore configurato in modo da usare il nuovo URL. È consigliabile aggiornare immediatamente il connettore per evitare interruzioni ai servizi di connessione. La procedura seguente deve essere seguita per aggiornare l'URL:
> 1. Nella pagina Configurazione connettori verrà visualizzato un messaggio di "attenzione obbligatoria" sotto il pulsante "Gestisci" per le connessioni che devono essere aggiornate.
> ![Screenshot del messaggio "attenzione necessaria".](media/Teams_Attention_Required_message.png)
> 2. Per i connettori webhook in arrivo, gli utenti possono ricreare la connessione semplicemente selezionando **URL di aggiornamento** e usando l'URL del webhook appena generato.
> ![Screenshot del pulsante "URL di aggiornamento".](media/Teams_update_URL_button.png)
> 3. Per altri tipi di connettore, l'utente deve rimuovere il connettore e ricreare la configurazione del connettore.
> 4. Verrà visualizzato un messaggio "l'URL è aggiornato" dopo l'aggiornamento dell'URL.
> ![Screenshot del messaggio "URL aggiornato".](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>Sviluppare connettori personalizzati
----------------------------

È anche possibile creare connettori personalizzati, oltre a webhook in entrata e in uscita. Per altre informazioni, vedere la [documentazione per sviluppatori](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
