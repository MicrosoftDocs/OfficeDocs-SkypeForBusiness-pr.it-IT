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

I connettori mantengono aggiornato il team offrendo aggiornamenti dei servizi e dei contenuti usati di frequente direttamente in un canale. Con i connettori, gli utenti di Microsoft Teams possono ricevere aggiornamenti da servizi popolari come Trello, Wunderlist, GitHub e Azure DevOps Services all'interno del flusso di chat del proprio team.

Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori, se le autorizzazioni del team lo consentono e tutti i membri del team vengono informati delle attività di quel servizio. I connettori continueranno a funzionare anche dopo che il membro che ha inizialmente configurato il connettore è stato lasciato. Qualsiasi membro del team con le autorizzazioni di aggiunta o rimozione può modificare la configurazione dei connettori da parte di altri membri.

I connettori di Microsoft 365 possono essere usati sia con Microsoft Teams che con i gruppi di Microsoft 365, rendendo più semplice la sincronizzazione per tutti i membri e la ricezione rapida di informazioni rilevanti. Sia Microsoft Teams che Exchange usano lo stesso modello di connettore, che consente di usare gli stessi connettori all'interno di entrambe le piattaforme. È tuttavia opportuno notare che la disabilitazione dei connettori per il gruppo di Microsoft 365 da cui dipende un team disattiva anche la possibilità di creare connettori per quel team.

<a name="add-a-connector-to-a-channel"></a>Aggiungere un connettore a un canale
----------------------------

Attualmente, è possibile aggiungere connettori utilizzando Microsoft Teams desktop e client Web. Tuttavia, le informazioni pubblicate da questi connettori possono essere visualizzate in tutti **i client,** inclusi i dispositivi mobili.

1. Per aggiungere un connettore a un canale, fare clic sui puntini di sospensione **(...),** a destra del nome di un canale, quindi fare clic su **Connettori.**

    > [!div class="mx-imgBorder"]
    > ![Screenshot dell'interfaccia di Teams con l'opzione Connettori selezionata.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. È possibile selezionare uno dei diversi connettori disponibili e quindi fare clic su **Aggiungi.**

    > [!div class="mx-imgBorder"]
    > ![Screenshot della finestra di dialogo Connettori che mostra i connettori disponibili.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Inserire le informazioni richieste del connettore selezionato e fare clic su **Salva.** Per il corretto funzionamento di ogni connettore è necessario un set di informazioni diverse e per alcuni potrebbe essere necessario accedere al servizio usando i collegamenti disponibili nella pagina di configurazione del connettore.

    > [!div class="mx-imgBorder"]
    > ![Screenshot della pagina di configurazione per il connettore RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. I dati forniti dal connettore vengono pubblicati automaticamente nel canale.

    > [!div class="mx-imgBorder"]
    > ![Screenshot dell'interfaccia di Teams che mostra una conversazione in un canale.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **Notifica di aggiornamento dell'URL del connettore**
>
> I connettori di Teams stanno per passare a un nuovo URL per migliorare la sicurezza. Durante la transizione, si riceveranno determinate notifiche per aggiornare il connettore configurato in modo da usare il nuovo URL. È consigliabile aggiornare immediatamente il connettore per evitare qualsiasi interruzione dei servizi dei connettori. Per aggiornare l'URL, è necessario seguire i passaggi seguenti:
> 1. Nella pagina di configurazione dei connettori verrà visualizzato un messaggio "Attenzione richiesta" sotto il pulsante "Gestisci" per le connessioni da aggiornare.
> ![Screenshot del messaggio "Attenzione richiesta".](media/Teams_Attention_Required_message.png)
> 2. Per i connettori Webhook in arrivo, gli utenti possono ricreare la connessione semplicemente selezionando Aggiorna **URL** e usando l'URL webhook appena generato.
> ![Screenshot del pulsante "Aggiorna URL".](media/Teams_update_URL_button.png)
> 3. Per altri tipi di connettore, l'utente dovrà rimuovere il connettore e ricreare la configurazione del connettore.
> 4. Dopo l'aggiornamento dell'URL verrà visualizzato il messaggio "L'URL è aggiornato".
> ![Screenshot del messaggio "L'URL è aggiornato".](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>Sviluppare connettori personalizzati
----------------------------

È anche possibile creare connettori personalizzati, nonché webhook in arrivo e in uscita. Per altre informazioni, vedere la [documentazione per sviluppatori](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
