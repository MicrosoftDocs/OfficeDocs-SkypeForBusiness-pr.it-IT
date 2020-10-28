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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e3ff2f42953d59d1eecbc96179759f2ad9024f82
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772257"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="2fecc-103">Connettere l'app Pazienti all'API di Azure per FHIR</span><span class="sxs-lookup"><span data-stu-id="2fecc-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="2fecc-104">Efficace il 30 ottobre 2020, l'app patients è stata ritirata e sostituita dall' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams.</span><span class="sxs-lookup"><span data-stu-id="2fecc-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="2fecc-105">Con gli elenchi, i team di assistenza nell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team per il monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="2fecc-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="2fecc-106">Vedere il modello di pazienti in elenchi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="2fecc-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="2fecc-107">Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="2fecc-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="2fecc-108">Seguire questa procedura per consentire all'app pazienti in Microsoft teams di accedere a un'API di Azure per l'istanza di FHIR.</span><span class="sxs-lookup"><span data-stu-id="2fecc-108">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="2fecc-109">In questo articolo si presuppone che sia stata configurata un' [API Azure per l'istanza di FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) e la configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="2fecc-109">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="2fecc-110">Se non è ancora stata creata un'API Azure per l'istanza di FHIR nel tenant, vedere [Guida introduttiva: distribuire Azure API per FHIR con Azure Portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="2fecc-110">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="2fecc-111">Fare clic [qui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) per concedere il consenso dell'amministratore per l'app pazienti.</span><span class="sxs-lookup"><span data-stu-id="2fecc-111">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="2fecc-112">Quando richiesto, accedere con l'amministratore del tenant o le credenziali di amministratore globale e quindi fare clic su **accetta** per concedere le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="2fecc-112">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Screenshot della richiesta di autorizzazione per l'app pazienti](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="2fecc-114">Dopo aver accettato, chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="2fecc-114">After you accept, close the window.</span></span> <span data-ttu-id="2fecc-115">Verrà visualizzata una pagina che può avere un aspetto simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="2fecc-115">You'll see a page that may look like this.</span></span> <span data-ttu-id="2fecc-116">È possibile ignorare il messaggio di errore nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2fecc-116">You can ignore the error message on the page.</span></span> <span data-ttu-id="2fecc-117">È innocuo e indica che viene concesso il consenso.</span><span class="sxs-lookup"><span data-stu-id="2fecc-117">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="2fecc-118">Stiamo lavorando a una pagina più user-friendly per questo URL.</span><span class="sxs-lookup"><span data-stu-id="2fecc-118">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="2fecc-119">Restate sintonizzati!)</span><span class="sxs-lookup"><span data-stu-id="2fecc-119">Stay tuned!)</span></span>

    ![Screenshot della richiesta di autorizzazione per i pazienti app](../../media/patients-app-permissions-request-granted.png)
    
2. <span data-ttu-id="2fecc-121">Accedere a [Azure Portal](https://portal.azure.com) con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="2fecc-121">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="2fecc-122">Nella barra di spostamento sinistra selezionare **Azure Active Directory** e quindi selezionare **applicazioni aziendali** .</span><span class="sxs-lookup"><span data-stu-id="2fecc-122">In the left navigation, select **Azure Active Directory** , and then select **Enterprise Applications** .</span></span>

    <span data-ttu-id="2fecc-123">Cercare una riga denominata **patients (dev)** e quindi copiare il valore nella colonna **ID oggetto** negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="2fecc-123">Look for a row named **Patients (dev)** , and then copy the value in the **Object ID** column to your clipboard.</span></span>
    
    ![Screenshot della riga dei pazienti (dev) in Azure Portal](../../media/patients-app-azure-portal-object-id.png)
    
4. <span data-ttu-id="2fecc-125">Passare all'istanza di risorsa Azure API for FHIR a cui si vuole connettere l'app patients, cercandola o sfogliando le risorse, quindi aprire le impostazioni per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="2fecc-125">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Screenshot dell'API Azure per le impostazioni delle istanze di FHIR in Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="2fecc-127">Fare clic su **autenticazione** e quindi incollare l'ID oggetto copiato nel passaggio 3 nella casella **ID oggetto consentiti** .</span><span class="sxs-lookup"><span data-stu-id="2fecc-127">Click **Authentication** , and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="2fecc-128">Questo consente all'app patients di accedere al server FHIR.</span><span class="sxs-lookup"><span data-stu-id="2fecc-128">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="2fecc-129">Dopo aver incollato l'ID oggetto, Azure Active Directory la convalida e viene visualizzato un segno di spunta verde accanto.</span><span class="sxs-lookup"><span data-stu-id="2fecc-129">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Screenshot delle impostazioni di autenticazione in Azure Portal](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="2fecc-131">Fare clic su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="2fecc-131">Click **Save** .</span></span> <span data-ttu-id="2fecc-132">Verrà ridistribuita l'istanza, che può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="2fecc-132">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="2fecc-133">Fare clic su **Panoramica** e quindi copiare l'URL dall' **endpoint di metadati FHIR** .</span><span class="sxs-lookup"><span data-stu-id="2fecc-133">Click **Overview** , and then copy the URL from **FHIR metadata endpoint** .</span></span> <span data-ttu-id="2fecc-134">Rimuovere il tag Metadata per ottenere l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="2fecc-134">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="2fecc-135">Ad esempio, https://test02-teamshealth.azurehealthcareapis.com/ .</span><span class="sxs-lookup"><span data-stu-id="2fecc-135">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Screenshot dell'endpoint di metadati in Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="2fecc-137">In teams passare all'istanza dell'app patients caricata nel team, fare clic su **Impostazioni** e quindi nella casella **collegamento** immettere l'URL dell'endpoint del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="2fecc-137">In Teams, go to the Patients app instance that's loaded in your team, click **Settings** , and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="2fecc-138">Fare quindi clic su **Connetti** per stabilire una connessione e cercare e aggiungere i pazienti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2fecc-138">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Screenshot delle impostazioni dell'app patients in teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="2fecc-140">Se viene visualizzato un messaggio di errore durante la connessione ai team durante questo passaggio, inviare una schermata dettagliata dell'errore, i registri di [Fiddler](https://www.telerik.com/download/fiddler) e qualsiasi altra procedura di riproduzione in un messaggio di posta elettronica con una riga dell'oggetto "app pazienti-risoluzione dei problemi della modalità EMR" in [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2fecc-140">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2fecc-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2fecc-141">Related topics</span></span>

- [<span data-ttu-id="2fecc-142">Panoramica dell'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="2fecc-142">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="2fecc-143">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2fecc-143">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
