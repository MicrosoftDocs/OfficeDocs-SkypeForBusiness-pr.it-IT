---
title: Connettere l'app Pazienti all'API di Azure per FHIR
author: cichur
ms.author: v-cichur
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
description: Informazioni su come connettere l'app Pazienti in Microsoft Teams ad Azure API for FHIR (Fast Healthcare Interoperability Resources).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096268"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="08120-103">Connettere l'app Pazienti all'API di Azure per FHIR</span><span class="sxs-lookup"><span data-stu-id="08120-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="08120-104">A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span><span class="sxs-lookup"><span data-stu-id="08120-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="08120-105">I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team.</span><span class="sxs-lookup"><span data-stu-id="08120-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="08120-106">Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="08120-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="08120-107">Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="08120-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="08120-108">Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="08120-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="08120-109">Estrai il modello Coordinamento pazienti in Elenchi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="08120-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="08120-110">Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="08120-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="08120-111">Seguire questa procedura per consentire all'app Pazienti in Microsoft Teams di accedere a un'istanza di Azure API per FHIR.</span><span class="sxs-lookup"><span data-stu-id="08120-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="08120-112">Questo articolo presuppone che nel tenant sia configurata e configurata un'istanza di Azure API per [FHIR.](https://azure.microsoft.com/services/azure-api-for-fhir/)</span><span class="sxs-lookup"><span data-stu-id="08120-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="08120-113">Se non è ancora stata creata un'istanza di Azure API per FHIR nel tenant, vedere Guida introduttiva: Distribuire l'API di Azure per [FHIR usando il portale di Azure.](/azure/healthcare-apis/fhir-paas-portal-quickstart)</span><span class="sxs-lookup"><span data-stu-id="08120-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="08120-114">Fare [clic qui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) per concedere il consenso dell'amministratore per l'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="08120-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="08120-115">Quando richiesto, accedere con le credenziali di amministratore tenant o amministratore globale e quindi fare clic **su** Accetta per concedere le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="08120-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Screenshot della richiesta di autorizzazione per l'app Pazienti](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="08120-117">Dopo aver accettato, chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="08120-117">After you accept, close the window.</span></span> <span data-ttu-id="08120-118">Verrà visualizzata una pagina simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="08120-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="08120-119">È possibile ignorare il messaggio di errore nella pagina.</span><span class="sxs-lookup"><span data-stu-id="08120-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="08120-120">È innocuo e indica che il consenso è concesso.</span><span class="sxs-lookup"><span data-stu-id="08120-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="08120-121">Stiamo lavorando a una pagina più facile da usare per questo URL.</span><span class="sxs-lookup"><span data-stu-id="08120-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="08120-122">Rimani sintonizzato!)</span><span class="sxs-lookup"><span data-stu-id="08120-122">Stay tuned!)</span></span>

    ![Screenshot della richiesta di autorizzazione per l'app Patients](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="08120-124">Accedere al portale [di Azure con](https://portal.azure.com) le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="08120-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="08120-125">Nel riquadro di spostamento sinistro selezionare **Azure Active Directory** e quindi applicazioni **aziendali.**</span><span class="sxs-lookup"><span data-stu-id="08120-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="08120-126">Cercare una riga denominata **Pazienti (dev)** e quindi copiare il valore nella **colonna ID oggetto** negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="08120-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Screenshot della riga Pazienti (dev) nel portale di Azure](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="08120-128">Passare all'istanza della risorsa API di Azure per FHIR a cui si vuole connettere l'app Pazienti (cercandola o esplorando le risorse) e quindi aprire le impostazioni per tale istanza.</span><span class="sxs-lookup"><span data-stu-id="08120-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Screenshot delle impostazioni dell'istanza di Azure API per FHIR nel portale di Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="08120-130">Fare **clic su** Autenticazione e quindi incollare l'ID oggetto copiato nel passaggio 3 nella casella ID **oggetto** consentiti.</span><span class="sxs-lookup"><span data-stu-id="08120-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="08120-131">In questo modo l'app Pazienti può accedere al server FHIR.</span><span class="sxs-lookup"><span data-stu-id="08120-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="08120-132">Dopo aver incollato l'ID oggetto, Azure Active Directory lo convalida e accanto viene visualizzato un segno di spunta verde.</span><span class="sxs-lookup"><span data-stu-id="08120-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Screenshot delle impostazioni di autenticazione nel portale di Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="08120-134">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="08120-134">Click **Save**.</span></span> <span data-ttu-id="08120-135">Questa operazione ridistribuisce l'istanza, che può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="08120-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="08120-136">Fare **clic su Panoramica** e quindi copiare l'URL dall'endpoint dei metadati **FHIR.**</span><span class="sxs-lookup"><span data-stu-id="08120-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="08120-137">Rimuovere il tag di metadati per ottenere l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="08120-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="08120-138">Ad esempio, `https://test02-teamshealth.azurehealthcareapis.com/` .</span><span class="sxs-lookup"><span data-stu-id="08120-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![endpoint dei metadati nel portale di Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="08120-140">In Teams passare all'istanza dell'app Pazienti caricata nel team, fare  clic su Impostazioni **e** quindi nella casella Collegamento immettere l'URL dell'endpoint del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="08120-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="08120-141">Quindi, fare clic **su Connetti** per stabilire una connessione e cercare e aggiungere pazienti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="08120-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="08120-142">Impostazioni dell'app Pazienti in Teams</span><span class="sxs-lookup"><span data-stu-id="08120-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="08120-143">Se durante questo passaggio viene visualizzato un messaggio di errore durante la connessione a Teams, inviare a teamsforhealthcare@service.microsoft.com uno screenshot dettagliato dell'errore, i log di [Fiddler](https://www.telerik.com/download/fiddler) e qualsiasi altro processo di riproduzione in un messaggio di posta elettronica con l'oggetto "Risoluzione dei problemi relativi all'app Pazienti – modalità [EMR"](mailto:teamsforhealthcare@service.microsoft.com)in teamsforhealthcare@service.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="08120-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="08120-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="08120-144">Related topics</span></span>

- [<span data-ttu-id="08120-145">Panoramica dell'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="08120-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="08120-146">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08120-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)