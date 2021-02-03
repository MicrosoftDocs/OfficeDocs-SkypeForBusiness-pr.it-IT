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
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="5b25e-103">Usare Microsoft 365 e connettori personalizzati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b25e-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="5b25e-104">I connettori mantengono la corrente del team consegnando i contenuti e gli aggiornamenti del servizio usati di frequente direttamente in un canale.</span><span class="sxs-lookup"><span data-stu-id="5b25e-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="5b25e-105">Con i connettori, gli utenti di Microsoft teams possono ricevere gli aggiornamenti da servizi popolari come Trello, Wunderlist, GitHub e Azure DevOps Services all'interno del flusso di chat del proprio team.</span><span class="sxs-lookup"><span data-stu-id="5b25e-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="5b25e-106">Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori se le autorizzazioni del team lo consentono e tutti i membri del team ricevono notifiche di attività da tale servizio.</span><span class="sxs-lookup"><span data-stu-id="5b25e-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="5b25e-107">I connettori continueranno a funzionare anche dopo che il membro che ha inizialmente configurato il connettore ha lasciato.</span><span class="sxs-lookup"><span data-stu-id="5b25e-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="5b25e-108">Qualsiasi membro del team con le autorizzazioni per Add\Remove può modificare la configurazione dei connettori da parte di altri membri.</span><span class="sxs-lookup"><span data-stu-id="5b25e-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="5b25e-109">I connettori Microsoft 365 possono essere usati sia con Microsoft teams che con i gruppi Microsoft 365, semplificando la sincronizzazione e la ricezione rapida delle informazioni rilevanti per tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="5b25e-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="5b25e-110">Sia Microsoft teams che Exchange usano lo stesso modello di connettore, che consente di usare gli stessi connettori in entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="5b25e-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="5b25e-111">È comunque importante notare che la disabilitazione dei connettori per il gruppo Microsoft 365 a cui un team dipende sarà in grado di disabilitare la possibilità di creare connettori anche per il team.</span><span class="sxs-lookup"><span data-stu-id="5b25e-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="5b25e-112">Aggiungere un connettore a un canale</span><span class="sxs-lookup"><span data-stu-id="5b25e-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="5b25e-113">Attualmente è possibile aggiungere connettori usando i client desktop e Web di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="5b25e-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="5b25e-114">Tuttavia, le informazioni pubblicate da questi connettori possono essere visualizzate in **tutti i client** , inclusi i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="5b25e-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="5b25e-115">Per aggiungere un connettore a un canale, fare clic sui puntini di sospensione **(...),** a destra di un nome di canale, quindi fare clic su **connettori**.</span><span class="sxs-lookup"><span data-stu-id="5b25e-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5b25e-116">![Screenshot dell'interfaccia teams con l'opzione Connectors selezionata.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="5b25e-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="5b25e-117">È possibile selezionare una varietà di connettori disponibili e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5b25e-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5b25e-118">![Screenshot della finestra di dialogo connettori che mostra i connettori disponibili.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="5b25e-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="5b25e-119">Immettere le informazioni necessarie del connettore selezionato e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b25e-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="5b25e-120">Ogni connettore richiede il corretto funzionamento di un set di informazioni diverso e alcuni potrebbero richiedere l'accesso al servizio usando i collegamenti forniti nella pagina di configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="5b25e-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5b25e-121">![Screenshot della pagina di configurazione per il connettore RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="5b25e-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="5b25e-122">I dati forniti dal connettore vengono automaticamente inseriti nel canale.</span><span class="sxs-lookup"><span data-stu-id="5b25e-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5b25e-123">![Screenshot dell'interfaccia teams che mostra una conversazione in un canale.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="5b25e-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="5b25e-124">**Notifica aggiornamento URL connettore**</span><span class="sxs-lookup"><span data-stu-id="5b25e-124">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="5b25e-125">I connettori teams stanno passando a un nuovo URL per migliorare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5b25e-125">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="5b25e-126">Durante il corso di questa transizione, riceverai alcune notifiche per aggiornare il connettore configurato in modo da usare il nuovo URL.</span><span class="sxs-lookup"><span data-stu-id="5b25e-126">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="5b25e-127">È consigliabile aggiornare immediatamente il connettore per evitare interruzioni ai servizi di connessione.</span><span class="sxs-lookup"><span data-stu-id="5b25e-127">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="5b25e-128">La procedura seguente deve essere seguita per aggiornare l'URL:</span><span class="sxs-lookup"><span data-stu-id="5b25e-128">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="5b25e-129">Nella pagina Configurazione connettori verrà visualizzato un messaggio di "attenzione obbligatoria" sotto il pulsante "Gestisci" per le connessioni che devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="5b25e-129">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="5b25e-130">![Screenshot del messaggio "attenzione necessaria".](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="5b25e-130">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="5b25e-131">Per i connettori webhook in arrivo, gli utenti possono ricreare la connessione semplicemente selezionando **URL di aggiornamento** e usando l'URL del webhook appena generato.</span><span class="sxs-lookup"><span data-stu-id="5b25e-131">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="5b25e-132">![Screenshot del pulsante "URL di aggiornamento".](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="5b25e-132">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="5b25e-133">Per altri tipi di connettore, l'utente deve rimuovere il connettore e ricreare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="5b25e-133">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="5b25e-134">Verrà visualizzato un messaggio "l'URL è aggiornato" dopo l'aggiornamento dell'URL.</span><span class="sxs-lookup"><span data-stu-id="5b25e-134">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="5b25e-135">![Screenshot del messaggio "URL aggiornato".](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="5b25e-135">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


<a name="develop-custom-connectors"></a><span data-ttu-id="5b25e-136">Sviluppare connettori personalizzati</span><span class="sxs-lookup"><span data-stu-id="5b25e-136">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="5b25e-137">È anche possibile creare connettori personalizzati, oltre a webhook in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="5b25e-137">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="5b25e-138">Per altre informazioni, vedere la [documentazione per sviluppatori](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="5b25e-138">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
