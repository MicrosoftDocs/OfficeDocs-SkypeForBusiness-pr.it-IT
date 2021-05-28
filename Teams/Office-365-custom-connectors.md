---
title: Usare Microsoft 365 connettori personalizzati
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
ms.openlocfilehash: 3e6e65c3462242b82691a292770de684b6c4404b
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684243"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="95450-103">Usare Microsoft 365 connettori personalizzati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95450-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="95450-104">I connettori mantengono aggiornato il team fornendo gli aggiornamenti dei servizi e dei contenuti usati di frequente direttamente in un canale.</span><span class="sxs-lookup"><span data-stu-id="95450-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="95450-105">Con i connettori, gli utenti Microsoft Teams possono ricevere aggiornamenti da servizi popolari come Trello, Wunderlist, GitHub e Azure DevOps Services all'interno dello stream di chat del team.</span><span class="sxs-lookup"><span data-stu-id="95450-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="95450-106">Qualsiasi membro di un team può connettere il team ai servizi cloud più diffusi con i connettori, se le autorizzazioni del team lo consentono e tutti i membri del team vengono informati delle attività da quel servizio.</span><span class="sxs-lookup"><span data-stu-id="95450-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="95450-107">I connettori continueranno a funzionare anche dopo che il membro che ha inizialmente configurazione il connettore è rimasto.</span><span class="sxs-lookup"><span data-stu-id="95450-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="95450-108">Qualsiasi membro del team con le autorizzazioni per aggiungere o rimuovere può modificare la configurazione dei connettori da parte di altri membri.</span><span class="sxs-lookup"><span data-stu-id="95450-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="95450-109">Microsoft 365 connettori possono essere usati con gruppi di Microsoft Teams e Microsoft 365, semplificando la sincronizzazione di tutti i membri e la ricezione rapida di informazioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="95450-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="95450-110">Sia Microsoft Teams che Exchange lo stesso modello di connettore, che consente di usare gli stessi connettori all'interno di entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="95450-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="95450-111">È tuttavia opportuno notare che la disabilitazione dei connettori per il gruppo di Microsoft 365 da cui dipende un team disabiliterà anche la possibilità di creare connettori per il team.</span><span class="sxs-lookup"><span data-stu-id="95450-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> [!NOTE]
> <span data-ttu-id="95450-112">I connettori sono disabilitati per impostazione predefinita negli ambienti Government Cloud Community (GCC).</span><span class="sxs-lookup"><span data-stu-id="95450-112">Connectors are disabled by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="95450-113">Se è necessario abilitarli, impostare i parametri ConnectorsEnabled o ConnectorsEnabledForTeams su $true con il cmdlet [SetOrganizationConfig.](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="95450-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="95450-114">In precedenza era necessario connettersi alla [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="95450-114">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="95450-115">Aggiungere un connettore a un canale</span><span class="sxs-lookup"><span data-stu-id="95450-115">Add a connector to a channel</span></span>

<span data-ttu-id="95450-116">Attualmente, è possibile aggiungere connettori usando Microsoft Teams desktop e client Web.</span><span class="sxs-lookup"><span data-stu-id="95450-116">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="95450-117">Tuttavia, le informazioni pubblicate da questi connettori possono essere visualizzate in **tutti i client,** inclusi i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="95450-117">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="95450-118">Per aggiungere un connettore a un canale, fare clic sui puntini di sospensione **(...),** a destra del nome di un canale, quindi fare clic su **Connettori**.</span><span class="sxs-lookup"><span data-stu-id="95450-118">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="95450-119">![Screenshot dell'interfaccia Teams con l'opzione Connettori selezionata.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="95450-119">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="95450-120">È possibile selezionare una varietà di connettori disponibili e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="95450-120">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="95450-121">![Screenshot della finestra di dialogo Connettori che mostra i connettori disponibili.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="95450-121">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="95450-122">Immettere le informazioni necessarie sul connettore selezionato e fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="95450-122">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="95450-123">Per il corretto funzionamento di ogni connettore è necessario un set di informazioni diverse e alcuni potrebbero richiedere l'accesso al servizio usando i collegamenti disponibili nella pagina di configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="95450-123">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="95450-124">![Screenshot della pagina di configurazione per il connettore RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="95450-124">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="95450-125">I dati forniti dal connettore vengono inseriti automaticamente nel canale.</span><span class="sxs-lookup"><span data-stu-id="95450-125">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="95450-126">![Screenshot dell'interfaccia Teams che mostra una conversazione in un canale.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="95450-126">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="95450-127">**Notifica di aggiornamento dell'URL del connettore**</span><span class="sxs-lookup"><span data-stu-id="95450-127">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="95450-128">I Teams connettori stanno per passare a un nuovo URL per migliorare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="95450-128">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="95450-129">Nel corso di questa transizione si riceveranno alcune notifiche per aggiornare il connettore configurato in modo da usare il nuovo URL.</span><span class="sxs-lookup"><span data-stu-id="95450-129">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="95450-130">È consigliabile aggiornare immediatamente il connettore per evitare interruzioni dei servizi del connettore.</span><span class="sxs-lookup"><span data-stu-id="95450-130">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="95450-131">Per aggiornare l'URL, è necessario seguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="95450-131">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="95450-132">Nella pagina di configurazione dei connettori verrà visualizzato un messaggio "Attenzione richiesta" sotto il pulsante "Gestisci" per le connessioni che devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="95450-132">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="95450-133">![Screenshot del messaggio "Attenzione richiesta".](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="95450-133">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="95450-134">Per i connettori Webhook in arrivo, gli utenti possono ricreare la connessione semplicemente selezionando **Aggiorna URL** e usando l'URL del webhook appena generato.</span><span class="sxs-lookup"><span data-stu-id="95450-134">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="95450-135">![Screenshot del pulsante "Aggiorna URL".](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="95450-135">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="95450-136">Per altri tipi di connettori, l'utente dovrà rimuovere il connettore e ricreare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="95450-136">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="95450-137">Dopo l'aggiornamento dell'URL, verrà visualizzato il messaggio "L'URL è aggiornato".</span><span class="sxs-lookup"><span data-stu-id="95450-137">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="95450-138">![Screenshot del messaggio "L'URL è aggiornato".](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="95450-138">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="95450-139">Sviluppare connettori personalizzati</span><span class="sxs-lookup"><span data-stu-id="95450-139">Develop custom connectors</span></span>


<span data-ttu-id="95450-140">È anche possibile creare connettori personalizzati, nonché webhook in arrivo e in uscita.</span><span class="sxs-lookup"><span data-stu-id="95450-140">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="95450-141">Per altre informazioni, vedere la [documentazione per sviluppatori](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="95450-141">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
