---
title: Usare Office 365 e connettori personalizzati in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: I connettori mantengono il team aggiornato fornendo contenuti e aggiornamenti dai servizi usati di frequente direttamente in un canale.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8235ce9eb950df0c04ab41949500a640376e612
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245519"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="e90c8-103">Usare Office 365 e connettori personalizzati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e90c8-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="e90c8-104">I connettori mantengono la corrente del team consegnando i contenuti e gli aggiornamenti del servizio usati di frequente direttamente in un canale.</span><span class="sxs-lookup"><span data-stu-id="e90c8-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="e90c8-105">Con i connettori, gli utenti di Microsoft teams possono ricevere gli aggiornamenti da servizi popolari come Twitter, Trello, Wunderlist, GitHub e Azure DevOps Services all'interno del flusso di chat del proprio team.</span><span class="sxs-lookup"><span data-stu-id="e90c8-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="e90c8-106">Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori se le autorizzazioni del team lo consentono e tutti i membri del team ricevono notifiche di attività da tale servizio.</span><span class="sxs-lookup"><span data-stu-id="e90c8-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="e90c8-107">I connettori continueranno a funzionare anche dopo che il membro che ha inizialmente configurato il connettore ha lasciato.</span><span class="sxs-lookup"><span data-stu-id="e90c8-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="e90c8-108">Qualsiasi membro del team con le autorizzazioni per Add\Remove può modificare la configurazione dei connettori da parte di altri membri.</span><span class="sxs-lookup"><span data-stu-id="e90c8-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="e90c8-109">I connettori di Office 365 possono essere usati sia con Microsoft teams che con i gruppi di Office 365, semplificando la sincronizzazione e la ricezione rapida delle informazioni rilevanti per tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="e90c8-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="e90c8-110">Sia Microsoft teams che Exchange usano lo stesso modello di connettore, che consente di usare gli stessi connettori in entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="e90c8-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="e90c8-111">È tuttavia importante notare che la disabilitazione dei connettori per il gruppo di Office 365 a cui un team dipende sarà in grado di disabilitare la possibilità di creare connettori anche per il team.</span><span class="sxs-lookup"><span data-stu-id="e90c8-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="e90c8-112">Aggiungere un connettore a un canale</span><span class="sxs-lookup"><span data-stu-id="e90c8-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="e90c8-113">Attualmente è possibile aggiungere connettori usando i client desktop e Web di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e90c8-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="e90c8-114">Tuttavia, le informazioni pubblicate da questi connettori possono essere visualizzate in **tutti i client** , inclusi i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="e90c8-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="e90c8-115">Per aggiungere un connettore a un canale, fare clic sui puntini di sospensione **(...),** a destra di un nome di canale, quindi fare clic su **connettori**.</span><span class="sxs-lookup"><span data-stu-id="e90c8-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Screenshot dell'interfaccia teams con l'opzione Connectors selezionata.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="e90c8-117">È possibile selezionare una varietà di connettori disponibili e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e90c8-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Screenshot della finestra di dialogo connettori che mostra i connettori disponibili.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="e90c8-119">Immettere le informazioni necessarie del connettore selezionato e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e90c8-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="e90c8-120">Ogni connettore richiede il corretto funzionamento di un set di informazioni diverso e alcuni potrebbero richiedere l'accesso al servizio usando i collegamenti forniti nella pagina di configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="e90c8-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Screenshot della pagina di configurazione per il connettore RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="e90c8-122">I dati forniti dal connettore vengono automaticamente inseriti nel canale.</span><span class="sxs-lookup"><span data-stu-id="e90c8-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Screenshot dell'interfaccia teams che mostra una conversazione in un canale.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="e90c8-124">Sviluppare connettori personalizzati</span><span class="sxs-lookup"><span data-stu-id="e90c8-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="e90c8-125">È molto semplice sviluppare connettori personalizzati che possono essere integrati con le applicazioni line-of-business (LOB).</span><span class="sxs-lookup"><span data-stu-id="e90c8-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="e90c8-126">Puoi usare il connettore webhook in **ingresso** incorporato per creare un endpoint per un canale che estrae i dati da qualsiasi applicazione usando i metodi post http.</span><span class="sxs-lookup"><span data-stu-id="e90c8-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="e90c8-127">Aggiungere il **webhook in arrivo** come qualsiasi altro connettore.</span><span class="sxs-lookup"><span data-stu-id="e90c8-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Screenshot dell'opzione per aggiungere il connettore webhook in arrivo.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="e90c8-129">Per creare un hook, specificare un **nome**, aggiornare l'immagine di Webhook, se necessario, e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e90c8-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![Screenshot della pagina di configurazione per il connettore del webhook in arrivo.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="e90c8-131">Le applicazioni che spingono i dati su questo canale richiedono l'URL del connettore webhook.</span><span class="sxs-lookup"><span data-stu-id="e90c8-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="e90c8-132">Quando si crea il webhook viene creato un URL univoco.</span><span class="sxs-lookup"><span data-stu-id="e90c8-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="e90c8-133">Condividere questo URL con gli sviluppatori in modo che possano configurare le proprie applicazioni per il push dei dati, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e90c8-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Screenshot dell'URL univoco del webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="e90c8-135">Quando un'applicazione esterna inserisce i dati in un connettore, il messaggio viene visualizzato nell'elenco di conversazione del canale come messaggio speciale denominato messaggio della **scheda connettore** .</span><span class="sxs-lookup"><span data-stu-id="e90c8-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Screenshot dell'interfaccia teams che mostra un messaggio di scheda connettore.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="e90c8-137">Gli sviluppatori possono configurare le proprie applicazioni per creare queste schede inviando una richiesta HTTP con un semplice payload JSON all'indirizzo webhook di un team, che è un URL univoco di tale endpoint fornito dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e90c8-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="e90c8-138">Fare in modo che gli sviluppatori facciano riferimento alla [Guida introduttiva ai connettori di Office 365 per Microsoft teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), nella rete Microsoft Developer Network, con istruzioni dettagliate e esempi di connettori.</span><span class="sxs-lookup"><span data-stu-id="e90c8-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="e90c8-139">Altre risorse includono le [App Connect per i gruppi in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) e [Office Dev Center-Microsoft teams](https://go.microsoft.com/fwlink/?linkid=855784).</span><span class="sxs-lookup"><span data-stu-id="e90c8-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
