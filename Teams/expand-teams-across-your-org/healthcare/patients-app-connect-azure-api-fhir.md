---
title: Connettere l'app Pazienti all'API di Azure per FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informazioni su come connettere l'app patients in Microsoft Teams a Azure API per FHIR (Fast Healthcare Resources).
ms.openlocfilehash: 92c5b033215b0e5520b0321042d52579dfb019bf
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827724"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="cc8f2-103">Connettere l'app Pazienti all'API di Azure per FHIR</span><span class="sxs-lookup"><span data-stu-id="cc8f2-103">Connect the Patients app to Azure API for FHIR</span></span>

<span data-ttu-id="cc8f2-104">Seguire questa procedura per consentire all'app pazienti in Microsoft teams di accedere a un'API di Azure per l'istanza di FHIR.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-104">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="cc8f2-105">In questo articolo si presuppone che sia stata configurata un' [API Azure per l'istanza di FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) e la configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-105">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="cc8f2-106">Se non è ancora stata creata un'API Azure per l'istanza di FHIR nel tenant, vedere [Guida introduttiva: distribuire Azure API per FHIR con Azure Portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="cc8f2-106">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="cc8f2-107">Fare clic [qui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) per concedere il consenso dell'amministratore per l'app pazienti.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-107">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="cc8f2-108">Quando richiesto, accedere con l'amministratore del tenant o le credenziali di amministratore globale e quindi fare clic su **accetta** per concedere le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-108">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Screenshot della richiesta di autorizzazione per i pazienti app](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="cc8f2-110">Dopo aver accettato, chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-110">After you accept, close the window.</span></span> <span data-ttu-id="cc8f2-111">Verrà visualizzata una pagina che può avere un aspetto simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-111">You'll see a page that may look like this.</span></span> <span data-ttu-id="cc8f2-112">È possibile ignorare il messaggio di errore nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-112">You can ignore the error message on the page.</span></span> <span data-ttu-id="cc8f2-113">È innocuo e indica che viene concesso il consenso.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-113">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="cc8f2-114">Stiamo lavorando a una pagina più user-friendly per questo URL.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-114">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="cc8f2-115">Restate sintonizzati!)</span><span class="sxs-lookup"><span data-stu-id="cc8f2-115">Stay tuned!)</span></span>

    ![Screenshot della richiesta di autorizzazione per i pazienti app](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="cc8f2-117">Accedere a [Azure Portal](https://portal.azure.com) con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-117">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="cc8f2-118">Nella barra di spostamento sinistra selezionare **Azure Active Directory**e quindi selezionare **applicazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-118">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="cc8f2-119">Cercare una riga denominata **patients (dev)** e quindi copiare il valore nella colonna **ID oggetto** negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-119">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="cc8f2-120">![Screenshot della riga dei pazienti (dev) in Azure Portal](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="cc8f2-120">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="cc8f2-121">Passare all'istanza di risorsa Azure API for FHIR a cui si vuole connettere l'app patients, cercandola o sfogliando le risorse, quindi aprire le impostazioni per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-121">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Screenshot dell'API Azure per le impostazioni delle istanze di FHIR in Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="cc8f2-123">Fare clic su **autenticazione**e quindi incollare l'ID oggetto copiato nel passaggio 3 nella casella **ID oggetto consentiti** .</span><span class="sxs-lookup"><span data-stu-id="cc8f2-123">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="cc8f2-124">Questo consente all'app patients di accedere al server FHIR.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-124">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="cc8f2-125">Dopo aver incollato l'ID oggetto, Azure Active Directory la convalida e viene visualizzato un segno di spunta verde accanto.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-125">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Screenshot delle impostazioni di autenticazione in Azure Portal](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="cc8f2-127">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-127">Click **Save**.</span></span> <span data-ttu-id="cc8f2-128">Verrà ridistribuita l'istanza, che può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-128">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="cc8f2-129">Fare clic su **Panoramica**e quindi copiare l'URL dall' **endpoint di metadati FHIR**.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-129">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="cc8f2-130">Rimuovere il tag Metadata per ottenere l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-130">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="cc8f2-131">Ad esempio, https://test02-teamshealth.azurehealthcareapis.com/.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-131">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Screenshot dell'endpoint di metadati in Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="cc8f2-133">In teams passare all'istanza dell'app patients caricata nel team, fare clic su **Impostazioni**e quindi nella casella **collegamento** immettere l'URL dell'endpoint del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-133">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="cc8f2-134">Fare quindi clic su **Connetti** per stabilire una connessione e cercare e aggiungere i pazienti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="cc8f2-134">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Screenshot delle impostazioni dell'app patients in teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="cc8f2-136">Se viene visualizzato un messaggio di errore durante la connessione ai team durante questo passaggio, inviare una schermata dettagliata dell'errore, i registri di [Fiddler](https://www.telerik.com/download/fiddler) e qualsiasi altra procedura di riproduzione in un messaggio di posta elettronica con una riga dell'oggetto "app pazienti-risoluzione dei problemi della modalità EMR" in [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cc8f2-136">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc8f2-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cc8f2-137">Related topics</span></span>

- [<span data-ttu-id="cc8f2-138">Panoramica dell'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="cc8f2-138">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="cc8f2-139">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc8f2-139">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
